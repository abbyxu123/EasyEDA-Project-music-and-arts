# 工程师交接说明

## 项目一句话

设计一块 v0.1 触摸音乐控制 PCB，用于连接导电涂料画作和导电纺织服装，并触发音符、鼓点、和弦或短音效。

## v0.1 设计目标

- 首版优先稳定验证，不追求极限小型化。
- 支持 12 路触摸输入，默认使用 MPR121。
- 支持 USB 供电和锂电池供电预留。
- 支持小喇叭或外接音频输出。
- 板子可以固定在画框背面，也可以放进服装模块袋。
- 接口、正负极、触摸编号必须在丝印中清晰标注。

## 推荐架构

```text
USB-C / LiPo Battery
        ↓
Power Switch / Regulation
        ↓
ESP32 MCU
        ↓ I2C
MPR121 12-channel Touch Controller
        ↓
Touch Connectors T0-T11

ESP32 MCU
        ↓ UART / I2S / GPIO
Audio Playback or Audio DAC
        ↓
Amplifier
        ↓
Speaker / Audio Output
```

## 工程师需要优先确认

| 项目 | 推荐方向 | 必须确认 |
|---|---|---|
| 主控 | ESP32 系列 | 具体模组、下载方式、供电 |
| 触摸 | MPR121 | I2C 地址、IRQ 是否使用、上拉电阻 |
| 音频 | 音频播放模块或 I2S DAC | 接口、功放、喇叭功率 |
| 供电 | USB + 电池接口 | 是否板载充电、是否需要保护 |
| 接口 | 触摸端子放板边 | 画作和服装是否都方便接线 |
| 结构 | 60 mm x 80 mm 以内优先 | 固定孔、板边、接口方向 |

## 不能省略的设计点

- 触摸输入和功放/喇叭走线要分区。
- T0 到 T11 必须有清晰丝印。
- 电池和喇叭接口必须标正负极。
- 保留调试接口，至少串口或 I2C 测试点。
- 电源开关必须易触达。
- 固定孔不能压线，孔周围留机械空间。
- 板上标注项目名、版本号 `v0.1`、GitHub 或项目短链接位置。

## 不建议首版实现

- 多板无线同步。
- 复杂音频合成器。
- 高功率扬声器。
- 完全隐藏式不可拆服装结构。
- 一次性把 PCB 做得很小。

## 交付物

打板前至少需要：

- EasyEDA 原理图源文件
- EasyEDA PCB 源文件
- 原理图 PDF
- PCB 2D/3D 预览图
- Gerber
- BOM
- Pick and Place，若需要贴片
- 更新后的 `docs/hardware/pin-map.csv`
- 更新后的 `docs/hardware/bom-draft.csv`

