
# Table of Contents

1.  [Quick start](#orgd5e671e)
    1.  [Connecting](#org8d98bd9)
        1.  [Identifying the device](#org09d42fd)
    2.  [Hardware](#org79daae7)
        1.  [Components](#orgfa9a8f7)
    3.  [CTF](#org51b38bb)
    4.  [Vagrant](#org68db7af)
        1.  [Requirements](#orgc5575cf)
        2.  [Using](#org8f78f1c)
2.  [Links](#orgb42ddeb)



<a id="orgd5e671e"></a>

# Quick start


<a id="org8d98bd9"></a>

## Connecting

In Putty, scroll down in the Category pane & fill in the
fields uner serial

-   **baud rate:** 115200
-   **data bits:** 8
-   **stop bits:** 1
-   **parity:** None

Hit Ctrl-C a few times and Enter to drop in to
a [micropython](https://micropython.org/) repl


<a id="org09d42fd"></a>

### Identifying the device

1.  Linux

        ls /dev/tty*

2.  OSX

        ls /dev/cu.*

3.  On Windows

    It will be listed under *Ports* in *Device Manager*


<a id="org79daae7"></a>

## Hardware

To get the correspending GPIO Pin numbers wiht the pins on on the board see `pins.jpg`
A schematic is provided in `hm2018badgechematic.pdf`


<a id="orgfa9a8f7"></a>

### Components

-   ESP-WROOM
-   CP2102 USB to UART
-   APA102 RGB LEDs (10) Controlled over SPI


<a id="org51b38bb"></a>

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

Challenges 10,11 & 12 are the flags.


<a id="org68db7af"></a>

## Vagrant


<a id="orgc5575cf"></a>

### Requirements

1.  Vagrant
2.  Virtual Box


<a id="org8f78f1c"></a>

### Using

-   `vagrant up` to start the VM
-   `vagrant ssh` to access a shell in the VM
-   `cd ~/micopython-esp32/ports/esp32` in the vm to 
    -   **`make`:** build firmware (will be in `build/` as `firmware.bin`)
    -   **`make erase`:** erase flash
    -   **`make deploy`:** to flash badge (make sure to pass through USB in VirtualBox)


<a id="orgb42ddeb"></a>

# Links

-   [Official Guide from Espressif](https://esp-idf.readthedocs.io/en/latest/get-started/establish-serial-connection.html)
-   [Expressif Site](https://www.espressif.com/)

