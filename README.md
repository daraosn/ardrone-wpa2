---
```
       __     __  __  __      __
   /\ |__)   |  \|__)/  \|\ ||_ 
  /--\| \ .  |__/| \ \__/| \||__
  
              WPA/WPA2 support
```
---

A major security flaw of the Parrot(c) AR.Drone is that you can easily hack them as they use an open network infrastructure.
One could prank on someone else's flying drone and crash it by simply doing:

```{ echo "reboot"; sleep 1 } | telnet 192.168.1.1```

And even when it's possible to pair a device with the drone, there are ways to fake the MAC Address and still get access to a drone.

Wi-Fi Protected Access solves this issue.

It's possible to cross-compile wpa_supplicant into ARM architecture by following a similar method as described in the great repo from @felixge [node-cross-compiler](http://github.com/felixge/node-cross-compiler).

I'll add instructions soon on how to compile it, but it can be basically achieved using vagrant to compile the source code of wpa_supplicant, which will take care of the WPA2 authentication.

How to Use
==========
---

1. Connect your laptop to your drone.
2. Install with: ```script/install```
3. Connect to a network with: ```script/connect "<essid>" -p "<password>" -a <address> -d <droneip>```

Run ```script/connect -h``` to get help.

Do Cool Stuff
=============
---

**Connect your drone to the Internet**

1. Use connect script to join your WIFI network.
2. ```telnet <your_new_drone_ip>```
3. ```route add default gw <your_router_ip> ath0```
4. ```wget -O - http://74.125.224.72/```

TODO
====
---

- Improve scripts (i.e. parse params with getopts).
- Add support to create a WPA2 network with the drone.
- ~~Add DHCP client support.~~
- Code internal scripts / deamons to handle authentication inside the drone.
- Not so related, but would be cool to add hostname resolution.

Collaboration
=============
---

Feel free to fork and collaborate :)

License
=======
---

ardrone-wpa2 @daraosn, MIT (see LICENSE)

wpa_supplicant (BSD licensed)
Copyright (c) 2003-2013, Jouni Malinen <j@w1.fi> and contributors.