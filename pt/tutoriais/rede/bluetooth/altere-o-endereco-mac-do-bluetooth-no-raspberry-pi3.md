---
title: Altere o endereço MAC do bluetooth no Raspberry Pi3
---

# Altere o endereço MAC do bluetooth no Raspberry Pi3

## Por quê?​ <a id="por-que"></a>

No meu caso, tenho um raspberry pi3 com defeito e nenhuma das portas USB funciona, por isso é impossível emparelhar os controles PS3 sem fio. Alterando o endereço mac do Bluetooth, posso sincronizar os controles com outro raspberry pi3 e depois clonar o mac :\)

## Pré-requisitos <a id="pre-requisitos"></a>

Você precisará adicionar arquivos à partição do sistema, você pode fazer isso montando o cartão SD ou por SSH \(eu recomendo o [FileZilla](https://filezilla-project.org/) para isso\) e um [terminal SSH](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal).

## Instale o bdaddr <a id="instale-o-bdaddr"></a>

Primeiro você precisa da ferramenta bdaddr instalada, você pode [compilá-la](http://www.petrilopia.net/wordpress/wp-content/uploads/bdaddrtar.bz2) usando uma imagem Raspibian ou apenas baixar o binário pré-compilado em [https://www.tbit.com.br/files/static/bdaddr.gz](https://www.tbit.com.br/files/static/bdaddr.gz) extraí-lo para a pasta `/bin`de seu recalbox e torná-lo executável por:

```text
chmod +x /bin/bdaddr
```

Lembre-se de tornar sua partição de sistema gravável primeiro com `mount -o remount,rw /`

## Mude seu mac <a id="mude-seu-mac"></a>

Ok, agora você pode alterar o endereço mac do Bluetooth por \(exemplo\):

```text
bdaddr -i hci0 -r B8:27:EB:00:00:00
hciconfig hci0 reset
```

## Mudar na hora do boot <a id="mudar-na-hora-do-boot"></a>

Edite ou crie o script de inicialização`recalbox\share\system\custom.sh`:

```text
#!/bin/sh
sleep 2
/bin/bdaddr -i hci0 -r B8:27:EB:00:00:00
hciconfig hci0 reset
```

