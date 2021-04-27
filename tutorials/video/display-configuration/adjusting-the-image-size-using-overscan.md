# Adjusting the image size using overscan

The _overscan_ option can be enabled if you have black borders on the image or if your image is cropped. You can enable the overscan option in the interface by enabling the **Overscan** option in the **USER INTERFACE SETTINGS**. You must restart the Rapsberry Pi after changing this option.

The overscan options are set by Noobs during the first installation. If it does not match your screen, you can change the settings for each border in your `config.txt` file:

```text
disable_overscan=0
overscan_left=24
overscan_right=24
overscan_top=24
overscan_bottom=24
```

The value specifies the number of pixels to be ignored at the edge of the screen. **Increase** this value _if the image is outside the edge_ of the screen; **decrease** it if there is _a black border_ between the edge of the screen and the image.

If these settings are not applied correctly in emulators or EmulationStation, try adding this :

```text
overscan_scale=1
```

