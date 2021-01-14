# Hackintosh Gigabyte B460M Aorus Pro(Bios: F4)


> 2021年01月07日更新：升级 OC 版本至 0.6.5，kext 常规更新。
>

## 配置

| 设备 |            型号             |
| :--: | :-------------------------: |
| CPU  |          I7-10700           |
| 主板 |  Gigabyte B460M Aorus Pro   |
| 内存 |  2 x 16GB DDR4 2666 MHz   |
| 显卡 |   Intel UHD Graphics 630    |
|      | AMD Radeon RX 590 8G        |
| 声卡 |      Realtek ALCS1200A      |
| 网卡 |   Intel® Ethernet Connection I219V12   |
|      |        Wi-Fi Bcm94360cd     |
| 蓝牙 |     Wi-Fi Bcm94360cd 自带      |
|      |   Wifi + Bluetooth (Airdrop, AirPlay)     |
| 硬盘 |     WD SN750=2块            |
|      |      4T机械硬盘 2块 数据盘     |

## 功能

| 功能     | 完成度                                    |
| -------- | ----------------------------------------- |
| CPU 变频 | 正常                                      |
| 核显     | 硬件加速正常                              |
| 声卡     | AppleALC直接驱动，且使用 id 为 50，完美适配   |
| 网卡     | 正常                                      |
| 蓝牙     | 正常                                      |
| 睡眠     | 正常                                      |
| USB      | 已定制，正常（默认未启用定制USB）               |

## BIOS 设置

|         关闭         |                 开启                  |
| :------------------: | :-----------------------------------: |
|      Fast Boot       |           Above 4G decoding           |
|     Secure Boot      |            Hyper-Threading            |
| Serial/COM Port（可打开） |          EHCI/XHCI Hand-off           |
|         VT-d         |       OS type: Windows 10 WHQL        |
|     CSM（可打开）   | DVMT Pre-Allocated(iGPU Memory): 64MB |
| Intel Platform Trust |            SATA Mode: AHCI            |
|       CFG Lock       |                                       |
|      Intel SGX       |                                       |

注1：F4版本BIOS中可关闭CFG。F3版本 BIOS 中无 CFG Lock 解锁选项，可在安装前在选择界面中选择 **CFG Lock.efi** 进行解锁，后可正常安装。

注2：注意 Windows10 WHQL 模式可以解决主板 logo 模糊的问题。

注3：单MAC系统时，出问题要BIOS引导进PE，需要开启GSM（开启此项一样可以使用苹果系统）。

注4：Settings--Super IO Configuration--Serial Port--Enabled （USB串口已可以打开，一切正常）

## 引导及系统版本

|   项目   |         版本          |
| :------: | :-------------------: |
| OpenCore |         0.6.5         |
|  macOS   | Catalina 10.15.7   |
|  macOS   | Big Sur 11.1   |
|  Windows   | Windows 10   |

## 安装须知

- 机型我设定为iMac20,2，有需要请自行更改，另需要自行补充三码。**仅适用安装 Catalina 10.15.6(19G2021) 及以上版本，如有需要请自行替换为 iMac19,1。**
- DeviceProperties 中核显、声卡、网卡已内建，进系统后请根据需要修正总线地址或移除。
- 理论上来讲本 EFI 在各个品牌 B460M 主板上通用，具体调整请自行解决。
- 使用本 EFI **请务必先阅读上述文字**，完成各项 BIOS 设置，尤其是在 **OC 引导菜单**先解锁 CFG。
