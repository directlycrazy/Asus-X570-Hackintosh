# Hackintosh Guide for **MSI X570 A-Pro Motherboard**

**This guide it will be updated to OpenCore 0.7.1 ASAP.**

## Specs:
| Component | Brand | Price |
|:--- |:---:|:--- |
| Motherboard:  | Msi A-Pro X570 | 169.99$ |
| CPU: | AMD Ryzen 9 3900X | 484.00$ |
| GPU: | Msi Mech OC 5700XT 8GB | At that time just 390$, now there is any GPU online... |
| Memory: | HyperX 3200MHz 8GB x2 | 129$ |
| Power Supply: | NZXT 650W | 139$ |
| Case: | NZXT 510 | 84,99$ |

![MSI X570 A-PRO Layout](/Images/Guide/layout2.png)
These are all the external ports of the Motherboard. (**They all work**)

### Working
- [x] **Tested with macOS Big Sur 11.1 and 11.4**
- [x] **Bluetooth:** ([With a USB adapter](amazon.com))
- [x] **USB:** All internal and external ports (Thanks to SSDT-EC-USBX-LAPTOP.aml)
- [x] **Ethernet:** Realtek RTL8111 (Thanks to RealtekRTL8111.kext)
- [x] **HDMI, DisplayPort:** Works perfect. 
- [x] **Shutdown/Restart/Sleep/Wake:** Yes

### Not working
- Continuity Features
- Some software due the limitations of an AMD CPU.


```bash
```

# INSTALLATION GUIDE

---

## Making the Booteable USB

### From macOS:
[**Link to Apple's Guide**](https://support.apple.com/en-us/HT201372)

**Download installers:** [Monterrey Beta 2](http://swcdn.apple.com/content/downloads/54/23/071-59953-A_U9D4NB05NR/nqzt71pnylsuux326a4vqexb33oz0auhas/InstallAssistant.pkg)(Execute de .pkg to extract the installer) - [Big Sur](https://itunes.apple.com/us/app/macos-big-sur/id1526878132) - [Catalina](https://itunes.apple.com/us/app/macos-catalina/id1466841314) - [Mojave](https://itunes.apple.com/us/app/macos-mojave/id1398502828) - [High Sierra](https://itunes.apple.com/us/app/macos-high-sierra/id1246284741)

1. Connect a >=16 GB pendrive.
2. Open *Disk Utility* and Erase the USB with the name: *MyVolume*.
3. Open *Terminal* and use the proper commands for your macOS installer:
- Monterrey: `sudo /Applications/Install\ macOS\ 12\ Beta.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Big Sur: `sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Catalina: `sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Mojave: `sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- High Sierra: `sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`

![Terminal](Images/Guide/BootableUSB.png)

### From Windows:

[**Link to Dortania's Guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html)

### From Linux:

[**Link to Dortania's Guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/linux-install.html)


---

# BIOS Settings:
- Make Sure you have [Latest BIOS](https://www.msi.com/Motherboard/support/X570-A-PRO#down-bios)
- After Updating the BIOS, you need some configuration to working.

---

# OpenCore Configuration

## [Here it's my config.plist and the explanation:](/config.plist.md)
#### [ACPI](/config.plist.md#acpi)
#### [Booter](/config.plist.md#booter)
#### [DeviceProperties](/config.plist.md#deviceproperties)
#### [Kernel](/config.plist.md#kernel)
#### [Misc](/config.plist.md#misc)
#### [NVRAM](/config.plist.md#nvram)
#### [PlatformInfo](/config.plist.md#platforminfo)
#### [UEFI](/config.plist.md#uefi)

---

# Post Install (Important!!)
Open Terminal.app and run those commands:
```bash
sudo rm /Library/Preferences/SystemConfiguration/NetworkInterfaces.plist
sudo rm /Library/Preferences/SystemConfiguration/preferences.plist
```
---

# BenchMarks:
#### Cinebench R23:
![Cinebench R23](/Images/Benchmarks/Cinebench_R23.png)

#### GeekBench 5:
![GeekBench 5_CPU Score](/Images/Benchmarks/GeekBench5_CPU.png)
![GeekBench 5_GPU Score](/Images/Benchmarks/GeekBench5_GPU.png)

---

# Credits

[Apple](https://apple.com) (macOS)

[OpenCore Team](https://github.com/acidanthera/OpenCorePkg) (Bootloader)

[Dortania](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/amd.html#starting-point) (Guide)
