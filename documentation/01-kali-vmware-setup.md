# Kali Linux on VMware – Setup Guide

## Overview
This document describes how I installed and configured Kali Linux on VMware Workstation as part of my cybersecurity home lab.

## Prerequisites
- VMware Workstation Player / Pro installed on host (Windows).
- Kali Linux VMware image downloaded from https://www.kali.org/get-kali/.
- Minimum host specs:
  - 8 GB RAM (16 GB recommended)
  - 4+ CPU cores
  - 50+ GB free disk space (SSD preferred)

## Step 1 – Download Kali VMware Image
- Visited https://www.kali.org/get-kali/.
- Under “Virtual Machines”, selected **VMware (64-Bit)** and downloaded the `.7z` archive.

## Step 2 – Extract and Open in VMware
- Extracted `.7z` file using 7-Zip.
- Opened VMware Workstation.
- Used **File → Open a Virtual Machine** and selected the `.vmx` file from the extracted folder.
- When prompted, chose **“I Copied It”** to regenerate MAC/UUID.

## Step 3 – Adjust VM Settings
Before powering on:
- RAM: increased to **4 GB**.
- CPU: set to **2 cores**.
- Network adapter: **NAT** (for internet access).
- Display memory: at least **128 MB**.

## Step 4 – Power On and Login
- Powered on the VM.
- Logged in with default credentials:
  - Username: `kali`
  - Password: `kali`

## Step 5 – System Update and Tools Installation
Inside Kali terminal:

```bash
sudo apt update
sudo apt full-upgrade -y

sudo apt install -y open-vm-tools open-vm-tools-desktop
sudo systemctl enable --now open-vm-tools

sudo apt install -y git curl wget net-tools
```

## Step 6 – Basic Validation
- Verified internet access:
  ```bash
  ping -c 4 8.8.8.8
  ```
- Verified VMware tools:
  - Checked resolution change, copy-paste between host and guest.

## Notes & Lessons Learned
- Using pre-built VMware image saved time compared to ISO install.
- NAT network is sufficient for initial learning; will move to isolated networks later.
- Snapshots will be used before major changes (future improvement).
