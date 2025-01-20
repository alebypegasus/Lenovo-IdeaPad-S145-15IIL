# EFI & Settings - Notebook Lenovo Idealpad S145 Core i7-1065G7 | Intel® 10th 

**Laptop Factory Defaults:**

Piece|Model
:----|:----
Plataforma|Notebook Lenovo Idealpad S145 | Intel 10th
Processador|Core I7-1065G7 | Intel® 10th
Vídeo|iGPU (Integrated) Intel Iris Plus
Audio|Realtek ALC230
Storage|SSD NVME 240GB for the operating system macOS
Memory|1x4GB 2667MHz DDR4
BIOS|Factory Default


**Laptop Upgrade::**

Piece|Model
:----|:----
Additional Storage| HD Sata 500GB for Time Machine
Memory| 1x16GB in 2667MHz DDR4, Total Memory 20GB
Wi-Fi end Bluetooth Card| BCM94360CS2 (I made an improvement I changed the default Wi-Fi card that came in the notebook. That way the Wi-Fi works natively)
Update BIOS| Version (DKCN53WW). I updated the notebook's BIOS with the Lenovo program and reconfigured some items in it


**EFI Information:**

Options|Information
:----|:----
SMBIOS|MacBookPro16,2
macOS|See the Releases and their descriptions
macOS install images|Directly from the Apple store using gibMacOS
OpenCore|Version 0.7.6 the 1.0.3


- After updating the BIOS to version (DKCN53WW) and making its settings, I also modified the BIOS internally to avoid Kernel Panics!


## **IMPORTANT ALERTS:**

Carefully read the above content, because if you carefully follow everything I've done, you'll be able to use macOS without problems on your notebook, but always take into account the Hardware and Software changes I've made.

However, even with these changes made by me, it is entirely possible to adapt these EFI to your Notebook as long as it has the same Hardware version mentioned above in (Laptop Factory Defaults), it is only necessary to update and configure for the BIOS version (DKCN53WW).

I will leave just one more important detail, I removed my serials from the EFI's so it is necessary to generate new serials and add them to the config.plist file.
Use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate the serials, in order to make your life easier the place to add the serials is config.plist>PlatformInfo>Generic; and I marked the values that needed to be replaced with XXXXXXXXXXXXXXXX, just replace with the serials that you will generate in GenSMBIOS

To modify the config.plist file I use [ProperTree](https://github.com/corpnewt/ProperTree).

See photos of my Hackintosh 100% working in the previews folder.

## **ACKNOWLEDGEMENTS**

A special thanks to the developers and contributors of the following tools and resources that made this project possible:

- **OpenCore**: [OpenCore](https://github.com/acidanthera/OpenCorePkg)
- **OCAuxiliaryTools**: [OCAuxiliaryTools](https://github.com/ic005k/OCAuxiliaryTools)
- **ProperTree**: [ProperTree](https://github.com/corpnewt/ProperTree)
- **GenSMBIOS**: [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
- **gibMacOS**: [gibMacOS](https://github.com/corpnewt/gibMacOS)
- **Hackintosh Community**: [olarila.com](https://olarila.com)

A special thanks to @MaLd0n for his professional consulting for macOS Hackintosh since 2006. You can access his services [here](https://olarila.com/topic/40852-professional-consulting-for-macos-hackintosh-since-2006/).

Your hard work and dedication are greatly appreciated!

## **💌 CONTACT & FEEDBACK**
Stay in touch and follow my journey on these platforms! 🌟
| Platform       | Link                                                                                     | 
|----------------|------------------------------------------------------------------------------------------|
| **Facebook**   | [facebook.com/alebypegasus](https://facebook.com/alebypegasus)                           |
| **Instagram**  | [instagram.com/alebypegasus](https://instagram.com/alebypegasus)                         |
| **X**          | [x.com/alebypegasus](https://x.com/alebypegasus)                                         |
| **LinkedIn**   | [linkedin.com/in/alebypegasus](https://linkedin.com/in/alebypegasus)                     |
| **TikTok**     | [tiktok.com/@alebypegasus](https://tiktok.com/@alebypegasus)                             |
| **Reddit**     | [reddit.com/u/alebypegasus](https://reddit.com/u/alebypegasus)                           |
| **Telegram**   | [telegram.me/alebypegasus](telegram.me/alebypegasus)                                     |
---
🌟 Let's connect and grow together! Don't hesitate to reach out on any of these platforms. 😊

**Thank You for Visiting!** 😊