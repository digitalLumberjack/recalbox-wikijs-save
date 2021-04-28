---
title: Jouer à Doom en utilisant PRBOOM
---

# Jouer à Doom en utilisant PRBOOM


>**Information :**
>
>PrBoom est un portage du moteur graphique de Doom.  
>Il peut faire fonctionner **Doom 1** et **Doom 2**.
{.is-info}

## Jouer rapidement à DOOM I ou II

**Placez** vos jeux **DOOM 1 et/ou 2** ainsi que **les mods associés** dans le répertoire :   
  
**`/recalbox/share/roms/prboom/`**


>Attention : 
>
>Les **jeux DOOM** doivent avoir **l'extension ".wad"**  
>**NE PAS EFFACER** LE FICHIER **"prboom.wad"** qui est nécessaire à l'émulation.
{.is-danger}

## Avoir les musiques dans DOOM

Placez vos soundtracks dans le répertoire :  
**`/recalbox/share/roms/prboom/game-musics`**

Compléter le fichier prboom.cfg



> \#Music  
> mus\_bunny "./bunny.mp3"  
> mus\_e1m1 "./e1m1.mp3"  
> mus\_e1m2 "./e1m2.mp3"  
> mus\_e1m3 "./e1m3.mp3"  
> mus\_e1m4 "./e1m4.mp3"  
> mus\_e1m5 "./e1m5.mp3"  
> mus\_e1m6 "./e1m6.mp3"  
> mus\_e1m7 "./e1m7.mp3"  
> mus\_e1m8 "./e1m8.mp3"  
> mus\_e1m9 "./e1m9.mp3"  
> mus\_e2m1 "./e2m1.mp3"  
> mus\_e2m2 "./e2m2.mp3"  
> mus\_e2m3 "./e2m3.mp3"  
> mus\_e2m4 "./e2m4.mp3"  
> mus\_e2m5 "./e1m7.mp3" &lt;-- ce n'est pas une faute, il y a plusieurs doublons dans la liste  
> mus\_e2m6 "./e2m6.mp3"  
> mus\_e2m7 "./e2m7.mp3"  
> mus\_e2m8 "./e2m8.mp3"  
> mus\_e2m9 "./e3m1.mp3"  
> mus\_e3m1 "./e3m1.mp3"  
> mus\_e3m2 "./e3m2.mp3"  
> mus\_e3m3 "./e3m3.mp3"  
> mus\_e3m4 "./e1m8.mp3"  
> mus\_e3m5 "./e1m7.mp3"  
> mus\_e3m6 "./e1m6.mp3"  
> mus\_e3m7 "./e2m7.mp3"  
> mus\_e3m8 "./e3m8.mp3"  
> mus\_e3m9 "./e1m9.mp3"  
> mus\_e4m1 "./e1m8.mp3"  
> mus\_e4m2 "./e3m2.mp3"  
> mus\_e4m3 "./e3m3.mp3"  
> mus\_e4m4 "./e1m5.mp3"  
> mus\_e4m5 "./e2m7.mp3"  
> mus\_e4m6 "./e2m4.mp3"  
> mus\_e4m7 "./e2m6.mp3"  
> mus\_e4m8 "./e1m7.mp3"  
> mus\_e4m9 "./e1m9.mp3"  
> mus\_inter "./e2m3.mp3"  
> mus\_introa "./intro.mp3"  
> mus\_intro "./intro.mp3"  
> mus\_victor "./victor.mp3"  
> mus\_adrian "./adrian.mp3"  
> mus\_ampie "./ampie.mp3"  
> mus\_betwee "./betwee.mp3"  
> mus\_count2 "./countd.mp3"  
> mus\_countd "./countd.mp3"  
> mus\_ddtbl2 "./ddtblu.mp3"  
> mus\_ddtbl3 "./ddtblu.mp3"  
> mus\_ddtblu "./ddtblu.mp3"  
> mus\_dead2 "./dead.mp3"  
> mus\_dead "./dead.mp3"  
> mus\_dm2int "./dm2int.mp3"  
> mus\_dm2ttl "./dm2ttl.mp3"  
> mus\_doom2 "./doom.mp3"  
> mus\_doom "./doom.mp3"  
> mus\_evil "./evil.mp3"  
> mus\_in\_cit "./in\_cit.mp3"  
> mus\_messag "./messag.mp3"  
> mus\_messg2 "./messag.mp3"  
> mus\_openin "./openin.mp3"  
> mus\_read\_m "./read\_m.mp3"  
> mus\_romer2 "./romero.mp3"  
> mus\_romero "./romero.mp3"  
> mus\_runni2 "./runnin.mp3"  
> mus\_runnin "./runnin.mp3"  
> mus\_shawn2 "./shawn.mp3"  
> mus\_shawn3 "./shawn.mp3"  
> mus\_shawn "./shawn.mp3"  
> mus\_stalks "./stalks.mp3"  
> mus\_stlks2 "./stalks.mp3"  
> mus\_stlks3 "./stalks.mp3"  
> mus\_tense "./tense.mp3"  
> mus\_theda2 "./the\_da.mp3"  
> mus\_theda3 "./the\_da.mp3"  
> mus\_the\_da "./the\_da.mp3"  
> mus\_ultima "./ultima.mp3"

## Principales versions de Doom

Afin de dégrossir tous les noms qu'on peut entendre, un petit récapitulatif :

* **Doom**, sorti en 1993, par Id Software, comporte 3 épisodes de 9 niveaux chacun \(Knee-Deep in the Dead, The Shores of Hell et Inferno\)
* **Doom1** est la version shareware librement téléchargeable, qui n'inclut que l'EP1.
* **Doom II : Hell on Earth**, sorti en 1994, suite de Doom, avec 30 niveaux \(+2 cachés\) consécutifs.
* **The Ultimate Doom**, sorti en 1995, = Doom + un 4e épisode de 9 niveaux \(Thy Flesh Consumed\)
* **Master Levels for Doom II**, sorti en 1995, ajout de 21 niveaux pour Doom II.
* **Final Doom**, sorti en 1996, extension pour Doom II avec deux épisodes distincts :
  * **TNT Evilution** \(32 niveaux\) et **The Plutonia Experiment** \(32 niveaux\).
* **Sigil**, sorti en 2019, est un 5e épisode de Doom, créé par John Romero à l'occasion du 25ième anniversaire de Doom ... et évidemment, énormément de niveaux supplémentaires pour Doom ou Doom II !

## Quelques infos sur les wads

Même si les fichiers portent tous l'extension .wad, il en existe de plusieurs sortes :

* **IWAD** : c'est un wad qui contient toutes les données et fonctionne tout seul \(par exemple: doom.wad, doom2.wad, tnt.wad, plutonia.wad\)
* **PWAD** : c'est un wad 'add-on' qui aura besoin d'un IWAD pour fonctionner \(par exemple: quasi tous les niveaux amateurs créés par la communauté doom\)

Les wads doivent aussi être compatibles avec PrBoom.  
Certains mods vont très loin dans la modification **\(comme Brutal Doom, Doom Raider, Golden Eye,...\)** mais **ne** **fonctionnent pas** avec PrBoom.  
Chercher les infos sur le wad auquel vous désirez jouer !  
Si un wad remplace un seul niveau, ce ne sera pas forcément le niveau 1 de l'épisode 1. Il faudra atteindre le bon niveau ou utiliser un cheat pour y accéder directement.

## Jouer à un IWAD

Le fichier `gamelist.xml` peut pointer directement sur cet IWAD. Par exemple, on aura :

> &lt;game&gt;  
> &lt;path&gt;./plutonia/plutonia.wad&lt;/path&gt;  
> &lt;name&gt;\(1996\) Final Doom: The Plutonia Experiment&lt;/name&gt;  
> &lt;/game&gt;

## Jouer à un PWAD

Si quelqu'un a une meilleure méthode que celle qui suit...  
Prenons un exemple : je désire jouer à SEWERS.WAD  
On va créer le sous-dossier **/recalbox/share/roms/prboom/sewers**  
A l'intérieur, on y met SEWERS.WAD et doom.wad \(et non doom2.wad car SEWERS.WAD est un level pour Doom premier du nom\)

Le fichier gamelist.xml va pointer sur un IWAD \(doom.wad ou doom2.wad selon la version du jeu nécessaire au fonctionnement du PWAD\).  
Pour mon exemple, on aura :

> &lt;game&gt;  
> &lt;path&gt;./sewers/doom.wad&lt;/path&gt;  
> &lt;desc&gt;Remplace E3M1.&lt;/desc&gt;  
> &lt;name&gt;\(1994\) E1M10: Sewers \(Xbox Doom\)&lt;/name&gt;  
> &lt;/game&gt;

Lancez une fois le jeu, ce sera Doom qui devrait être démarré.  
Quittez le jeu et allez dans le dossier **/recalbox/share/saves/prboom/doom** qui s'est créé en lançant le jeu.  
Dans ce dossier, il y a un fichier prboom.cfg, ouvrez-le et modifiez la ligne :

> \#\# Files  
> \#wadfile\_1 ""  
> \#wadfile\_2 ""  
> \#wadfile\_3 ""  
> \#wadfile\_4 ""

en

> \#\# Files  
> \#wadfile\_1 "SEWERS.WAD" &lt;-- attention à respecter les majuscules/minuscules !  
> \#wadfile\_2 ""  
> \#wadfile\_3 ""  
> \#wadfile\_4 ""

Relancez le jeu, choisissez l'épisode 3 Inferno, le 1er level devrait être Sewers.

## Modifier les commandes de la manette

Jouant sur une 8bitdo NES30, aucun bouton ne me permettait de switcher d'arme, plutôt gênant...  
L'astuce consiste par passer par la config de Retroarch \[hotkey\] + \[B\]  
puis Touches &gt; Bouton B \(ou Y\) pour affecter une action.  
Chez moi, \[B\]=Next Weapon et \[Y\]=Run.  
Puis Sauvegarder le remappage pour le Cœur

## Les cheats

Il faut regarder du côté de RetroArch.  
Faire \[hotkey\] + \[B\] et choisir le menu Cheats.  
Puis Charger des cheats \(Remplacer\) et chercher le fichier Computer - Games &gt; DOOM.cht  
Une liste de 14 cheats se charge.  
Il suffit d’activer ou pas le cheat puis Appliquer les changements.

Parait que les cheats ne fonctionnent pas en mode NightMare!  
Les codes de changement de niveaux IDCLEV \#\# \(E\#M\# ou MAP\#\#\) ne sont pas implémentés.  
J’avais créé à la main le fichier DOOM\_levels.cht.  
Les mettre par SSH dans //recalbox/share\_init/cheats/cht/Computer - Games

Contenu de DOOM\_levels.cht :

> \# Doom  
> \# [http://doom.wikia.com/wiki/Doom\_cheat\_codes](http://doom.wikia.com/wiki/Doom_cheat_codes)
>
> cheats = 36
>
> cheat0\_desc = "E1M1: Hangar"  
> cheat0\_code = "idclev11"  
> cheat0\_enable = false
>
> cheat1\_desc = "E1M2: Nuclear Plant"  
> cheat1\_code = "idclev12"  
> cheat1\_enable = false
>
> cheat2\_desc = "E1M3: Toxin Refinery"  
> cheat2\_code = "idclev13"  
> cheat2\_enable = false
>
> cheat3\_desc = "E1M4: Command Control"  
> cheat3\_code = "idclev14"  
> cheat3\_enable = false
>
> cheat4\_desc = "E1M5: Phobos Lab"  
> cheat4\_code = "idclev15"  
> cheat4\_enable = false
>
> cheat5\_desc = "E1M6: Central Processing"  
> cheat5\_code = "idclev16"  
> cheat5\_enable = false
>
> cheat6\_desc = "E1M7: Computer Station"  
> cheat6\_code = "idclev17"  
> cheat6\_enable = false
>
> cheat7\_desc = "E1M8: Phobos Anomaly"  
> cheat7\_code = "idclev18"  
> cheat7\_enable = false
>
> cheat8\_desc = "E1M9: Military Base \(secret level\)"  
> cheat8\_code = "idclev19"  
> cheat8\_enable = false
>
> cheat9\_desc = "E2M1: Deimos Anomaly"  
> cheat9\_code = "idclev21"  
> cheat9\_enable = false
>
> cheat10\_desc = "E2M2: Containment Area"  
> cheat10\_code = "idclev22"  
> cheat10\_enable = false
>
> cheat11\_desc = "E2M3: Refinery"  
> cheat11\_code = "idclev23"  
> cheat11\_enable = false
>
> cheat12\_desc = "E2M4: Deimos Lab"  
> cheat12\_code = "idclev24"  
> cheat12\_enable = false
>
> cheat13\_desc = "E2M5: Command Center"  
> cheat13\_code = "idclev25"  
> cheat13\_enable = false
>
> cheat14\_desc = "E2M6: Halls of the Damned"  
> cheat14\_code = "idclev26"  
> cheat14\_enable = false
>
> cheat15\_desc = "E2M7: Spawning Vats"  
> cheat15\_code = "idclev27"  
> cheat15\_enable = false
>
> cheat16\_desc = "E2M8: Tower of Babel"  
> cheat16\_code = "idclev28"  
> cheat16\_enable = false
>
> cheat17\_desc = "E2M9: Fortress of Mystery \(secret level\)"  
> cheat17\_code = "idclev29"  
> cheat17\_enable = false
>
> cheat18\_desc = "E3M1: Hell Keep"  
> cheat18\_code = "idclev31"  
> cheat18\_enable = false
>
> cheat19\_desc = "E3M2: Slough of Despair"  
> cheat19\_code = "idclev32"  
> cheat19\_enable = false
>
> cheat20\_desc = "E3M3: Pandemonium"  
> cheat20\_code = "idclev33"  
> cheat20\_enable = false
>
> cheat21\_desc = "E3M4: House of Pain"  
> cheat21\_code = "idclev34"  
> cheat21\_enable = false
>
> cheat22\_desc = "E3M5: Unholy Cathedral"  
> cheat22\_code = "idclev35"  
> cheat22\_enable = false
>
> cheat23\_desc = "E3M6: Mt. Erebus"  
> cheat23\_code = "idclev36"  
> cheat23\_enable = false
>
> cheat24\_desc = "E3M7: Limbo"  
> cheat24\_code = "idclev37"  
> cheat24\_enable = false
>
> cheat25\_desc = "E3M8: Dis"  
> cheat25\_code = "idclev38"  
> cheat25\_enable = false
>
> cheat26\_desc = "E3M9: Warrens \(secret level\)"  
> cheat26\_code = "idclev39"  
> cheat26\_enable = false
>
> cheat27\_desc = "E4M1: Hell Beneath"  
> cheat27\_code = "idclev41"  
> cheat27\_enable = false
>
> cheat28\_desc = "E4M2: Perfect Hatred"  
> cheat28\_code = "idclev42"  
> cheat28\_enable = false
>
> cheat29\_desc = "E4M3: Sever the Wicked"  
> cheat29\_code = "idclev43"  
> cheat29\_enable = false
>
> cheat30\_desc = "E4M4: Unruly Evil"  
> cheat30\_code = "idclev44"  
> cheat30\_enable = false
>
> cheat31\_desc = "E4M5: They Will Repent"  
> cheat31\_code = "idclev45"  
> cheat31\_enable = false
>
> cheat32\_desc = "E4M6: Against Three Wickedly"  
> cheat32\_code = "idclev46"  
> cheat32\_enable = false
>
> cheat33\_desc = "E4M7: And Hell Followed"  
> cheat33\_code = "idclev47"  
> cheat33\_enable = false
>
> cheat34\_desc = "E4M8: Unto the Cruel"  
> cheat34\_code = "idclev48"  
> cheat34\_enable = false
>
> cheat35\_desc = "E4M9: Fear \(secret level\)"  
> cheat35\_code = "idclev49"  
> cheat35\_enable = false

## Organiser tout ça

Si vous avez beaucoup de wad, ça va vite devenir le bazar dans vos dossiers.  
De plus, dans le dossier **/recalbox/share/saves/prboom/doom**, il n'y a qu'un seul fichier prboom.cfg !  
Alors on fait comment pour jouer à plusieurs wad ?!?

Si ça peut vous inspirer, voici mon rangement :

1. Dans **/recalbox/share/roms/prboom/**, j'ai créé deux dossiers DOOM et DOOM2 qui contiendront respectivement les wad pour DOOM et DOOM2
2. Dans **/recalbox/share/roms/prboom/DOOM/**, je crée un dossier par wad, j'y copie doom.wad \(que je renomme au passage\) et le wad add-on

Par exemple :

> roms
>
> > prboom
> >
> > > DOOM
> > >
> > > > 1993\_doom
> > > >
> > > > > doom\_1993.wad

> > > > 1994\_sewers\_\(e1m10\)
> > > >
> > > > > doom\_1994\_sewers.wad  
> > > > >  SEWERS.WAD

> > > > 2019\_doomep5
> > > >
> > > > > doom\_2019\_sigil.wad  
> > > > >  SIGIL\_v1\_21.wad

> > > DOOM2
> > >
> > > > 1994\_doom2
> > > >
> > > > > doom2\_1994.wad

> > > > 1996\_plutonia
> > > >
> > > > > doom2\_1996\_plutonia.wad &lt;---- ici c'est plutonia.wad et non doom2.wad

> > > > 2011\_nuts
> > > >
> > > > > doom2\_2001\_nuts.wad  
> > > > >  NUTS.WAD

Mon fichier gamelist.xml ressemble à ça :

> &lt;?xml version="1.0" encoding="utf-8"?&gt;  
> &lt;gameList&gt;

> &lt;folder&gt;  
> &lt;path&gt;./DOOM&lt;/path&gt;  
> &lt;name&gt;DOOM & mods&lt;/name&gt;  
> &lt;image&gt;./media/images/Doom\_folder.png&lt;/image&gt;  
> &lt;/folder&gt;

> &lt;folder&gt;  
> &lt;path&gt;./DOOM2&lt;/path&gt;  
> &lt;name&gt;DOOM II & mods&lt;/name&gt;  
> &lt;image&gt;./media/images/Doom2\_folder.png&lt;/image&gt;  
> &lt;/folder&gt;

> &lt;game&gt;  
> &lt;path&gt;./DOOM/1993\_doom/doom\_1993.wad&lt;/path&gt;  
> &lt;name&gt;\(1993\) The Ultimate Doom&lt;/name&gt;  
> &lt;/game&gt;

> &lt;game&gt;  
> &lt;path&gt;./DOOM/1994\_sewers\_\(e1m10\)/doom\_1994\_sewers.wad&lt;/path&gt;  
> &lt;name&gt;\(1994\) E1M10: Sewers \(Xbox Doom\)&lt;/name&gt;  
> &lt;/game&gt;

> &lt;game&gt;  
> &lt;path&gt;./DOOM/2019\_doomep5/doom\_2019\_sigil.wad&lt;/path&gt;  
> &lt;name&gt;\(2019\) Doom EP5 SIGIL&lt;/name&gt;  
> &lt;/game&gt;

> &lt;game&gt;  
> &lt;path&gt;./DOOM2/1994\_doom2/doom2\_1994.wad&lt;/path&gt;  
> &lt;name&gt;\(1994\) Doom II: Hell On Earth&lt;/name&gt;  
> &lt;/game&gt;

> &lt;game&gt;  
> &lt;path&gt;./DOOM2/1996\_plutonia/doom2\_1996\_plutonia.wad&lt;/path&gt;  
> &lt;name&gt;\(1996\) Final Doom: The Plutonia Experiment&lt;/name&gt;  
> &lt;/game&gt;

> &lt;game&gt;  
> &lt;path&gt;./DOOM2/2011\_nuts/doom2\_2001\_nuts.wad&lt;/path&gt;  
> &lt;name&gt;\(2001\) Nuts&lt;/name&gt;  
> &lt;/game&gt;

Dans **/recalbox/share/saves/prboom/**, on retrouvera autant de dossier une fois les wad lancés une première fois.  
Modifiez ensuite prboom.cfg

