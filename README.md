# GNU/Linux and Asus C201 Chromebook
Here you can find links and guides about installing and configuring GNU/Linux on the Asus C201 (C201P or C201PA) Chromebook (veryon speedy). I do not guarantee that any of them really works. I have noted down what I have tried and what it worked for me. The experience is absolutely personal and I do not (and cannot) claim that any image/distro does not work for another person.

I am trying to gather as much information as possible, so I will also post stuff not necessarily complete like forum posts, because they might be of use for other people.

**NOTE**: Don't forget that the wifi chipset (BRCM4354) on the C201 needs proprietary drivers, so it's certain that installing a _totally_ libre distribution will not get it working. Either you buy a wifi dongle which works with free drivers (such as the ones with the Atheros AR9271 chipset) or you use the proprietary drivers which can be found in the Chrome OS that the chromebook ships with.

## Libreboot
* [Info about Libreboot on Asus C201](https://libreboot.org/docs/hardware/c201.html) and [Installation Guide](https://libreboot.org/docs/install/c201.html) [it works!]

The installation was very straightforward. Disassembling the chromebook was a bit hard, but all in all everything went ok (thanks @paulkocialkowski!).

## Installing GNU/Linux distros on the Asus C201 Chromebook (tested and not)

*Good news!* You can always boot the chromebook from a *USB*!
> For anybody else having this problem booting from USB on a C201, I was having the same problem. I tried installing debian jessie, debian stretch and arch and wasn't able to boot any of them. Then I realized that if I took out the USB drive and then put it back in and waited about 4-5 seconds, I could Ctrl-U and it would boot. (first I have to Ctrl-H to hold the libreboot screen.)

[link to original (Arch Linux ARM forum)](https://archlinuxarm.org/forum/viewtopic.php?f=60&t=12062&p=57254&sid=f4cfa1697408be24091cf8896c14e487#p57254)

### [Devsus](https://github.com/dimkr/devsus) [It works!] [compiled image](https://archive.org/details/devuan-jessie-c201-libre-2GB)
Devsus is a project for installing Libre Devuan (a fork of Debian without the evil systemd) on the machine.

To successfully compile the image, you need to run it on a Devuan machine. I failed to produce the image on my Debian Stretch. Nonetheless, I downloaded the image and dd-ed it to an SD card and this distro works far better than the Arch Linux one; I highly recommend it!

#### [Devuan (non-deblobbed kernel)](https://mirror.leaseweb.com/devuan/devuan_jessie/embedded/) [It works!]
[This image](https://mirror.leaseweb.com/devuan/devuan_jessie/embedded/devuan_jessie_1.0.0_armhf_chromeveyron.img.xz) ([with installation guide](https://mirror.leaseweb.com/devuan/devuan_jessie/embedded/README.txt)) is the Devuan distribution but with a non-free kernel, i.e. the internal Broadcom wifi chip works.

### [Arch Linux ARM](https://archlinuxarm.org/platforms/armv7/rockchip/asus-chromebook-flip-c100p) [It works!]
This guide of installing [Arch Linux ARM](https://archlinuxarm.org/) is for another chromebook, C100P, but it's the only one that worked straight away without absolutely any problem. **I installed X, lightdm and MATE and it just works**. I haven't yet tested the webcam and the HDMI but will do soon.

### [Parabola](https://wiki.parabola.nu/index.php?title=Migration_from_the_GNU/Linux_distribution_of_Arch_ARM&redirect=no)
This is a guide to migrate the Arch Linux installation to a [Parabola](https://www.parabola.nu/) one. Parabola is one of the few [FSF endorsed](https://www.gnu.org/distros/free-distros.en.html) GNU/Linux distributions.

### [Gentoo](https://wiki.gentoo.org/index.php?title=Asus_Chromebook_C201)
From the `Introduction` of the page:
> While there's a fair bit of documentation on how others have installed Devuan/Arch on this computer, there's very little information in the Gentoo realm on the Asus C201/C100P, other devices with an RK3288 SoC, or ARM Chromebooks in general. This is how I managed to get Gentoo working on the C201. I went the Libreboot route, but that's up to you. 

### [Debian Stretch](https://github.com/atopuzov/c201)
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

### [Fedora](https://fedoraproject.org/wiki/Architectures/ARM/Chromebook)
You can give it a try. There are instructions only for the ChromeOS kernel, the respective instructions for the mainline one are not yet present.

### [Ubuntu Mate](https://github.com/mibs510/ubuntu-mate-armhf)
> The Ubuntu MATE team have made an Ubuntu MATE 15.04 root file system image for ARMv7 devices. This root file system is intended for ARMv7 enthusiasts and board manufacturers who'd like to make an Ubuntu MATE image for their device.

(from the repository)

## Setting up Linux Distributions

### Alsa configuration
[Jan Prunk](http://janprunk.com/) has written a guide on how to setup ALSA on a C201 running Debian (originally Jessie and then update to Stretch) in this [blog post](http://blog.janprunk.com/?p=1038). Try also [this link](https://notabug.org/dimkr/devsus/issues/14#issuecomment-6543), if the previous is unavailable.
