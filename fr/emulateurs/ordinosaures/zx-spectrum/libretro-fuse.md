---
title: Libretro Fuse
---

# Libretro Fuse



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**GPLv3**](https://github.com/libretro/fuse-libretro/blob/master/LICENSE).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

### Liste des bios optionnels

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| 128p-0.rom | Pentagon 1024K ROM | a249565f03b98d004ee7f019570069cd | ⚠ |
| 128p-1.rom | Pentagon 1024K ROM | 6e09e5d3c4aef166601669feaaadc01c | ⚠ |
| gluck.rom | Pentagon 1024K ROM | d5869034604dbfd2c1d54170e874fd0a | ⚠ |
| trdos.rom | Pentagon 1024K ROM | 0c42e3b9ab8dd91ea096f1d0c07c55e5 0da70a5d2a0e733398e005b96b7e4ba6 14399030d8228ca1b16872ed426a5835 3f8a2a239a10b6694ec79148a292cfb4 4123fd0b5c218ef704770596dc6533e1 48b5da4079ff8394852429e53cfc607f 4a3e2b04982ac6c594adb6793be4d6e7 4da473775c4badcc83ab5d86dc8231de 53e2f417c6996df9af170e147df8e369 5c097b0fb75bb7147104d6e77db0300a 62cbbdca554c8c23676618d4c83ef40e 6459c606ff23a610e504d0387383148a 7031f2610845d39c54c97097afa8fa03 a3242d31a0624a64a56f3a6cb5484e7c a701f54355b53fa93fb8599933d518b7 a92db09c9aa3cfda478a9bf1eec7ff90 aa9f9acf05382aff569dfdadde4ef8f2 b08fa49b5de8448e94936a9d061dc0f5 b4c9634312b796063015450daef13dfa b6d8db853c24621cbd5fef3c892c976c c511eaa8fcc968cc13baf7ad80f3aea3 cc46c7bacbbaf528a864113c76d9b9c9 d6f43c70c003f07d0a694f81ff55db95 dd70541ed6a6e8176e8dace64f9344ad | ⚠ |
| 256s-0.rom | Scorpion 256K ROM | b9fda5b6a747ff037365b0e2d8c4379a | ⚠ |
| 256s-1.rom | Scorpion 256K ROM | 643861ad34831b255bf2eb64e8b6ecb8 | ⚠ |
| 256s-2.rom | Scorpion 256K ROM | d8ad507b1c915a9acfe0d73957082926 | ⚠ |
| 256s-3.rom | Scorpion 256K ROM | ce0723f9bc02f4948c15d3b3230ae831 | ⚠ |

⚠ Fourni mais n'est pas le bon bios.

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 📁 fuse
> > > >
> > > > > 🗒 128p-0.rom
> > > > >
> > > > > 🗒 128p-1.rom
> > > > >
> > > > > 🗒 gluck.rom
> > > > >
> > > > > 🗒 trdos.rom
> > > > >
> > > > > 🗒 256s-0.rom
> > > > >
> > > > > 🗒 256s-1.rom
> > > > >
> > > > > 🗒 256s-2.rom
> > > > >
> > > > > 🗒 256s-3.rom

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .tzx
* .tap
* .z80
* .rzx
* .scl
* .trd
* .zip
* .7z

Ce système supporte les roms compressées au format .zip/.7z. Attention toutefois, il ne s'agit que d'une archive.

Les fichiers contenus dans les .zip/.7z doivent correspondre aux extensions citées précédemment.  
De plus, chaque fichier .zip/.7z ne doit contenir qu'une seule rom compressée.

### **Emplacement**

Placez les roms comme ceci : 

> 📁recalbox
>
> > 📁share
> >
> > > 📁roms
> > >
> > > > 📁zxspectrum
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/v/francais/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur

### Disquettes TRDOS

* Pour utiliser les disquettes TRDOS \(_.scl ou_ .trd\), il faut passer la machine a "**Scorpion 256k**" dans les options
  * Menu RetroArch
  * Options
  * Passer la machine a "**Scorpion 256k**" 
  * Utiliser le clavier pour valider "GLUK BOOT"
  * Puis le nom du jeu.

## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/fuse-libretro/](https://github.com/libretro/fuse-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/fuse/](https://docs.libretro.com/library/fuse/)

