---
title: Código Wi-Fi por país
---

# Código Wi-Fi por país

Desde a versão 18.06.27, você pode alterar o código Wifi do país em [recalbox.conf](/v/portugues/manual-basico/primeiras-nocoes/o-arquivo-recalbox.conf) para ativar mais canais wi-fi para o seu país.

Alguns canais estão desativados em alguns países:

| Canal | Frequência \(Mhz\) | America do Norte | Japão | A Maior parte do Mundo |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 2412 | :✅: | ✅ | ✅ |
| 2 | 2417 | ✅ | ✅ | ✅ |
| 3 | 2422 | ✅ | ✅ | ✅ |
| 4 | 2427 | ✅ | ✅ | ✅ |
| 5 | 2432 | ✅ | ✅ | ✅ |
| 6 | 2437 | ✅ | ✅ | ✅ |
| 7 | 2442 | ✅ | ✅ | ✅ |
| 8 | 2447 | ✅ | ✅ | ✅ |
| 9 | 2452 | :✅: | ✅ | ✅ |
| 10 | 2457 | ✅ | ✅ | ✅ |
| 11 | 2462 | ✅ | ✅ | ✅ |
| 12 | 2467 | ​❌​ | ✅ | ✅ |
| 13 | 2472 | ​❌​ | ✅ | ✅ |
| 14 | 2484 | ​❌ | ✅ \(11b somente\) | ​❌​ |

​[Fonte](https://en.wikipedia.org/wiki/List_of_WLAN_channels)​

Aqui está o parâmetro:

```text
## Set Wifi regionwifi.region=US
```

| País | Código |
| :--- | :--- |
| Áustria | AT |
| Austrália | AU |
| Bélgica | BE |
| Brasil | BR |
| Canadá | CA |
| Suíça e Liechtenstein | CH |
| China | CN |
| Chipre | CY |
| República Checa | CZ |
| Alemanha | DE |
| Dinamarca | DK |
| Estônia | EE |
| Espanha | ES |
| Finlândia | FI |
| França | FR |
| Reino Unido | GB |
| Grécia | GR |
| Hong Kong | HK |
| Hungria | HU |
| Indonésia | ID |
| Irlanda | IE |
| Israel | IL |
| Índia | IN |
| Islândia | IS |
| Itália | IT |
| Japão | JP |
| República da Coreia | KR |
| Lituânia | LT |
| Luxemburgo | LU |
| Letônia | LV |
| Malásia | MY |
| Países Baixos | NL |
| Noruega | NO |
| Nova Zelândia | NZ |
| Filipinas | PH |
| Polônia | PL |
| Portugal | PT |
| Suécia | SE |
| Singapura | SG |
| Eslovênia | SI |
| Eslováquia | SK |
| Tailândia | TH |
| Taiwan | TW |
| Estados Unidos | US |
| África do Sul | ZA |

Mais códigos de países [aqui](http://www.arubanetworks.com/techdocs/InstantWenger_Mobile/Advanced/Content/Instant%20User%20Guide%20-%20volumes/Country_Codes_List.htm#regulatory_domain_3737302751_1017918).

