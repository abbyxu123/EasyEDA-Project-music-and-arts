# Hardware

This folder stores hardware design files for the touch music PCB.

## Recommended workflow

1. Confirm the hardware architecture in `docs/hardware/hardware-spec.md`.
2. Fill the actual pins in `docs/hardware/pin-map.csv`.
3. Build and test the circuit with modules or a breadboard.
4. Draw the schematic in EasyEDA.
5. Place the EasyEDA source files in `hardware/easyeda/`.
6. Run the PCB checklist in `hardware/pcb-checks/pre-fab-checklist.md`.
7. Export Gerber, BOM, and Pick and Place files only after review.

## Do not fabricate until

- Power input is checked.
- Touch inputs are labeled and separated from noisy traces.
- Audio output and amplifier power traces are reviewed.
- Mounting holes and board dimensions match the physical artwork/clothing module.
- All connector polarities are visible in silkscreen.

