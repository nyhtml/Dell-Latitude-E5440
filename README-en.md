# Dell Latitude E5440
The Dell Latitude E5440 Hackintosh Laptop Project

## Table of Contents

* [The Build](#the-build)
* [Prepare Install Media](#prepare-install-media)
* [Install a Bootloader](#install-a-bootloader)
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

The complete [specs](https://www.dualbootpc.com/systems/laptop/e5440/specs/) used for the build are listed here: `http://gixxer.us/2T0stFx`

## Prepare Install Media

1. Download the [macOS Mojave installer](https://www.dualbootpc.com/software/system/macos/mojave/) (v10.14.6) from the Mac App Store
2. Open Terminal and format the target USB drive as with the following command:

    `diskutil partitionDisk /dev/{YOUR_DISK_ID} GPT JHFS+ "MojaveUSB" 100%`
    
3. [Create the bootable macOS installer](https://www.dualbootpc.com/guide/creating-a-usb-installer/): 

    `sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/MojaveUSB /Applications/Install\ macOS\ Mojave.app`

4. Once the program finishes, your [USB drive](https://www.dualbootpc.com/hardware/usb/) should now be called the following:

    `Install macOS Mojave`
    
## Install a Bootloader

#### Configure Clover

* Download [Clover Install Package](https://github.com/Dids/clover-builder/releases) (v2.5k_r5097) and [Clover Configurator Global Edition](http://mackie100projects.altervista.org/download-clover-configurator/) (v5.7.0.0)
* Install Clover to the USB device and customize with the following options:
  * Clover for UEFI booting only
  * Install Clover in the ESP
  * UEFI Drivers
    * Recommended drivers
      * ApfsDriverLoader
      * HFSPlus
    * Memory fix drivers
      * OsxAptioFix3Drv
    * Additional drivers
      * EmuVariableUefi

#### Configure OpenCore

* Download OpenCore
* Install Clover to the USB device and customize with the following options:
  * Step 1
    * Action 1
  * Step 2
    * Action 1
    * Action 2 
  * Step 3
    * Action 1
    * Action 2 
    * Action 3
