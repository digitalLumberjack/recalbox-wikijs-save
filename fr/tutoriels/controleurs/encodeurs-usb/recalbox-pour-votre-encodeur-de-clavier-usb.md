---
title: Recalbox pour votre encodeur de clavier USB
---

# Recalbox pour votre encodeur de clavier USB

## Introduction

Xarcade2jstick a été patché pour supporter les encodeurs de clavier. Vous devrez peut-être reconfigurer quelques touches de votre encodeur car malheureusement, les appareils Xarcade de X-gaming n'ont pas été mappés comme les contrôleurs habituels de MAME.

## Ajout de votre encodeur de clavier

Pour l'instant, seule la première génération d'IPAC a été incluse. Si vous disposez d'un autre encodeur de clavier, suivez les étapes suivantes :

* Connectez-vous à votre Recalbox localement ou via SSH.
* Trouvez le nom du périphérique de votre encodeur avec `ls /dev/input/by-id`. Habituellement, le résultat est suivi d'un kbd. Par exemple : _usb-Ultimarc\_IPAC\_2\_Ultimarc\_IPAC\_2\_9-if01-event-kbd_


>**NOTE** : Un seul encodeur peut avoir plusieurs noms possibles, alors essayez-les tous par exemple :
>
>* usb-Cypress\_I-PAC\_Arcade\_Control\_Interface-event-kbd -&gt; fonctionne
>* usb-Cypress\_I-PAC\_Arcade\_Control\_Interface-if01-event-kbd -&gt; ne fonctionne pas
{.is-info}

* Remontez / en lecture-écriture `mount -o remount,rw /`
* Créez un fichier vide qui porte le même nom que votre périphérique de clavier trouvé 2 étapes plus haut`touch /recalbox/share_init/system/configs/xarcade2jstick/devicename`. Dans l'exemple précédent :`touch /recalbox/share_init/system/configs/xarcade2jstick/usb-Ultimarc_IPAC_2_Ultimarc_IPAC_2_9-if01-event-kbd`
* Modifiez [recalbox.conf](/fr/usage-basique/premieres-notions/le-fichier-recalbox.conf) et réglez sur : `controllers.xarcade.enabled=1`
* Redémarrer en tapant `reboot`

Recalbox est désormais configurée pour ces périphériques.

## Cartographie des touches

### v4.0.0 - beta4 :

| Touche | Joueur 1 | Joueur 2 |
| :--- | :--- | :--- |
| HAUT | Touche Haut ou Pavé numérique touche 8 | Touche R |
| BAS | Touche Bas ou Pavé numérique touche 2 | Touche F |
| GAUCHE | Touche Gauche ou Pavé numérique touche 4 | Touche D |
| DROIT | Touche Droit ou Pavé numérique touche 6 | Touche G |
| A | Touche Z | Touche E |
| B | Touche MAJ gauche | Touche W |
| X | Touche ALT gauche | Touche S |
| Y | Touche CTRL gauche | Touche A |
| START | Pavé numérique touche 1 | Pavé numérique touche 2 |
| SELECT | Pavé numérique touche 5 | Pavé numérique touche 6 |
| L1 | Barre Espace | Touche Q |
| R1 | Touche X | Touche \[ ou Touche K |
| HOTKEY | Pavé numérique touche 3 ou Touche V | Pavé numérique touche 4 ou Touche L |



### v4.0.0 - beta2 :

| Touche | Joueur 1 | Joueur 2 |
| :--- | :--- | :--- |
| HAUT | Touche Haut ou Pavé numérique touche 8 | Touche R |
| BAS | Touche Bas ou Pavé numérique touche 2 | Touche F |
| GAUCHE | Touche Gauche ou Pavé numérique touche 4 | Touche D |
| DROIT | Touche Droit ou Pavé numérique touche 6 | Touche G |
| A | Touche Z | Touche E |
| B | Touche SHIFT gauche | Touche W |
| X | Touche ALT gauche | Touche S |
| Y | Touche CTRL gauche | Touche A |
| START | Pavé numérique touche 1 | Pavé numérique touche 2 |
| SELECT | Pavé numérique touche 3 | Pavé numérique touche 4 |
| L1 | Barre Espace | Touche Q |
| R1 | Touche X | Touche \[ |
| HOTKEY | Touche C | Touche \] |

