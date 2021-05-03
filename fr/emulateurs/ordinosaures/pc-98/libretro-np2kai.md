---
title: Libretro NP2Kai
---

# Libretro NP2Kai



## ![](/migration-images/emulateurs/ordinosaures/pc-98/gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**MIT**](https://github.com/AZO234/NP2kai/blob/master/LICENSE).

## ![](/migration-images/emulateurs/ordinosaures/pc-98/compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](/migration-images/emulateurs/ordinosaures/pc-98/cogwheel-145804_640.png) Fonctionnalités



## ![](/migration-images/emulateurs/ordinosaures/pc-98/tqfp32.svg) BIOS

### Liste des bios obligatoires

<table>
  <thead>
    <tr>
      <th style="text-align:center"><b>Nom de fichier</b>
      </th>
      <th style="text-align:center">Description</th>
      <th style="text-align:center">MD5</th>
      <th style="text-align:center">Fourni</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">bios.rom</td>
      <td style="text-align:center">-</td>
      <td style="text-align:center">052f5f6010877522f78803498a625727 0c052b1f1bfd0ece11286d2ff45d296f 36293e23fe0c86cb115d59b653c13876
        3af0ae018c5710eec6e2891064814138 50274bb5dcb707e4450011b09accffcb c70ee9df11794bd5cc8aadb3721b4a03
        cd237e16e7e77c06bb58540e9e9fca68 e246140dec5124c5e404869a84caefce</td>
      <td
      style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">font.bmp</td>
      <td style="text-align:center">Affichage du texte</td>
      <td style="text-align:center">
        <p>0c8624e9ced7cca8769e5c7b0dd4279b</p>
        <p>7da1e5b7c482d4108d22a5b09631d967</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">font.rom</td>
      <td style="text-align:center">Police alternative</td>
      <td style="text-align:center">38d32748ae49d1815b0614970849fd40 4133b0be0d470920da60b9ed28d2614f 693fd1da3239d4bbeafc77d211718fc5
        829b963e21334e0fc2092ebd58f2ab4a add4a225048c85ca2bc588696c6ecdc5 ca87908a99ea423093f6d497fc367f7d
        fd0b856899aec843cbe69d2940df547f</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">itf.rom</td>
      <td style="text-align:center">-</td>
      <td style="text-align:center">1d295699ffeab0f0e24e09381299259d 72ea51443070f0e9212bfc9b793ee28e a13d96da03a28af8418d7f86ab951f1a
        b49ea39a1f730f1c966babc11961dc9a e9fc3890963b12cf15d0a2eea5815b72</td>
      <td
      style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">sound.rom</td>
      <td style="text-align:center">-</td>
      <td style="text-align:center">42c271f8b720e796a484cc1165ff4914 524473c1a5a03b17e21d86a0408ff827 a77fc2bc7c696dd68dba18e02f89d386
        caf90f22197aed6f14c471c21e64658d</td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
  </tbody>
</table>

### Emplacement

Placez les BIOS comme ceci :

> 📁 recalbox
>
> > 📁 share
> >
> > > 📁 bios
> > >
> > > > 📁 np2kai
> > > >
> > > > > 🗒 bios.rom
> > > > >
> > > > > 🗒 font.bmp
> > > > >
> > > > > 🗒 font.rom
> > > > >
> > > > > 🗒 itf.rom
> > > > >
> > > > > 🗒 sound.rom

### Liste des bios optionnels

<table>
  <thead>
    <tr>
      <th style="text-align:center">Nom de fichier</th>
      <th style="text-align:center">Description</th>
      <th style="text-align:center">MD5</th>
      <th style="text-align:center">Fourni</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">2608_hd.wav</td>
      <td style="text-align:center">YM2608 RYTHM sample</td>
      <td style="text-align:center">
        <p>9c6637930b1779abe00b8b63e4e41f50</p>
        <p>d94546e70f17fd899be8df3544ab6cbb</p>
      </td>
      <td style="text-align:center">&#x26A0;</td>
    </tr>
    <tr>
      <td style="text-align:center">2608_hh.wav</td>
      <td style="text-align:center">YM2608 RYTHM sample</td>
      <td style="text-align:center">
        <p>73548a1391631ff54a1f7c838d67917e</p>
        <p>08c54a0c1f774a5538a848a6665a34b4</p>
      </td>
      <td style="text-align:center">&#x26A0;</td>
    </tr>
    <tr>
      <td style="text-align:center">2608_rim.wav</td>
      <td style="text-align:center">YM2608 RYTHM sample</td>
      <td style="text-align:center">
        <p>43d54b3e05c081fa280c9bace3af1043</p>
        <p>465ea0768b27da404aec45dfc501404b</p>
      </td>
      <td style="text-align:center">&#x26A0;</td>
    </tr>
    <tr>
      <td style="text-align:center">2608_sd.wav</td>
      <td style="text-align:center">YM2608 RYTHM sample</td>
      <td style="text-align:center">
        <p>08124ccb84a9f65e2affc29581e690c9</p>
        <p>d71004351c8bbfdad53b18222c061d49</p>
      </td>
      <td style="text-align:center">&#x26A0;</td>
    </tr>
    <tr>
      <td style="text-align:center">2608_tom.wav</td>
      <td style="text-align:center">YM2608 RYTHM sample</td>
      <td style="text-align:center">
        <p>0faed5664a2dd8b1b2308e8a50ac25ea</p>
        <p>96a4ead13f364734f79b0c58af2f0e1f</p>
      </td>
      <td style="text-align:center">&#x26A0;</td>
    </tr>
    <tr>
      <td style="text-align:center">2608_top.wav</td>
      <td style="text-align:center">YM2608 RYTHM sample</td>
      <td style="text-align:center">
        <p>3721ace646ffd56439aebbb2154e9263</p>
        <p>593cff6597ab9380d822b8f824fd2c28</p>
      </td>
      <td style="text-align:center">&#x26A0;</td>
    </tr>
  </tbody>
</table>

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 📁 np2kai
> > > >
> > > > > 🗒 2608\_hd.wav
> > > > >
> > > > > 🗒 2608\_hh.wav
> > > > >
> > > > > 🗒 2608\_rim.wav
> > > > >
> > > > > 🗒 2608\_sd.wav
> > > > >
> > > > > 🗒 2608\_tom.wav
> > > > >
> > > > > 🗒 2608\_top.wav

## ![](/migration-images/emulateurs/ordinosaures/pc-98/rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .d98
* .98d
* .dcp
* .fdi
* .fdd
* .nfd
* .2hd
* .tfd
* .d88
* .88d
* .hdm
* .xdf
* .dup
* .cmd
* .hdi
* .thd
* .nhd
* .hdd
* .hdn
* .m3u
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
> > > > 📁pc98
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](/migration-images/emulateurs/ordinosaures/pc-98/hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](/migration-images/emulateurs/ordinosaures/pc-98/kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/AZO234/NP2kai/](https://github.com/AZO234/NP2kai/)
* **Doc Libretro** : [https://docs.libretro.com/library/neko\_project\_ii\_kai/](https://docs.libretro.com/library/neko_project_ii_kai/)

