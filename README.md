# EFI - Lenovo IdeaPad S145 | Intel® Core i7-1065G7

<div>
    <img src="https://olhardigital.com.br/wp-content/uploads/2024/06/macos_sequoia-1024x576.png" alt="macOS Sequoia" width="900"/>
</div>
<br>
**Transforming your Lenovo laptop into a perfect Hackintosh!**

---

## **Laptop Factory Defaults:**

<table style="width:100%; border-collapse: collapse; margin-top: 20px;">
    <thead>
        <tr style="background-color: #f5f5f7;">
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Component</th>
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Model</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Platform</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Lenovo IdeaPad S145 | Intel® 10th Gen</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Processor</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Core i7-1065G7 | Intel® 10th Gen</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Graphics</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Intel® Iris Plus (iGPU)</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Audio</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Realtek ALC230</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Storage</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">240GB NVMe SSD (macOS)</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Memory</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">1x4GB 2667MHz DDR4</td>
        </tr>
        <tr>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">BIOS</td>
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Factory Default</td>
        </tr>
    </tbody>
</table>

---

## **Screenshots:**

Here are some screenshots of my Hackintosh setup:

<div align="left">
    <img src="Prints/Captura de Tela 2025-01-20 às 14.05.27.png" alt="Screenshot" width="200"/>
</div>

For more screenshots, check the "Prints" folder.

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
            <td style="padding: 12px; border-bottom: 1px solid #ddd;">Version 0.7.6 to 1.0.4</td>
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
