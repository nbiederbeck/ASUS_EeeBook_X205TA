# ASUS_EeeBook_X205TA
Compilation of scripts and files and links to install linux on ASUS EeeBook X205TA.

## Installation Guide
The ASUS EeeBook X205TA is a mixed mode EFI system (64-bit CPU with 32-bit EFI).
Therefore not every Linux distro will boot without problems:

| Tried  | Booting? |
| ------ | --------:|
| Debian | yes      |
| Fedora | yes      |
| Arch   | no       |
| Ubuntu | no       |

Some components dont work out of the box and need a fix, others don't work at all.

| Component             | Status      |
| --------------------- | -----------:|
| Audio                 | Not Working |
| Battery               |     Working |
| Bluetooth             |     Working |
| External Screen       |     Working |
| Hibernation           | Not Working |
| (Multitouch) Touchpad |     Working |
| MicroSD Card Reader   |     Working |
| Sleep/Suspend         | Not Working |
| Wi-Fi                 |         Fix |

### Audio
Audio is currently not supported.

### Hibernation
Hibernation is currently not supported.

### Sleep/Suspend
Sleep/Suspend is currently not supported.

### Wi-Fi
The Wi-Fi card needs a driver and firmware. I will provide the steps here,
for more information visit the [Debian Wiki][installingdebianon].
In the directory [files](files) are two files.
Now you have two options:
1. During install when asked for drivers on USB stick, press `Alt-F2` to change to
virtual terminal.
Now mount a second USB stick and copy the firmware.
2. When installed, copy the firmware.
The firmware may only be loaded after a reboot.

```bash
mkdir -p /lib/firmware/brcm/
cp brcmfmac43340-sdio.txt /lib/firmware/brcm/
cp brcmfmac43340-sdio.bin /lib/firmware/brcm/
```

## Links
The Debian wiki describes perfectly well what steps one has to do to install Debian 9 on the EeeBook:
- [InstallingDebianOn/Asus/X205TA][installingdebianon]


[installingdebianon]: https://wiki.debian.org/InstallingDebianOn/Asus/X205TA
