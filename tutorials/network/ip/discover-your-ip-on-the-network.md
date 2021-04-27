# Discover your IP on the network

## Recalbox network settings​

**Since version 3.3.0:**

Press Start and go to Network Settings. The current IP address is displayed here.

### Prerequisite

Make sure your recalbox is launched and connected to the network via an ethernet cable or wifi dongle.

> Do you have any doubts and your network has Internet access? Nothing could be simpler, go to the Recalbox menu then on `UPDATE THE SYSTEM`.  
> If a pop-up is displayed with the message `An update is available` or `No update available`, then your Recalbox does have access to the Internet and therefore to the network.  
> If the message `Please connect a network cable` appears, either you do not have Internet on the network which is not a problem, or you have a configuration problem on your router, a defective cable or a wifi dongle that does not does not work.

Please note that the IP is not fixed and is liable to change on each restart. You can define one yourself via the dedicated mini How-to: [Manual IP settings](https://recalbox.gitbook.io/tutorials/ip/manual-ip-settings)

## Windows​ <a id="sous-microsoft-windows"></a>

* Launch the command `Run`

  _You don't know where the command is to run,_ [_Google is your friend_](https://thegeekpage.com/101-windows-10-run-commands-shortcuts-to-find-hidden-features/)\_\_

* **Type** **`cmd`** and **`Enter`**
* Then once **in the terminal, type** `ping recalbox` **then** `Enter`
* You should have **the following message displayed:**

> Sending a 'ping' request on RECALBOX with 32 bytes of data: Response of 192.168.0.XX: bytes = 32 time = 1 ms TTL = 128 Response of 192.168.0.XX: bytes = 32 time = 1 ms TTL = 128 Response from 192.168.0.XX: bytes = 32 time = 1 ms TTL = 128 Ping statistics for \[...\]

* You have **your IP.**

## Apple OSX​ <a id="sous-apple-osx"></a>

* Launch the **`Terminal`**

  _**It is located** in the_ **`Utilities`** _folder in the_ **`Applications`** _folder_

* Type `arp -a`
* The **list of all devices connected to the network**, in the form of an IP list, **is displayed**. 
* **The Raspberry IP** is often of the type **`192.168.0.XX`**. 
* You have **your IP**.

## Other solutions

* **Smartphone applications** are available **to scan your network**. Go to your **device's store** to find **the app of your choice**.
* **Another solution** is to go to **your router settings**. The **list of connected devices** is **listed** there.

