---
title: Retroarch overloads
---

# Retroarch overloads

Here is a non-exhaustive list of keys that can be altered in a .retroarch.cfg type overload file, these modifications can only be done if the emulator is a core retroarch.


>An \* after the value means that the parameter can also be overloaded via a .recalbox.conf
{.is-info}

## Audio <a id="audio"></a>

* **`audio_enable = "true"`** _Enable or disable audio_
* **`audio_volume = "0.000000"`** _Set the volume gain, 0 = default volume by default_

## Retroarch Menu <a id="retroarch-menu"></a>

* **`quick_menu_show_save_content_dir_overrides = "false"`** _Show or hide the Configuration override option for the directory_
* **`quick_menu_show_save_core_overrides = "false"`** _Show or hide the Configuration override option for the core_
* **`quick_menu_show_save_game_overrides = "false"`** _Show or hide the option Configuration override for the game_


>Configuration Overrides are a feature of Retroarch, similar to overloads, but which retain a lot of information, in the context of recalbox, better to prefer overloads if possible
{.is-info}

## Debug <a id="debug"></a>

* **`fps_show = "true"`** _Show in-game FPS_
* **`menu_driver = "ozone"`** _Choose the retroarch menu, ozone base, except on GPi Case, where rgui is used_
* **`menu_enable_widgets = "true"`** _Enable in-game popups, if set to false, will display notifications as yellow text_

## Dossiers <a id="dossiers"></a>

* **`recording_output_directory = ""`** _Folder where video recordings go_
* **`savefile_directory = ""`** _Where to save / load saves_
* **`savestate_directory = ""`** _Where to save / load savestates_
* **`screenshot_directory = ""`** _Folder where screenshots go_

## Translation service

* **`ai_service_enable = "true"`** **\*** _Enable or disable the translation service_
* **`ai_service_mode = "0"`** _Translation service mode, 0: image, 1: voice_
* **`ai_service_source_lang = "0"`** **\*** _Language to read for the translation service, 0 = not specified_
* **`ai_service_target_lang = "1"`** \* _Language to translate into, 1 = English, 3 = French_
* **`ai_service_url =`** **\*** _Internet link of the service to use_

## Overlays <a id="overlays"></a>

* **`aspect_ratio_index = "23"`** **\*** _Ratio index, 23 = Custom_
* **`input_overlay = ""`** _Link to the overlay configuration file_
* **`input_overlay_enable = "true"`** _Activation of the overlay_
* **`input_overlay_hide_in_menu = "true"`** _Hide Overlay in Retroarch menu_

Coordinates to be defined with the overlay:

* **`custom_viewport_height = ""`**
* **`custom_viewport_width = ""`**
* **`custom_viewport_x = ""`**
* **`custom_viewport_y = ""`**
* **`video_message_pos_x = "0.050000"`**
* **`video_message_pos_y = "0.050000"`**

## Netplay <a id="netplay"></a>

* **`netplay_nickname = ""`** \* _Pseudo netplay_

_​_

## Screen rotation

* **`video_rotation = "1"`** _Rotate the video rendering, 0 = normal, 1 = 90 °, 2 = 180 °, 3 = 270 °, pay attention to the aspect ratio_

## Joystick and Directional Pad

dissociate / associate the Directional Pad to one of the joysticks

* **`input_player1_analog_dpad_mode = "0"`** _dissociate_
  * _**=**_ **"1"** _associated with the left joystick_
  * **= "2"** _associated with the right joystick_

## Remapping hotkeys


>The settings for changing hotkeys depend on the controller mapping in Recalbox, so if the controller changes, the configuration overloaded with these lines may no longer work.
{.is-warning}

To have the numerical value for each key on your controller, look in the _system/configs/retroarch/retroarchcustom.cfg_ file for the value of the desired key according to this table:

{% tabs %}
{% tab title="Hide" %}
Click on the "Show" tab to show the keys for each key
{% endtab %}

{% tab title="Show" %}
| Key name | Key concerned whose value must be taken |
| :--- | :--- |
| A | input\_player1\_a\_btn |
| B | input\_player1\_b\_btn |
| X | input\_player1\_x\_btn |
| Y | input\_player1\_y\_btn |
| Up | input\_player1\_up\_btn |
| Down | input\_player1\_down\_btn |
| Left | input\_player1\_left\_btn |
| Right | input\_player1\_right\_btn |
| Select | input\_player1\_select\_btn |
| Start | input\_player1\_start\_btn |
| L | input\_player1\_l\_btn |
| L2 | input\_player1\_l2\_btn |
| L3 | input\_player1\_l3\_btn |
| R | input\_player1\_r\_btn |
| R2 | input\_player1\_r2\_btn |
| R3 | input\_player1\_r3\_btn |
| L Axis Up | input\_player1\_l\_y\_minus\_axis |
| L axis Down | input\_player1\_l\_y\_plus\_axis |
| L Axis Left | input\_player1\_l\_x\_minus\_axis |
| L Axis Right | input\_player1\_l\_x\_plus\_axis |
| R axis Up | input\_player1\_r\_y\_minus\_axis |
| R axis Down | input\_player1\_r\_y\_plus\_axis |
| R Axis Left | input\_player1\_r\_x\_minus\_axis |
| R axis Right | input\_player1\_r\_x\_plus\_axis |
{% endtab %}
{% endtabs %}


>The modifications to be made to the following values must be made in the overload file.
>
>The previous file is only used to observe the current mapping.
{.is-warning}

* **`input_enable_hotkey_btn =`** _Hotkey key_
* **`input_screenshot_btn =`** _Key to take a screenshot_
* **`input_exit_emulator_btn =`** _Key to quit the game_
* **`input_load_state_btn =`** _Key to load a save state_
* **`input_save_state_btn =`** _Key to Save state_
* **`input_menu_toggle_btn =`** _Key to access the Retroarch menu_
* **`input_reset_btn =`** _Key to restart the game_
* **`input_ai_service_btn =`** _Key to translate the current screen_

For example, **The legend of Zelda: Link's Awakening** on Game Boy requires to use `Start + Select + A + B` to save, if your controller does not have a home button, and therefore the hotkey is on `Select`, natural saving of the game will be impossible, also put the **input\_enable\_hotkey\_btn** key on the `R` key of your controller, as a replacement exclusively for this game. If for your controller, the `R` key, so the value of the **`input_player1_r_btn`** key is `4`, then you will have to enter**`input_enable_hotkey_btn = 4`**.

