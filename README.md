# Efi-Hackintosh-SVS1512X9E-B-VAIO

### Before you give this EFI a try, make sure you read [this](#Generating-your-own-serial-and-Editing-ROM)!

This repo includes an OpenCore EFI for the Sony VAIO SVS1512X9E/SVS1512X9EB.

Testing on:

Model | Sony VAIO SVS1512X9E/SVS1512X9EB
------------- | ---------------
CPU | Intel Core i5-3210M
iGPU | Intel HD 4000
dGPU | Nvidia GT640 LE (disabled)
RAM | 6GB DDR3L
WiFi | Intel® Dual Band-Wireless-N 6235
macOS | Catalina

## What works?

- Audio
- Battery readout
- Boot
- Brightness Control
- Ethernet
- GPU acceleration
- Keyboard + Trackpad
- SD card reader
- WiFi
- Bluetooth
- Sleep
- USB
- Webcam
- Speaker

## What doesn't work?

- dGPU (macOS doesn't support Optimus)

## BIOS settings

- to be determined

## How to install

Download this repo and place the EFI folder into your internal drive's EFI partition... That's it.


## How to Install macOS Big Sur

There are two ways you can make a USB installer:

1. Have a working install of macOS, download the Installer from the App Store, then make a bootable Installer with `createinstallmedia` by using this command in Terminal `sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`

2. If you are using Windows, use [macrecovery.py](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html) from the offical OpenCore release package.

After you have created a bootable Installer, copy the EFI folder to the EFI partition of the installer drive and install as usual (GUID Partiton Map; APFS). After the installation, mount the EFI partition of the installed OS and copy the EFI folder to its partition.

## Generating your own serial and Editing ROM

Use GenSMBIOS (https://github.com/corpnewt/GenSMBIOS) to generate a serial for MacBookPro9,1 (if using a quad core CPU) or 9,2 (if using a dual core)

use PlistEdit Pro or any decent plist editor to manually enter the details in the following sections of the config (as shown in the video): (SystemSerialNumber, MLB, and UUID)

https://user-images.githubusercontent.com/59102649/116117179-3ea51200-a6bc-11eb-8a18-a03f7bb5bf1d.mp4

You should also put in your ethernet adapter's MAC address into the ROM section.

## Credits

* [acidanthera](https://github.com/acidanthera) (for OpenCore and the kexts)
* [dortania](https://dortania.github.io/OpenCore-Install-Guide/) (for their awesome guide)
* [OpenIntelWireless](https://github.com/OpenIntelWireless) (for Intel WiFi and Bluetooth)
* [iDrinkCoffee](https://github.com/huhugh221) (for creating the EFI)
* [0xFireWolf](https://github.com/0xFireWolf) (for RealtekCardReader)
* [TECHNIKVERBOT](https://github.com/TECHNIKVERBOT) (for fixing alot of the unneeded and missing stuff)

