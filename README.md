# Cybersecurity Home Lab

## Overview
This repository documents my personal cybersecurity home lab used to practice SOC analyst skills.  
The lab is built on **VMware Workstation** with **Kali Linux** and planned extensions like pfSense, Windows, and Wazuh SIEM.

## Goal
- Build a safe, isolated environment to practice:
  - Network segmentation
  - Log collection and analysis
  - Basic threat detection
  - Incident response workflows
- Document the setup so I can reproduce and improve it over time.

## Lab Components (Current)
- Virtualization: VMware Workstation Player / Pro
- Endpoint VMs:
  - Kali Linux (attack / testing machine)
  - Windows 10/11 client (planned)
  - pfSense firewall (planned)
  - Wazuh / Splunk SIEM (planned)

## Network Design (Summary)
- Initial setup:
  - Single NAT network for all VMs (internet access for updates and tools).
- Future design:
  - Isolated virtual networks:
    - LAN: 192.168.100.0/24
    - DMZ: 192.168.10.0/24
    - SERVERS: 192.168.20.0/24
    - ADMIN: 192.168.99.0/24 (host access)
  - Firewall rules to control traffic between segments.

> Note: This is a personal learning lab. No real production systems or user data are used.

## Repository Structure
- `documentation/` – Step-by-step setup guides and notes.
- `diagrams/` – Network topology and architecture diagrams.
- `configs/` – Sample configuration files (firewall, SIEM, etc.).
- `scripts/` – Automation and utility scripts.
- `logs/` – Sample sanitized logs for analysis practice.
- `tools/` – List of tools used with links and brief descriptions.

## How to Use This Repo
- Follow the setup guides in `documentation/` to build a similar lab.
- Use sample configs and logs for practice.
- Refer to diagrams to understand network flow and segmentation.

## Skills Practiced
- Virtualization and network design
- Linux (Kali) basics and security tooling
- Planning for firewall configuration and SIEM setup
- Basic detection and alerting (future)
