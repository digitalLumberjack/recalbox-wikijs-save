---
title: DOSbox pour émuler des jeux DOS
---

# DOSbox pour émuler des jeux DOS

## Fonctionnement basique

Prenons un **exemple** simple avec le jeu ****_**Alley Cat**_ :

* Commencez par **créer le répertoire** pour votre jeu en le nomment `AlleyCat.pc`. La première partie du nom du répertoire avant le '.' doit avoir **au maximum 8 caractères** et ne **pas** contenir **de caractères spéciaux** ;
* Copiez-y les fichiers de votre jeu \(Pour les gros jeux, installez-les sur votre ordinateur avant de les copier\)
* A l'intérieur de _AlleyCat.pc,_ créez un fichier `dosbox.bat` et **éditez pour appeler l’exécutable** du jeu.

Ceci nous donne :

```text
c: 
CAT.EXE
```

* Le disque C: est **positionné par DOSBox** **sur le répertoire de votre jeu** \(ici C: équivaut à `/recalbox/share/roms/dos/AlleyCat.pc`\). De même pour '.'
* **Rebootez ou rafraichissez** votre gamelist pour voir le jeu
* Pour sortir de l'émulateur, appuyez sur **CTRL + F9** sur votre clavier

##  Fonctionnement avancé

**Ajouter** un fichier `dosbox.cfg` dans votre répertoire de jeu **au même niveau** que `dosbox.bat` vous **permet de définir une configuration DOS spécifique** pour ce jeu

Vous pouvez soit copier le fichier `dosbox.conf` depuis `\recalbox\share\system\configs\dosbox\dosbox.conf` ou utilisez celui-ci : [https://pastebin.com/13xrJdkw](https://pastebin.com/13xrJdkw)


>ATTENTION :
>
>L'extension dans le répertoire du jeu doit bien être `cfg` et non `conf`!
{.is-danger}

Dans ce fichier, la ligne `mapperfile=mapper.map` vous **permet d'utiliser** un fichier `mapper.map` pour **mapper n'importe quelle touche clavier ou** même **la souris sur votre gamepad**.  
Ce fichier peut être **créée depuis votre jeu** en pressant **CTRL + F1** à n'importe quel moment et sera alors sauvé à côté de vos fichiers `dosbox.cfg` et `dosbox.bat`.

**Quelques paramètres** du fichier `dosbox.cfg` **peuvent aussi être mis au début** de votre fichier `dosbox.bat` si vous ne voulez pas utiliser un fichier `dosbox.cfg` spécifique mais certains de ces paramètres ne fonctionneront pas dans le `dosbox.bat` ;  tout ce qui est graphique semble fonctionner, mais le paramètre _mapperfile_ ne fonctionne pas par exemple.

## Convertir un jeu pour l'utiliser sur Recalbox

Comment convertir un jeu pour l'utiliser sur Recalbox, qu'il soit acheté sur GOG ou provenant de l'excellente _ExoDOS_ Collection ?

Tout d'abord, **copiez le contenu du répertoire de jeu** \(renommez le correctement avec le .pc\).

Nous devons ensuite **adapter le contenu** du _dosbox.cfg_ et du fichier bat utilisé pour lancer le jeu.

Prenons un exemple avec la version _ExoDOS_ de **Wacky Wheels**

**Ne copiez pas directement** le `dosbox.cfg` \(or .conf\) du répertoire original car ceci peut conduire à des bugs difficiles à débusquer. **Copiez plutôt le fichier** standard **linké plus haut**, il suffit ensuite de vérifier si le `dosbox.cfg` avait une configuration spéciale et si oui, l'utiliser dans votre `dosbox.cfg`. Celle-ci se trouve dans la partie `[autoexec]` du fichier.

**Déplacer** tout d'abord **le contenu de cette partie au début** de votre fichier `dosbox.bat` et adaptez les chemins. Ici nous avons :

```text
[autoexec] 
cd .. 
cd .. 
mount c .\games\WackyWhe  
imgmount d .\games\WackyWhe\cd\wackywheels.iso -t cdrom 
c: 
cd wacky
cls 
@ww
exit 
```

et cela va nous donner une fois converti pour Recalbox :

```text
imgmount d .\cd\wackyw~1.iso -t cdrom
c: 
cd WACKY
pause
WW.EXE
```

##  Explications :

* **C: est déjà monté** par _DOSBox_ \(dans le répertoire du jeu\), nous n'en avons pas besoin ;
* '.' est également **positionné** par _DOSBox_ **sur le même répertoire** et en utilisant des chemins relatifs, **votre jeu ne sera pas configuré en dur** sur un répertoire \(vous pourrez l'utiliser dans un sous-répertoire différent ou avec une autre distribution\) ;
* **exit est supprimé** car ceci est géré par _DOSBox_ aussi ;
* Le chemin utilisé par `imgmount` est simplifié et nous devons convertir le nom d'iso à un nom DOS standard \(**8 caractères maximum** avec les deux derniers changés à ~1, ~2, ~3 etc. si le chemin est plus long et si vous avez plusieurs fichiers du même nom\). Dans ce cas, il vaut de toute façon mieux changer le nom du fichier pour quelque chose de simple ;
* Les **noms longs ne sont pas supportés** dans les fichiers **.cue** non plus, donc vous aurez peut-être à renommer les fichiers **.vue/.bin** manuellement et à éditer le fichier **.cue** pour référencer le nouveau nom du fichier **.bin** Et _DOSBox_ peut-être plutôt strict : **pas de caractères spéciaux, et parfois pas de caractères majuscules**.
* La commande **pause permet de figer l'écran et de débugger** facilement les instructions DOS, vous pouvez la supprimer une fois que vous aurez vérifié que la commande _imgmount_ fonctionne bien \(**n'utilisez pas pause après l'appel de l'exécutable du jeu** ou vous ne verrez rien\)
* _@ww_ devient **WW.EXE** \(il s'agit juste de l'appel de l'exécutable du jeu\)

Et voilà ! Certains jeux peuvent aussi utiliser un lanceur en `.bat`, copiez ses instructions à la fin de votre `dosbox.bat` après celles-provenant de la partie `[autoexec]` de `dosbox.cfg` et adaptez-les.

## Dépannage \(dans `dosbox.cfg`\)

**L'image est déformée :** Pour certains vieux jeux, vous aurez peut-être à modifier le paramètre `aspect=false` en `aspect=true` **pour obtenir une image en 4/3 ratio**. Attention sur des jeux plus récents, ceci pourrait conduire à un problème de performances ;

**Le joystick bouge tout seul :** Essayez de modifier `timed=false` en `timed=true`. Ceci peut-être dû aux _deadzone_ des joysticks également et malheureusement **il n'y aucun moyen de configurer celle-ci dans DOSBox pour le moment ;**

**On ne peut pas mapper le D-pad d'une manette xbox360 :** Oui, le mapper _**DOSBox**_ **permet de configurer le D-PAD** mais ça ne marche pas en jeu, vous pouvez peut-être essayer de changer le type de joystick ;

**Comment configurer la deadzone d'un joystick :** Malheureusement, **ce n'est pas possible** dans DOSBox pour le moment ;

**CD Not Found / CD Driver not present :** Vous avez du mal renommer vos **fichiers cd** \(io, cue, bin, edition du cue\) ou utiliser des noms ne respectant pas le standard DOS \(voir adv. rundown\) ;

**Je n'arrive pas à faire marcher `mount a` ou `mount d` :** Contrairement à `imgmount`, la commande `mount` **ne peut pas utiliser des chemins 'virtuels' de l'intérieur** de la machine _DOSBox_. Pour que `mount` marche, vous ne pouvez utiliser que des chemins réels locaux du _file system_ de Recalbox. Comme '.' est positionné sur le répertoire root / au lancement de _DOSBox_, il est **obligatoire d'utiliser le chemin absolu complet** vers le fichier ou le répertoire ;

**Le mapper est bugué, il efface mon fichier ou mélange mes boutons :** Vous êtes vraisemblablement victime du paramètre `buttonwrap`. Quand celui-ci est mis à **true**, il configure les boutons de votre pad avec une ID supérieure à celle du nombre de boutons du joystick émulé en repartant à zéro \(5 sera remappé à 0, 6 à 1, etc...\) . Mettez ce paramètre à **false** et tout devrait rentrer dans l'ordre.

