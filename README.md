<div align="center">
 <a href="https://www.reddit.com/r/Gentoo/comments/kiyemu/if_gentoo_logo_look_so_outdated_why_did_does_not/">
  <img src="https://i.imgur.com/CWmDvMA.png" width="70" alt="">
 </a>
 <br>
 <strong>merlin2gentk</strong>
 <p>Unofficial Gentoo Linux port for Xiaomi Redmi Note 9 (merlin) [aarch64]</p>
</div>

## 
## Images

<p align="center">
 <img src="https://github.com/user-attachments/assets/64cf705b-00d0-4f98-9eae-a5c32dcbf3f6" width="32%" alt="Gentoo Fastfetch 1" />
 <img src="https://github.com/user-attachments/assets/8093644a-5004-4806-9c5e-c50046d505d0" width="32%" alt="Gentoo Fastfetch 2" />
 <img src="https://github.com/user-attachments/assets/76eabae7-b735-4d43-a622-8d4f69f12844" width="32%" alt="Gentoo Fastfetch 3" />
</p>

## Installation

### Requirements:
* The phone itself with an unlocked bootloader.
* A computer (host machine) with a Linux system.
* Data USB cable (***D+*** and ***D-***).
* Before firmware, it is advisable to flash MIUI 13.x.x.x (R Vendor)

### Preparation:

## FOR FASTBOOT

1. Install ADB & Fastboot tools on the host machine:
```sh
pacman -S android-tools # arch/arch based
emerge dev-util/android-tools # gentoo
apt install adb fastboot # debian/debian based
# ... on other distributions try the packages `android-tools`, `adb`, `fastboot`
```

2. Check the versions:
```sh
fastboot --version
adb --version
```

3. Make sure your user is in the plugdev group:
```sh
groups
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If not, add them to this group and re-login to the system
```sh
usermod -aG plugdev $USER
```

4. Make sure the device is charged to at least 25%.

### Flashing:
Extract the firmware archive. Inside there should be the files: `boot.img`, `logo.bin`, `userdata.img`, `vbmeta.img` and the install.sh setup script.

1. Connect the device to the computer in fastboot mode. Check if the computer sees it using the command:
```sh
fastboot devices
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The output should look something like this:
```
1234567890ABCBD         fastboot
```
2. Run the installation script:
```sh
./install.sh
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If you get a Permission denied error, give the script execution permissions and run it again:
```sh
chmod +x install.sh
./install.sh
```
3. Follow the instructions in the script.

## FOR TWRP

1. Reboot into Recovery mode (TWRP)

2. Put the TWRP installer in your phone's internal memory/external storage

3. Install the firmware by following the instructions on the TWRP screen.

4. Reboot to Gentoo.

## Credits
* **Kernel and logo.bin:** kiberrrxx
* **Stage3:** gentoo
* **Guide and idea:** elaann

🐧🐧🐧🐧🐧🐧🐧🐧
