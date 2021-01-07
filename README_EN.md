# Hackintosh Gigabyte B460M Aorus Pro


> 2021/01/07 update：update OC 0.6.5 and kexts.

## Hardware

|    Device     |            Model            |
| :-----------: | :-------------------------: |
|      CPU      |          I5-10700           |
|  Motherboard  |  Gigabyte B460M Aorus Pro   |
|     GPU0      |   Intel UHD Graphics 630    |
|     GPU1      | AMD Radeon RX 590 8G        |
|     Audio     |      Realtek ALCS1200A      |
| Ethernet Card |        Intel I219V12        |
| WiFI/BT Card  |        Wi-Fi Bcm94360cd        |

## What works

| Function      | Status                       |
| ------------- | ---------------------------- |
| CPU           | Work.                        |
| GPU           | Hardware acceleration works. |
| Audio         | AppleALC Work with layout-id 50.      |
| Ethernet Card | Work.                        |
| WIFI/BT       | Work.                        |
| Sleep/Wake    | Work.                        |
| USB Mapping   | Work.                        |

## BIOS setting

|       Disable        |                Enable                 |
| :------------------: | :-----------------------------------: |
|      Fast Boot       |           Above 4G decoding           |
|     Secure Boot      |            Hyper-Threading            |
|   Serial/COM Port    |          EHCI/XHCI Hand-off           |
|         VT-d         |       OS type: Windows 10 WHQL        |
|         CSM          | DVMT Pre-Allocated(iGPU Memory): 64MB |
| Intel Platform Trust |            SATA Mode: AHCI            |
|       CFG Lock       |                                       |
|      Intel SGX       |                                       |

**Note 1:** The BIOS version is F3, and there is no CFG Lock option in Setting, **So you should select the CFG Lock.efi in OpenCore Picker menu before you try to install the macOS.**

**Note2:** Windows10 WHQL can solve the problem of vague logo of mobo.

## OpenCore/OS

|   Item   |        Version        |
| :------: | :-------------------: |
| OpenCore |         0.6.5         |
|  macOS   | Big Sur 11.1       |

## README Before Install

- I set the model to iMac20,1, please change it if necessary, and you need to add Serial number, UUID and MLB by yourself.
- I have inject GPU0, Audio and Ethernet info in DeviceProperties, modify them if necessary after you login OS.
- In theory, this EFI is universal on each brand B460M motherboard, please solve the specific adjustment on your own.
- Be sure to read the above text **before using this EFI** to complete the BIOS settings, especially to unlock the CFG in the **OC boot menu**.
