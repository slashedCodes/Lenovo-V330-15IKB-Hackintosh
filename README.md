
# [Lenovo V330-15IKB](https://pcsupport.lenovo.com/ro/en/products/laptops-and-netbooks/lenovo-v-series-laptops/v330-15ikb) Hackintosh Notes

These are my notes installing [MacOS 13 Ventura](https://dortania.github.io/OpenCore-Install-Guide/extras/ventura.html) on this laptop using [OpenCore 1.0.0](https://github.com/acidanthera/OpenCorePkg/releases/tag/1.0.0) (latest version as of writing).

# Hardware

| PART | MODEL | NOTES |
|------|-------|-------|
| CPU | Intel i7-8550U | Supported up to current |
| IGPU | Intel UHD Graphics 620 | Supported up to current |
| DGPU | AMD Radeon 530 | Supported up to 12.6.x, you can disable it in BIOS if you want. |
| RAM | 8GB |
| STORAGE | 1TB 7200RPM HDD |
| WIFI CARD | Intel Corporation Dual Band Wireless-AC 3165 |
| NETWORK CONTROLLER | Realtek Semiconductor Co., Ltd. RTL8111  |
| TOUCHPAD | Synaptics I2C |
| KEYBOARD | PS/2 |
| AUDIO | CX29751 | Layout ID: 3 |

# Kexts used:

| KEXT | NOTES |
|------|-------|
| [Lilu](https://github.com/acidanthera/Lilu/releases/download/1.6.7/Lilu-1.6.7-RELEASE.zip) | Required |
| [VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases/download/1.3.2/VirtualSMC-1.3.2-RELEASE.zip) | Required |
| [WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases/download/1.6.6/WhateverGreen-1.6.6-RELEASE.zip) | Required |
| [AppleALC](https://github.com/acidanthera/AppleALC/releases/download/1.9.0/AppleALC-1.9.0-RELEASE.zip) | 
| [RealtekRTL8111](https://github.com/Mieze/RTL8111_driver_for_OS_X/releases/download/2.4.2/RealtekRTL8111-V2.4.2.zip) |
| [BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM/releases/download/2.6.8/BrcmPatchRAM-2.6.8-RELEASE.zip) | DO NOT USE ON BIG SUR AND BELOW!!! |
| [AirportITLWM](https://github.com/OpenIntelWireless/itlwm/releases) | Grab the corresponding kext for the corresponding MacOS version you want to install. I used Ventura. |
| [VoodooPS2](https://github.com/acidanthera/VoodooPS2/releases/download/2.3.5/VoodooPS2Controller-2.3.5-RELEASE.zip) | For the keyboard to work |
| [ECEnabler](https://github.com/1Revenger1/ECEnabler/releases/download/1.0.4/ECEnabler-1.0.4-RELEASE.zip) |
| [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys/releases/download/1.0.3/BrightnessKeys-1.0.3-RELEASE.zip) |

# SSDT's Used
Note: All of these were compiled using [SSDTTime](https://github.com/corpnewt/SSDTTime).

| SSDT | Notes |
|------|-------|
| [SSDT-PLUG](https://dortania.github.io/Getting-Started-With-ACPI/Universal/plug) |
| [SSDT-EC/USBX](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-fix) |
| [SSDT-PNLF](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/backlight) |
| [SSDT-XOSI/SSDT-GPI0](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/trackpad) |
| [SSDT-USBX](https://github.com/dortania/OpenCore-Post-Install/blob/master/extra-files/SSDT-USBX.aml) |

# Known Issues
 - Touchpad not working (I’m not going to bother. I tried to fix it using VoodooI2C and VoodooRMI but it just stops working after a while.)
 - Sleep (I just disabled it, I don’t need sleep)