---
title: MD5sum
---

# MD5sum

Pour vérifier la signature d'un fichier autrement dit son empreinte \(**checksum**\) MD5.

## En ligne :

[HTML5 File Hash Online Calculator](https://md5file.com/calculator)

## Local : <a id="sous-windows"></a>

{% tabs %}
{% tab title="Windows" %}
Téléchargez [winmd5free](http://www.winmd5.com/download/winmd5free.zip). Installez-le puis cliquez sur le bouton browse pour sélectionner votre fichier. Entrer le checksum recommandé sur cette page \([Voir ajouter des bios](/fr/usage-basique/gestion-des-fichiers#iii-ajouter-du-contenu)\) en le mettant dans la zone Original file MD5 puis cliquer sur Verify

EXEMPLE : **gba\_bios.bin**

### **Méthode alternative 1 :**

Depuis Powershell v4.0 \(Windows 8.1 et supérieur\), la commande `get-filehash` permet de vérifier nativement le checksum d'un fichier.

1. Lancer powershell.exe
2. Exécuter la commande suivante :

```text
Get-FileHash "fichier à vérifier" -Algorithm MD5
```


>Astuce :
>
>Pour tester tous les fichiers d'un dossier \(de manière récursive\), exécutez la commande suivante après s'être positionné dans le répertoire :`Get-ChildItem -recurse | % {Get-FileHash $_.Fullname -Algorithm MD5} | select Path,Hash | ft -AutoSize`
{.is-info}

### **Méthode alternative 2 :**

Vous pouvez aussi télécharger ce script : [HackCheck Shell Extension](http://code.kliu.org/hashcheck/) Qui permet d'ajouter un onglet supplémentaire dans les propriétés d'un fichier pour windows 10.
{% endtab %}

{% tab title="macOS / Linux" %}
Utilisez la commande `md5sum`.  
Dans terminal, pour vérifier le checksum des fichiers bios, utilisez la commande shasum suivie du nom du fichier.
{% endtab %}
{% endtabs %}

