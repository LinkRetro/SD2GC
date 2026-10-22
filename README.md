# LinkRetro SD2GC

**A ground-up redesign of the GC2SD microSD adapter for the Nintendo GameCube — new PCB, new enclosure.**

## Overview

LinkRetro SD2GC is a microSD adapter for the GameCube's **Memory Card Slot B**, used by Swiss to load games, homebrew and game data from SD instead of a memory card.

This repository holds the **v2.3** revision. It is not a small tweak of the previous board: the PCB was redesigned from scratch, and a matching custom enclosure was designed alongside it, so the finished adapter is a proper piece of hardware rather than a bare PCB sticking out of the console.

## Highlights

- **New PCB design.** The layout was redone as a 2-layer, 0.8 mm board so it sits flush in the slot. The OR gate, microSD socket and optional status LED are placed for a short, clean and manufacturable routing.
- **Custom enclosure.** A board this small only feels finished once it has a proper shell, so a 3D-printed enclosure was designed together with the PCB — both are dimensioned around each other, the card sits where it should, the LED stays visible, and the printed part locks into the slot just as cleanly as the bare board.
- **Open and buildable.** Complete KiCad sources plus a ready-to-order Gerber archive, so anyone can fabricate, modify or improve it.

## What's on the board

| Ref | Part | Notes |
| --- | --- | --- |
| U1 | 74AHC1G32 OR gate, SC-74A-5 | single-gate glue logic for the slot interface |
| J1 | SOFNG TF-004 microSD socket | `TF-SMD_TF-01A` footprint |
| R1 | 470 Ω resistor, 0603 | LED current limiting |
| D1 | LED, 0402 | optional status indicator |
| — | GameCube memory card edge connector | custom gold-finger footprint |

## Repository contents

```
gerber/LinkRetro-SD2GC-V2.3-20261014.zip   fabrication archive (Gerbers, drills, pick & place)
kicad/LinkRetro-SD2GC_2.3.kicad_sch        schematic
kicad/LinkRetro-SD2GC_2.3.kicad_pcb        PCB layout
kicad/LinkRetro-SD2GC_2.3.kicad_pro        KiCad project
kicad/Library.pretty/                      custom footprints (card edge, microSD, LED, resistor, OR gate)
kicad/packages3D/                          STEP models referenced by the layout
```

## Building one

- Order the PCB in **0.8 mm** thickness with **ENIG** finish at minimum — the board thickness and the flat gold edge connector are what make it fit the slot.
- **R1 and D1 are optional.** Leave them out if you don't want the LED or want to keep the part count minimal.
- The design is drawn in KiCad; the Gerber archive is included so no CAD work is needed to get a board made.

## Using it

- **Slot A** behaves like a normal passive SDGecko.
- **Slot B** runs in semi-passive 2.0 enhanced speed mode.
- Use a current build of [Swiss](https://github.com/emukidid/swiss-gc) — older builds do not handle the adapter the way described above.

## Enclosure

The PCB and its enclosure were developed as one product, which is why the board outline, connector overhang and LED position match the case exactly. The enclosure models are not part of this repository.

## Credits

This adapter exists because other people shared their work first:

- **Extrems** — for [SD2SP2](https://github.com/Extrems/SD2SP2), the open hardware design this whole adapter family is built on, and for years of GameCube research that made it worthwhile.
- **The GC2SD open-source authors** — for publishing their design instead of keeping it closed. This redesign started from your work, and there is no version of it without you. Thank you.
- **emukidid and the Swiss contributors** — for [Swiss](https://github.com/emukidid/swiss-gc), which is what turns a small piece of plastic and copper into something the console can actually use.

## Links

- Swiss — https://github.com/emukidid/swiss-gc
- SD2SP2 (Extrems) — https://github.com/Extrems/SD2SP2
