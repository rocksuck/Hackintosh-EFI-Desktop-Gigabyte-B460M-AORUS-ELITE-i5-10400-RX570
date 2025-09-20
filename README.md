# Hackintosh-EFI-Desktop-Gigabyte-B460M-AORUS-ELITE-i5-10400-RX570
Hackintosh EFI for Desktop (Gigabyte B460M AORUS ELITE + i5-10400 + RX570) | 适配macOS Sequoia 15.4 | OpenCore 1.0.5 | 显卡免驱/硬件全识别/稳定使用
# Hackintosh-EFI-Gigabyte-B460M-i5-10400-RX570

![macOS](https://img.shields.io/badge/macOS-Sequoia_15.4-blue.svg)
![OpenCore](https://img.shields.io/badge/OpenCore-1.0.5-green.svg)
![Status](https://img.shields.io/badge/Status-Working-brightgreen.svg)

## 📋 硬件配置

| 组件         | 型号                          | 状态       |
|--------------|-------------------------------|------------|
| 主板         | 技嘉B460M AORUS ELITE         | 完美支持   |
| CPU          | Intel Core i5-10400 (Comet Lake) | 完美支持   |
| 显卡         | AMD Radeon RX570              | 免驱，完美支持 |
| 网卡         | 奋威BCM94360CD                | 完美支持所有功能 |
| 硬盘         | 1TB SATA固态硬盘              | 完美支持   |
| 内存         | 8GB × 2（共16GB）| 完美支持   |

## 💻 系统与引导信息

- **支持系统**：macOS Sequoia 15.4
- **OpenCore版本**：1.0.5
- **SMBIOS建议**：iMac20,1（与硬件最匹配的机型）

## ✅ 功能工作状态

| 功能               | 状态 | 备注                     |
|--------------------|------|--------------------------|
| RX570显卡驱动      | ✅ 正常 | 免驱，支持硬件加速       |
| 声卡与音频         | ✅ 正常 | 输入/输出均正常          |
| 有线网络           | ✅ 正常 | 稳定连接                 |
| 无线网络（BCM94360CD） | ✅ 正常 | 原生支持（含隔空投送）|
| 蓝牙功能           | ✅ 正常 | 支持设备配对/连接        |
| AirDrop/Handoff    | ✅ 正常 | 跨苹果设备传输/接续       |
| 睡眠与唤醒         | ✅ 正常 | 秒醒，无睡死问题         |
| USB端口            | ✅ 正常 | 所有USB 2.0/3.0端口工作  |
| Type-C端口         | ✅ 正常 | 支持正反接入             |

## 🛠️ BIOS设置指南

**关键选项设置：**
- **Secure Boot**：Disabled（关闭安全启动）
- **CFG Lock**：Disabled（关闭，避免内核崩溃）
- **VT-d**：Enabled（若用虚拟机可开，不影响黑苹果）
- **XHCI Hand-off**：Enabled（开启，修复USB设备兼容性）
- **SATA Mode**：AHCI（硬盘模式必须为AHCI）
- **Above 4G Decoding**：Enabled（开启，支持大显存显卡）
- **Hyper-Threading**：Enabled（开启CPU超线程）
- **CSM Support**：Disabled（关闭旧版兼容模式）

## 📝 使用步骤

1. **下载EFI**：从本仓库下载`EFI`文件夹。
2. **修改三码**：用[OpenCore Configurator（ocat）](https://mackie100projects.altervista.org/opencore-configurator/)打开`EFI/OC/config.plist`，在`PlatformInfo`板块生成并替换**Serial Number、Board Serial Number、SmUUID**（避免与他人重复，确保iMessage和App Store正常工作）。
3. **刷入ESP分区**：通过`OpenCore Configurator`或`DiskGenius`，将`EFI`文件夹复制到硬盘的**ESP分区**（一般是磁盘的小容量隐藏分区）。
4. **启动测试**：重启电脑，在BIOS启动项中选择`OpenCore`，引导进入macOS。

## 🚧 已知问题

- 暂无重大问题。
- 若遇故障，可在仓库**Issues**区提交（附报错截图+硬件细节）。

## 📅 更新日志

- **2025-09-19**：初始版本
  - 适配macOS Sequoia 15.4
  - OpenCore 1.0.5稳定配置
  - 全硬件功能验证通过

## 🙏 致谢

- [Dortania黑苹果指南](https://dortania.github.io/OpenCore-Install-Guide/)
- 黑苹果社区的Kexts与配置经验
- 特别感谢 [RampagerB的技嘉B460M系列EFI仓库](https://github.com/RampagerB/OpenCore-Gigabyte-Aorus-Elite-B460M-10700-RX560-EFI) 提供的参考配置

## 📄 免责声明

本EFI仅供学习，商业使用风险自担；因使用本EFI导致的硬件/数据问题，作者不承担责任。
