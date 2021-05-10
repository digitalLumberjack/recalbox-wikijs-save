---
title: Libretro Flycast
---

# Libretro Flycast

**Libretro Flycast** é um núcleo **Libretro** \(**flycast**\) disponível apenas nas arquiteturas **x86\_64** e **x86**.

É um emulador **Sega Dreamcast multiplataformas** capaz de emular:

* Dreamcast
* NAOMI M1
* NAOMI M2
* NAOMI M4
* Naomi GD-ROMs
* **Sammy Atomiswave**

## ​![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aPNd5d_r7v6pbzegB%2FGerald-G-Parchment-Background-or-Border-5.svg?alt=media&token=06e7b244-ffcb-4728-a3e2-dbd348f378d5)Licença <a id="licenca"></a>

**​**[**GPLv2**](https://github.com/reicast/reicast-emulator/blob/master/LICENSE)​

## ​![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aK37rklfJnoXBVnEt%2Fcogwheel-145804_640.png?alt=media&token=0802d221-cd6f-48f4-b2f3-72767b0e1eae)Recursos <a id="recursos"></a>

| Recursos | Suportado |
| :--- | :---: |
| Reiniciar | ✔ |
| Captura de tela | ✔ |
| Salvar | ✔ |
| Opções do Núcleo | ✔ |
| Trapaças \(RetroArch Cheats\) | ✔ |
| Controles | ✔ |
| Remapeamento | ✔ |
| Vibração do Controle | ✔ |
| Controle de Disco | ✔ |

## ​![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8XiT7IYKKaiugqvx_V%2F-M8Xmbk84n_wFmAjHuYz%2Ftqfp32.svg?alt=media&token=e16549a1-1f0a-407a-9ac1-016a0c61d9d6)Bios <a id="bios"></a>

### Lista das BIOS obrigatórias <a id="lista-das-bios-obrigatorias"></a>

| Nome do arquivo bios | Descrição | Md5sum |
| :---: | :---: | :---: |
| awbios.zip | Bios "Atomiswave" \(Formato Mame\) | 0ec5ae5b5a5c4959fa8b43fcf8687f7c |

### **Localização** <a id="localizacao-bios"></a>

Posicione a BIOS assim:

┣ ​📁recalbox  
┃ ┣ ​📁share  
┃ ┃ ┣ ​📁bios  
┃ ┃ ┃ ┣ ​📁dc  
┃ ┃ ┃ ┃ ┣ **​🗒arquivo.\***  

## **​**![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aNa4dCTHo4lu4UBan%2From-30098_640.png?alt=media&token=3580fa09-47e6-4c89-b00e-1e655c7ffffe)**Roms** <a id="roms"></a>

Libretro Flycast é baseado no romset **MAME**, mas também em formatos **nullDC** para sua parte Atomiswawe.

## Romset Mame <a id="romset-mame"></a>

Somente roms Atomiswawe **de um RomSet MAME 0.135 ou superior** são compatíveis!  
Recomendamos o **RomSet Mame 0.221** que trará muitas **compatibilidades adicionais!**  
Para obter mais informações sobre a versão atual do Romset, consulte a página [MameDev](https://www.mamedev.org/release.html).


>**Nota:**
>Para classificar suas ROMs de arcade, os **arquivos dat** estão disponíveis na pasta:`/recalbox/share/bios/dc/Atomiswawe_datfiles.zip`
{.is-info}

### **Localização** <a id="localizacao-romset-mame"></a>

Posicione as ROMS assim:

┣ ​📁recalbox  
┃ ┣ ​📁share  
┃ ┃ ┣ ​📁roms  
┃ ┃ ┃ ┣ ​📁atomiswawe  
┃ ┃ ┃ ┃ ┣ **​🗒arquivo.zip**  

## Romset NullDC <a id="romset-nulldc"></a>

Essas ROMs são compatíveis com Flycast, mas, **menos confiáveis** ​​do que ROMs **de um romset MAME**.


>**Informação:**
>As Roms **NullDC** são no formato: _`.bin + .lst`_
{.is-info}

### **Localização** <a id="localizacao-romset-nulldc"></a>

Posicione as ROMS assim:

┣ ​📁recalbox  
┃ ┣ ​📁share  
┃ ┃ ┣ ​📁roms  
┃ ┃ ┃ ┣ ​📁atomiswawe  
┃ ┃ ┃ ┃ ┣ ​📁**jogo**  
┃ ┃ ┃ ┃ ┃ ┣ ​🗒**jogo.bin**  
┃ ┃ ┃ ┃ ┃ ┣ ​🗒**jogo.lst**  

## ​![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aKPqMCdW7WO3xrn1F%2Fhammer-28636_640.png?alt=media&token=d513c9a6-0bfe-48ec-8bc7-28e0de5a3754)Configuração avançada do emulador <a id="configuracao-avancada-do-emulador"></a>

### Opções do núcleo <a id="opcoes-do-nucleo"></a>

Você pode configurar várias opções via:

┣ ​📁Menu Retroarch  
┃ ┣ ​📁Opções do núcleo  
┃ ┃ ┣ ​🧩Nome\_da\_opção  


>**Informação:**  
>Para poder manter suas configurações personalizadas durante uma atualização, recomendamos que você use nosso recurso [Sobrecargas de configuração](/v/portugues/usuario-avancado/configuracoes/sobrecargas-de-configuracoes).
{.is-info}

## ​![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8XiT7IYKKaiugqvx_V%2F-M8XjzBRKUnesS-H0963%2Fkisspng-web-development-world-wide-web-computer-icons-webs-world-wide-web-icon-png-5ab05c24477216.4540070115215073642927.png?alt=media&token=0e50278c-a2c7-449b-9cd2-4dd9379f5d9f)**Links externos** <a id="links-externos"></a>

* **Github utilizado :** [https://github.com/libretro/flycast](https://github.com/libretro/flycast)\*\*\*\*
* **Doc Libretro :** [https://docs.libretro.com/library/flycast/](https://docs.libretro.com/library/flycast/)\*\*\*\*
* **Github Oficial :** [https://github.com/flyinghead/flycast](https://github.com/flyinghead/flycast)

