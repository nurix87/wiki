# Helios64 Overview

## Block Diagram

### Helios64 Board
![!Block Diagram](/helios64/img/hardware/helios64_block_diagram.png)

### RK3399 System-On-Chip
![!Block Diagram](/helios64/img/hardware/rk3399_block_diagram.png)

This block diagram is cited from the RK3399 website documentation. [1](http://opensource.rock-chips.com/wiki_File:RK3399_Block_Diagram.png)

## Connector / Interface List

![!Board Legend](/helios64/img/hardware/helios64_board_labeled.jpg)

| Name | Peripheral Type | Connector Type | Details |
|-----|---------------|--------------|-------|
| J1 | [USB 3.0](/helios64/usb/) | USB 3.0 Type-A | USB 3.0 Port 3  |
| J2 | [M.2](/helios64/m2/) | M.2 Key-B | M.2 Slot for SATA SSD<br> or USB 2.0 Device |
| J3 | [SATA](/helios64/sata/) | SATA 3.0 | Port 0 (SATA1) |
| J4 | [SATA](/helios64/sata/) | SATA 3.0 | Port 1 (SATA2) |
| J5 | [SATA](/helios64/sata/) | SATA 3.0 | Port 2 (SATA3) |
| J6 | [SATA](/helios64/sata/) | SATA 3.0 | Port 3 (SATA4) |
<<<<<<< HEAD
| J8 | [SATA](/helios64/sata/) | SATA 3.0 | Port 4 (SATA5) |
| J7 | [HDD Power](/helios64/sata/#hdd-power) | 8 Pin Mini-Fit Jr | HDD Power 5V + 12V<br>(supports 5x HDD) |
=======
| J7 | [SATA](/helios64/sata/) | SATA 3.0 | Port 4 (SATA5) |
| J8 | [HDD Power](/helios64/sata/#hdd-power) | 8 Pin Mini-Fit Jr | HDD Power 5V + 12V<br>(supports 5x HDD) |
>>>>>>> 7b10e9c9ea26cf4306a6515323a5af6affe76a39
| J9 | [UPS Battery](/helios64/ups/) | 6 Pin Mini-Fit Jr | UPS Battery Power |
| J10 | ATX PSU | 4 Pin Mini-Fit Jr | DC input 12V |
| J11 | [LAN1](/helios64/ethernet/) | RJ45 | Gigabit Ethernet |
| J12 | [LAN2](/helios64/ethernet/) | RJ45 | 2.5 Gigabit Ethernet |
| J13 | [USB 3.0 (x2)](/helios64/usb/) | Dual USB 3.0 Type-A | USB 3.0 Port 1 and 2  |
| J14 | microSD | Push-Push card connector | Support SDHC and SDXC |
| J15| [USB Type-C](/helios64/usb/#type-c-functionality-on-helios64) | USB Type-C Connector | Supports following:<br>- DisplayPort Mode<br>- DAS Mode<br>- Host Mode<br>- Serial Console |
| J16| AC Adapter | Kycon 4-Pin Mini-DIN | DC input 12V |
| P1 | [I2C](/helios64/i2c/) | 4x1 Pin Header | I2C Bus |
| P2 | [UEXT](/helios64/uext/) | 2x5 Pin Header | Universal EXTension<br>(I2C, SPI and UART)|
| P3 | [Front Panel](/helios64/front-panel/) | 12x2 Pin Header | Front Panel Extension |
| P4 | Buzzer | 2x1 Pin Header | Buzzer Alarm Speaker |
| P5 | [GPIO](/helios64/gpio/) | 7x2 Pin Header | User Configurable GPIO |
| P6 | [PWM Fan](/helios64/pwm/) | 4x1 Pin Header | Fan 1 with PWM support |
| P7 | [PWM Fan](/helios64/pwm/) | 4x1 Pin Header | Fan 2 with PWM support |
| P8 | [SATA Ctrl. Programming](/helios64/jumper/#sata-controller-flash-p8) | 2x1 Pin Header | SATA Controller Flash Enable |
| P9 | [eFuse Programming](/helios64/jumper/#efuse-power-enable-p9) | 2x1 Pin Header | eFuse Power Supply Enable |
| P10 | [eMMC Flash Disable](/helios64/jumper/#boot-mode-p10-p11) | 2x1 Pin Header | Disable eMMC |
| P11 | [SPI Flash Disable](/helios64/jumper/#boot-mode-p10-p11) | 2x1 Pin Header | Disable SPI Flash |
| P12 | Battery Configuration | 2x1 Pin Header | *unpopulated*  |
| P13 | [USB Console/Recovery Mode](/helios64/jumper/#usb-consolerecovery-mode-p13) | 2x1 Pin Male Header | USB-C HS Mode |
<<<<<<< HEAD
| P14 | [ATX Priority Jumper](/helios64/jumper/#dc-in-priority-p14-p15) | 2x1 Pin Male Header | ATX Supply Priority |
| P15 | [ACDC Priority Jumper](/helios64/jumper/#dc-in-priority-p14-p15) | 2x1 Pin Male Header | AC Adapter Supply Priority |
=======
| P14 | [UART Debug](/helios64/usb/#serial-console) | 2x1 Pin Male Header | UART 2 Debug |
| P15 | [ATX Priority Jumper](/helios64/jumper/#dc-in-priority-p15) | 2x1 Pin Male Header | ATX Supply Priority |
>>>>>>> 7b10e9c9ea26cf4306a6515323a5af6affe76a39
| SW1 | [Power Button](/helios64/button/#power-button) | Push Button | Power Button |
| SW2 | [Recovery Button](/helios64/button/#recovery-button) | Push Button | Recovery Button |
| SW3 | [Reset Button](/helios64/button/#reset-button) | Push Button | Reset Button |

<<<<<<< HEAD
## Power Management

Coming Soon.
=======
## Power Consumption

**Board only**

| State | DC measured<br>power consumption | AC calculated<br>power consumption | Remarks |
|---|---|---|---|
| Idle | 5.4 W | 6.2 W | |
| CPU Load | 10.8 W | 12.4 W | stress-ng (all cores) |

**Full Kit (with 5x HDDs)**

| State | DC measured<br>power consumption | AC calculated<br>power consumption | Remarks |
|---|---|---|---|
| Idle | 25.2 W | 29 W | |
| Suspend | 8.4 W | 9.7 W | Suspend-to-RAM, HDD in Standby mode |
| CPU Load | 31.2 W | 35.9 W | stress-ng (all cores) |
| HDD Read | 36 W | 41.4 W | dd read (no caching) from RAID6 array|
| HDD Write | 34.8 W | 40 W | dd write (no caching) to RAID6 array |
| Network Access | 33.6 W | 38.6 W | HTTP download from RAID6 array |
| Stress Test | 40.8 W | 47 W | stress-ng (all cores) + fio (all disks) + iperf |

!!! note
    Measures were done using a Current Clamp Meter on the Helios64 12V DC input. AC Power consumption is calculated based on a AC/DC conversion efficiency of 85%.

    * Meter tool : Extech 380942 - 30A True RMS AC/DC Mini Clamp
    * AC/DC Adapter : 12V 10A (efficiency : 85%)
    * HDD: 5x Toshiba P300 1TB (HDWD110) configured as RAID6
    * Network : Connected at 2500Mb/s
    * Fan : Medium speed (PWM 100)
    * Battery : Charge status 100%
    * OS: Armbian Ubuntu (Bionic) Linux 4.4.213-rk3399

    **Power consumption depends a lot on the HDDs brand and model used.**


## HDD Recommendation

We recommend HDD which are designed for NAS (Network Attached Storage). Those NAS HDD are specially conceived for reliable 24/7 operation and offers lower power consumption and dissipation, less vibration and noise, and finally better warranty. We recommend the following brands / families :

* **Western Digital** : WD Red NAS
* **Seagate** : IronWolf NAS
* **HGST** : Deskstar NAS
* **Toshiba** : NAS N300
>>>>>>> 7b10e9c9ea26cf4306a6515323a5af6affe76a39
