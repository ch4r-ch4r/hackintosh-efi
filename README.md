# Opencore [0.7.9](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.7.9) Hackintosh EFI
EFI for my Hackintosh v2 (upgraded from BigSur 11.4) build dual-booting macOS Monterey and Windows 10. This build is based on [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/). The version numbers reported in this specification were the releases available at the time of installation, and ***more than likely*** can be replaced with the latest versions. 

>Please note the bolded words above and be mindful if using different versions, since computers have a life of their own and may not work and/or like what you are doing to them.

## Disclaimer

This EFI is for  ***personal***  use. Please do some research if you have any intentions of replacing your EFI with mine. 

I am not responsible for any loss, including but not limited to Kernel Panic, device fail to boot, storage damage, data loss, rig spontaneously combusting, AI takeover, the Big Freeze and whatever else I can think of in the future.

## Screenshots
[![Screen-Shot-2022-04-13-at-9-44-40.png](https://i.postimg.cc/59Pf7Sc3/Screen-Shot-2022-04-13-at-9-44-40.png)](https://postimg.cc/dDyMDdVk)

## Hardware

|**Type**|**Specification**|
|----------------|---------|
|CPU|AMD Ryzen 5950X|
|Mobo|ASRock X570 Phantom Gaming-ITX/TB3|
|GPU|AMD Radeon RX 6800 XT Taichi X 16G OC|
|RAM|Kingston HyperX RAM Fury 64GB|
|Storage|960GB Kingston SSD A400|
|CPU|AMD Ryzen 5950X|


## Kexts

|**Kext**|**Version**|**Description**|
|---------|---------|---------|
|itlwm|[2.1.0](https://github.com/OpenIntelWireless/itlwm/releases/tag/v2.1.0) | Enables Wi-Fi.|
|AppleALC|[1.7.0](https://github.com/acidanthera/AppleALC/releases/tag/1.7.0)|Enables native macOS HD audio.|
|AppleMCEReporterDisabler|[x.x.x](https://github.com/acidanthera/bugtracker/files/3703498/AppleMCEReporterDisabler.kext.zip)|Solves the KP `Collection UUID matches with loaded KCs` on AMD CPU with SMBIOS `MacPro6,1`. [More info](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#extras).|
|BrcmPatchRAM -> BlueToolFixup |[2.6.1](https://github.com/acidanthera/BrcmPatchRAM/releases/tag/2.6.1)|Enables Intel card Bluetooth device in Monterey.|
|IntelBluetoothFirmware|[2.1.0](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases/tag/v2.1.0)|Uploads Intel Wireless Bluetooth Firmware to provide native Bluetooth in macOS. Replaced by `BlueToolFixup`.|
|IntelBluetoothInjector|[2.1.0](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases/tag/v2.1.0)|Disabled in `config.plist`. Leftover kext from previous Big Sur EFI. If enabled, will break Bluetooth in Monterey.|
|IntelMausi|[1.0.7](https://github.com/acidanthera/IntelMausi/releases/tag/1.0.7)|Intel onboard LAN driver for macOS.|
|Lilu|[1.6.0](https://github.com/acidanthera/Lilu/releases/tag/1.6.0)|Allows patching of the kernel, system extensions and Apps. Needed for `AppleALC`, `WhateverGreen`, `SMCProcessor`, `SMCSuperIO`, and `VirtualSMC` kexts.|
|SMCProcessor|[1.2.9](https://github.com/acidanthera/VirtualSMC/releases/tag/1.2.9)|Advanced Apple SMC emulator in the kernel.|
|SMCSuperIO|[1.2.9](https://github.com/acidanthera/VirtualSMC/releases/tag/1.2.9)|Advanced Apple SMC emulator in the kernel.|
|SmallTreeIntel82576|[1.3.0](https://github.com/khronokernel/SmallTree-I211-AT-patch/releases/tag/1.3.0)|Disabled in `config.plist`. Leftover kext from previous Big Sur EFI, needed for the I211 NIC included in the X570 mobo. Replaced by `IntelMausi`.|
|WhateverGreen|[1.5.8](https://github.com/acidanthera/WhateverGreen/releases/tag/1.5.8)|Provides patches to select GPUs on macOS. In this case, the RX 6800 XT.|
|VirtualSMC|[1.2.9](https://github.com/acidanthera/VirtualSMC/releases/tag/1.2.9)|Advanced Apple SMC emulator in the kernel.|

## Tools

|**Tool**|**Description**|
|---------|---------|
|[ProperTree](https://github.com/corpnewt/ProperTree)| Cross-platform GUI plist editor.|
|[MountEFI](https://github.com/corpnewt/MountEFI)| Mounts the EFI partition.|
|[GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)| Generates SMBIOS.|
|[OCAuxiliaryTools](https://github.com/ic005k/OCAuxiliaryTools/releases/tag/20220205)| Validates, detects, and fixes errors in the `config.plist` according to the selected OpenCore version.|

## What is not working?
* Continuity
	* Not working
		* AirDrop
		* Continuity Camera
		* Continuity Markup
		* Continuity Sketch
		* Sidecar
		* Universal Control
	* Not tested
		* Apple Pay
		* Auto Unlock
