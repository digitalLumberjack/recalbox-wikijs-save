---
title: Dmesg
---

# Dmesg

## Solução de problemas com a resposta do Dmesg <a id="solucao-de-problemas-com-a-resposta-do-dmesg"></a>

* Primeiro [**obtenha acesso root**](https://recalbox.gitbook.io/tutorials/v/portugues/sistema/acesso/acesso-root-via-terminal)
* **Desligue** o seu dispositivo USB
* **Execute** `dmesg` \(lembre-se da última linha\)
* **Conecte** seu dispositivo usb
* **Execute** o `dmesg` novamente
* Agora **copie / cole** as informações **no fórum** ou abra uma discussão sobre o **problema no github**

​

## Aqui está um exemplo de um Dongle Wifi: <a id="aqui-esta-um-exemplo-de-um-dongle-wifi"></a>

```text
 [    2.817251] usb 1-1.4: new high-speed USB device number 5 using dwc_otg
 [    2.918993] usb 1-1.4: New USB device found, idVendor=7392, idProduct=7811
 [    2.919019] usb 1-1.4: New USB device strings: Mfr=1, Product=2, SerialNumber=3
 [    2.919030] usb 1-1.4: Product: 802.11n WLAN Adapter
 [    2.919041] usb 1-1.4: Manufacturer: Realtek
 [    2.919052] usb 1-1.4: SerialNumber: 00e04c000001
```

## Aqui está um exemplo com um dongle Bluetooth sem firmware: <a id="aqui-esta-um-exemplo-com-um-dongle-bluetooth-sem-firmware"></a>

```text
[ 194.192286] usb 1-1.4: new full-speed USB device number 4 using dwc_otg

[ 194.297324] usb 1-1.4: New USB device found, idVendor=0cf3, idProduct=3000

[ 194.297350] usb 1-1.4: New USB device strings: Mfr=0, Product=0, SerialNumber=0

[ 194.303210] usb 1-1.4: Direct firmware load for ath3k-1.fw failed with error -2

[ 194.303265] Bluetooth: Firmware file "ath3k-1.fw" not found

[ 194.303307] ath3k: probe of 1-1.4:1.0 failed with error -2
```

