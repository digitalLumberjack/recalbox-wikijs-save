---
title: Configuração de shaders \(antigo 3.2.11\)
---

# Configuração de shaders \(antigo 3.2.11\)

Veja como adicionar um shader ou renderizar graficamente seu Recalbox. Obrigado a @ironic por suas explicações e capturas de tela.

* Para começar, você precisa do software [winscp](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-a-rede-via-winscp), para transferir arquivos e modificar outros.
* Baixe o arquivo scanline.glsl: [https://app.box.com/s/10rjdgnc3a4uihxsnhal29rrekt5v17o](https://app.box.com/s/10rjdgnc3a4uihxsnhal29rrekt5v17o)​ 
* Em seguida, transfira-o para uma pasta de shaders, crie-a se ainda não existir

**Exemplo:** `/recalbox/share/system/shaders`

* Atribua direitos de execução à pasta e ao arquivo via winscp: clique com o botão direito&gt; propriedades&gt; 0775
* Edite o arquivo`/recalbox/scripts/config/retroarch/retroarchcustom.cfg`

### Adicione: <a id="adicione"></a>

`video_shader = "/recalbox/share/system/shaders/scanline.glsl"`

`video_shader_dir = "/recalbox/share/system/shaders/"`

`video_shader_enable = "true"`

* Salve as alterações.
* Reinicie o seu Recalbox.
* Para obter outros **shaders,** você pode baixar alguns nesta página: [https://github.com/gizmo98/common-shaders](https://github.com/gizmo98/common-shaders)​

Basta clicar no botão no canto inferior direito "Baixar ZIP"

## Aqui estão alguns exemplos Antes - Sem scanline sem suavização:​ <a id="aqui-estao-alguns-exemplos-antes-sem-scanline-sem-suavizacao"></a>

![](http://rnc.free.fr/RaspberryPi/FinalFightScanline/5%20-%20pas%20de%20scanline%20+%20pas%20de%20lissage.jpg)

Sem scanline sem suavização

![](http://rnc.free.fr/RaspberryPi/FinalFightScanline/2%20-%20scanline%20+%20lissage.jpg)

Com Scanline - Com Suavização

![](http://rnc.free.fr/RaspberryPi/FinalFightScanline/1%20-%20scanline%20+%20lissage.jpg)

Com Scanline - Com Suavização

![](http://rnc.free.fr/RaspberryPi/FinalFightScanline/4%20-%20scanline%20+%20pas%20de%20lissage.jpg)

Com scanline sem suavização

![](http://rnc.free.fr/RaspberryPi/FinalFightScanline/3%20-%20scanline%20+%20pas%20de%20lissage.jpg)

Com scanline sem suavização

