
# Table of Contents

1.  [Quick start](#orga1ffd18)
    1.  [Connecting](#org2c9b795)
        1.  [Identifying the device](#org6d69ace)
    2.  [Hardware](#org92834f1)
        1.  [Components](#orgc3db99e)
    3.  [CTF](#org2dfafbd)
2.  [Links](#org5b3a4c8)



<a id="orga1ffd18"></a>

# Quick start


<a id="org2c9b795"></a>

## Connecting

In Putty, scroll down in the Category pane & fill in the
fields uner serial

-   **baud rate:** 115200
-   **data bits:** 8
-   **stop bits:** 1
-   **parity:** None

Hit Ctrl-C a few times and Enter to drop in to
a [micropython](https://micropython.org/) repl


<a id="org6d69ace"></a>

### Identifying the device

1.  Linux

        ls /dev/tty*

2.  OSX

        ls /dev/cu.*

3.  On Windows

    It will be listed under *Ports* in *Device Manager*


<a id="org92834f1"></a>

## Hardware

To get the correspending GPIO Pin numbers wiht the pins on on the board see `pins.jpg`
A schematic is provided in `hm2018badgechematic.pdf`


<a id="orgc3db99e"></a>

### Components

-   ESP-WROOM
-   CP2102 USB to UART
-   APA102 RGB LEDs (10) Controlled over SPI


<a id="org2dfafbd"></a>

## CTF

Only available if you've flashed your badge with the GitHub version in `firmware/firmware.bin`

To play:
```python
>>> from ctf import CTF
>>> CTF.challenges()
[0]
>>> CTF.view(0)
>>> CTF.submit<sub>solution</sub>(0, 'my answer')
```

- Challenges 10,11 & 12 are the flags.

- Solutions are always submitted as a string

<a id="org5b3a4c8"></a>

# Links

-   [Official Guide from Espressif](https://esp-idf.readthedocs.io/en/latest/get-started/establish-serial-connection.html)
-   [Expressif Site](https://www.espressif.com/)

