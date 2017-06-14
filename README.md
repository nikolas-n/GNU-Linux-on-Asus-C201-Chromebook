# GNU/Linux and Asus C201 Chromebook
Here you canf find links and guides to install and configure GNU/Linux on Asus C201(P/PA) Chromebook. I do not guarantee that any of them really works. I have noted down what I have tried and what it worked for me. The experience is absolutely personal and I do not (and cannot) claim that any image/distro does not work for another person.

## Libreboot
* [Info about Libreboot on Asus C201](https://libreboot.org/docs/hardware/c201.html) and [Installation Guide](https://libreboot.org/docs/install/c201.html) [it works!]

The installation was very straightforward. Disassembling the chromebook was a bit hard, but all in all everything went ok (thanks @paulkocialkowski!).

## Installing GNU/Linux distros on the Asus C201 Chromebook (tested and not)

### [ArchLinux ARM](https://archlinuxarm.org/platforms/armv7/rockchip/asus-chromebook-flip-c100p) [It works!]
This guide is for another chromebook, C100P, but it's the only one that worked straight away without absolutely any problem. I installed X and xfce and, apart from some freezes, it just works.

### [Devsus](https://github.com/dimkr/devsus) Libre Devuan (a fork of Debian without the evil systemd)
I generated the two images (2GB and 16GB one) with `devsus.sh` on a Debian Jessie machine, I `dd`-ed the 2GB on a SD card but I have not yet managed to boot it on the chromebook. I get a beep as if there the SD is not bootable. These days though I'm trying to make it work (see [here](https://github.com/dimkr/devsus/issues/3))

### [Debian Jessie](https://wiki.debian.org/InstallingDebianOn/Asus/C201)
I followed the guide with altering just the distro from Jessie to Stretch. Couldn't boot it. I managed to with the kernel from the Arch Linux ARM distro but haven't managed to get wifi to work yet.
