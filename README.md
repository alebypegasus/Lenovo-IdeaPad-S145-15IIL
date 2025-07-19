# EFI for Lenovo IdeaPad S145 (Intel® Core i7-1065G7)

![macOS Sequoia](https://olhardigital.com.br/wp-content/uploads/2024/06/macos_sequoia-1024x576.png)

> **Turn your Lenovo IdeaPad S145 into a perfect Hackintosh!**

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
| Storage    | 240GB NVMe SSD (macOS) |
| Memory     | 1x4GB 2667MHz DDR4 |
| BIOS       | Factory Default |

---

## Laptop Upgrades

| Component           | Model                                 |
|---------------------|---------------------------------------|
| Additional Storage  | 500GB SATA HDD (Time Machine)         |
| Memory              | 1x16GB 2667MHz DDR4 (Total: 20GB)     |
| Wi-Fi & Bluetooth   | BCM94360CS2 (Upgraded Wi-Fi card)     |
| BIOS                | Version DKCN53WW (Updated)            |

---

## EFI Overview

| Option                | Information                                 |
|-----------------------|---------------------------------------------|
| SMBIOS                | MacBookAir9,1 / MacBookPro16,2              |
| macOS                 | See Releases and their descriptions         |
| macOS Install Images  | Downloaded from Apple Store via gibMacOS    |
| OpenCore              | Version 0.7.6 to 1.0.5                      |

---

## ACPI Patches (EFI/OC/ACPI)

All ACPI files below are custom SSDTs or patches to enable or fix specific hardware features for macOS compatibility:

| File                      | Description |
|---------------------------|-------------|
| DMAR.aml                  | Fixes for DMA Remapping (VT-d) |
| SSDT-ALS0.aml             | Ambient Light Sensor support |
| SSDT-EC.aml               | Embedded Controller device for battery and sensors |
| SSDT-EXT1-FixShutdown.aml | Fixes shutdown issues |
| SSDT-EXT3-WakeScreen.aml  | Fixes screen wake from sleep |
| SSDT-EXT5-TP-LED.aml      | Touchpad LED support |
| SSDT-GPI0.aml             | General Purpose I/O support |
| SSDT-GPI0_GPHD.aml        | Additional GPIO support |
| SSDT-GPRW.aml             | Proper wake support for sleep |
| SSDT-HPET.aml             | High Precision Event Timer patch |
| SSDT-PLUG.aml             | CPU power management (PluginType) |
| SSDT-PMC.aml              | Intel Power Management Controller patch |
| SSDT-PNLF.aml             | Enables backlight control (Panel device) |
| SSDT-PTSWAKTTS.aml        | Power state wake fix |
| SSDT-RTCAWAC.aml          | Real Time Clock patch |
| SSDT-SBUS-MCHC.aml        | SMBus and Memory Controller support |
| SSDT-TPD0.aml             | Touchpad device patch |
| SSDT-USB-Reset.aml        | USB port reset/fix |
| SSDT-USBX.aml             | USB power properties |
| SSDT-XOSI.aml             | OSI patch for macOS compatibility |

---

## Kexts Used (EFI/OC/Kexts)

All kexts below are used to enable or improve hardware compatibility and macOS features:

| Kext                    | Description |
|-------------------------|-------------|
| ACPIBatteryManager      | Battery status and management |
| AMFIPass                | Bypass Apple Mobile File Integrity (for some patches) |
| AirportBrcmFixup        | Enables Broadcom Wi-Fi cards |
| AppleALC                | Enables onboard audio (ALC230) |
| BrightnessKeys          | Brightness hotkey support |
| CPUFriend               | CPU power management tuning |
| CPUFriendDataProvider   | Data provider for CPUFriend |
| CpuTscSync              | Fixes CPU TSC sync issues (multi-core) |
| ECEnabler               | Enables EC device for battery/sensors |
| FeatureUnlock           | Unlocks macOS features (Sidecar, etc) |
| HibernationFixup        | Fixes hibernation/sleep issues |
| HoRNDIS                 | USB tethering for Android devices |
| IO80211FamilyLegacy     | Wi-Fi support for legacy chipsets |
| IOSkywalkFamily         | Network stack support |
| Lilu                    | Core patching framework (required by most kexts) |
| NVMeFix                 | Fixes NVMe SSD compatibility |
| NullEthernet            | Enables Ethernet for unsupported chips |
| RTCMemoryFixup          | RTC memory patch |
| RestrictEvents          | Prevents unwanted macOS events |
| SMCLightSensor          | Light sensor support |
| SMCProcessor            | CPU sensor support |
| SMCSuperIO              | Fan and sensor support |
| USBPorts                | USB port mapping |
| USBToolBox              | USB port configuration |
| UTBMap                  | USB mapping data |
| VirtualSMC              | SMC device emulation (required for boot) |
| VoodooI2C               | I2C touchpad support |
| VoodooI2CSynaptics      | Synaptics touchpad support |
| VoodooPS2Controller     | PS/2 keyboard/touchpad support |
| WhateverGreen           | Graphics patching (iGPU) |
| itlwm                   | Intel Wi-Fi support |

---

## **Screenshots:**

Here are some screenshots of my Hackintosh setup:

<div align="left">
    <img src="Prints/Captura de Tela 2025-01-20 às 14.05.27.png" alt="Screenshot" width="200"/>
</div>

For more screenshots, check the "[Prints](Prints)" folder.

---

## **Laptop Upgrade:**

<table style="width:100%; border-collapse: collapse; margin-top: 20px;">
    <thead>
        <tr style="background-color: #f5f5f7;">
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Component</th>
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Model</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Additional Storage</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">500GB SATA HDD (Time Machine)</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Memory</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">1x16GB 2667MHz DDR4 (Total: 20GB)</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Wi-Fi & Bluetooth</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">BCM94360CS2 (Upgraded Wi-Fi card)</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">BIOS</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Version (DKCN53WW) - Updated</td>
        </tr>
    </tbody>
</table>

---

## **EFI Information:**

<table style="width:100%; border-collapse: collapse; margin-top: 20px;">
    <thead>
        <tr style="background-color: #f5f5f7;">
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Options</th>
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Information</th>
        </tr>
    </thead>
    <tbody>
            <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">SMBIOS</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">MacBookAir9,1</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">SMBIOS</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">MacBookPro16,2</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">macOS</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">See Releases and their descriptions</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">macOS Install Images</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Directly from the Apple Store using gibMacOS</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">OpenCore</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Version 0.7.6 to 1.0.5</td>
        </tr>
    </tbody>
</table>

---

### **IMPORTANT NOTE:**

<p style="background-color: #ffefc1; border: 1px solid #f7d268; padding: 15px; margin-top: 20px; font-size: 16px; border-radius: 8px;">
    <strong>Follow the instructions carefully!</strong> If you follow all the steps, you will be able to run macOS without issues. However, keep in mind the hardware and software changes necessary for perfect Hackintosh functionality.
</p>

---

### **Generating Serial & Configuration:**

Don't forget to generate new serials and insert them into the `config.plist` file to customize your Hackintosh. Use the tool [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) for this.

To modify the `config.plist`, use [**ProperTree**](https://github.com/corpnewt/ProperTree).

---

## **Acknowledgements** 🙏

A special thanks to the developers and contributors of the following tools and resources that made this project possible:

- [**OpenCore**](https://github.com/acidanthera/OpenCorePkg)
- [**OCAuxiliaryTools**](https://github.com/ic005k/OCAuxiliaryTools)
- [**ProperTree**](https://github.com/corpnewt/ProperTree)
- [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS)
- [**gibMacOS**](https://github.com/corpnewt/gibMacOS)
- [**Hackintool**](https://github.com/benbaker76/Hackintool)
- [**IORegistryExplorer**](https://github.com/utopia-team/IORegistryExplorer)
- [**MaciASL**](https://github.com/acidanthera/MaciASL)

A special thanks to [@MaLd0n](https://olarila.com/topic/40852-professional-consulting-for-macos-hackintosh-since-2006/) for his professional consulting for macOS Hackintosh since 2006.

Your hard work and dedication are greatly appreciated! 🎉

---

## **Contact & Feedback** 📬

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

🌟 Let's connect and grow together! Feel free to reach out on any of these platforms. 😊

**Thank you for visiting!** 😊
