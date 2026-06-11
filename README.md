# merlin2gentk (Gentoo Linux for Redmi Note 9)

A lightweight, fully functional Gentoo Linux custom ROM for the Xiaomi Redmi Note 9 (merlin).

⚠️ **DISCLAIMER:** Flashing custom operating systems can brick your device. I am not responsible for dead SD cards, bricked phones, or lost data. Do this at your own risk!

## Overview
This project brings a barebone, highly optimized Gentoo Linux environment to the MTK-based Redmi Note 9. The graphical user interface (KDE/X11) has been intentionally stripped out to save resources, making it an ideal pocket server or a base for embedded Linux experiments. The uncompressed rootfs is around 4GB.

## Features
- **Linux Kernel 4.14** booting smoothly via OpenRC.
- **Working Display:** framebuffer is set
- **Working Wi-Fi:** Automatically initialized at boot via a modified `wmt-pyloader` script.
- **Working USB Networking (RNDIS):** Plug into your PC and connect instantly.
- **SSH Ready:** Pre-configured and ready to accept connections out of the box.
- **Custom Boot Logo:** Completely custom boot logo.

## Installation

## Requirements
- **Engineering Firmware:** You MUST flash this firmware before installing the ROM to ensure hardware compatibility.
- [Download Engineering FW](https://drive.google.com/file/d/1qVk-ygzGT0aP_hCX9CjnQjlwn6EoJ8kX/view?pli=1)

You can install this ROM using either Fastboot or TWRP. Download the respective archive from the [Releases](../../releases) tab.

### Method 1: Fastboot (For PC)
1. Extract `merlin2gentk-fastboot.zip` on your computer.
2. Reboot your phone into **Fastboot Mode** (Volume Down + Power).
3. Connect the phone to your PC via a USB cable.
4. Run the installer script:
  - On Linux: `bash install.sh`
  - *(Or manually flash the provided `.img` and `.bin` files).*
5. Wait for the userdata partition to be flashed (it takes a few minutes).
6. Reboot and enjoy.

### Method 2: TWRP Recovery (For SD Card)
1. Copy `merlin2gentk-twrp.zip` to your SD card or USB OTG.
2. Reboot your phone into TWRP recovery.
3. Tap **Install** and select the ZIP file.
4. Follow the interactive on-screen instructions (you will need to confirm the userdata wipe by pressing the **Volume Up** button).
5. Reboot your device.

## Credits
- Project maintained by **kiberrrxx & elaann.
- Thanks to Jbub5 for the kernel source code.
