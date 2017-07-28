# GNU/Linux and Asus C201 Chromebook
Here you can find links and guides about installing and configuring GNU/Linux on the Asus C201 (C201P or C201PA) Chromebook (veryon speedy). I do not guarantee that any of them really works. I have noted down what I have tried and what it worked for me. The experience is absolutely personal and I do not (and cannot) claim that any image/distro does not work for another person.

I am trying to gather as much information as possible, so I will also post stuff not necessarily complete like forum posts, because they might be of use for other people.

**NOTE**: Don't forget that the wifi chipset (BRCM4354) on the C201 needs proprietary drivers, so it's certain that installing a _totally_ libre distribution will not get it working. Either you buy a wifi dongle which works with free drivers (such as the ones with the Atheros AR9271 chipset) or you use the proprietary drivers which can be found in the Chrome OS that the chromebook ships with.

## Libreboot
* [Info about Libreboot on Asus C201](https://libreboot.org/docs/hardware/c201.html) and [Installation Guide](https://libreboot.org/docs/install/c201.html) [it works!]

The installation was very straightforward. Disassembling the chromebook was a bit hard, but all in all everything went ok (thanks @paulkocialkowski!).

## Installing GNU/Linux distros on the Asus C201 Chromebook (tested and not)

### [Arch Linux ARM](https://archlinuxarm.org/platforms/armv7/rockchip/asus-chromebook-flip-c100p) [It works!]
This guide of installing [Arch Linux ARM](https://archlinuxarm.org/) is for another chromebook, C100P, but it's the only one that worked straight away without absolutely any problem. I installed X and xfce and, apart from some freezes, it just works.

### [Parabola](https://wiki.parabola.nu/index.php?title=Migration_from_the_GNU/Linux_distribution_of_Arch_ARM&redirect=no)
This is a guide to migrate the Arch Linux installation to a [Parabola](https://www.parabola.nu/) one. Parabola is one of the few [FSF endorsed](https://www.gnu.org/distros/free-distros.en.html) GNU/Linux distributions.

### [Devsus](https://github.com/dimkr/devsus)
Devsus is a project for installing Libre Devuan (a fork of Debian without the evil systemd) on the machine.

I generated the two images (2GB and 16GB one) with `devsus.sh` on a Debian Jessie machine, I `dd`-ed the 2GB on a SD card but I have not yet managed to boot it on the chromebook. I get a beep as if the SD is not bootable. You may find more on the specific issue [here](https://github.com/dimkr/devsus/issues/3).

## [Debian Stretch](https://github.com/atopuzov/c201)
Install Debian Stretch with the debian mainline kernel (not the Chrome OS one), more specifically the kernel `4.9.0-3-armmp-lpae`.

### [Debian Jessie](https://wiki.debian.org/InstallingDebianOn/Asus/C201)
I followed the guide with altering just the distro from Jessie to Stretch. Couldn't boot it. I eventually managed to make it work with the kernel from the Arch Linux ARM distro but haven't managed to get wifi to work too yet. [Here](http://forums.debian.net/viewtopic.php?f=30&t=124429) you can find a discussion related to installing Debian on the machine. [This blog](http://galexander.org/chromebook) of Greg Alexander and in particular [this post](http://galexander.org/chromebook/#17-04-23) are also very helpful.

### [Slackware](http://www.linuxquestions.org/questions/slackware-arm-108/installing-slackware-on-arm-chromebook-4175589620/)
That's just a very interesting forum topic on linuxquestions.org where some people claim that they managed to install [Slackware](http://www.slackware.com/) (version 14.1) on the machine. I haven't tried that yet.

### [Dragora](https://github.com/NuclearKev/dragora-c201)
From the `README.md` of the repo:
> This repo is a guide on how to install Dragora version 3 on the C201 Chromebook. Some of the things require some GNU/Linux know-how but I will attempt to make it easy to understand. This will not only help you install Dragora but should also help you boot your own modified version of Linux/Linux-libre or any ARM-supported GNU/Linux distributions on the C201.


### [Kali Linux](https://github.com/offensive-security/kali-arm-build-scripts)
I haven't tried it but the script provided for the C201 ([here](https://github.com/offensive-security/kali-arm-build-scripts/blob/master/chromebook-arm-veyron.sh)) is very helpful in understanding the whole procedure of making an SD work for the chromebook.
