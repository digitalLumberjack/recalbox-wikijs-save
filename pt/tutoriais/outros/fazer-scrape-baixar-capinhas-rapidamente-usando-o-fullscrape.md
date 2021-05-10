---
title: Fazer Scrape \(baixar capinhas\) rapidamente usando o Fullscrape
---

# Fazer Scrape \(baixar capinhas\) rapidamente usando o Fullscrape

Atualmente, este método depende da versão do Recalbox que você está usando.

Para a versão 3.3.0 17 ou anterior, consulte a seguinte documentação.

### **Etapa 1:** <a id="etapa-1"></a>

Conecte-se ao seu Raspebrry Pi. No Windows você pode usar Putty e simplesmente abrir uma conexão para o seu IP; use _root_ para o nome de usuário, _recalboxroot_ para a senha.

Ou um cliente terminal:

> ssh root@yourip

### **Etapa 2:** <a id="etapa-2"></a>

Copie o seguinte comando:

> wget [https://raw.githubusercontent.com/substring/fullscrape/master/fullscrape.sh](https://raw.githubusercontent.com/substring/fullscrape/master/fullscrape.sh) && chmod u+x ./fullscrape.sh

### **Etapa 3:** <a id="etapa-3"></a>

Inicie um scrape individual, sistema por sistema. Por exemplo, para fazer o SNES:

> ./fullscrape.sh snes -no\_thumb=true -max\_width=375

Usando o nome da pasta rom como referência.

​

Aqui está uma lista de exemplos de sistemas que você pode usar:

**cavestory fba fbalibretro fds gamegear gb gba gbc gw lutro lynx mame mastersystem megadrive moonlight msx n64 neogeo ngp pcengine prboom psx scummvm sega32x segacd sg1000 snes vectrex virtualboy wswan**

Se desejar atualizar ou apenas adicionar imagens que ainda não foram achadas, você pode fazer:

> ./fullscrape.sh -u -no\_thumb=true -max\_width=375

## Coisas a ter em mente​ <a id="coisas-a-ter-em-mente"></a>

Para executar o script`./fullscrape.sh`, você deve estar na pasta de onde o baixou originalmente na etapa um.

A arte é armazenada na pasta:`/root/.emulationstation/downloaded_images/` O arquivo **gamelist.xml** é armazenado na pasta:`/root/.emulationstation/gamelists`, cada um em sua respectiva pasta.


>**ATENÇÃO:**
>
>fba\_libretro tem um pequeno bug, que será corrigido na versão 4.0.0: o scrape não pode ser exibido. Este problema pode ser resolvido manualmente, se você estiver realmente desesperado ...
{.is-danger}

Para Recalbox versão 4.0 ou posterior, faça o mesmo. Você só precisa modificar a primeira etapa com:

> wget [https://raw.githubusercontent.com/substring/fullscrape/4.0.0/fullscrape.sh](https://raw.githubusercontent.com/substring/fullscrape/4.0.0/fullscrape.sh) && chmod u+x ./fullscrape.sh

