# CompTIA A+ — Hands-On Lab Journal

A working portfolio of the hands-on labs I'm completing for the **CompTIA A+** certification (exams **220-1201** & **220-1202**). Each lab turns an exam objective into something I actually built, broke, and fixed — documented so it doubles as study notes and a demonstration of real troubleshooting.

**Progress: 2 / 25 labs complete**

---

## About this repo

Reading about RAID or the malware-removal process earns partial credit; *doing* it makes the performance-based questions (PBQs) easy. This repo is my lab journal: for every lab I record what I did, what broke, how I fixed it, and how the topic shows up on the exam.

The labs are worked **in order** — each section builds on the one before, and Lab 1 sets up the VM environment reused throughout.

## My lab environment

- **Host:** Windows main PC (64 GB RAM)
- **Hypervisor:** VMware Workstation Pro (Type 2)
- **VMs:** `Win11-Lab` (Windows 11) and `Ubuntu-Lab` (Ubuntu 26.04)
- **Also used:** a spare PC for physical hardware labs, home network + router, and a printer

## Repo structure

```
Comptia_A+_Labs/
├── README.md            ← this file (progress tracker)
├── Labs/
│   ├── Lab1/README.md   ← one writeup per lab
│   ├── Lab2/README.md
│   └── ...
└── Assets/
    ├── Lab1/            ← screenshots per lab
    └── ...
```

## How each lab is documented

Every lab writeup follows the same six sections:

1. **Objective** — what the lab proves I can do
2. **What I did** — the steps, in my own words
3. **Screenshots** — evidence from the VMs / hardware
4. **What broke / how I fixed it** — real issues, written in the 7-step troubleshooting order (Lab 13)
5. **Verification** — how I confirmed it worked
6. **Exam relevance** — how the topic appears on the A+

---
 
## Progress tracker

Legend: ✅ complete · 🔄 in progress · ⬜ not started

### Section A — Build Your Lab Environment

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [1](Labs/Lab1/README.md) | Set up VMware and build Windows & Linux VMs | Core 1 & 2 · Virtualisation / OS | Beginner | 60–90 min | ✅ |
| [1b](Labs/Lab1b/README.md) | Master snapshots (your undo button) | Core 1 · Virtualisation | Beginner | 10 min | ✅ |

### Section B — Hardware & Mobile Devices (Core 1)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [2](Labs/Lab2/README.md) | Full PC teardown and rebuild | Core 1 · Hardware (25%) | Intermediate | 90 min | ✅ |
| [3](Labs/Lab3/README.md) | Identify and match RAM, storage, and interfaces | Core 1 · Hardware (25%) | Beginner | 30 min | 🔄 |
| [4](Labs/Lab4/README.md) | Simulate RAID levels | Core 1 · Hardware (25%) | Intermediate | 30 min | ⬜ |
| [5](Labs/Lab5/README.md) | Install and troubleshoot a printer | Core 1 · Hardware / Peripherals | Beginner | 30 min | ⬜ |
| [6](Labs/Lab6/README.md) | Configure a mobile device (email + security) | Core 1 · Mobile Devices (15%) | Beginner | 20 min | ⬜ |

### Section C — Networking (Core 1)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [7](Labs/Lab7/README.md) | IP addressing and the command line | Core 1 · Networking (20%) | Beginner | 30 min | ⬜ |
| [8](Labs/Lab8/README.md) | Memorise ports by using them | Core 1 · Networking (20%) | Beginner | 25 min | ⬜ |
| [9](Labs/Lab9/README.md) | Configure your home router | Core 1 · Networking (20%) | Intermediate | 40 min | ⬜ |
| [10](Labs/Lab10/README.md) | Build and test a patch cable / identify cabling | Core 1 · Networking (20%) | Beginner–Int. | 30 min | ⬜ |

### Section D — Virtualisation & Cloud (Core 1)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [11](Labs/Lab11/README.md) | Explore cloud service models hands-on | Core 1 · Virtualisation & Cloud (11%) | Beginner | 30 min | ⬜ |
| [12](Labs/Lab12/README.md) | Containers vs VMs | Core 1 · Virtualisation & Cloud (11%) | Intermediate | 30 min | ⬜ |

### Section E — Hardware & Network Troubleshooting (Core 1)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [13](Labs/Lab13/README.md) | Apply the 7-step troubleshooting method | Core 1 · Troubleshooting (29%) | Core skill | 40 min | ⬜ |
| [14](Labs/Lab14/README.md) | Diagnose common hardware/network symptoms | Core 1 · Troubleshooting (29%) | Intermediate | 40 min | ⬜ |

### Section F — Operating Systems (Core 2)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [15](Labs/Lab15/README.md) | Clean-install Windows (partitioning, MBR vs GPT) | Core 2 · Operating Systems (30%) | Intermediate | 60 min | ⬜ |
| [16](Labs/Lab16/README.md) | Tour every Windows administrative tool | Core 2 · Operating Systems (30%) | Beginner | 45 min | ⬜ |
| [17](Labs/Lab17/README.md) | Windows command line deep-dive | Core 2 · Operating Systems (30%) | Intermediate | 40 min | ⬜ |
| [18](Labs/Lab18/README.md) | Linux and macOS basics | Core 2 · Operating Systems (30%) | Beginner | 40 min | ⬜ |

### Section G — Security (Core 2)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [19](Labs/Lab19/README.md) | Practise the 7-step malware removal process | Core 2 · Security (27%) / Software TS | Core skill | 40 min | ⬜ |
| [20](Labs/Lab20/README.md) | Encryption and access control | Core 2 · Security (27%) | Intermediate | 35 min | ⬜ |
| [21](Labs/Lab21/README.md) | Spot social engineering and physical security | Core 2 · Security (27%) | Beginner | 25 min | ⬜ |

### Section H — Software Troubleshooting (Core 2)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [22](Labs/Lab22/README.md) | Repair a Windows machine that won't boot | Core 2 · Software Troubleshooting (26%) | Intermediate | 45 min | ⬜ |

### Section I — Operational Procedures (Core 2)

| Lab | Title | Domain | Level | Time | Status |
|-----|-------|--------|-------|------|--------|
| [23](Labs/Lab23/README.md) | Backups and the 3-2-1 rule | Core 2 · Operational Procedures (17%) | Beginner | 30 min | ⬜ |
| [24](Labs/Lab24/README.md) | Scripting, remote support, and documentation | Core 2 · Operational Procedures (17%) | Beginner–Int. | 40 min | ⬜ |

---

## Golden rules I follow

- **Break things on purpose** in VMs and on the spare PC — never the main computer. That's the point of a lab.
- **Snapshot before every change**, so a bad step rolls back in seconds.
- **Narrate each step** out loud. If I can teach it, I know it.
- **Keep the journal current** — date, what I did, what broke, how I fixed it. This is gold before the exam.

## A note on sensitive info

Screenshots and notes are sanitized before committing — no real passwords, license keys, public IP addresses, or personal account details. Practicing safe documentation is itself part of the A+ Security and Operational Procedures objectives.

---

*Companion to my CompTIA A+ Hands-On Lab Manual · July 2026*
