# Lab 1 — Set Up VMware and Build Windows & Linux VMs

**Exam:** CompTIA A+ Core 1 & 2 · Virtualisation / OS · Beginner · ~60–90 min
**Date completed:** 2026-07-23
**Environment:** Windows main PC · VMware Workstation Pro 17 · Win11 Evaluation + Ubuntu 26.04 Desktop

---

## Objective

Stand up a reusable lab environment by building two virtual machines — a Windows 11 VM and an Ubuntu Linux VM — on a Type 2 hypervisor. Every later lab reuses these VMs, so the goal is a clean, snapshot-ready baseline.

## What I need

- Windows main PC with hardware virtualisation (VT-x / AMD-V) enabled in BIOS/UEFI
- VMware Workstation Pro installed
- Windows 11 Evaluation ISO (Microsoft Evaluation Center) and Ubuntu Desktop ISO (ubuntu.com)
- ~60 GB free disk space, internet connection

## What I did

1. Confirmed virtualisation was enabled in the host BIOS/UEFI (VMware won't run 64-bit guests without VT-x/AMD-V).
2. Downloaded the Windows 11 Evaluation ISO and the Ubuntu Desktop ISO. (An ISO is a disk image used to install an OS.)
3. Created the Windows VM: **New Virtual Machine → Typical → Installer disc image (ISO)**, pointed it at the Win11 ISO.
4. Named it `Win11-Lab`, set a 50 GB disk, then **Customize Hardware**: 4096 MB RAM, 2 processor cores.
5. Powered on and completed the Windows install.
6. Repeated the process for `Ubuntu-Lab`: pointed at the Ubuntu ISO, 2048 MB RAM, 25 GB disk, and installed.
7. Made sure each VM is updated.
8. In each guest, ran **VM → Install VMware Tools** for better resolution, clipboard sharing, and drag-and-drop.

## Screenshots

> Save images under `assets/lab-01/` and reference them here.

- ![Windows VM Settings](Assets/Lab1/Windows_VM_Settings.jpg)
- ![Windows VM Desktop](Assets/Lab1/Windows_VM_Desktop.jpg)
- ![Ubuntu VM Settings](Assets/Lab1/Ubuntu_VM_Settings.jpg)
- ![Ubuntu VM Desktop](Assets/Lab1/Ubuntu_VM_Desktop.jpg)

## What broke / how I fixed it

Documented in the 7-step spirit (Lab 13) — these were real issues, not the guide's happy path:

- **Did not have enough RAM on Host computer (16gb)**
  *Cause*: While trying to start the VMs, the Host showed an error that explained the lack of resources
  *Resolution*: Upgraded Host to 64GB of RAM

- **Ubuntu boot showed `Bluetooth: hci0: ... Opcode 0x0c12 failed: -38` errors.**
  *Cause:* the virtualised Bluetooth controller doesn't fully implement the "Write Class of Device" HCI command, so the kernel logs the malformed response (`-38` = ENOSYS, "not implemented"). 
  *Resolution:* harmless in a VM — boot continues normally. Silenced it with `sudo systemctl disable --now bluetooth` since Bluetooth isn't needed in the guest.

- **Ubuntu installer appeared frozen at "Copying files…".**
  *Cause:* the copy/unpack stage stalls when RAM is tight; the progress bar is not linear. 
  *Resolution:* Bumped up RAM from 2GB to 8GB. (A corrupt ISO produces the same symptom, so verifying the ISO's SHA256 is the first check if it truly hangs.)

- **Windows 11 setup pushed a mandatory Microsoft account.**
  *Cause:* recent OOBE hides the local-account path when a network is present. 
  *Resolution:* Used `Shift+F10` → `start ms-cxh:localonly`.

## Verification (how I confirmed it worked)

- Both VMs boot to their desktops.
- `winver` in the Windows guest confirms the edition/version.
- VMware Tools active: clipboard sharing and dynamic resolution work in both guests.
- Windows VM shows the TPM present and firmware set to UEFI in the VM settings.

## Exam relevance (how this shows up on the A+)

- **Hypervisor types:** VMware Workstation is a **Type 2** (hosted) hypervisor — runs on top of an OS. Contrast with **Type 1** (bare-metal, e.g. ESXi, Hyper-V).
- **Requirements:** hardware virtualisation (VT-x/AMD-V) must be enabled; know that VMs need adequate RAM/CPU/disk allocated from the host.
- **Windows 11 requirements:** TPM 2.0, UEFI/Secure Boot — common exam and PBQ material.
- **Firmware/partitioning:** UEFI pairs with GPT disks; legacy BIOS with MBR (revisited in Lab 15).
- **Purpose of VMs:** sandboxing, testing, and cross-platform labs — "break things safely."

---

*Companion to the CompTIA A+ Hands-On Lab Manual · Section A — Build Your Lab Environment*
