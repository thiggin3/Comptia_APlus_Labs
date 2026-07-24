# Lab 2 — PC Teardown & Rebuild (Component / Connector Reference)

**Exam:** CompTIA A+ Core 1 · Hardware (25%) · Intermediate · ~90 min
**Date completed:** 2026-07-23
**Environment:** Prior hands-on builds + spare PC for verification

---

## Objective

Demonstrate the Hardware domain competency this lab targets — identifying every internal component, connector, and the POST/boot behavior — and confirm I can name them in CompTIA's terms, not just assemble a working machine.

> **Note on approach:** I've built several PCs before starting this manual, so rather than stage a teardown I don't need, I documented my existing build experience and verified the exam-facing knowledge (connector names, POST behavior, beep codes) against a spare PC. The reference tables below are the study artifact.

## What I did

1. Confirmed I can name every major component aloud: motherboard, CPU (under the cooler), RAM, storage drive(s), PSU, expansion cards, cooling fans.
2. Reviewed the ESD safety I already practice: anti-static wrist strap clipped to bare metal, PSU unplugged, power button held ~5 s to drain residual charge, parts in a tray.
3. Walked the full disassembly/reassembly order from memory and checked it against the spare PC — including reseating RAM until both clips snap and releasing the PCIe latch before pulling a card.
4. Verified I can identify each **power connector** by shape (table below).
5. Confirmed the machine **POSTs** and reaches BIOS/OS, and reviewed what beep codes and no-POST symptoms mean.

## Component & connector reference

### Power connectors (PSU)

| Connector | Pins | Goes to |
|-----------|------|---------|
| ATX main power | 24-pin (20+4) | Motherboard |
| CPU / EPS power | 4-pin or 8-pin (4+4) | Motherboard, near CPU |
| PCIe power | 6-pin / 8-pin (6+2) | Graphics card |
| SATA power | 15-pin flat | Drives (SSD/HDD) |
| Molex (legacy) | 4-pin | Fans, older drives |

### Data / expansion interfaces

| Interface | Notes |
|-----------|-------|
| SATA data | 7-pin L-shaped; ~6 Gb/s; drives |
| M.2 | Slot on board; **SATA** vs **NVMe** keying differs — NVMe uses PCIe lanes, much faster |
| PCIe x16 / x1 | Expansion slots; x16 for GPUs (has a retention latch) |
| Front-panel header | Power SW, reset SW, power LED, HDD LED — polarity matters on LEDs |

## What broke / how I fixed it (from real builds)

- 

## POST & beep-code quick reference

- **POST** = Power-On Self-Test, the firmware's hardware check before boot.
- **Beeps / no display** patterns vary by BIOS vendor, but common meanings:
  - Continuous / repeating beeps → RAM not detected or seated
  - One long + two/three short → video/GPU problem
  - No beep, no power → PSU, front-panel power connector, or dead board
- Symptom triage: **no power** (PSU / power connector / switch) vs **no POST** (RAM / CPU / board) vs **no display** (GPU / cable / monitor).

## Verification (how I confirmed it worked)

- Named every component and power connector correctly without notes.
- Spare PC POSTs and boots to the OS after a reseat pass.
- Can state the difference between M.2 SATA and M.2 NVMe, and between the 24-pin and 8-pin CPU connectors.

## Exam relevance (how this shows up on the A+)

- **Connector identification** is heavily tested — know 24-pin ATX, 4/8-pin CPU, PCIe 6/8-pin, SATA power vs SATA data on sight.
- **ESD safety** (wrist strap, anti-static bag, equipment grounding) is a recurring safety objective.
- **POST / boot symptoms** and beep codes feed directly into the troubleshooting labs (13 & 14) and PBQs.
- **Storage interfaces:** M.2 NVMe vs SATA, and drive form factors, appear in both hardware and performance questions.

---

*Companion to my CompTIA A+ Hands-On Lab Manual · Section B — Hardware & Mobile Devices*
