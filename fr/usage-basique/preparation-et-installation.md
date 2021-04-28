---
title: Préparation et Installation
description: Comment installer Recalbox
---

# Préparation et Installation

Il est possible d’installer Recalbox sur différents types d'appareils, le plus connu étant le Raspberry Pi \(0, 0w, 1, 2, 3 et 3B+\). Recalbox est également compatible avec l'Odroid \(XU4 et XU4Q\), ainsi que sur ordinateur x86 \(32bits\) et x86\_64 \(64bits\).

## I - Les accessoires nécessaires

Vérifiez si vous avez le dispositif de stockage requis et l’alimentation pour l’appareil choisi.

<table>
  <thead>
    <tr>
      <th style="text-align:center">Cat&#xE9;gorie</th>
      <th style="text-align:center">Raspberry Pi
        <br />0/0w/1/2/3</th>
      <th style="text-align:left">Raspberry Pi 4</th>
      <th style="text-align:center">Odroid
        <br />XU4/XU4Q</th>
      <th style="text-align:center">PC
        <br />(32/64 bits)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center"><b>Alimentation</b>
      </td>
      <td style="text-align:center">&#xB5;USB <b>2.5A </b>(de bonne qualit&#xE9;)</td>
      <td style="text-align:left"></td>
      <td style="text-align:center">Utiliser l&apos;alimentation officielle Odroid</td>
      <td style="text-align:center">Alimentation PC standard</td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Vid&#xE9;o</b>
      </td>
      <td style="text-align:center">Cable HDMIc HDMI2VGA ou HDMI2DVI</td>
      <td style="text-align:left"></td>
      <td style="text-align:center">Cable HDMI</td>
      <td style="text-align:center">HDMI/VGA
        <br />Et probablement DVI et DP</td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Contr&#xF4;leurs</b>
      </td>
      <td style="text-align:center">USB ou Bluetooth</td>
      <td style="text-align:left">USB ou Bluetooth</td>
      <td style="text-align:center">USB ou Bluetooth</td>
      <td style="text-align:center">USB ou Bluetooth</td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Stockage<br /></b>Syst&#xE8;me</td>
      <td style="text-align:center">Carte &#xB5;SD 8GB+
        <br />classe 10
        <br />Sauf Rpi1 : SD</td>
      <td style="text-align:left"></td>
      <td style="text-align:center">Carte &#xB5;SD 8GB+</td>
      <td style="text-align:center">Disque dur 8GB+</td>
    </tr>
    <tr>
      <td style="text-align:center">
        <p><b>Stockage<br /></b>Configurations</p>
        <p>Bios et Roms</p>
      </td>
      <td style="text-align:center">Disque dur externe avec sa propre alimentation</td>
      <td style="text-align:left"></td>
      <td style="text-align:center">Disque dur externe avec sa propre alimentation</td>
      <td style="text-align:center">Disque Dur
        <br />Interne
        <br />ou
        <br />Disque Dur Externe Usb
        <br />(Brancher sur la Carte M&#xE8;re)</td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Vid&#xE9;o</b>
      </td>
      <td style="text-align:center">Cable HDMIc, HDMI2VGA ou HDMI2DVI</td>
      <td style="text-align:left"></td>
      <td style="text-align:center">C&#xE2;ble HDMI</td>
      <td style="text-align:center">HDMI, VGA
        <br />(DVI et TP
        <br />probablement )</td>
    </tr>
  </tbody>
</table>


>**Informations :**
>
>Vous avez besoin des éléments suivants pour créer votre Recalbox :  
>N'hésitez pas à visiter [notre boutique](https://www.recalbox.com/fr/shop/)!
{.is-info}

## II - Installation <a id="telechargement"></a>

### 1 - Téléchargement

La première étape est de **télécharger** le fichier **.img.xz** correspondant à votre type de matériel sur [archive.recalbox.com](https://archive.recalbox.com/).


>**Attention :**  
>Seule la **dernière version** de Recalbox est **disponible.**  
>Les **anciennes versions** ne sont plus ni **téléchargeables** ni **soutenues par l'équipe de développement.**
{.is-danger}

### 2 - Flasher l'image

En utilisant un programme pour flasher l'image **Recalbox OS** sur votre média de stockage \(carte SD, carte eMMC ou Disque Dur\).


>**Remarques :**
>
>Vous devez utiliser un média de 8 Go pour le système \(nous recommandons la **Sandisk Ultra series** pour les cartes SD\)**.**
>
>* Pour l'**installation sur Rpi :**
>  * Comme média de stockage : une **carte SD.**
>* Pour l'**installation sur Odroid :**
>  * Comme média de stockage : une **carte SD ou eMMC.** 
>* Pour l'**installation sur** **x86 et x86\_64**  **:**
>  * Comme média de stockage : un **Disque Dur.**
{.is-warning}

[Lien Tutoriel Raspberry Pi Imager](../../tutoriels/utilitaires/flasher-une-image/raspberry-pi-imager.md)

[Lien Tutoriel Etcher](../../tutoriels/utilitaires/flasher-une-image/balena-etcher-disque-dur.md)

[Lien Tutoriel  UNetbootin](../../tutoriels/utilitaires/flasher-une-image/unetbootin.md)

[Lien Tutoriel Rufus](../../tutoriels/utilitaires/flasher-une-image/rufus.md)

### 3 - Installer

#### Rpi

* Insérer la carte microSD dans l’appareil avec lequel vous voulez utiliser Recalbox.
* Le démarrer et vous devriez voir Recalbox prendre vie.



#### Boîtier Retroflag GPI

Pour l'installation sur Gpi Case veuillez suivre [ce lien](/v/francais/usage-basique/preparation-et-installation/boitier-retroflag-gpi).



#### Odroid

* Insérer votre carte microSD ou eMMC dans l’appareil avec lequel vous voulez utiliser Recalbox.
* Le démarrer et vous devriez voir Recalbox prendre vie.



#### X86 / X86\_64


>**Remarques :**
>
>L'installation sur une clé usb \(tous matériels confondus\) n'est conseillée qu'à but de test. Mais n'étant pas pérenne. Cela pourrait  faire apparaître des bugs non présent sur l'installation sur Disque Dur.  
>  
>Nous vous orientons donc **sur une installation sur Disques Durs :**
>
>* Un pour le **Système**.
>* Un pour le **Stockage** de roms, bios, saves , etc... 
{.is-warning}

* Le démarrer et vous devriez voir Recalbox prendre vie.



#### Dépannage x86/x86\_64 :

* **Votre ordinateur ne boot que sur Windows :**  
  Vérifier que le **Secure Boot** est désactivé.

  * Renseignez vous sur Internet où se trouve l'option Secure boot \(différent selon le constructeur et le modèle de l'ordinateur\)
  * Puis assigner Off ou Disable pour le Secure Boot.
  * Éteindre l'ordinateur.

* **Recalbox ne boot pas :** Configurer votre **bios** en **Legacy.**
  * Pour configurer votre bios en Legacy, au démarrage de l'ordinateur, appuyer sur la touche d'accès au bios **`F*`** \(différent selon le constructeur\).
  * Renseignez-vous sur Internet où se trouve l'option Legacy \(différent selon le constructeur et le modèle de l'ordinateur\)
  * Puis assigner Legacy en l'activant avec **"enabled**" 
* **En cas de pc dédié Multiboot :** SI vous voulez que votre **Recalbox boot** avant tout autre système.
  * Accéder au **Boot Menu** des Disques Durs.
  * Appuyer sur **`F*`** pour accéder au **Boot Menu** des Disques Durs \(différent selon le constructeur\).
  * Sélectionner votre **Disque Dur Système** Recalbox.

