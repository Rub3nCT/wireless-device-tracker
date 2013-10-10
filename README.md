# Wireless Device Tracker
## Utility to track and lookup for wireless devices

This is a tool that helps you track and lookup for wireless devices.

It may be useful if you have lost your mobile phone, tablet, laptop, etc. or if it has been stolen...
You can also use it to track every device near you.

Special thanks to my friend HASH-IT for the main idea, improvement suggestions, beta-testing...

## Requirements

* [aircrack-ng](http://www.aircrack-ng.org/ "aircrack-ng homepage") (mandatory).
* [Term::ReadKey](https://metacpan.org/module/Term::ReadKey "Term::ReadKey homepage") (mandatory) (you can install it with 'cpan install Term::ReadKey').
* [sox and libsox-fmt-mp3](http://sox.sourceforge.net/ "SoX homepage") (optional / to enable sound) [_only tested on debian_].

        usage: sudo ./wdt.pl <MODE> [options]

## Modes

Wireless Device Tracker has two available working modes:

### Discovery mode (a.k.a. Gossip mode) {-d, --discovery}

This mode tracks everything around, any wireless device will be tracked.

### Lookup mode  {-l, --lookup}

This mode looks for specific devices. You need to specify them in a comma separated format. eg:

       - MAC:                  AA:BB:CC:DD:EE:FF,11:22:33:44:55:66
       - MAC + name:           AA:BB:CC:DD:EE:FF-Laptop,11:22:33:44:55:66-Phone
       - String (ESSID):       [Home],[WLAN]
       - Mixed:                AA:BB:CC:DD:EE:FF,11:22:33:44:55:66-Phone,[WLAN]

##### Lookup mode options

    -p, --play [file]

You can play a file when a device you are looking for is found. If no file is set, then the embedded one is used.

### General options

    -i, --interface <interface>
You can select the interface you want to use for tracking. Monitor mode is enabled automatically if needed.

    -a, --ap
    -s, --sta
You can filter the type of devices you want to track. This can be only _APs_ or only _STAs_.

    -g, --gap
You can set the _sleep_ time between prints (in seconds). Default time gap value is set to 30 seconds for Discovery mode.

    -w, --write <logfile>
You can log all the tracked information and store it in a file.

    -h, --help
Shows the usage screen and exits.

#Important note

While scanning, press 'q' to exit... **_DON'T PRESS Ctrl^C_**  

# License

This program is free software: you can redistribute it and / or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
