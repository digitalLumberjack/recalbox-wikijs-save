---
title: Libretro Opera
---

# Libretro Opera

**Libretro Opéra** est un core Libretro capable d'émuler la Panasonic 3DO.

## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**Modified GNU LGPL / Non-commercial**](https://github.com/libretro/opera-libretro/blob/master/libopera/opera_3do.c)**.**

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC x86\_64 | ODROID GO |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ 🐌  |

🐌 Basses performances mais jouable.

## ![](./cogwheel-145804_640.png)Fonctionnalités

| Fonctionnalité | Supporté |
| :---: | :---: |
| Restart  | ✔ |
| Screenshots | ✔ |
| Saves | ✔ |
| States | ✔ |
| Rewind | ✔ |
| Netplay | - |
| Core Options | ✔ |
| Controls | ✔ |
| Remapping | ✔ |

## ![](./tqfp32.svg)BIOS

### Liste des bios obligatoires

| Nom de fichier | Description | **MD5** | Fourni |
| :---: | :---: | :---: | :---: |
| panafz1.bin | Panasonic FZ-1 | f47264dd47fe30f73ab3c010015c155b | ❌ |
| panafz1j.bin | Panasonic FZ-1J | a496cfdded3da562759be3561317b605 | ❌ |
| panafz1j-norsa.bin | Panasonic FZ-1J \[RSA Patch\] | f6c71de7470d16abe4f71b1444883dc8 | ❌ |

### **Liste des bios optionnels**

| Nom de fichier | Description | **MD5** | Fourni |
| :---: | :---: | :---: | :---: |
| panafz10.bin | Panasonic FZ-10 | 51f2f43ae2f3508a14d9f56597e2d3ce | ⚠  |
| panafz10-norsa.bin | Panasonic FZ-10 \[RSA Patch\] | 1477bda80dc33731a65468c1f5bcbee9 | ⚠ |
| panafz10e-anvil.bin | Panasonic FZ-10-E \[Anvil\] | a48e6746bd7edec0f40cff078f0bb19f | ⚠ |
| panafz10e-anvil-norsa.bin | Panasonic FZ-10-E \[Anvil RSA Patch\] | cf11bbb5a16d7af9875cca9de9a15e09 | ⚠ |
| goldstar.bin | Goldstar GDO-101M | 8639fd5e549bd6238cfee79e3e749114 | ⚠ |
| sanyotry.bin | Sanyo IMP-21J TRY | 35fa1a1ebaaeea286dc5cd15487c13ea | ⚠ |
| 3do\_arcade\_saot.bin | Shootout At Old Tucson | 8970fc987ab89a7f64da9f8a8c4333ff | ⚠ |
| panafz1-kanji.bin | Panasonic FZ-1 \(J\) Kanji ROM. Utile pour lire les caractères japonais. | b8dc97f778a6245c58e064b0312e8281 | ⚠ |
| panafz1j-kanji.bin | Panasonic FZ-1 \(J\) Kanji ROM. Utile pour lire les caractères japonais. | c23fb5d5e6bb1c240d02cf968972be37 | ⚠ |
| panafz10ja-anvil-kanji.bin | Panasonic FZ-10 \(J\) Kanji ROM \[Anvil\]. Utile pour lire les caractères japonais. | 428577250f43edc902ea239c50d2240d | ⚠ |

⚠Fourni mais n'a pas la bonne signature MD5.

### **Emplacement**

Placez les **bios** comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 🗒**panafz1.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz1j.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz1j-norsa.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz10.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz10-norsa.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz10e-anvil.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz10e-anvil-norsa.bin**
> > > >
> > > > \*\*\*\*🗒 **goldstar.bin**
> > > >
> > > > \*\*\*\*🗒 **sanyotry.bin**
> > > >
> > > > \*\*\*\*🗒 **3do\_arcade\_saot.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz1-kanji.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz1j-kanji.bin**
> > > >
> > > > \*\*\*\*🗒 **panafz10ja-anvil-kanji.bin**

## \*\*\*\*![](./rom-30098_640.png)**Roms**

### **Extensions supportées**

Les isos doivent avoir les extensions suivantes :

* .iso
* .chd
* .bin/.cue

### **Emplacement**

Placez les isos comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁**3do**
> > > >
> > > > > 🗒**fichier.iso**


>Les isos au format **Redump** sont vivement conseillés.
{.is-success}


>Pour plus d'information sur les isos, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png)Configuration avancée de l'émulateur


>**Attention :**  
>Pour pouvoir conserver vos configurations personnalisées lors d'une mise à jour, nous vous conseillons d'utiliser notre fonctionnalité [Surcharges de configuration](/v/francais/usage-avance/surcharge-de-configuration).
{.is-danger}

### Accéder aux options

Vous pouvez configurer diverses options de deux façons différentes.

* Via le Menu RetroArch :

> 📁Menu RetroArch
>
> > 📁Options du core
> >
> > > 🧩Name\_option

* Via le fichier `retroarch-core-options.cfg`:

> 📁recalbox
>
> > 📁share
> >
> > > 📁system
> > >
> > > > 📁configs
> > > >
> > > > > 📁retroarch
> > > > >
> > > > > > 📁cores
> > > > > >
> > > > > > > 🧩**retroarch-core-options.cfg**

### Options du core

[https://docs.libretro.com/library/opera/\#core-options](https://docs.libretro.com/library/opera/#core-options)

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png)**Liens externes**

* **Github utilisé :** [https://github.com/libretro/opera-libretro/](https://github.com/libretro/opera-libretro)
* **Doc Libretro :** [https://docs.libretro.com/library/opera/](https://docs.libretro.com/library/opera/)
* **Liste de compatibilité :** [http://wiki.fourdo.com/Compatibility\_List](http://wiki.fourdo.com/Compatibility_List)

