# Firmware

固件负责读取触摸输入、切换音色、触发音频输出，并为画作和服装两种载体提供稳定的演奏模式。

## 首版固件目标

- 读取 12 路 MPR121 触摸输入
- 将触摸通道映射到音符、鼓点或音效
- 支持至少 2 种模式：画作旋律模式、服装节奏模式
- 支持模式切换按键
- 支持串口调试输出，方便观察误触发

## 建议目录

```text
firmware/
  arduino/        Arduino IDE / PlatformIO 版本
  samples/        音频文件说明，不直接提交大文件
```

## 触摸映射草案

| 通道 | 画作模式 | 服装模式 |
|---|---|---|
| T0 | C4 | Kick |
| T1 | D4 | Snare |
| T2 | E4 | Hi-hat |
| T3 | F4 | Clap |
| T4 | G4 | Chord 1 |
| T5 | A4 | Chord 2 |
| T6 | B4 | Chord 3 |
| T7 | C5 | Bass |
| T8 | Effect 1 | Mode accent |
| T9 | Effect 2 | Fill |
| T10 | Effect 3 | Start/stop loop |
| T11 | Effect 4 | Special sound |

## 稳定性要求

- 上电后先校准触摸基线。
- 每次触摸触发后增加短暂防抖。
- 串口输出当前触摸通道和模式。
- 对服装模式使用更高触发阈值，减少晃动误触。

