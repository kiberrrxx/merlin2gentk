<div align="center">
 <a href="https://www.reddit.com/r/Gentoo/comments/kiyemu/if_gentoo_logo_look_so_outdated_why_did_does_not/">
  <img src="https://i.imgur.com/CWmDvMA.png" width="75" alt="Gentoo Logo">
 </a>
 <br>
 <strong>merlin2gentk</strong>
 <p>Unofficial Gentoo Linux port for Xiaomi Redmi Note 9 (merlin) [aarch64]</p>

</div>

## About

**merlin2gentk** is an unofficial port of [Gentoo Linux](https://gentoo.org/) for the **Redmi Note 9** (codename `merlin`). This project provides a barebones, highly optimized Gentoo environment.

<!-- why tf are you reading the raw file baka!! -->

No desktop environment is included by default, making it suitable as a pocket server or a base for linux experiments. The uncompressed rootfs size is around 4GB.

> [!WARNING]
> Flashing custom operating systems can brick your device. I am not responsible for dead SD cards, bricked phones, or lost data. Do this at your own risk!


## Screenshots

<p align="center">
 <img src="https://github.com/user-attachments/assets/64cf705b-00d0-4f98-9eae-a5c32dcbf3f6" width="32%" alt="Gentoo on Redmi Note 9 — Fastfetch system info" />
 <img src="https://github.com/user-attachments/assets/8093644a-5004-4806-9c5e-c50046d505d0" width="32%" alt="Gentoo on Redmi Note 9 — Terminal session" />
 <img src="https://github.com/user-attachments/assets/76eabae7-b735-4d43-a622-8d4f69f12844" width="32%" alt="Gentoo on Redmi Note 9 — System details" />
</p>

## Installation

### Requirements

- The phone itself with an **unlocked bootloader**.
- A computer (host machine) running **Linux**.
- A USB data cable (with ***D+*** and ***D−*** lines).
- It is recommended to update to Q Vendor before flashing.

### Download

Download the latest `fastboot` or `twrp` archive from the [**Releases**](https://github.com/kiberrrxx/merlin2gentk/releases/latest) page.

---

### Fastboot

#### 1. Install ADB & Fastboot

```sh
pacman -S android-tools # arch / arch-based
emerge dev-util/android-tools # gentoo
apt install adb fastboot # debian / ubuntu
# on other distributions look for `android-tools`, `adb`, or `fastboot`
```

#### 2.

```sh
fastboot --version
adb --version
```

#### 3. Check user groups

Make sure your user is in the `plugdev` group:

```sh
groups
```

If not, add yourself and re-login:

```sh
usermod -aG plugdev $USER
```

#### 4. Charge the device

Make sure the device is charged to **at least 25%**.

#### 5. Flash

Extract the firmware archive. It should contain: `boot.img`, `logo.bin`, `userdata.img`, `vbmeta.img`, and the `install.sh` script.

1. Connect the device in **fastboot mode** and verify it is detected:
   ```sh
   fastboot devices
   ```
   Expected output:
   ```
   1234567890ABCBD    fastboot
   ```

2. Run the installation script:
   ```sh
   ./install.sh
   ```
   If you get a *Permission denied* error:
   ```sh
   chmod +x install.sh
   ./install.sh
   ```

3. Follow the on-screen instructions.

---

### TWRP (Custom Recovery)

1. Reboot into **TWRP** (or any custom recovery).
2. Copy the installation package to internal storage or an SD card.
3. Flash the package following the recovery instructions.
4. Reboot into **Gentoo**.

## Credits

| Contribution | Author |
|---|---|
| Kernel & `logo.bin` | [kiberrrxx](https://github.com/kiberrrxx) |
| Stage3 base | [Gentoo](https://gentoo.org/) |
| Guide & idea | [xewvvi](https://github.com/xewvvi) |

🐧🐧🐧🐧🐧🐧🐧🐧