Helios64 has one UEXT (Universal-Extension-Connector) header which exposes 3 serial communication interfaces into a single header:

* I2C
* SPI
* RS232 (UART)

![P2 Location](/helios64/img/uext/uext.jpg)

## Pinout Table

![P2 Pinout](/helios64/img/uext/uext_pinout.jpg)

Below is the full pinout of the UEXT header:

| PIN | Port | Remarks |
|-----|------|-------------|
| 1 | 3.3V | |
| 2 | GND | |
| 3 | TXD (UART) | |
| 4 | RXD (UART) | |
| 5 | SCL (I2C) | |
| 6 | SDA (I2C) | |
| 7 | MISO (SPI) | |
| 8 | MOSI (SPI) | |
| 9 | SCK (SPI) | |
|10 | SSEL (SPI) | |

!!! Warning
    Be careful with the header polarity when connecting.

## SPI & I2C

Refer to the respective pages directly:

- [SPI](/helios64/hardware/)
<<<<<<< HEAD
- [I2C](/helios64/I2C/)

## RS232 (UART)

The UART bus exposed on the UEXT header is the same than the RK3399 SoC serial console exposed on the USB Type-C. There is no dedicated UART bus on the UEXT connector. The intention is to allow user to connect to SoC serial console by another way than the USB-to-Serial bridge.

!!! Important
    If you connect some modules which might require dedicated serial UART line to the SoC, this module will not operate properly.
=======
- [I2C](/helios64/i2c/)

## RS232 (UART)

The UART exposed on the UEXT header is UART Controller 0 from the RK3399 SoC. The primary purpose of this UART is to provide serial communication between SoC and Device connected to the UEXT port.

!!! Note
    If you are looking for SoC serial console you should refer to [USB-C Console Mode](/helios64/usb/#serial-console).
>>>>>>> 7b10e9c9ea26cf4306a6515323a5af6affe76a39
