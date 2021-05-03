---
title: Accès réseau via WinSCP \(Windows\)
---

# Accès réseau via WinSCP \(Windows\)


>**Remarque :**
>
>Ce tutoriel s'adresse aux utilisateurs de Windows. Veuillez consulter [ce tutoriel](/fr/tutoriels/systeme/acces/acces-sftp-ssh-via-cyberduck-osx-win) si vous êtes utilisateur de macOS ou si vous souhaitez utiliser Cyberduck sur Windows.
{.is-info}

## Pré-requis <a id="prerequis"></a>

* Assurez-vous que votre Recalbox est bien lancée et connectée au réseau via un cable Ethernet ou un dongle Wifi.


>**Remarque :**
>
>Vous avez un doute et votre réseau à un accès Internet ? Rien de plus simple, rendez-vous dans le menu de recalbox puis sur OPTIONS RESEAU. Vous aurez accès à votre IP et a l’état du réseau.
{.is-info}

* Téléchargez et installer le logiciel [WinSCP](https://winscp.net/).


>**Attention :**
>
>Pour macOS, il n'existe pas de version de winSCP. Cependant, vous pouvez utiliser Cyberduck en SFTP \(SSH\). Vous pourrez trouver la démarche à suivre sur ce lien.  
{.is-warning}

* Facultatif : Connaitre l'adresse IP de votre recalbox. Suivez [ce tutoriel](/fr/tutoriels/reseau/wifi/indicatif-wifi-dun-pays) si vous ne la connaissez pas.

## Configuration <a id="configuration"></a>

* Lancez `WinSCP`
* Cliquez sur `Nouveau site`
* Remplissez les informations comme il suit :
  * Protocole de fichier `SCP`
  * Nom de l'hôte `recalbox` ou l'IP que vous avez précédemment identifié \(la config sera à modifier à chaque redémarrage de recalbox si vous avez rentré l'ip et que cette dernière est dynamique\).
  * Numéro de port `22`
  * Nom d'utilisateur `root`
  * Mot de passe `recalboxroot`
  * Faite `Sauver...`
  * Remplissez les informations comme il suit :
  * Enregistre la session sous : `Recalbox` par exemple
  * Cochez la case Enregistrer le mot de passe \(non recommandé\) puis faite `OK`
* Votre logiciel est maintenant configuré
* Rendez-vous dans vos favoris \(colonne de gauche\) et double cliquez sur recalbox
* Une pop-up s'ouvre vous informant de la connexion en cours
* Une autre pop-in peut s'ouvrir vous demandant de `Continuer la connexion au serveur inconnu et ajouter la clé d'hôte dans le cache ?` puis cliquez sur `oui`
* Vous êtes connecté.

## Afficher les fichiers cachés <a id="afficher-les-fichiers-caches"></a>


>Cela vous sera utile pour **accéder** au dossier .**emulationstation** pour **modifier le thème** par exemple.
{.is-info}

* Allez dans `Préférences` \(CTRL+ALT+P\)
* Puis `Panneaux` 
* Et cochez la case `Afficher les fichiers cachés`.

## Utilisation <a id="utilisation"></a>

L'utilisation se veut assez intuitive.  
  
Par défaut, vous retrouvez à gauche votre ordinateur et à droite, l'arborescence de votre recalbox.

**Quelques astuces :**

* Pour revenir au dossier supérieur ou à la racine de votre recalbox, il suffit de cliquer sur le premier dossier avec un picto de retour haut et identifié comme `...`.
* Vous pouvez déposer des dossiers par simple glisser déposer dans la colonne de droite ou depuis la colonne de droite.
* Vous pouvez changer les permissions sur un fichier via un clic droit sur ce dernier puis `Propriétés`
* Retrouvez les chemins vers les fichiers/dossiers utiles dans le [FAQ](https://winscp.net/eng/docs/faq)

## Mettre WinSCP en français <a id="mettre-winscp-en-francais"></a>


>Une fois winscp installé, télécharger le fichier de langue français sur cette page \(French\) :[ http://winscp.net/eng/translations.php](http://winscp.net/eng/translations.php)​
{.is-info}

* Décompressez-le et placer le fichier dans `C:\Program Files(x86)\winscp\`
* Puis execute winscp,

Si l'interface est toujours en anglais, nous allons modifier la langue en français :

* Clic sur le bouton tools en bas à gauche, choisir `préférences`.
* A gauche en haut, environnements &gt; languages &gt; french - français doit apparaître ; sélectionne le puis clic sur ok.

## Ajouter Putty : <a id="ajouter-putty"></a>

* il suffit de placer l’exécutable de putty dans le dossier %programfiles%\WinSCP\Putty
* Puis de le configurer dans WinSCP &gt; outils &gt; Préférences &gt; Intégration &gt; Applications  [télécharger ici](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)


>Une astuce est aussi de cocher la case suivante : se souvenir du mot de passe de la session et le passer à Putty \(SSH\)
{.is-info}

## Ajouter Notepad++ <a id="ajouter-notepad"></a>

* Télécharger [notepad++](https://notepad-plus-plus.org/downloads/)
* Il suffit de l'ajouter à WinSCP en l'ajoutant comme éditeur externe : Outils &gt; Préférences &gt; Editeurs &gt; Ajouter indiquer le chemin vers l application notepad++
* Coche les cases comme indiqué sur la capture d'écran puis cliquer sur le bouton monter pour qu'il soit en haut dans la liste des choix.

