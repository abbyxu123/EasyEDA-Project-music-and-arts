# 系统方框图

## v0.1 总体结构

```text
                       ┌────────────────────┐
                       │  USB-C Power/Input  │
                       └─────────┬──────────┘
                                 │
                       ┌─────────▼──────────┐
                       │ Power Switch / Reg  │
                       └─────────┬──────────┘
                                 │
        ┌────────────────────────┼────────────────────────┐
        │                        │                        │
┌───────▼───────┐        ┌───────▼───────┐        ┌───────▼───────┐
│   ESP32 MCU   │ I2C    │    MPR121     │ Touch  │ Touch Pads    │
│               ├────────► 12ch Touch IC ├────────► T0-T11        │
└───────┬───────┘        └───────────────┘        └───────────────┘
        │
        │ UART / I2S / GPIO
┌───────▼───────┐
│ Audio Module  │
│ or Audio DAC  │
└───────┬───────┘
        │
┌───────▼───────┐
│   Amplifier   │
└───────┬───────┘
        │
┌───────▼───────┐
│ Speaker/Audio │
└───────────────┘
```

## 外部作品连接

```text
Painting touch areas:
  Conductive paint -> wire/copper tape -> PCB T0-T5

Wearable touch areas:
  Conductive thread/fabric -> detachable connector -> PCB T6-T9

Control:
  Mode button -> switch painting/wearable/performance mode
  Status LED -> power/touch/playback feedback
```

## 信号分区

| 分区 | 内容 | PCB 设计要求 |
|---|---|---|
| 触摸区 | MPR121、T0-T11 接口 | 远离功放、电源开关、大电流线 |
| 主控区 | ESP32、下载、调试 | 靠近 USB 和调试接口 |
| 音频区 | 音频模块、功放、喇叭接口 | 靠板边，远离触摸输入 |
| 电源区 | USB、电池、稳压、开关 | 走线加宽，正负极标注清楚 |
| 机械区 | 固定孔、板边、接口方向 | 服务画框和服装模块袋 |

