---
title: Scripts sur evenements d'EmulationStation
description: Description des scripts lancé par EmulationStation sur certains evenements
---

# Scripts sur evenements d'EmulationStation


>**Recalbox 7.0 et superieur !**
{.is-warning}

## A quoi ça sert?

L’intérêt premier est de pouvoir exécuter des actions externes selon les actions de l'utilisateur dans EmulationStation.

Bien entendu, c'est principalement sur Raspberry Pi et autres boards permettant des pilotages materiel faciles, que cette fonctionnalité va révéler tout son potentiel.

Sur un certain nombre d’événements d'EmulationStation, on va pouvoir lancer un script \(ou un executable\) ou envoyer un message MQTT que des scripts vont attendre et traiter.

A chaque événement, un fichier est rempli avec tout un tas d'information que les scripts pourront, ou pas, utiliser.

## Fonctionnement

### Les événements

On commence par la liste exhaustive des événements, quand ils sont déclenché, et s'ils exposent des informations supplémentaires qui seront passées en paramètres aux scripts.

| Événement | Quand? | Paramètres |
| :--- | :--- | :--- |
| Start | Démarrage ou redémarrage d'EmulationStation | Nombre de démarrages |
| Stop | Arrêt d'EmulationStation | Nombre de démarrages |
| Shutdown | Arrêt complet du système |  |
| Reboot | Redémarrage du système |  |
| Quit | Arrêt d'EmulationStation suite a une requête externe \(Arrêt du GPI case par le bouton on/off par exemple\) |  |
| Relaunch | Redémarrage d'EmulationStation \(gamelist.xml modifiée de l’extérieur par exemple, ou mise à jour des listes de jeux\) |  |
| SystemBrowsing | L'utilisateur est sur la liste des système et un nouveau système vient d'être sélectionné. | Nom court du système |
| GamelistBrowsing | L'utilisateur est sur une liste de jeu et un nouveau jeu \(ou répertoire\) vient d'être sélectionné. | Chemin du fichier de la rom |
| RunGame | Un jeu va être lancé | Chemin du fichier de la rom |
| RunDemo | Un jeu va être lancé en mode démo | Chemin du fichier de la rom |
| EndGame | Un jeu vient de se terminer | Chemin du fichier de la rom |
| EndDemo | La démo d'un jeu vient de se terminer | Chemin du fichier de la rom |
| Sleep | Démarrage de l'économiseur d'écran |  |
| WakeUp | Sortie de l'économiseur d'écran |  |
| ScrapStart | Une session de scrapping multi-jeu a démarré |  |
| ScrapStop | Une session de scrapping multi-jeu est terminée | Nombre de jeux scrapés |
| ScrapGame | Un jeu vient d'être scrappé. | Chemin du fichier de la rom |
| ConfigurationChanged | Quelque chose vient de changer dans la configuration |  |



### Les scripts

Les scripts sont à placer dans **`/recalbox/share/userscripts`** ou **`\\recalbox\share\userscripts`** ``ou dans des sous-répertoires si on désire les organiser.

EmulationStation choisi lui même le meilleur lanceur, si besoin est, en fonction de l'extension des scripts:

* .sh : Lancé par **sh**
* .ash : Lancé par **ash** \(un shell optimisé fourni par busybox\)
* .py : Lancé par **python** \( = python2.7 sur Recalbox \)
* .py2 : Lancé explicitement par **python2.7**

Toutes les autres extensions sont considérées comme des exécutables et les fichiers sont lancés en direct.


>Au moment ou cette documentation est écrite, Python3 n'est pas encore disponible dans Recalbox!
{.is-danger}

#### Paramètres de lancements

Chaque script/executable est lancé avec les arguments suivants:

**script** -action _**action**_ -statefile _**statefile**_ \[-param _**parametre**_\]

* _**action**_ est l’événement qui a lancé le script, _entièrement en minuscule._
* _**statefile**_ ****est le fichier qui contient les information complémentaire. Voir [le paragraphe sur ce fichier](scripts-sur-evenements-demulationstation.md#le-fichier-de-status-complet-demulationstation).
* _**parametre**_ est le paramètre optionnel de l’événement. Si l’événement n'a aucun paramètre, -param n'est pas present du tout.

#### Filtrage

Par défaut, les scripts sont lancés pour chaque événements. 

Pour filtrer et ne lancer le script que pour certains événements ciblés, il suffit de les indiquer entre crochets et séparés par des virgules. La casse n'est pas importante.

Par exemple: **`/recalbox/share/userscripts/marquee[start,stop].sh`** ne sera lancé que lorsque EmulationStation démarre ou s'arrête.  
Ou encore: **`/recalbox/share/userscripts/gamesinfo[browsinggamelist,rungame,rundemo,scrapgame].sh`** ne sera lancé que pour les événements qui concernent directement les jeux, pour afficher les infos du jeux sur un écran secondaire par exemple.

#### Synchrone/Asynchrone

Tous les scripts sont lancés en asynchrone. C'est a dire qu'EmulationStation continue son execution pendant que le script s'execute en parallèle.

Dans la majorité des cas, ça n'a aucune importance, mais il peut arriver qu'on veuille bloquer EmulationStation jusqu'à ce que notre script soit terminé. Un cas d'usage typique, est un script qui s’exécuterait sur les événements de reboot ou d'arrêt du système.  
Dans ce cas là, il faut s'assurer que notre script soit bien exécuté avant que le système ne démarre sa procédure d’arrêt, sans ça, nous pourrions perdre des infos ou pire.

Pour qu'un script s'execute de façon synchrone, il suffit de placer un **`(sync)`** dans le nom de fichier.

Par exemple: **`/recalbox/share/userscripts/backup[reboot,shutdown](sync).sh`** sera exécuté à l'arrêt ou au reboot du système. EmulationStation sera bloqué jusqu'à la fin de son execution et l'arrêt du système ne démarrera qu'après.

#### Scripts permanents

Certains scripts peuvent nécessiter de tourner en continu. Principalement s'ils sont utilisés pour intercepter des messages [MQTT que nous verrons un peu plus bas](scripts-sur-evenements-demulationstation.md#mqtt).

Il suffit de placer **`(permanent)`** dans le nom du fichier d'un script pour qu'il soit lancé par EmulationStation au démarrage.


>Si EmulationStation redémarre, les scripts permanents continueront leur execution et ne seront pas redémarrés.
{.is-info}

### MQTT

Recalbox embarque un mini serveur **MQTT** \(Mosquitto\) qui permet de faire du "_publish/subscribe_".

Chaque fois qu'EmulationStation va lancer les scripts sur un événement, il publie également l’événement \(en minuscule\) sur le topic **`/Recalbox/EmulationStation/Event`**.

Un programme qui écoute sur ce topic peut donc intercepter tous les événements pour un coût en utilisation processeur presque nul.  
Mosquitto met à disposition 2 petits exécutables **`mosquitto_pub`** et **`mosquitto_sub`** qui permettent respectivement de publier un message sur un topic ou d'attendre un message d'un topic. 

Vous pouvez donc utiliser **`mosquitto_sub`** dans un script, pour écouter et attendre des événements EmulationStation, de la façon suivante:  
**`event = $(mosquitto_sub -h 127.0.0.1 -p 1883 -q 0 -t /Recalbox/EmulationStation/Event -C 1)`**  
Cette commande bloque l'execution du script jusqu'à ce qu'un événements soit publié. Le script récupère alors le type d''événement dans la variable **`event`**.


>On comprends rapidement l’intérêt des scripts permanents: plutôt que de lancer un script à chaque fois, pour chaque événement, on peut lancer un script permanent et lui faire intercepter tous les événements en boucle.  
>C'est une solution bien moins lourde pour le système.
{.is-info}


>Mosquitto est lancé explicitement sur l'IP de la boucle locale 127.0.0.1, ce qui empêche son accès et son utilisation hors de Recalbox, pour des raisons évidentes de sécurité.  
>Si vous souhaitez modifier sa configuration, c'est ici que ça se passe: [https://mosquitto.org/man/mosquitto-conf-5.html](https://mosquitto.org/man/mosquitto-conf-5.html)
{.is-danger}

### Le fichier de status complet d'EmulationStation

A chaque événement, EmulationStation écrit un petit fichier dans le ram-disk: **`/tmp/es_state.inf`**

Ce fichier est un fichier simple de type **ini**, contenant des associations **clef=valeur**.

Ce fichier en est déjà a sa version 2.0. Jusqu'à Recalbox 6.1.1, ce fichier contenait un nombre de clefs fixes, avec des valeurs vides selon les contextes.  
La version 2.0 conserve la compatibilité avec la 1.0, mais rajoute des clefs fixes et optionnelles selon le contexte.

Voici la liste des clefs/valeurs disponibles depuis la version 1.0:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Clef</th>
      <th style="text-align:left">Valeur</th>
      <th style="text-align:left">Peut &#xEA;tre Vide?</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">System</td>
      <td style="text-align:left">Nom complet du syst&#xE8;me concern&#xE9; par l&apos;&#xE9;v&#xE9;nement.
        Peut &#xEA;tre vide.</td>
      <td style="text-align:left">Oui</td>
    </tr>
    <tr>
      <td style="text-align:left">SystemId</td>
      <td style="text-align:left">Nom court du syst&#xE8;me concern&#xE9; par l&apos;&#xE9;v&#xE9;nement.
        Peut &#xEA;tre vide</td>
      <td style="text-align:left">Oui</td>
    </tr>
    <tr>
      <td style="text-align:left">Game</td>
      <td style="text-align:left">Nom complet du jeu concern&#xE9; par l&apos;&#xE9;v&#xE9;nement. Peut
        &#xEA;tre vide</td>
      <td style="text-align:left">Oui</td>
    </tr>
    <tr>
      <td style="text-align:left">GamePath</td>
      <td style="text-align:left">Chemin complet de la rom concern&#xE9; par l&#x2019;&#xE9;v&#xE9;nement.
        Peut-&#xEA;tre vide</td>
      <td style="text-align:left">Oui</td>
    </tr>
    <tr>
      <td style="text-align:left">ImagePath</td>
      <td style="text-align:left">Chemin complet de l&apos;image du jeu concern&#xE9; par l&apos;&#xE9;v&#xE9;nement.
        Peut &#xEA;tre vide</td>
      <td style="text-align:left">Oui</td>
    </tr>
    <tr>
      <td style="text-align:left">State</td>
      <td style="text-align:left">
        <p>Contient une les valeurs suivantes:</p>
        <ul>
          <li>playing : Un jeu est en cours</li>
          <li>demo : Un jeu est en cours de d&#xE9;mo</li>
          <li>selected : Tous les autres cas.</li>
        </ul>
      </td>
      <td style="text-align:left">Non</td>
    </tr>
  </tbody>
</table>

Et la liste de ce qui est disponible en plus, depuis la 2.0:

| Clef | Valeur | Evenements |
| :--- | :--- | :--- |
| Action | Le nom de l'evenement qui a généré l'écriture du fichier state. | Tous |
| ActionData | Parametres de l'evenement, possiblement vide | Tous |
| Emulator | Émulateur par défaut pour le système concerné. | BrowsingSystem |
| Core | Core utilisé par défaut pour le système concerné. Peut avoir la même valeur que l'émulateur pour les émulateur sans plugins comme Amiberry. | BrowsingSystem |
| Emulator | Émulateur utilisé pour lancer ce jeu. | Jeux \(\*\) |
| Core | Core utilisé pour lancer ce jeu. Même remarque que pour le core système. | Jeux \(\*\) |
| IsFolder | Vaut 1 si un dossier est sélectionné dans la liste de jeu. 0 si c'est un jeu. | Jeux \(\*\) |
| ThumbnailPath | Chemin complet vers la vignette correspondant au jeu. \(\*\*\) | Jeux \(\*\) |
| VideoPath | Chemin complet vers la vidéo du jeu. \(\*\*\) | Jeux \(\*\) |
| Developer | Nom du développeur ou du studio de développement. \(\*\*\) | Jeux \(\*\) |
| Publisher | Nom de l'éditeur. \(\*\*\) | Jeux \(\*\) |
| Players | Nombre de joueurs. \(\*\*\) | Jeux \(\*\) |
| Region | Region du jeu. \(\*\*\) | Jeux \(\*\) |
| Genre | Genre du jeu. \(\*\*\) | Jeux \(\*\) |
| GenreId | Identifiant numérique du genre du jeu. \(\*\*\) | Jeux \(\*\) |
| Favorite | Vaut 1 si le jeux est en favoris, sinon 0. \(\*\*\) | Jeux \(\*\) |
| Hidden | Vaut 1 si le jeu est caché, sinon 0. \(\*\*\) | Jeux \(\*\) |
| Adult | Vaut 1 si le jeu est classé adulte, sinon 0. \(\*\*\) | Jeux \(\*\) |


>\(\*\) __Signifie en détail: GameBrowsing, RunGame, RunDemo, EndGame, EndDemo et GameScrap.
>
>\(\*\*\) Chacune de ces information provient des métadata associées au jeu concerné. Elle peuvent être donc vide si le jeu n'a pas été scrappé.
{.is-info}




>_**Ce fichier est écrit avant que les scripts ne soient lancés que le message MQTT ne soit envoyé**_. Il est donc valide lorsque les scripts s’exécutent. **Cependant**... Certains événements étant extrêmement proches, il est possible que ce fichier ait déjà été changé par un deuxième événement lorsque vous irez le lire suite à un premier événement. Il est donc conseillé de:
>
>* Vérifier la valeur de la clef **`action`** pour être sur qu'elle correspond à l’événement voulu.
>* Ne pas présumer qu'une clef optionnelle sera forcement présente ou qu'une clef fixe aura forcement une valeur.
{.is-warning}

## Les bonnes pratiques

Voici une série de conseils pour écrire vos scripts. Libre à vous de ne pas en tenir compte, mais sachez que lancer des scripts à chaque événement EmulationStation peut avoir un impact sur le système:

* Ralentissement du système
* Lags en jeux, lags dans le son, ...
* Lenteur de démarrage des jeux
* etc.

Dans la mesure du possible, limitez vos scripts au strict minimum.

Évitez les scripts qui ne filtre pas les événements. Si Recalbox rajoute des événements dans les versions futures, vos scripts seront encore plus sollicités.

Évitez les scripts synchrone si ce n'est pas strictement nécessaire \(lors de la phase d’arrêt\).

Utilisez au maximum le shell **`ASH`** plutôt que **`SH`**, il est bien plus rapide et optimisé. En contrepartie, il a quelques légères differences avec **`SH`**. [https://fr.wikipedia.org/wiki/Almquist\_shell](https://fr.wikipedia.org/wiki/Almquist_shell)

Si vous devez traiter beaucoup d’événements, utilisez un seul script permanent conjointement avec **`mosquitto_sub`**, vous économiserez beaucoup de resources systèmes.



