# RFStorm nRF24LU1+ Research Firmware modified for milighTX

Mousejack firmware reworked to speak MiLight via USB dongle.  Utilize timer interrupt and hardware retransmit capability.

------------------------------

Firmware and research tools for Nordic Semiconductor nRF24LU1+ based USB dongles and breakout boards.

## Requirements

- SDCC (minimum version 3.1.0)
- GNU Binutils
- Python
- PyUSB
- platformio

Install dependencies on Ubuntu:

```
sudo apt-get install sdcc binutils python python-pip
sudo pip install -U pip
sudo pip install -U -I pyusb
sudo pip install -U platformio
```

## Supported Hardware

The following hardware has been tested and is known to work.

- CrazyRadio PA USB dongle
- SparkFun nRF24LU1+ breakout board
- Logitech Unifying dongle (model C-U0007, Nordic Semiconductor based)

## Build the firmware

```
make
```

## Flash over USB

nRF24LU1+ chips come with a factory programmed bootloader occupying the topmost 2KB of flash memory. The CrazyRadio firmware and RFStorm research firmware support USB commands to enter the Nordic bootloader.

Dongles and breakout boards can be programmed over USB if they are running one of the following firmwares:

- Nordic Semiconductor Bootloader
- CrazyRadio Firmware
- RFStorm Research Firmware

To flash the firmware over USB:

```
sudo make install
```

## Flash a Logitech Unifying dongle

*The most common Unifying dongles are based on the nRF24LU1+, but some use chips from Texas Instruments.
This firmware is only supported on the nRF24LU1+ variants, which have a model number of C-U0007. The flashing
script will automatically detect which type of dongle is plugged in, and will only attempt to flash the nRF24LU1+ variants.*

To flash the firmware over USB onto a Logitech Unifying dongle:

```
sudo make logitech_install
```
