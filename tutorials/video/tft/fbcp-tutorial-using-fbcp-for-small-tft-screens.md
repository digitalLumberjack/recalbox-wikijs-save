---
description: Using FBCP for Small TFT Screens
---

# FBCP Tutorial - Using FBCP for small TFT screens

This page is still under construction. Feel free to correct it and add information ;\)

## What is FBCP ? <a id="what-is-fbcp"></a>

​[https://github.com/tasanakorn/rpi-fbcp](https://github.com/tasanakorn/rpi-fbcp)​

This program is used to copy the primary framebuffer to the secondary framebuffer \(for example, FBTFT\). It requires the latest Raspberry Pi firmware \(as of July 11, 2013\) to work properly.

FBCP takes a snapshot of `/dev/fb0`, copies it to `/dev/fb1` and waits 25ms before repeating itself. The snapshot takes about 10ms and with a delay of 25ms it gives about 1000/\(10+25\) = 28fps; CPU usage: about 2%.


>**Note :**
>
>The snapshot and refresh of the /dev/fb1 driver are not synchronized.
>
{.is-info}

## Why you need FBCP

Since Recalbox does not use Xorg or any other graphics server, all displays are done on the first framebuffer \(`/dev/fb0`\) \(HDMI or composite output\) which uses GPU power and hardware acceleration.

In the case of using Xorg, we can easily redirect the display to /dev/fb1. This is not as simple with Recalbox's framebuffer mode. Even if it is possible with some programs, thanks to the environment variable in some cases [https://github.com/notro/fbtft/wiki/Framebuffer-use](https://github.com/notro/fbtft/wiki/Framebuffer-use).

In the case of a SPI/I2C TFT display or use, this new display receives the second framebuffer \(`/dev/fb1`\) and does not take advantage of the GPU.

And in the case of the Recalbox, all programs send their display to `/dev/fb0`. So, if you try to use it with a small I2C/TFT display, you will not get any display even if your display is properly configured and enabled.

So FBCP allows you to display the contents of `/dev/fb0` using snapshot.

This method is not necessary for screens that use the DPI display mode [https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md](https://www.raspberrypi.org/documentation/hardware/raspberrypi/dpi/README.md)

## Modified version of the FBCP Recalbox program

​[https://github.com/ian57/rpi-fbcp](https://github.com/ian57/rpi-fbcp)

In fact, FBCP is not yet included in Recalbox, but it should be available in version 4.1. The original program has been modified to try to get more than 28 FPS, with a reduction of the waiting time :

```text
//usleep(25 * 1000);
usleep(5 * 1000); //only 5 ms to try to get 60fps
```

If you want to try it, you can compile it or get the right binary file at [https://github.com/ian57/rpi-fbcp](https://github.com/ian57/rpi-fbcp) depending on your version of Pi.

To compile it, you can get the rb-4.1.X-fbcp branch or simply add the `rpi-fbcp` directory in the package directory [https://github.com/ian57/recalbox-buildroot/tree/rb-4.1.X-fbcp/package/rpi-fbcp](https://github.com/ian57/recalbox-buildroot/tree/rb-4.1.X-fbcp/package/rpi-fbcp) \(dead link!\) with its 2 makefiles to try it.

This program doesn't require much dependency and should compile on versions 4.0 and 4.1. To create and install the program in the buildroot Recalbox tree, just run `make rpi-fbcp` in the root directory of your buildroot Recalbox tree. You will get the `fbcp` program in the output directory `/target/usr/bin` when the build is complete.

Then just run the general `make` command to create the Recalbox img file with the FBCP program, or simply copy it to the `/usr/bin` directory of the Recalbox partition on your SD card.

After that, read [https://recalbox.gitbook.io/tutorials/tft/setting-up-your-small-tft-screen-on-the-spi-bus](https://recalbox.gitbook.io/tutorials/tft/setting-up-your-small-tft-screen-on-the-spi-bus) page to configure your screen and launch it at boot time.

