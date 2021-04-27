---
description: How to install your Recalbox
---

# Recalbox - Preparation and Setup


>This page take the Raspberry Pi as example, some steps might be different for other systems.
>
{.is-warning}

You can install your Recalbox on several devices, while the most well-known is the Raspberry Pi \(0, 1, 2, 3 and 3B+\), Recalbox is also compatible with the Odroid \(C2, XU4 and XU4Q\), as well as several [32 and 64 bits computers](../../../hardware-compatibility/compatible-pcs.md).

## What you'll need


>We advise you to read the [First use manual page](../#i-first-use) and check if you have the required storage device and power supply for the chosen device.
>
{.is-info}

<table>
  <thead>
    <tr>
      <th style="text-align:center">Category</th>
      <th style="text-align:center">Raspberry 0/0w/1/2/3</th>
      <th style="text-align:center">Odroid XU4/XU4Q</th>
      <th style="text-align:center">PC
        <br />(32 or 64 bits)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center"><b>Power supply</b>
      </td>
      <td style="text-align:center">&#xB5;USB 2.5A
        <br />(good quality)</td>
      <td style="text-align:center">Use the official Odroid power supply</td>
      <td style="text-align:center">Standard PC power supply</td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Video</b>
      </td>
      <td style="text-align:center">HDMIc cable HDMI2VGA
        <br />or HDMI2DVI</td>
      <td style="text-align:center">HDMI cable</td>
      <td style="text-align:center">HDMI / VGA, DVI and DP might work</td>
    </tr>
    <tr>
      <td style="text-align:center"><b>Control</b>
      </td>
      <td style="text-align:center">USB, Bluetooth</td>
      <td style="text-align:center">USB, Bluetooth</td>
      <td style="text-align:center">USB, Bluetooth</td>
    </tr>
    <tr>
      <td style="text-align:center">
        <p><b>Storage</b>
        </p>
        <p>System</p>
      </td>
      <td style="text-align:center">&#x39C;SD 8GB + Card class 10
        <br />Except Rpi1: SD</td>
      <td style="text-align:center">&#x39C;SD 8GB + Card</td>
      <td style="text-align:center">8GB + hard drive</td>
    </tr>
    <tr>
      <td style="text-align:center">
        <p><b>Storage</b>
        </p>
        <p>Configurations Bios and Roms</p>
      </td>
      <td style="text-align:center">External hard drive with its own power supply</td>
      <td style="text-align:center">External hard drive with its own power supply</td>
      <td style="text-align:center">PC&apos;s Hard Drive or Usb External Hard Drive (Connect to the Motherboard)</td>
    </tr>
  </tbody>
</table>


>**Information:**   
>You will need the following elements to create your Recalbox: Do not hesitate to visit our shop!
>
{.is-info}

## Download

The first step is to download the corresponding **.img.xz** file on [archive.recalbox.com](https://archive.recalbox.com/).


>**Warning :**   
>Only the **latest version** of Recalbox is **available**. **Older versions** are **no longer downloadable** or supported by the development team.
>
{.is-danger}

## Flashing the image

By using a program called **balenaEtcher**, you can flash the image file to the desired drive \(a microSD card for exemple\), the program is straightforward : you select the image, you select the correct drive, and you flash.

Once the operation is done, you can eject the drive, plug it into the device you want Recalbox to use, and start it up, you should see it booting properly.


>**Notes:**   
>You must use 8 GB media for the system \(we recommend the **Sandisk Ultra series** for SD cards\). 
>
>* For installation on **Rpi**: 
>  * storage media: an SD card. 
>* For installation on **Odroid:** 
>  * storage media: an SD or eMMC card. 
>* For installation on **x86 and x86\_64** \(on Etcher\): 
>  * storage media: a Hard Disk.
>
{.is-warning}

Etcher Tutorial link. 

UNetbootin Tutorial link. 

Rufus Tutorial link.

## Set up

### Rpi

* Insert the microSD card into the device with which you want to use Recalbox. 
* Start it up and you should see Recalbox come to life.



### **RetroFlag GPi Case**

For installation on Gpi Case please follow [this link](/basic-manual/getting-started/preparation-and-installation-of-recalbox/retroflag-gpi-case).

### Odroid

* Insert the microSD or eMMC card into the device with which you want to use Recalbox. 
* Start it up and you should see Recalbox come to life.

### X86 / X86\_64


>**Notes:**   
>  
>There are rumors about the proper functioning with the installation on a usb key \(all hardware combined\), but this remains controversial because it can possibly cause bugs not present on the installation on Hard Disk.  
>  
>We therefore guide you on an installation on **Hard Drive:** 
>
>* One for the **System.** 
>* One for the **storage** of roms, bios, saves, etc ... 
>
{.is-warning}

* Insert your two **Hard Drives** \(System and Storage\). 
* Configure your **bios** in **Legacy**. 

  * To configure your bios in Legacy, when the computer starts, press the `F *` bios access key \(different depending on the manufacturer\). 
  * Go to Then assign Legacy by activating it with **"enabled"**

  \*\*\*\*

* Check that the **Secure Boot** is disabled. 

  * Go to 
  * Then assign **Off** or **Disable** for the Secure Boot. 
  * Shutdown the computer.

* Access the **Boot Menu** of Hard Drives. 

  * Press `F *` to access the Boot Menu of **Hard Drives**. 
  * Select your Recalbox **System Hard Drive**.

* **Restart the computer** and you should see Recalbox come to life after a few minutes \(depending on the System disk storage space\). 
* **\[Optional: In case of dedicated PC\]**   
  Assign the **Boot Order** of the Hard Drives. 

  * Press
  * Then assign the **Hard Disk** that you want dedicated to the **System in 1st** then that of **Storage in 2nd**. 
  * **Restart** the computer. 

  The order of the System and Storage Hard Drives being assigned, you **no longer need to access the Boot Menu** during startup.



