What it is

Basically it’s a device which performs a deauth attack.
You select the clients you want to disconnect from their network and start the attack. As long as the attack is running, the selected devices are unable to connect to their network.

How it works

The 802.11 WiFi protocol contains a so called deauthentication frame. It is used to disconnect clients safely from a wireless network.
Because these packets are unencrypted, you just need the mac address of the WiFi router and of the client device which you want to disconnect from the network. You don’t need to be in the network or know the password, it’s enough to be in its range.

What an ESP8266 is

The ESP8266 is a very cheap micro controller with build in WiFi. It contains a powerfull 160 MHz processor and you can program it with the Arduino IDE. This makes it perfect for this project.

How to protect against it

With 802.11w-2009 WiFi got an update to encrypt management frames. So make sure your router is up to date and has management frame protection enabled. But be sure that your client device supports it too, both ends need to have it enabled!

Disclaimer

Use it only for testing purposes on your own devices!

Please check the legal regulations in your country before using it. Jamming transmitters are illegal in most countries and this device can fall into the same category (even if it’s technically not the same).

My intention with this project is to draw attention to this issue. This attack shows how vulnerable the 802.11 WiFi standard is and that it has to be fixed.

FAQ

Could it auto-deauth all APs in the range?
Yes, but I will not implement this 'feature' for ethical and legal reasons.

Can it sniff handshakes?
The ESP8266 has a promiscuous mode in which you can sniff packets, but handshake packets are dropped and there is no other way to get them with the functions provided by the SDK.
Maybe someone will find a way around this barrier but I wasn't able to.

espcomm_sync failed/espcomm_open when uploading
The ESP upload tool can't communicate with the chip, make sure the right port is selected!
You can also try out different USB ports and cables.
If this doesn't solve it you may have to install USB drivers.
Which drivers you need depends on the board, most boards use a cp2102, cp2104 or ch340.

AP scan doesn't work
Try out switching the browser or open the website with another device.

Deauth attack won't work
If you see 0 pkts/s on the website you have made a mistake. Check if you have followed the the installation steps correctly and that the right SDK installed, it must be version 2.0.0!
If it can send packets but your target don't loose its connection then the WiFi router uses 802.11w and it's protected against such attacks or they communicate via 5 GHz WiFi, which the ESP8266 doesn't support.

License

This project is licensed under the MIT License - see the license file file for details
