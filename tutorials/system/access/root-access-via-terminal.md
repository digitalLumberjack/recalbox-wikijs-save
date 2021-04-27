# Root access via Terminal

To gain access to a terminal with a root access to Recalbox, you have two options:

## SSH

To connect via SSH to Recalbox, with the following informations:

* IP Address of your Recalbox: `192.168.x.x`
* Username: `root`
* Pasword: `recalboxroot`

{% tabs %}
{% tab title="Windows" %}
You can use the software [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).
{% endtab %}

{% tab title="macOS" %}
Terminal is already installed in the system. Open your `Applications` folder and go into the `Utilities` directory.

Command line to execute: `ssh root@ip-address-of-your-Recalbox`
{% endtab %}

{% tab title="Linux" %}
Terminal is already installed in the system. Its location depends of the Linux distribution you are using.

Command line to execute: `ssh root@ip-address-of-your-Recalbox`
{% endtab %}
{% endtabs %}

## Direct access

Into EmulationStation with a keyboard plugged/linked to your Recalbox

* Press `F4` to quit EmulationStation.
* Push `ALT + F2` to gain Terminal access.
* Use the same username/password listed above.

