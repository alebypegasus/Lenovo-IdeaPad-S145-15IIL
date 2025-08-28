# EFI para Lenovo IdeaPad S145 (Intel® Core i7-1065G7)

![macOS Sequoia](https://olhardigital.com.br/wp-content/uploads/2024/06/macos_sequoia-1024x576.png)

> **Transforme seu Lenovo IdeaPad S145 em um Hackintosh perfeito!**

---

## Sobre Este Projeto

Este repositório fornece uma pasta EFI completa para rodar macOS no Lenovo IdeaPad S145 com Intel® Core i7-1065G7 (10ª Geração). Aqui você encontrará todos os patches ACPI, kexts e dicas de configuração necessários para obter uma experiência Hackintosh estável e totalmente funcional.

---

## Especificações de Fábrica do Notebook

| Componente | Modelo |
|------------|-------|
| Plataforma | Lenovo IdeaPad S145 (Intel® 10ª Geração) |
| Processador | Core i7-1065G7 (Intel® 10ª Geração) |
| Gráficos | Intel® Iris Plus (iGPU) |
| Áudio | Realtek ALC230 |
| Armazenamento | 240GB NVMe SSD (Original) |
| Memória | 1x4GB 2667MHz DDR4 |
| BIOS | Padrão de Fábrica |

---

## Upgrades do Notebook

| Componente | Modelo |
|---------------------|------------------------------------------------|
| SSD Principal | 1000GB NVMe (Substituiu o SSD original de 240GB) |
| Armazenamento Adicional | 500GB SATA HDD (Time Machine) |
| Memória | 1x16GB 2667MHz DDR4 (Total: 20GB) |
| Wi-Fi e Bluetooth | BCM94360CS2 (Placa Wi-Fi atualizada) |
| BIOS | Versão DKCN53WW (Atualizada) |

---

## Visão Geral da EFI

| Opção | Informação |
|-----------------------|---------------------------------------------|
| SMBIOS | MacBookPro16,2 |
| macOS | Veja os Releases e suas descrições |
| Imagens de Instalação do macOS | Baixadas da Apple Store via gibMacOS |
| OpenCore | Versão 0.7.6 a 1.0.6 |

---

## Configurações da BIOS

Para garantir o funcionamento adequado do macOS, é crucial configurar sua BIOS (firmware UEFI) com as seguintes opções. Reinicie seu notebook e pressione `F2` (ou a tecla respectiva da BIOS) repetidamente para entrar nas configurações:

### Segurança
*   **Secure Boot**: `Disabled` (Desativado)
*   **Intel SGX**: `Disabled` (Desativado)
*   **Intel VT-d**: `Enabled` (Ativado) – *Se disponível, essencial para virtualização e mapeamento DMA.*

### Inicialização
*   **Fast Boot**: `Disabled` (Desativado)
*   **CSM Support**: `Disabled` (Desativado) – *Recomendado para UEFI puro.*
*   **Boot Mode**: `UEFI Only` (Apenas UEFI)

### Configuração / Avançado
*   **Intel Virtualization Technology (VT-x)**: `Enabled` (Ativado)
*   **DVMT Pre-Allocated Memory**: `64MB` ou `128MB` (se disponível, escolha o valor mais alto para a iGPU)
*   **XHCI Hand-off**: `Enabled` (Ativado) – *Se disponível, necessário para suporte USB.*
*   **SATA Mode**: `AHCI` (Essencial, nunca `RAID` ou `Intel RST`)

*Nota: As opções da BIOS podem variar ligeiramente dependendo da versão do firmware. Certifique-se de salvar as alterações antes de sair.*

---

## Benchmarks

Aqui estão os resultados dos benchmarks do Geekbench 6 para este Hackintosh:

- **CPU**: [https://browser.geekbench.com/v6/cpu/13545229](https://browser.geekbench.com/v6/cpu/13545229)
- **iGPU Metal**: [https://browser.geekbench.com/v6/compute/4698032](https://browser.geekbench.com/v6/compute/4698032)
- **iGPU OpenCL**: [https://browser.geekbench.com/v6/compute/4698039](https://browser.geekbench.com/v6/compute/4698039)

---

## Patches ACPI (EFI/OC/ACPI)

Todos os arquivos ACPI abaixo são SSDTs personalizados ou patches para habilitar ou corrigir recursos de hardware específicos para compatibilidade com macOS:

| Arquivo | Descrição |
|---------------------------|---------------------------------------------------|
| DMAR.aml | Correções para Remapeamento DMA (VT-d) |
| SSDT-ALS0.aml | Suporte para Sensor de Luz Ambiente |
| SSDT-Audio.aml | Enumeração e correções de dispositivo de áudio |
| SSDT-EC.aml | Dispositivo de Controlador Embarcado para bateria e sensores – *Crucial para o monitoramento de bateria e sensores de temperatura do seu laptop.* |
| SSDT-GPI0.aml | Suporte para Entrada/Saída de Propósito Geral |
| SSDT-HPET.aml | Patch para High Precision Event Timer |
| SSDT-MEM2.aml | Mapeamento de memória e correções relacionadas |
| SSDT-PLUG.aml | Gerenciamento de energia da CPU (PluginType) |
| SSDT-PMC.aml | Patch para o Controlador de Gerenciamento de Energia Intel |
| SSDT-PNLF.aml | Habilita o controle de luz de fundo (dispositivo de Painel) – *Essencial para o controle de brilho nativo no painel do IdeaPad S145.* |
| SSDT-RHUB-Reset.aml | Correções de reset do controlador USB |
| SSDT-RTCAWAC.aml | Patch para Real Time Clock |
| SSDT-SBUS-MCHC.aml | Suporte para SMBus e Controlador de Memória |
| SSDT-TPD0.aml | Patch para dispositivo Touchpad |
| SSDT-USBX.aml | Propriedades de energia USB |
| SSDT-XOSI.aml | Patch OSI para compatibilidade com macOS |
| SSDT-XSPI.aml | Suporte para barramento SPI |

---

## Kexts Utilizados (EFI/OC/Kexts)

Todos os kexts abaixo são usados para habilitar ou melhorar a compatibilidade de hardware e os recursos do macOS:

| Kext | Descrição |
|-------------------------|---------------------------------------------------|
| ACPIBatteryManager | Status e gerenciamento da bateria |
| AMFIPass | Ignora a Integridade de Arquivos Móveis da Apple (para alguns patches) |
| AirportBrcmFixup | Habilita placas Wi-Fi Broadcom |
| AppleALC | Habilita áudio onboard (ALC230) |
| BrightnessKeys | Suporte para teclas de brilho |
| CPUFriend | Ajuste de gerenciamento de energia da CPU |
| CPUFriendDataProvider | Provedor de dados para CPUFriend |
| CpuTscSync | Corrige problemas de sincronização TSC da CPU (multi-core) |
| ECEnabler | Habilita o dispositivo EC para bateria/sensores |
| HibernationFixup | Corrige problemas de hibernação/suspensão |
| HoRNDIS | Tethering USB para dispositivos Android |
| IO80211FamilyLegacy | Suporte Wi-Fi para chipsets legados |
| IOSkywalkFamily | Suporte à pilha de rede |
| Lilu | Estrutura de patching central (exigida pela maioria dos kexts) |
| NVMeFix | Corrige compatibilidade de SSD NVMe |
| RTCMemoryFixup | Patch de memória RTC |
| RestrictEvents | Previne eventos indesejados do macOS |
| SMCLightSensor | Suporte para sensor de luz |
| SMCProcessor | Suporte para sensor da CPU |
| SMCSuperIO | Suporte para fan e sensores |
| USBMap | Mapeamento de portas USB |
| VirtualSMC | Emulação de dispositivo SMC (necessário para inicialização) |
| VoodooI2C | Suporte para touchpad I2C – *Habilita a funcionalidade completa do touchpad do seu Lenovo IdeaPad S145, incluindo gestos.* |
| VoodooI2CSynaptics | Suporte para touchpad Synaptics – *Complementa o VoodooI2C para suporte específico ao touchpad Synaptics.* |
| VoodooPS2Controller | Suporte para teclado/touchpad PS/2 |
| WhateverGreen | Patching gráfico (iGPU) |
| YogaSMC | Plugin SMC para notebooks Yoga e alguns sensores específicos |

---

## Capturas de Tela

Aqui estão algumas capturas de tela da minha configuração Hackintosh:

<div align="left">
    <img src="Prints/Captura de Tela 2025-01-20 às 14.05.27.png" alt="Screenshot" width="200"/>
</div>

Para mais capturas de tela, verifique a pasta "[Prints](Prints)".

---

### NOTA IMPORTANTE:

> **Siga as instruções cuidadosamente!** Se você seguir todos os passos, conseguirá rodar o macOS sem problemas. No entanto, lembre-se das mudanças de hardware e software necessárias para a funcionalidade perfeita do Hackintosh.

---

### Gerando Serial e Configuração:

Não se esqueça de gerar novos seriais e inseri-los no arquivo `config.plist` para personalizar seu Hackintosh. Use a ferramenta [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) para isso.

Para modificar o `config.plist`, use [**ProperTree**](https://github.com/corpnewt/ProperTree).

---

## Pós-Instalação e Otimizações

Após a instalação inicial do macOS, considere os seguintes passos para otimizar sua experiência:

*   **Gerar Seriais SMBIOS:** Conforme mencionado, use o [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) para gerar novos seriais únicos e garantir o funcionamento dos iServices (iCloud, iMessage, FaceTime).
*   **Atualização do OpenCore e Kexts:** Mantenha seu OpenCore e todos os kexts atualizados regularmente para compatibilidade contínua com as novas versões do macOS e melhorias de desempenho.
*   **Otimizações Gráficas:** Verifique se a aceleração gráfica completa (Metal/OpenCL) está funcionando conforme os benchmarks. Ajustes adicionais no WhateverGreen ou nas propriedades da iGPU podem ser necessários em casos específicos.
*   **Mapeamento de USBs:** O `USBMap.kext` já deve fornecer um mapeamento robusto. No entanto, se encontrar portas USB que não funcionam corretamente, você pode querer remapear as portas USB para o seu hardware específico.
*   **Gerenciamento de Energia:** Monitore o consumo de energia e a temperatura para garantir que o gerenciamento de energia da CPU esteja otimizado. Ferramentas como o HWMonitor (parte do VirtualSMC) podem ajudar.

---

## Agradecimentos 🙏

Um agradecimento especial aos desenvolvedores e colaboradores das seguintes ferramentas e recursos que tornaram este projeto possível:

- [**OpenCore**](https://github.com/acidanthera/OpenCorePkg)
- [**OCAuxiliaryTools**](https://github.com/ic005k/OCAuxiliaryTools)
- [**ProperTree**](https://github.com/corpnewt/ProperTree)
- [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS)
- [**gibMacOS**](https://github.com/corpnewt/gibMacOS)
- [**Hackintool**](https://github.com/benbaker76/Hackintool)
- [**IORegistryExplorer**](https://github.com/utopia-team/IORegistryExplorer)
- [**MaciASL**](https://github.com/acidanthera/MaciASL)

Um agradecimento especial a [@MaLd0n](https://olarila.com/topic/40852-professional-consulting-for-macos-hackintosh-since-2006/) por sua consultoria profissional em macOS Hackintosh desde 2006.

Seu trabalho árduo e dedicação são imensamente apreciados! 🎉

---

## Contato e Feedback 📬

Mantenha-se conectado comigo nestas plataformas e acompanhe minha jornada Hackintosh!

<table style="width:100%; margin-top: 20px;">
    <thead>
        <tr style="background-color: #f5f5f7;">
            <th style="padding: 12px; text-align: left; border-bottom: 1px solid #ddd;">Plataforma</th>
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

🌟 Vamos nos conectar e crescer juntos! Sinta-se à vontade para entrar em contato em qualquer uma dessas plataformas. 😊

**Obrigado pela visita!** 😊
