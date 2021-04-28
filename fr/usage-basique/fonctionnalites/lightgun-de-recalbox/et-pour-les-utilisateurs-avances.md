---
title: Et pour les utilisateurs avancés ;-\)
description: Comment rajouter des jeux "lightgun" soi même comme un grand ;-)
---

# Et pour les utilisateurs avancés ;-\)

## Comment aller plus loin ?

### L'idée de base...

Le principe est d'avoir un fichier unique de configuration regroupant toutes les informations nécessaires pour les jeux "Lightgun" de tous les systèmes & émulateurs. 

Ainsi, on pourra faire de l'héritage, des regroupements de jeux mais aussi gérer des particularités sans avoir un fichier par jeu ou par système comme on peut le faire déjà mais sans pouvoir regrouper des systèmes par exemple. Ce qui est possible avec ce xml unique. 

De plus, on pourra, dans les versions suivantes \(teaser ;-\), rajouter des aides en lignes, des messages lors du chargement des jeux, etc...

Un autre avantage par rapport aux surcharges classiques : on peut rajouter des fonctions dans le python du Configgen pour aller chercher/identifier si un matériel est présent comme la Mayflash dolphin bar ou savoir sur quel board/pc on se trouve. On peut décider de configurer ainsi entre 1 à 3 joueurs Lightgun à ce jour.


>Pour rappel, ceci n'est possible que pour Libretro pour l'instant. Rien ne nous empêcherait de le faire pour d'autres émulateurs avec le fichier xml que l'on a déjà ;-\)
{.is-info}

### **Le fichier XML de configuration**

En fait, la configuration des jeux est dans un fichier xml \(pour info, c'est un ".cfg" en fait ;-\) \).

Le fichier est organisé ainsi en terme de structure _\(ici il est vide sans configurations pour montrer la structure xml au complet\)_ :

```markup
<?xml version="1.0"?>
<root>
	<common_inputs>
 	</common_inputs>
  <common_options>
  </common_options>
  <system>
 		<platform></platform>
		<emulator>
			<core></core>
		</emulator>
    <inputs>
    </inputs>
    <options>
    </options>
    <games>
      <inputs>
      </inputs>
      <options>
      </options>
      <game>
        <name></name> 
        <inputs>
        </inputs>
        <options>
        </options>
      <game>
    </games>
  </system>
</root>
```

###  **Les Tags XML**

**&lt;root&gt; :** c'est la base du XML où tout va se retrouver ainsi qu'une version pour suivre les évolution de ce fichier

```markup
<?xml version="1.0"?>
<root>
	<!-- internal version of the file to help follow-up of update, same version until release -->
	<version>1.0 - Beta8 - 20-10-2020</version>
</root>
```

**&lt;common\_inputs&gt; :** c'est la partie dans &lt;root&gt; et commune de surchage de _retroarchcustom.cfg_ que l'on va avoir pour tous les systèmes, dans le cas du lightgun, on va y mettre les touches de base comme select/exit/start/trigger.

```markup
	<!--MANDATORY inputs (for retroarchcustom.cfg): comon part to use for all systems (using dolphinbar and until 2 wiimotes) -->
	<common_inputs>
        <string name="input_player1_gun_start" value="enter" />
        <string name="input_player2_gun_start" value="enter" />
        <string name="input_player1_gun_select" value="escape" />
        <string name="input_player2_gun_select" value="escape" />
        <!-- force selecte and start for consoles games -->
        <string name="input_player1_select" value="escape" />
        <string name="input_player2_select" value="escape" />
        <string name="input_player1_start" value="enter" />
        <string name="input_player2_start" value="enter" />
        <!--for many it's necessary to move in menu or else -->
        <string name="input_player1_gun_dpad_up" value="up" />
        <string name="input_player1_gun_dpad_down" value="down" />
        <string name="input_player1_gun_dpad_right" value="right" />
        <string name="input_player1_gun_dpad_left" value="left" />
        <string name="input_player2_gun_dpad_up" value="up" />
        <string name="input_player2_gun_dpad_down" value="down" />
        <string name="input_player2_gun_dpad_right" value="right" />
        <string name="input_player2_gun_dpad_left" value="left" />
        <!-- index to manage distinction between guns -->
        <string name="input_player1_mouse_index" value="GUNP1" />
        <string name="input_player2_mouse_index" value="GUNP2" />
        <!-- wiimotes home button for exit game -->
		    <string name="input_exit_emulator" value="lsuper" />
	  	  <string name="input_enable_hotkey" value="lsuper" />
        <!-- set on fullscreen for don't see cursor mouse on x86(-64) -->
	  	  <string name="video_fullscreen" value="true" />
        <!-- to have help using overlay switch and finally ask to press 2 times home to exit -->
        <string name="input_overlay_next" value="lsuper" />
        <string name="quit_press_twice" value="true" />
 	</common_inputs>
```

**&lt;common\_options&gt; :** c'est la partie dans &lt;root&gt; et commune de surchage de _retroarch-core-options.cfg_ que l'on va avoir. Dans notre cas, ce n'est pas utilisé de manière commune mais cela serait possible.

```markup
    <!--OPTIONAL options (for retroarch-core-options.cfg): comon part to use for all systems (using dolphinbar and until 2 wiimotes) -->
  	<common_options>
        <!-- only for more log on test -->
        <!-- <string name="libretro_log_level" value="2" />
        <string name="log_verbosity" value="true" /> -->
  	</common_options>
```

**&lt;string&gt; :** ce sont les valeurs de base de configuration toujours composées de 2 attributs _"name" & "value"_ :

```markup
<string name="input_player1_gun_start" value="enter" />
```

**&lt;system&gt; :** c'est la partie qui regroupe toute la configuration d'un système. On y retrouve les tags _&lt;platform&gt;, &lt;emulator&gt;, &lt;inputs&gt;, &lt;options&gt;, &lt;games&gt; et &lt;game&gt;_.

```markup
  <!-- ********************************************************* Nintendo Entertainment System ************************************************************** -->
	<system>
    <!-- MANDATORY: name of the platform as in roms directory -->
		<platform>nes</platform>
		<!-- MANDATORY: emulator and core selected for lightgun-->
		<emulator name="libretro">
			<core>fceumm</core>
		</emulator>
    <!--MANDATORY: inputs common to this system -->
		<inputs>
      	<!-- Wiimote button B -->
		  	<string name="input_player2_gun_trigger_mbtn" value="1" />
      	<!-- gamepad -->
      	<string name="input_libretro_device_p1" value="513" />
      	<!-- lightgun -->
      	<string name="input_libretro_device_p2" value="258" />
        <!-- Set index to GUNP1 on player 2 to have first wiimote as player 1 -->
        <string name="input_player2_mouse_index" value="GUNP1" />
		</inputs>
		<!--MANDATORY: options common to this system-->
		<options>
		  	<string name="fceumm_zapper_mode" value="lightgun" />
		  	<string name="fceumm_zapper_tolerance" value="6" />
      	<string name="fceumm_show_crosshair" value="enabled" />
		</options>
        <games>
            <!--list of games using lightgun-->
            <!-- see 'duckhunt' game to see more explainations to know how to setup game part -->
            <game tested="no">
                <name>2in1</name>
            </game>
```

**&lt;platform&gt; :** c'est le tag qui correspond au nom du système mais finalement, on peut avoir plusieurs plate-formes dans le même système comme pour les systèmes à base de l'emulateur _flycast_ par exemple.

```markup
  	<!-- ******************************* Sega Naomi & Sega NaomiGd & Sega Atomiswave ********************************************************* -->
  	<system>
    <!-- MANDATORY: name of the platform as in roms directory -->
        <platform>atomiswave</platform>
        <platform>naomi</platform>
        <platform>naomigd</platform>
    		<!-- MANDATORY: emulator and core selected for lightgun-->
    		<emulator name="libretro">
      			<core>flycast</core>
    		</emulator>
```


>On peut avoir plusieurs systèmes distincts avec la même plate-forme pour avoir des jeux utilisant des émulateurs et/ou cores différents. C'est de cas de de la plate-forme MAME utilisant un core "MAME" \(sur PC\) ou "mame2003plus" \(sur les boards\).
{.is-warning}

**&lt;emulator&gt; :** ce tag a pour attribut le nom de l'émulateur à utiliser pour le système en question :

```markup
    	<!-- MANDATORY: emulator and core selected for lightgun-->
    	<emulator name="libretro">
      		<core>flycast</core>
    	</emulator>
```

**&lt;core&gt; :** ce tag a pour valeur le nom de l'émulateur à utiliser. il se trouve toujours dans _&lt;emulator&gt;_ comme ci-dessus.

```markup
<core>flycast</core>
```

**&lt;inputs&gt;** : ce tag permet de surcharger _retroarchcustom.cfg_ en plus de la partie _&lt;common\_inputs&gt;_ au niveau des _&lt;system&gt;,&lt;games&gt; et/ou &lt;game&gt;._

```markup
<system>
.....
		<inputs>
      	<!-- Wiimote button B -->
		  	<string name="input_player2_gun_trigger_mbtn" value="1" />
      	<!-- gamepad -->
      	<string name="input_libretro_device_p1" value="513" />
      	<!-- lightgun -->
      	<string name="input_libretro_device_p2" value="258" />
        <!-- Set index to GUNP1 on player 2 to have first wiimote as player 1 -->
        <string name="input_player2_mouse_index" value="GUNP1" />
.....
```

```markup
.....
        <games>
            <inputs>
                <!-- no reload, this game is a free fire but need secondary input fo grenade and more -->
                <string name="input_player1_a_mbtn" value="2" />
                <string name="input_player2_a_mbtn" value="2" />     
            </inputs>
            <game tested="ok">
                <name>alien3thegun</name>
            </game>
.....
```

```markup
.....            
            <game tested="ok">
                <name>gunbuster</name>
                <inputs>
                    <!-- no reload free fire game but ned secondary input fo grenade and more -->
                    <!-- move players with dpad on wiimote  -->
                    <string name="input_player1_a" value="2" />
                    <string name="input_player1_gun_offscreen_shot_mbtn" value="nul" />
                    <string name="input_player2_a" value="2" />
                    <string name="input_player2_gun_offscreen_shot_mbtn" value="nul" />
                </inputs>
            </game>
.....
```

**&lt;options&gt;**: ce tag permet de surcharger _retroarch-core-options.cfg_  en plus de la partie &lt;common\_options&gt; au niveau des _&lt;system&gt;,&lt;games&gt; et/ou &lt;game&gt;._ 

```markup
        <!-- options common to this system-->
        <options>
            <string name="genesis_plus_gx_gun_input" value="lightgun" />
            <string name="genesis_plus_gx_gun_cursor" value="enabled" />
        </options>
```

**&lt;games&gt; :** ce tag est la racine des groupes de jeux. Cela permet d'avoir une configuration distinct pour une partie des jeux dans un même système, on peut donc avoir plusieurs sections _&lt;games&gt;_ dans le même système.

```markup
        <games>
            <inputs>
                <!-- no reload, these games have a free fire but need secondary input for grenade and more -->
                <string name="input_player1_a_mbtn" value="2" />
                <string name="input_player2_a_mbtn" value="2" />     
            </inputs>
            <game tested="ok">
                <name>alien3thegun</name>
            </game>
            <game tested="ok">
                <name>beastbusters</name>
            </game>
            <game tested="ok">
                <name>dragongun</name>
            </game>
        </games>

```

 **&lt;game&gt; :** ce tag qui est dans &lt;games&gt; est pour définir la configuration du jeu en particulier.

```markup
            <game tested="ok">
                <name>gunbuster</name>
                <inputs>
                    <!-- no reload free fire game but ned secondary input fo grenade and more -->
                    <!-- move players with dpad on wiimote  -->
                    <string name="input_player1_a" value="2" />
                    <string name="input_player1_gun_offscreen_shot_mbtn" value="nul" />
                    <string name="input_player2_a" value="2" />
                    <string name="input_player2_gun_offscreen_shot_mbtn" value="nul" />
                </inputs>
            </game>
```


>**&lt;game&gt;** possède l'attribut _"tested"_ pour savoir si on a déjà testé cette rom en particulier et connaitre son statut \(3 valeurs possibles\) :
>
>* **no** -&gt; pas testé mais va être pris en compte en utilisant la configuration par défaut du système.
>* **ok** -&gt; testé avec la configuration défini.
>* **nok** -&gt; testé mais pas fonctionnel, donc ne sera pas configuré pour fonctionner en mode lightgun pour l'instant \(on a de l'espoir ;-\).
{.is-warning}

**&lt;name&gt; :** ce tag dans _&lt;game&gt;_ permet de préciser le nom qui va servir à l'identifier pour activer la fonctionnalité lightgun de recalbox lors du lancement.

```markup
.....
<name>duckhunt</name>
.....
<name>mobilsuitgundamfinalshooting</name>
.....
```


>Il faut toujours mettre le ****nom **sans espace/caractères spéciaux et en minuscule** pour le parsing de la "gamelist" d'un système par Recalbox. Attention, c’est le nom du jeu dans son plus simple appareil, c’est ni le nom du fichier de la rom ni le nom avec la zone géographique, etc… il faut rester le plus simple possible pour que la correspondance se fasse à coup sûr. **Faire un scrap permettra d'être sur d'avoir un jeu avec un nom identifiable.**
{.is-danger}

###  **L’héritage**

En fait dans ce paragraphe, je veux expliquer que dans l'ordre la configuration se fera ainsi : 

_**common -&gt; system -&gt; games -&gt; game**_

.... Je vous laisse me dire à quoi sera égale _****input\_player2\_gun\_trigger\_mbtn_ dans l'exemple suivant ;-\)

```markup
<?xml version="1.0"?>
<root>
	<common_inputs>
	  <string name="input_player2_gun_trigger_mbtn" value="1" />
 	</common_inputs>
  <common_options>
  </common_options>
  <system>
 		<platform></platform>
		<emulator>
			<core></core>
		</emulator>
    <inputs>
      <string name="input_player2_gun_trigger_mbtn" value="2" />
    </inputs>
    <options>
    </options>
    <games>
      <inputs>
        <string name="input_player2_gun_trigger_mbtn" value="1" />
      </inputs>
      <options>
      </options>
      <game>
        <name></name> 
        <inputs>
          <string name="input_player2_gun_trigger_mbtn" value="2" />
        </inputs>
        <options>
        </options>
      <game>
    </games>
  </system>
</root>
```

### **Gestion des index pour le multi-joueur**

Nous avons du gérer les index des "mouse" et le préciser de manière commune ou plus précise par jeu. Par exemple quand le joueur 1 est finalement sur le port 2, et le joueur 2 sur le port 3. Nous avons donc des mots clés comme **"GUNP1", "GUNP2" ou "GUNP3".**

```markup
.....
     <common_inputs>
        <!-- index to manage distinction between guns -->
        <string name="input_player1_mouse_index" value="GUNP1" />
        <string name="input_player2_mouse_index" value="GUNP2" />
        .....
```

```markup
        <games> <!-- games using justifier -->
            <inputs>
                <!-- lightguns always on port 2 -->
                <!-- For Justifier device (blue cross) -->
                <string name="input_libretro_device_p2" value="516" />
                <string name="input_player2_mouse_index" value="GUNP1" />
                <!-- Wiimote button B or Z -->
                <string name="input_player2_gun_trigger_mbtn" value="1" />
                <!-- For Justifier(P2) device (pink cross) -->
                <string name="input_libretro_device_p3" value="772" />
                <string name="input_player3_mouse_index" value="GUNP2" />
                <!-- Wiimote button B or Z -->
                <string name="input_player3_gun_trigger_mbtn" value="1" />
                <!-- Common inputs part replicated for this game using player 3 -->
                <string name="input_player3_gun_start" value="enter" />
                <string name="input_player3_gun_select" value="escape" />
                <!-- Common inputs part replicated to force select and start for consoles games -->
                <string name="input_player3_select" value="escape" />
                <string name="input_player3_start" value="enter" />
            </inputs>
            <game tested="ok">
                <name>lethalenforcers</name>
            </game>
        </games>
```

## **Mais plus simplement...** 

En fait, le fichier xml de configuration n'est pas trouvable dans votre “share” mais il est dans le système et accessible uniquement en SSH sous : **/recalbox/share\_init/system/.emulationstation**

et sous le nom: **lightgun.cfg**

Voici ce que l'on affiche dans une console SSH :

```text
# cd /recalbox/share_init/system/.emulationstation
# ls -l
total 252
-rwxr-xr-x    1 root     root         51359 Oct 22 19:13 es_bios.xml
-rwxr-xr-x    1 root     root          1254 Oct 22 19:13 es_bios.xsd
-rwxr-xr-x    1 root     root         70383 Oct 22 19:13 es_input.cfg
-rwxr-xr-x    1 root     root          2979 Oct 22 19:13 es_settings.cfg
-rw-r--r--    1 root     root         61973 Oct 23 02:31 es_systems.cfg
-rw-r--r--    1 root     root         68513 Oct 22 14:19 lightgun.cfg
drwxr-xr-x    3 root     root            36 Oct 23 02:28 themes

```


>Pour pouvoir éditer ce fichier, il faudra monter cette partition en écriture avec la commande suivante :
>
>#### mount -o remount,rw /
{.is-warning}

Début de ce fichier quand on l’ouvre avec un éditeur de texte \(ici c’est notepad++\) ****:

![](https://lh3.googleusercontent.com/NJ-LvcibdoLRqbZp4BKwPVZNtKAHmfpAve4_PAPWjoTbUW2scJYJ88azitaTROpfXIUpd_JM1TN_WoCjbZUwxXSNGLJ58J8GVp2MbhVRZKNAv6y5fX2Rfx26B3S7VzoDB7aZbMhv)

### **Comment rajouter un jeu/rom ?**

il suffit de trouver le système, exemple pour la NES :

![](https://lh5.googleusercontent.com/YuX9NuYpGF94fQ18_OxU4dYduipHfB_p6SisD0LewA-bsms877pIM11Vb8PZJrvxEWYGeNQOd48o8rcDATzvuJUog8uVHMVrZFFWZLo_oyWHUpSlFnUeF8bzgqOeDmwc-fA9-FPE)

Et de rajouter dans la section &lt;games&gt; le tag &lt;game&gt; puis &lt;name&gt; ainsi :

```markup
           <game tested="ok">
                <name>monjeu2</name>
            </game>
```


>RAPPEL: Il faut toujours mettre le ****nom **sans espace/caractères spéciaux et en minuscule** pour le parsing de la "gamelist" d'un système par Recalbox. Attention, c’est le nom du jeu dans son plus simple appareil, c’est ni le nom du fichier de la rom ou le nom avec la zone géographique, etc… il faut rester le plus simple possible pour que la correspondance se fasse à coup sûr. **Faire un scrap permettra d'être sur d'avoir un jeu avec un nom identifiable.**
{.is-danger}

### **Pour vérifier que c’est bien pris en compte** 

* Si le fichier est mal formaté, vous revenez directement à la liste des jeux.
* Si le nom n’est pas trouvé/reconnu, vous ne pourrez pas activer le mode Lightgun.
* Si vous êtes vraiment en mode Lightgun, vous devez pouvoir sortir du jeu avec la touche HOME de la Wiimote.

### Pour rajouter des configurations à un jeu

Le mieux est de regarder ce que l'on a fait pour d'autres jeux… En général, vous allez avoir besoin de modifier les paramètres correspondants aux boutons de tir primaire et secondaire, voire désactiver des touches \(voir ci-après\) mais cela peut être encore plus compliqué… Si c'est le cas, il faudra aller voir les manuels des jeux de l'époque et passer beaucoup de temps dans les menu de RetroArch ;-\) … donc maitriser l'art de la surcharge !

```markup
        <game tested="ok">
            <name>ninjaassault</name>
            <inputs>
                <!--for this game start p1 for P2 aux_c -->
                <string name="input_player1_gun_start" value="nul" />
                <string name="input_player1_gun_aux_b" value="enter" />
                <!--for this game trigger -->
                <string name="input_player1_gun_trigger_mbtn" value="nul" />
                <string name="input_player1_gun_aux_a_mbtn" value="1" />
                <!--for this game real offscreen reload -->
                <string name="input_player1_gun_offscreen_shot_mbtn" value="nul" />
            </inputs>
        </game>
```

### Pour rajouter un nouveau système

Dans ce cas,  il faut vraiment connaitre le core à utiliser, les paramètres de RetroArch et en général configurer aussi le "device" dans _&lt;inputs&gt;_ ainsi que les paramètres "lightgun" du core dans _&lt;options&gt;_.

```markup
......
<system>
<!-- MANDATORY: name of the platform as in roms directory -->
    <platform>megadrive</platform>
    <!-- MANDATORY: emulator and core selected for lightgun-->
    <emulator name="libretro">
        <core>genesisplusgx</core>
    </emulator>
    <!-- MANDATORY: inputs common to this system-->
    <inputs>
        <!-- Wiimote button B or Z -->
        <string name="input_player2_gun_trigger_mbtn" value="1" />
        <!-- Wiimote button A or c - aux when it's necessary as jump, rocket, etc... -->
        <string name="input_player2_gun_aux_a_mbtn" value="2" />
        <!-- <string name="input_player2_gun_aux_a_mbtn" value="2" /> -->
        <!-- gamepad always on port 1-->
        <string name="input_libretro_device_p1" value="1" />
    </inputs>
    <!--MANDATORY: options common to this system-->
    <options>
        <string name="genesis_plus_gx_gun_input" value="lightgun" />
        <string name="genesis_plus_gx_gun_cursor" value="enabled" />
    </options>
    .....
```

**Bon courage !!! ;-\)**

