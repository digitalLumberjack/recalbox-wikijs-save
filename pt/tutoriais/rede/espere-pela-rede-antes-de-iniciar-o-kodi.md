---
title: Espere pela rede antes de iniciar o Kodi
---

# Espere pela rede antes de iniciar o Kodi

## O problema​ <a id="o-problema"></a>

Quando o Kodi está no **modo de inicialização automática no Recalbox**, é possível que em algum sistema **o serviço de rede ainda não tenha sido iniciado** quando o programa abrir. Isso causa **problemas para usuários** que possuem **compartilhamentos de rede** ou **usam um banco de dados remoto**.

## Solução alternativa para versões anteriores a 4.X.X <a id="solucao-alternativa-para-versoes-anteriores-a-4-x-x"></a>

​Se você estiver usando **uma versão inferior a 4.X.X**, a solução mais fácil é **encerrar e reiniciar o kodi** no Emulationstation, **a rede deve** ter tempo durante esse intervalo **para inicializar**.

## No Recalbox 4.x \(e posterior\) <a id="no-recalbox-4-x-e-posterior"></a>

## ​ <a id="sur-recalbox-4-x-et-version-ulterieur-1"></a>

* No arquivo [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf), olhe **na seção A - Opções do sistema:**

```text
;kodi.network.waitmode=required
;kodi.network.waittime=10
;kodi.network.waithost=192.168.0.50
```

* **Remova o comentário** das linhas e **modifique os valores** conforme necessário, **removendo o ponto-e-vírgula no início das linhas**.


>**Informações:**
>
>* _**kodi.network.waitmode**_
>
>  * **required** - Use esta opção para forçar o kodi a não ser iniciado antes de conseguir o endereço IP especificado.
>  * **wish** - Usa um cronômetro de contagem regressiva em vez da opção de fazer ping em uma máquina antes de iniciar
>
>* _**kodi.network.waittime**_
>
>Tempo em segundos de espera antes que a inicialização do kodi falhe \(quando "**required**" for especificado\) ou continue a iniciar \(quando "**wish**" for especificado\)
>
>* _**kodi.network.waithost**_
>
>O endereço IP do sistema usado para testar a conexão de rede \(exemplo: o endereço IP de seu roteador ou seu compartilhamento de rede usado por kodi\)
{.is-info}

**​**

