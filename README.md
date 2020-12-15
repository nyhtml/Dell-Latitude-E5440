# Dell Latitude E5440
The Dell Latitude E5440 Hackintosh Laptop Project

## Table of Contents

* [The Build](#the-build)
* [Prepare Install Media](#prepare-install-media)
* [Install bootloader](#install-bootloader)
  * [Configure Clover](#configure-clover)
  * [Configure OpenCore](#configure-opencore)
* [Gather Kexts](#gather-kexts)
* [BIOS Settings](#bios-settings-version-f12c)
* [Prepare for macOS Installation](#prepare-for-macos-installation)
* [Install macOS Mojave](#install-macos-mojave)
* [Post Installation](#post-installation)
  * [Make macOS Drive Bootable](#make-macos-drive-bootable)
  * [Enable the Discrete Graphics Card with Headless iGPU](#enable-the-discrete-graphics-card-with-headless-igpu)
  * [Map USB Ports](#map-usb-ports)
  * [Enable Bluetooth](#enable-bluetooth)
  * [Enable FileVault](#enable-filevault)
  * [Enable TRIM for Solid State Drives](#enable-trim-for-solid-state-drives)
  * [Fix CPU Type in About This Mac](#fix-cpu-type-in-about-this-mac)
  * [Fix Memory Tab in About This Mac](#fix-memory-tab-in-about-this-mac)
  * [Install Clover Theme](#install-clover-theme)
* [Install Windows 10](#install-windows-10)
* [Final BIOS Settings](#final-bios-settings)
* [Final Clover Configuration](#final-clover-configuration)
* [Benchmarks](#benchmarks)
* [Issues](#issues)
* [Upgrade Log](#upgrade-log)
* [References](#references)
* [Resources](#resources)

## The Build

★ Intel Core i5-4300u 1.9GHz Processor<br>
★ 16GB DDR3 RAM<br>
★ Samsung 1TB SSD (7mm and partitioned for Multi-booting)<br>
★ Dell 14-inch HD (1366×768) or 14-inch HD+ (1600×900) Anti-Glare LED-backlit display<br>
★ Dell 65W AC Adapter with 6-foot cord<br>
★ Dell 65W VV0NF Rechargeable Battery<br>
★ Dell Backlit Keyboard<br>

View the complete build on [Gixxer PC](https://www.dualbootpc.com): **https://gixxer.us/2T0stFx**

## Prepare Install Media

1. Download the [macOS Mojave installer](https://www.dualbootpc.com/software/system/macos/mojave/) (v10.14.6) from the Mac App Store
2. Open Terminal and format the target USB drive as with the following command:

    `diskutil partitionDisk /dev/{YOUR_DISK_ID} GPT JHFS+ "GixxerUSB" 100%`
    
3. [Create the bootable macOS installer](https://www.dualbootpc.com/guide/creating-a-usb-installer/): 

    `sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/GixxerUSB /Applications/Install\ macOS\ Mojave.app`

4. Once the program finishes, your [USB drive](https://www.dualbootpc.com/hardware/usb/) should now be called `Install macOS Mojave`
