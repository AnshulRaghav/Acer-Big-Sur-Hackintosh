# Big Sur Acer-Aspire-5-A515-51G-Hackintosh
Apple's Mac OS Big Sur in Acer laptop using OpenCore.

![Screenshot](https://github.com/AnshulRaghav/Big-Sur-Hackintosh/blob/master/Screen%20Shot%202020-12-31%20at%2006.49.42.png)

I followed [TechNolli's](https://www.youtube.com/watch?v=jqg7MX3FS7M) video tutorial and [OpenCore](https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html) guide to create my hackintosh machine.I highly recommend to follow these two as they will give you a brief idea about Hackintosh and you can then create your Hackintosh machine according to your system specifications.
<br> **Note: These two methods(Technolli and Opencore guide) use recovery pkg to create bootable USB which means you will be required to access internet during MacOS install.**

<br>

## What's Working
#### Audio
#### Headphone(To fix cracking sound try [SiddheshNan](https://github.com/SiddheshNan/Acer-A515-51G-Hackintosh fix)
#### Audio Fn keys
#### Internet(using HoRNDis kext)
#### TouchPad
#### Keyboard
#### Battery Read In/Out
#### Internal Graphics (Intel HD 620)
#### Bluetooth
#### Usb 3.0/USB 2.0 + Type C

<br>

## What's not working
#### Nvidia graphics(Geforce MX130)(not supported on macOS)

<br>

## Creating Bootable USB
If you don't want to use recovery method to create bootable USB and want full bootable MacOS USB then you'll be required to access the MacOS machine. If you don't have access to an actual MacOS machine(which I guess is true for most cases :) ) then you can create a virtual machine using softwares like [VirtualBox](https://www.virtualbox.org/) or VMWare.I used VBox.You can follow up [this](https://www.youtube.com/watch?v=_faDsGKkvCs) tutorial to create the macOS virtual machine.
<br>
* After installing virtual machine download the Big Sur OS from [Apple Developer site](https://apps.apple.com/in/app/macos-big-sur/id1526878132?mt=12) or simply upgrade your macOS using **System Preferences** and it'll download the Big Sur Installer into **Applications**.Don't install it in your VM.
* Now plug in your USB and go to **Disk Utility**,select your USB and Erase using ***name:USB,format:macOS extended journal and scheme:GUID partition map.*** 
* After that open terminal and paste following command: `sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/USB`.Check Technolli video for more detailed instructions.
* After you're done with creating bootable USB, copy the EFI folder and paste it into the root of your USB and you're done.

<br>

## Installation
* After creating bootable USB, reboot your machine and got to your BIOS, set settings same as [SiddheshNan](https://github.com/SiddheshNan/Acer-A515-51G-Hackintosh) and plus also enable boot menu for F12 key(relevant to acer aspire 5 A515-51G model).<br>
I'll also recommend to place your USB at the top in your boot priority order as it'll save you from the hassle of pressing F12 key on every reboot and select your stick since your laptop will reboot several times during the installation process. <br>
* Save changes and press F12 to bring up the boot menu(not required if you've placed USB at the top in boot priority).<br>
* Select your USB stick and allow it to perform it's magic for you until you see the Big Sur installer.My laptop took 40 minutes before I finally saw the Big Sur installer. <br>
<br>
If you find that your installation is stuck at some point you could always refer to [OpenCore troubleshooting](https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/troubleshooting.html) guide.

## Post Installation
#### Internet Fix
If you are like me who use mobile internet on laptop then you'll be required to perform USB tethering using HoRNDIS.kext since Qualcom Atheros QCA9377 Wifi is not supported on macOS Big Sur.<br>
* Install HoRNDis.pkg from the repo to your hackintosh machine.It'll show that the installation failed(Don't worry it'll).<br>
* Reboot and connect your mobile device to your laptop using USB cable and enable USB tethering on your mobile settings(Settings > Tethering & Portable Hotspot > USB Tethering) and you'll be good to go.

# CREDITS
[Technolli](https://www.youtube.com/channel/UCO4u3XLKPLDLWkPnpfD2Vlg)
[OpenCore](https://dortania.github.io)
[Special credits to SiddheshNan(you made it a perfect Hackintosh machine)](https://github.com/SiddheshNan)

## A big shoutout to all the geeks out there.Without you people, this won't be possible.If I kept googling stuff and it kept on working,it was because of you.
