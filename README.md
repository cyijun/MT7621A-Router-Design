# MT7621A-Router-Design
An MT7621A pure-ethernet router design which can form a ZigBee-To-Ethernet stack with my OpenZ3Gateway project. High forwarding performance and efficiency because of HWNAT. Security and privacy provided by Openwrt.

This repository includes Altium Designer files, PCB and schematic in PDF, DTS and Makefile, and bootloaders.

## Hardware
Specifications:

- SoC: MediaTek MT7621AT
- RAM: 256 MB (DDR3)
- Flash: 32 MB SPI NOR 44MHz
- Switch: 1 WAN, 4 LAN (Gigabit)
- LEDs: 1 WAN, 4 LAN (controlled by PHY)

UART Serial:

- UART1 as console : 57600 baud
- UART2
- UART3

Usage:

- Update firmware by internal GNUBEE uboot: [https://github.com/gnubee-git/GnuBee-MT7621-uboot](url)
- By HTTP: Initial uboot address is http://10.10.10.123, your address needs to be 10.10.10.0/24, and mask 255.255.255.0.
- By TFTP: Uboot is in client mode, the address of the firmware must be tftp://10.10.10.3/uboot.bin
- You can flash the bootloader in the serial console or the web interface. I suggest to flash the "breed" bootloader in [the bootloader folder](https://github.com/cyijun/MT7621A-Router-Design/tree/main/bootloader) for better compatibility with the latest Linux kernels.

User Manual of the module (Chinese & English):
[HLK-7621A用户手册V1.5.pdf](https://github.com/openwrt/openwrt/files/5884699/HLK-7621A.V1.5.pdf)

## Compiling Openwrt
- If [Openwrt](https://github.com/openwrt/openwrt), it has been merged to the master branch🎉
- If [LEDE By Lean](https://github.com/coolsnowwolf/lede), you can use the DTS and makefile [here](https://github.com/cyijun/MT7621A-Router-Design/tree/main/dts%26makefile).
