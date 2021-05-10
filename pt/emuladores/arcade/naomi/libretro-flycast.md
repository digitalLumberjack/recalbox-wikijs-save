---
title: Libretro Flycast
---

# Libretro Flycast

**Libretro Flycast** é um núcleo **Libretro** \( **flycast** \).

É um emulador **Sega Dreamcast multiplataformas** capaz de emular:

* Dreamcast
* **NAOMI M1**
* **NAOMI M2**
* **NAOMI M4**
* **Naomi GD-ROMs**
* Sammy Atomiswave.

## ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aK37rklfJnoXBVnEt%2Fcogwheel-145804_640.png?alt=media&token=0802d221-cd6f-48f4-b2f3-72767b0e1eae)Recursos <a id="fonctionnalites"></a>

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

## ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8XiT7IYKKaiugqvx_V%2F-M8Xmbk84n_wFmAjHuYz%2Ftqfp32.svg?alt=media&token=e16549a1-1f0a-407a-9ac1-016a0c61d9d6)Bios <a id="bios"></a>

As bios **necessárias** para o Naomi :

| Nome do arquivo bios | Descrição | **MD5** |
| :---: | :---: | :---: |
| `naomi.zip` | Formato MAME a partir do Romset 0.154 | `eb4099aeb42ef089cfe94f8fe95e51f6` |

​

 As bios **opcionais** para o Naomi :

| Nome do arquivo bios | Descrição | MD5 |
| :---: | :---: | :---: |
| `f355dlx.zip` | Naomi Ferrari F355 Challenge deluxe Bios from MAME | `5e83867c751f692a000afdf658dc181f` |
| `f355bios.zip` | Naomi Ferrari F355 Challenge twin/deluxe Bios from MAME | `f126d318f135f38ee377fef2acf08d7e` |
| `airlbios.zip` | Naomi Airline Pilots deluxe Bios from MAME | `3f348c88af99a40fbd11fa435f28c69d` |
| `hod2bios.zip` | Naomi The House of the Dead 2 Bios from MAME | `9c755171b222fb1f4e1439d5b709dbf1` |

### **Localização** <a id="localizacao-bios"></a>

Posicione a\(s\) BIOS assim:

┣ ​📁recalbox  
┃ ┣ ​📁share  
┃ ┃ ┣ ​📁bios  
┃ ┃ ┃ ┣ ​📁dc  
┃ ┃ ┃ ┃ ┣ **​🗒arquivo.\***  

## ![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LdKWTKrrUvJVmGP83hw%2F-M8aCYUVKmyQVmzExaM5%2F-M8aNa4dCTHo4lu4UBan%2From-30098_640.png?alt=media&token=3580fa09-47e6-4c89-b00e-1e655c7ffffe)**Roms** <a id="roms"></a>

Libretro Flycast é baseado no romset **MAME**, mas também em formatos **nullDC** para sua parte Naomi.

### Romset Mame <a id="romset-mame"></a>

Somente roms Naomi **de um RomSet MAME 0.135 ou superior** são compatíveis!  
Recomendamos o RomSet mais recente que trará muitas **compatibilidades adicionais!**  
Para obter mais informações sobre a versão atual do Romset, consulte a página [MameDev](https://www.mamedev.org/release.html).

No Naomi, algumas roms exigem um arquivo `.chd` também do Romset MAME:


>**Nota:**
>Para classificar suas ROMs de arcade, os **arquivos dat** estão disponíveis na pasta:`/recalbox/share/bios/dc/Naomi_datfiles.zip`
{.is-warning}


>**Informação:**
>Os jogos **Naomi em** **cartuchos** **suportados** estão no formato `.zip`  
>Os jogos **Naomi GD-ROMS** estão no formato `.zip` + `.chd`
{.is-info}

### **Localização** <a id="localizacao-romset-mame"></a>

Exemplo para o jogo **`cfield.zip`** :

* coloque o arquivo do jogo na raiz da pasta NaomiGD`/recalbox/share/roms/`**`naomigd`**`/cfield.zip`
* coloque o \(s\) arquivo \(s\) `.chd` necessário \(s\) em uma pasta com o mesmo nome do jogo: `/recalbox/share/roms/naomigd/`**`cfield`**`/gdl-0025.chd`

​**Fica** assim:

┣ ​📁recalbox  
┃ ┣ ​📁share  
┃ ┃ ┣ ​📁roms  
┃ ┃ ┃ ┣ ​📁naomigd  
┃ ┃ ┃ ┃ ┣ 🗒`cfield.zip`  
┃ ┃ ┃ ┃ ┣ 📁cfield  
┃ ┃ ┃ ┃ ┃ ┣ 🗒`gdl-0025.chd`  

### Romset NullDC <a id="romset-nulldc"></a>

Essas ROMs são compatíveis com Flycast, mas, **menos confiáveis** ​​do que ROMs **de um romset MAME**.


>**Informação:**
>As Roms **NullDC** são no formato: _`.bin + .lst`_
{.is-info}

### **Localização** <a id="localizacao-romset-nulldc"></a>

Posicione as ROMS assim:

┣ ​📁recalbox  
┃ ┣ ​📁share  
┃ ┃ ┣ ​📁roms  
┃ ┃ ┃ ┣ ​📁naomi  
┃ ┃ ┃ ┃ ┣ ​📁**jogo**  
┃ ┃ ┃ ┃ ┃ ┣ ​🗒**jogo.bin**  
┃ ┃ ┃ ┃ ┃ ┣ ​🗒**jogo.lst**  


>**Atenção:**
>Coloque suas roms Naomi na pasta: `/recalbox/share/roms/naomi`
{.is-info}

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

