---
title: Libretro QUASI88
---

# Libretro QUASI88



## ![](./gerald-g-parchment-background-or-border-5.svg) Licence

Ce core est sous licence [**BSD 3-Clause**](https://github.com/libretro/quasi88-libretro/blob/master/LICENSE).

## ![](./compatibility.png) Compatibilité

| RPI0/RPI1 | RPI2 | RPI3 | RPI4 | RPI-400 | ODROID XU4 | ODROID GO | PC x86 | PC X86\_64 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

## ![](./cogwheel-145804_640.png) Fonctionnalités



## ![](./tqfp32.svg) BIOS

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
      <td style="text-align:center">n88.rom</td>
      <td style="text-align:center">BASIC rom</td>
      <td style="text-align:center">
        <p>22be239bc0c4298bc0561252eed98633</p>
        <p>f7cba6a308c2718dbe97e60e46ddd66a</p>
        <p>4f984e04a99d56c4cfe36115415d6eb8</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">n88_0.rom</td>
      <td style="text-align:center">BASIC rom #1</td>
      <td style="text-align:center">
        <p>e28fe3f520bea594350ea8fb00395370</p>
        <p>c254685f00ca9c31b97203d6ef19f5e2</p>
        <p>d675a2ca186c6efcd6277b835de4c7e5</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">n88_1.rom</td>
      <td style="text-align:center">BASIC rom #2</td>
      <td style="text-align:center">
        <p>e844534dfe5744b381444dbe61ef1b66</p>
        <p>a8e298da7ac947669bcb1ff25cee0a83</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">n88_2.rom</td>
      <td style="text-align:center">BASIC rom #3</td>
      <td style="text-align:center">
        <p>6548fa45061274dee1ea8ae1e9e93910</p>
        <p>9d03154fd9abfc28c4e6d4dc705e6e23</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">n88_3.rom</td>
      <td style="text-align:center">BASIC rom #4</td>
      <td style="text-align:center">
        <p>fc4b76a402ba501e6ba6de4b3e8b4273</p>
        <p>e1791f8154f1cdf22b576a1a365b6e1f</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">n88n.rom</td>
      <td style="text-align:center">Emulation de la s&#xE9;rie PC-8000</td>
      <td style="text-align:center">
        <p>5d6854624dd01cd791f58727fc43a525</p>
        <p>93cd1d78b7b9c50b80041ed330332ece</p>
        <p>2ff07b8769367321128e03924af668a0</p>
      </td>
      <td style="text-align:center">&#x274C;</td>
    </tr>
    <tr>
      <td style="text-align:center">disk.rom</td>
      <td style="text-align:center">Chargement des images disque</td>
      <td style="text-align:center">
        <p>793f86784e5608352a5d7f03f03e0858</p>
        <p>01b1af474fcabe93c40d779b234a3825</p>
      </td>
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
> > > > 📁 quasi88
> > > >
> > > > > 🗒 n88.rom
> > > > >
> > > > > 🗒 n88\_0.rom
> > > > >
> > > > > 🗒 n88\_1.rom
> > > > >
> > > > > 🗒 n88\_2.rom
> > > > >
> > > > > 🗒 n88\_3.rom
> > > > >
> > > > > 🗒 n88n.rom
> > > > >
> > > > > 🗒 disk.rom

### Liste des bios optionnels

| Nom de fichier | Description | MD5 | Fourni |
| :---: | :---: | :---: | :---: |
| n88knj1.rom | Affichage des kanjis. | d81c6d5d7ad1a4bbbd6ae22a01257603 | ⚠ |

⚠ Fourni mais n'est pas le bon bios.

### **Emplacement**

Placez les bios comme ceci :

> 📁recalbox
>
> > 📁share
> >
> > > 📁bios
> > >
> > > > 📁 quasi88
> > > >
> > > > > 🗒 n88knj1.rom

## ![](./rom-30098_640.png) Roms

### **Extensions supportées**

Les roms doivent avoir les extensions suivantes :

* .d88
* .t88
* .cmt
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
> > > > 📁pc88
> > > >
> > > > > 🗒**fichier.zip**


>Les roms au format **TOSEC** sont vivement conseillées.
{.is-success}


>Pour plus d'information sur les roms, rendez-vous sur [ce tutoriel](/fr/tutoriels/jeux/generalite/les-roms-et-les-isos) !
{.is-info}

## ![](./hammer-28636_640.png) Configuration avancée de l'émulateur



## ![](./kisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png) Liens externes

* **Github utilisé** : [https://github.com/libretro/quasi88-libretro/](https://github.com/libretro/quasi88-libretro/)
* **Doc Libretro** : [https://docs.libretro.com/library/quasi88/](https://docs.libretro.com/library/quasi88/)

