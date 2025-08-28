# EFI for Lenovo IdeaPad S145 (Intel® Core i7-1065G7)

![macOS Sequoia](https://olhardigital.com.br/wp-content/uploads/2024/06/macos_sequoia-1024x576.png)

> **Turn your Lenovo IdeaPad S145 into a perfect Hackintosh!**

---

## 🇧🇷 [Leia este README em Português do Brasil](README-BR.md)

---

## About This Project

This repository provides a complete EFI folder for running macOS on the Lenovo IdeaPad S145 with Intel® Core i7-1065G7 (10th Gen). Here you will find all the necessary ACPI patches, kexts, and configuration tips to achieve a stable and fully functional Hackintosh experience.

---

## Laptop Factory Specs

| Component  | Model |
|------------|-------|
| Platform   | Lenovo IdeaPad S145 (Intel® 10th Gen) |
| Processor  | Core i7-1065G7 (Intel® 10th Gen) |
| Graphics   | Intel® Iris Plus (iGPU) |
| Audio      | Realtek ALC230 |
| Storage    | 240GB NVMe SSD (Original) |
| Memory     | 1x4GB 2667MHz DDR4 |
| BIOS       | Factory Default |

---

## Laptop Upgrades

| Component           | Model                                   |
|---------------------|-----------------------------------------|
| Main SSD            | 1000GB NVMe (Replaced the original 240GB) |
| Additional Storage  | 500GB SATA HDD (Time Machine)           |
| Memory              | 1x16GB 2667MHz DDR4 (Total: 20GB)       |
| Wi-Fi & Bluetooth   | BCM94360CS2 (Upgraded Wi-Fi card)       |
| BIOS                | Version DKCN53WW (Updated)              |

---

## EFI Overview

| Option                | Information                                 |
|-----------------------|---------------------------------------------|
| SMBIOS                | MacBookPro16,2                              |
| macOS                 | See Releases and their descriptions         |
| macOS Install Images  | Downloaded from Apple Store via gibMacOS    |
| OpenCore              | Version 0.7.6 to 1.0.6                      |

---

## BIOS Settings

To ensure proper macOS functionality, it is crucial to configure your BIOS (UEFI firmware) with the following options. Restart your laptop and press `F2` (or the respective BIOS key) repeatedly to enter settings:

### Security
*   **Secure Boot**: `Disabled`
*   **Intel SGX**: `Disabled`
*   **Intel VT-d**: `Enabled` – *If available, essential for virtualization and DMA mapping.*

### Boot
*   **Fast Boot**: `Disabled`
*   **CSM Support**: `Disabled` – *Recommended for pure UEFI.*
*   **Boot Mode**: `UEFI Only`

### Configuration / Advanced
*   **Intel Virtualization Technology (VT-x)**: `Enabled`
*   **DVMT Pre-Allocated Memory**: `64MB` or `128MB` (if available, choose the highest value for iGPU)
*   **XHCI Hand-off**: `Enabled` – *If available, required for USB support.*
*   **SATA Mode**: `AHCI` (Essential, never `RAID` or `Intel RST`)

*Note: BIOS options may slightly vary depending on firmware version. Make sure to save changes before exiting.*

---

## Benchmarks

Here are the Geekbench 6 benchmark results for this Hackintosh:

- **CPU**: [https://browser.geekbench.com/v6/cpu/13545229](https://browser.geekbench.com/v6/cpu/13545229)
- **iGPU Metal**: [https://browser.geekbench.com/v6/compute/4698032](https://browser.geekbench.com/v6/compute/4698032)
- **iGPU OpenCL**: [https://browser.geekbench.com/v6/compute/4698039](https://browser.geekbench.com/v6/compute/4698039)

---

## ACPI Patches (EFI/OC/ACPI)

All ACPI files below are custom SSDTs or patches to enable or fix specific hardware features for macOS compatibility:

| File                      | Description                                   |
|---------------------------|-----------------------------------------------|
| DMAR.aml                  | Fixes for DMA Remapping (VT-d)                |
| SSDT-ALS0.aml             | Ambient Light Sensor support                  |
| SSDT-Audio.aml            | Audio device enumeration and fixes            |
| SSDT-EC.aml               | Embedded Controller device for battery and sensors – *Crucial for battery and temperature monitoring on your laptop.* |
| SSDT-GPI0.aml             | General Purpose I/O support                   |
| SSDT-HPET.aml             | High Precision Event Timer patch              |
| SSDT-MEM2.aml             | Memory mapping and related fixes              |
| SSDT-PLUG.aml             | CPU power management (PluginType)             |
| SSDT-PMC.aml              | Intel Power Management Controller patch       |
| SSDT-PNLF.aml             | Enables backlight control (Panel device) – *Essential for native brightness control on the IdeaPad S145.* |
| SSDT-RHUB-Reset.aml       | USB controller reset fixes                    |
| SSDT-RTCAWAC.aml          | Real Time Clock patch                         |
| SSDT-SBUS-MCHC.aml        | SMBus and Memory Controller support           |
| SSDT-TPD0.aml             | Touchpad device patch                         |
| SSDT-USBX.aml             | USB power properties                          |
| SSDT-XOSI.aml             | OSI patch for macOS compatibility             |
| SSDT-XSPI.aml             | SPI bus support                               |

---

## Kexts Used (EFI/OC/Kexts)

All kexts below are used to enable or improve hardware compatibility and macOS features:

| Kext                    | Description                                       |
|-------------------------|---------------------------------------------------|
| ACPIBatteryManager      | Battery status and management                     |
| AMFIPass                | Bypass Apple Mobile File Integrity (for some patches) |
| AirportBrcmFixup        | Enables Broadcom Wi-Fi cards                      |
| AppleALC                | Enables onboard audio (ALC230)                    |
| BrightnessKeys          | Brightness hotkey support                         |
| CPUFriend               | CPU power management tuning                       |
| CPUFriendDataProvider   | Data provider for CPUFriend                       |
| CpuTscSync              | Fixes CPU TSC sync issues (multi-core)            |
| ECEnabler               | Enables EC device for battery/sensors             |
| HibernationFixup        | Fixes hibernation/sleep issues                    |
| HoRNDIS                 | USB tethering for Android devices                 |
| IO80211FamilyLegacy     | Wi-Fi support for legacy chipsets                 |
| IOSkywalkFamily         | Network stack support                             |
| Lilu                    | Core patching framework (required by most kexts)  |
| NVMeFix                 | Fixes NVMe SSD compatibility                      |
| RTCMemoryFixup          | RTC memory patch                                  |
| RestrictEvents          | Prevents unwanted macOS events                    |
| SMCLightSensor          | Light sensor support                              |
| SMCProcessor            | CPU sensor support                                |
| SMCSuperIO              | Fan and sensor support                            |
| USBMap                  | USB port mapping                                  |
| VirtualSMC              | SMC device emulation (required for boot)          |
| VoodooI2C               | I2C touchpad support – *Enables full touchpad functionality on your Lenovo IdeaPad S145, including gestures.* |
| VoodooI2CSynaptics      | Synaptics touchpad support – *Complements VoodooI2C for specific Synaptics touchpad support.* |
| VoodooPS2Controller     | PS/2 keyboard/touchpad support                    |
| WhateverGreen           | Graphics patching (iGPU)                          |
| YogaSMC                 | SMC plugin for Yoga laptops and specific sensors  |

---

## Screenshots

Here are some screenshots of my Hackintosh setup:

<div align="left">
    <img src="Prints/Captura%20de%20Tela%202025-08-28%20a%CC%80s%2018.51.15.png" alt="Screenshot" width="200"/>
</div>

For more screenshots, check the "[Prints](Prints)" folder.

---

### IMPORTANT NOTE:

> **Follow the instructions carefully!** If you do everything correctly, you’ll be able to run macOS without issues. However, remember the hardware and software adjustments required for a perfectly functional Hackintosh.

---

### Generating Serial & Configuration:

Don’t forget to generate new serials and insert them into the `config.plist` file to customize your Hackintosh. Use [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) for this.

To edit the `config.plist`, use [**ProperTree**](https://github.com/corpnewt/ProperTree).

---

## Post-Installation & Optimizations

After the initial macOS installation, consider the following steps to optimize your experience:

*   **Generate SMBIOS Serials:** As mentioned, use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate new unique serials and ensure proper functionality of iServices (iCloud, iMessage, FaceTime).
*   **Update OpenCore & Kexts:** Keep OpenCore and all kexts regularly updated for continuous compatibility with new macOS releases and performance improvements.
*   **Graphics Optimizations:** Check if full graphics acceleration (Metal/OpenCL) is working as shown in benchmarks. Additional tweaks to WhateverGreen or iGPU properties may be required in specific cases.
*   **USB Mapping:** The `USBMap.kext` should already provide a solid mapping. However, if you find USB ports not working properly, you may want to remap them to match your exact hardware.
*   **Power Management:** Monitor power consumption and temperature to ensure CPU power management is optimized. Tools like HWMonitor (part of VirtualSMC) can help.

---

## Acknowledgements 🙏

Special thanks to the developers and contributors of the following tools and resources that made this project possible:

- [**OpenCore**](https://github.com/acidanthera/OpenCorePkg)
- [**OCAuxiliaryTools**](https://github.com/ic005k/OCAuxiliaryTools)
- [**ProperTree**](https://github.com/corpnewt/ProperTree)
- [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS)
- [**gibMacOS**](https://github.com/corpnewt/gibMacOS)
- [**Hackintool**](https://github.com/benbaker76/Hackintool)
- [**IORegistryExplorer**](https://github.com/utopia-team/IORegistryExplorer)
- [**MaciASL**](https://github.com/acidanthera/MaciASL)

Special thanks to @MaLd0n for his professional Hackintosh consulting since 2006.

Your hard work and dedication are greatly appreciated! 🎉

---

## Contact & Feedback 📬

Stay connected with me on these platforms and follow my Hackintosh journey!

<table style="width:100%; margin-top: 20px;">
    <thead>
        <tr style="background-color: #f5f5f7;">
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Platform</th>
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Link</th>
        </tr>
    </thead>
    <tbody>
        <tr><td style="padding: 12px; border-bottom: 1px solid #ddd;">Facebook</td><td style="padding: 12px; border-bottom: 1px solid #ddd;"><a href="https://facebook.com/alebypegasus">alebypegasus</a></td></tr>
        <tr><td style="padding: 12px; border-bottom: 1px solid #ddd;">Instagram</td><td style="padding: 12px; border-bottom: 1px solid #ddd;"><a href="https://instagram.com/alebypegasus">alebypegasus</a></td></tr>
        <tr><td style="padding: 12px; border-bottom: 1px solid #ddd;">X</td><td style="padding: 12px; border-bottom: 1px solid #ddd;"><a href="https://x.com/alebypegasus">alebypegasus</a></td></tr>
        <tr><td style="padding: 12px; border-bottom: 1px solid #ddd;">LinkedIn</td><td style="padding: 12px; border-bottom: 1px solid #ddd;"><a href="https://linkedin.com/in/alebypegasus">alebypegasus</a></td></tr>
        <tr><td style="padding: 12px; border-bottom: 1px solid #ddd;">TikTok</td><td style="padding: 12px; border-bottom: 1px solid #ddd;"><a href="https://tiktok.com/@alebypegasus">alebypegasus</a></td></tr>
        <tr><td style="padding: 12px; border-bottom: 1px solid #ddd;">Reddit</td><td style="padding: 12px; border-bottom: 1px solid #ddd;"><a href="https://reddit.com/u/alebypegasus">alebypegasus</a></td></tr>
        <tr><td style="padding: 12px; border-bottom: 1px solid #ddd;">Telegram</td><td style="padding: 12px; border-bottom: 1px solid #ddd;"><a href="https://telegram.me/alebypegasus">alebypegasus</a></td></tr>
    </tbody>
</table>

---

🌟 Let’s connect and grow together! Feel free to reach out on any of these platforms. 😊

**Thank you for visiting!** 😊
