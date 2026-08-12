# Hardware

This folder stores hardware design files for the touch music PCB.

## Recommended workflow

1. Confirm the hardware architecture in `docs/hardware/hardware-spec.md`.
2. Read the engineering handoff in `docs/engineering/engineer-handoff.md`.
3. Confirm interfaces in `docs/engineering/interface-control.md`.
4. Confirm net names and test points in `docs/engineering/net-naming-and-test-points.md`.
5. Fill the actual pins in `docs/hardware/pin-map.csv`.
6. Build and test the circuit with modules or a breadboard.
7. Draw the schematic in EasyEDA.
8. Place the EasyEDA source files in `hardware/easyeda/`.
9. Run the PCB checklist in `hardware/pcb-checks/pre-fab-checklist.md`.
10. Export Gerber, BOM, and Pick and Place files only after review.

## Do not fabricate until

- Power input is checked.
- Touch inputs are labeled and separated from noisy traces.
- Audio output and amplifier power traces are reviewed.
- Mounting holes and board dimensions match the physical artwork/clothing module.
- All connector polarities are visible in silkscreen.
