---
title: Conectando o Recalbox a um monitor DVI
---

# Conectando o Recalbox a um monitor DVI

Você precisa **conectar o Recalbox a uma tela DVI**, mas aparece uma **tela preta ou uma linha rosa** na borda da tela?

Então, edite o arquivo config.txt e comente a seguinte linha com \(digite na frente da linha\) um \# \(hashtag\): `# hdmi_drive = 2`


>**Aviso :**
>
>Desde o recalbox v4.0.0, a partição / boot é somente leitura. Portanto, antes de editar o arquivo config.txt, você precisa montar a partição / boot com permissões de leitura e gravação.
{.is-danger}

* **Conecte-se com privilégios administrativos \(root\)**,
* Então, entre com a seguinte linha de comando: `mount -o remount, rw /boot`

