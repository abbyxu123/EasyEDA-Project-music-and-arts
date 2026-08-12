# 打板生产文件包

## 目的

这个文件定义 PCB v0.1 准备打板时应该导出的文件。不要只上传 EasyEDA 工程，生产和复刻都需要明确的导出文件。

## 必需文件

| 文件 | 说明 | 建议位置 |
|---|---|---|
| 原理图 PDF | 方便评审和工程师快速查看 | `hardware/easyeda/schematic.pdf` |
| PCB 预览图 | 展示正反面布局 | `hardware/easyeda/pcb-preview-front.png` |
| Gerber | PCB 生产文件 | `hardware/easyeda/gerber/` |
| BOM | 元件清单 | `hardware/easyeda/production/bom.csv` |
| Pick and Place | 贴片坐标 | `hardware/easyeda/production/pick-and-place.csv` |
| EasyEDA 源文件 | 可继续编辑 | `hardware/easyeda/` |

## 打板前命名建议

```text
touch-music-controller-v0.1.epro
touch-music-controller-v0.1-schematic.pdf
touch-music-controller-v0.1-gerber.zip
touch-music-controller-v0.1-bom.csv
touch-music-controller-v0.1-pnp.csv
```

## 生产备注

- 板厚：默认 1.6 mm，若服装穿戴需要更薄可后续再改。
- 铜厚：默认 1 oz。
- 阻焊颜色：首版按可读性选择，深色板要确保丝印清楚。
- 表面处理：按常规打样即可。
- SMT：首版可混合手焊和贴片，不建议把所有风险都放进 SMT。

## 下单前检查

- [ ] Gerber 在线预览无缺层。
- [ ] PCB 外形和固定孔正确。
- [ ] BOM 中每个封装和 PCB 一致。
- [ ] 极性元件方向检查过。
- [ ] USB、电池、喇叭、按键封装方向检查过。
- [ ] 触摸接口编号和固件映射一致。
- [ ] 版本号是 `v0.1`。

