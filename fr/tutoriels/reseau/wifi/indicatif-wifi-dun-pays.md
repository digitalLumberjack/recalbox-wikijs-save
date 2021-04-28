---
title: Indicatif Wifi d'un pays
---

# Indicatif Wifi d'un pays

Depuis la version 18.06.27, vous pouvez changer l'indicatif Wifi du pays dans recalbox.conf pour activer plus de canaux wifi concernant votre pays.

## Canaux désactivés par pays

Certaines canaux sont désactivés dans certains pays :

| Channel | Frequency \(Mhz\) | North America | Japan | Most of World |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 2412 | ✅ | ✅ | ✅ |
| 2 | 2417 | ✅ | ✅ | ✅ |
| 3 | 2422 | ✅ | ✅ | ✅ |
| 4 | 2427 | ✅ | ✅ | ✅ |
| 5 | 2432 | ✅ | ✅ | ✅ |
| 6 | 2437 | ✅ | ✅ | ✅ |
| 7 | 2442 | ✅ | ✅ | ✅ |
| 8 | 2447 | ✅ | ✅ | ✅ |
| 9 | 2452 | ✅ | ✅ | ✅ |
| 10 | 2457 | ✅ | ✅ | ✅ |
| 11 | 2462 | ✅ | ✅ | ✅ |
| 12 | 2467 | ❌ | ✅ | ✅ |
| 13 | 2472 | ❌ | ✅ | ✅ |
| 14 | 2484 | ❌ | ✅  \(11b only\) | ❌ |

[Source](https://en.wikipedia.org/wiki/List_of_WLAN_channels)

## Paramètre

```text
## Set Wifi region
wifi.region=US
```

| Pays | Code |
| :--- | :--- |
| Autriche | AT |
| Australie | AU |
| Belgique | BE |
| Bresil | BR |
| Canada | CA |
| Suisse et Liechtenstein | CH |
| Chine | CN |
| Chypre | CY |
| Republique tchéque | CZ |
| Allemagne | DE |
| Danemark | DK |
| Estonie | EE |
| Espagne | ES |
| Finlande | FI |
| France | FR |
| Royaume-Uni | GB |
| Grece | GR |
| Hong Kong | HK |
| Hongrie | HU |
| Indonesie | ID |
| Irlande | IE |
| Israël | IL |
| Inde | IN |
| Islande | IS |
| Italie | IT |
| Japon | JP |
| République de Corée | KR |
| Lituanie | LT |
| Luxembourg | LU |
| Lettonie | LV |
| Malaisie | MY |
| Pays-Bas | NL |
| Norvège | NO |
| Nouvelle Zélande | NZ |
| Philippines | PH |
| Pologne | PL |
| Portugal | PT |
| Suède | SE |
| Singapour | SG |
| Slovenie | SI |
| Slovaquie | SK |
| Thailande | TH |
| Taiwan | TW |
| Etats-Unis | US |
| Afrique du Sud | ZA |

## Autres indicatifs

Plus d'indicatifs de pays [ici](http://www.arubanetworks.com/techdocs/InstantWenger_Mobile/Advanced/Content/Instant%20User%20Guide%20-%20volumes/Country_Codes_List.htm#regulatory_domain_3737302751_1017918).

