# Lab 3 — Identify & Match RAM, Storage, and Interfaces

**Exam:** CompTIA A+ Core 1 · Hardware (25%) · Beginner · ~30 min
**Date completed:** 2026-07-23
**Environment:** Prior hands-on builds · CPU-Z on the main/spare PC

---

## Objective

Demonstrate that I can identify memory generations, storage types, and their interfaces on sight and confirm them in software — the Hardware-domain identification skills this lab targets.

> **Note on approach:** I already know these distinctions from building PCs, so I documented the reference knowledge and verified it against real hardware with CPU-Z rather than re-running the walkthrough. The tables below are the study artifact.

## What I did

1. Identified RAM by **notch position** and label: generation (DDR3/DDR4/DDR5) and form factor (DIMM desktop vs SO-DIMM laptop).
2. Ran **CPU-Z** and read the **Memory** and **SPD** tabs: type, size, speed, and channel configuration (single vs dual).
3. Identified the storage drive by form factor and connector: 3.5"/2.5" SATA, M.2 SATA, or M.2 NVMe.
4. Located the **SATA ports** and the **M.2 slot** on the motherboard.
5. Wrote a one-line spec sheet for the machine: CPU, RAM type/size/speed, storage type/interface.

## RAM reference

| Generation | Pins (DIMM) | Notch | Notes |
|------------|-------------|-------|-------|
| DDR3 | 240 | Off-center (differs from DDR4) | ~1.5 V; older |
| DDR4 | 288 | Center-ish, unique position | ~1.2 V; mainstream |
| DDR5 | 288 | Different notch than DDR4 | ~1.1 V; on-module power mgmt |

- **Form factor:** DIMM = desktop; **SO-DIMM** = laptop/SFF (shorter).
- **Not interchangeable:** the notch physically prevents seating the wrong generation.
- **Channels:** matched pairs in the correct slots enable **dual-channel** (more bandwidth) — read this in CPU-Z's Memory tab.
- **ECC vs non-ECC:** ECC (error-correcting) is for servers/workstations.

## Storage reference

| Type | Form factor | Interface | Speed tier |
|------|-------------|-----------|-----------|
| HDD | 3.5" (desktop) / 2.5" (laptop) | SATA | Slowest (spinning) |
| SATA SSD | 2.5" | SATA (~6 Gb/s) | Faster |
| M.2 SATA | M.2 stick | SATA lanes | Same ceiling as SATA SSD |
| M.2 NVMe | M.2 stick | PCIe lanes | Fastest |

- **Key gotcha:** M.2 SATA and M.2 NVMe look alike but use different keying/lanes — check the slot and drive support.
- **SATA data = 7-pin**, **SATA power = 15-pin** (from Lab 2).

## What broke / how I fixed it (from real builds)

- 

## Verification (how I confirmed it worked)

- CPU-Z Memory/SPD tabs matched what I read off the physical sticks (type, size, speed, dual-channel).
- Correctly told M.2 NVMe from M.2 SATA on the board's slot.
- Produced a one-line spec sheet from memory and confirmed it against CPU-Z.

## Exam relevance (how this shows up on the A+)

- **RAM identification:** DDR3/4/5 and DIMM vs SO-DIMM by sight is common exam and PBQ content.
- **Dual-channel:** knowing matched pairs + correct slots is tested.
- **Storage interfaces:** M.2 NVMe vs M.2 SATA vs 2.5" SATA — a frequent distinction.
- **Tools:** CPU-Z / Task Manager for reading installed memory and speed.

---

*Companion to my CompTIA A+ Hands-On Lab Manual · Section B — Hardware & Mobile Devices*
