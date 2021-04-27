---
description: Emulation of all the 8-bit Thomson computers with Theodore
---

# Thomson MO/TO

These computers are emulated by the [theodore](https://github.com/Zlika/theodore) libretro core. This core is able to emulate all the models of the MOTO family \(MO5, MO6, TO7, TO7/70, TO8, TO8D, TO9, TO9+\) and also the Olivetti PC128 \(a rebranded MO6 for the Italian market\).

## Supported file extensions <a id="supported-file-extensions"></a>

The following file extensions are supported:

* .fd \(floppy disk\)
* .sap \(floppy disk\)
* .k7 \(tape\)
* .rom \(cartridge\)
* .m7 \(cartridge\)
* .m5 \(cartridge\)

## Usage <a id="usage"></a>

By default, the model emulated depends on the name of the rom file used. For example, super-tennis-fil\_mo5.k7 will trigger the emulation of the MO5 computer \(if the file does not include the name of a supported Thomson model, the core will fallback emulating the TO8 computer\). It is possible to force the emulation of a particular model by using a configuration option in the RetroArch menu.

Once the content and core are loaded the start screen is displayed. The "Start" button of the controller can be used to start the game. The core will then make an "educated guess" to start the game \(cf. [Theodore's README file](https://github.com/Zlika/theodore/blob/master/README.md#video_game-gamepad-mapping-of-the-buttons) for more info about it\).

## Controllers <a id="controllers"></a>

Besides the "B" button used as the single button of the Thomson's joysticks, other buttons are used by the "virtual keyboard" feature. This feature allows to use the emulator and play most games without the need for a real keyboard.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Button</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">B</td>
      <td style="text-align:left">
        <p>&quot;Fire&quot; button if the virtual keyboard is not displayed.</p>
        <p>If the virtual keyboard is displayed:</p>
        <ul>
          <li>Short press: Press the focused key.</li>
          <li>Long press: Make the key &quot;sticky&quot; (or release it if it was already
            sticky). Up to 3 keys can be made sticky. All sticky keys are released
            when the virtual keyboard is hidden.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Move the keyboard in the upper or lower part of the screen.</td>
    </tr>
    <tr>
      <td style="text-align:left">Start</td>
      <td style="text-align:left">
        <p>Start the game if the virtual keyboard is not displayed.</p>
        <p>Shortcut to press the &quot;Enter&quot; key if the virtual keyboard is
          displayed.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Select</td>
      <td style="text-align:left">Show/hide the virtual keyboard</td>
    </tr>
  </tbody>
</table>

