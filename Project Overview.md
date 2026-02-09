# Network Observability Lab (GNS3 + Proxmox)

## Overview
A centralized infrastructure simulation representing a full operational IT environment. It includes virtual servers, applications, and network devices with automated logs, metrics, and network traffic, providing a shared and reliable data source for testing, demonstrations, training, and troubleshooting.

## Goals

- Simulate a hub-and-spoke enterprise network across three South African sites
- Validate connectivity, security, and monitoring
- Deploy core infrastructure:
  - Routers, switches, firewalls
  - Servers (Active Directory, SQL, Web, DHCP)
  - Endpoint PCs
- Generate telemetry data (SNMP, NetFlow, Syslog, WMI metrics)
- Aggregate data centrally for export to monitoring and AIOps platforms
- Host workloads on Proxmox and orchestrate networking with GNS3

This project simulates enterprise network telemetry, including:
- NetFlow / IPFIX
- SNMP metrics
- WMI metrics
- Syslog
- Traffic generation

## Architecture
- Proxmox hosts GNS3
- Servers are hosted across two Proxmox nodes configured as a cluster
- Routers generate NetFlow data
- Metrics are collected via SNMP
- Logs are forwarded using Syslog
- Telemetry data is visualized using Grafana

## Technologies Used
- GNS3
- Proxmox
- Cisco IOS
- MikroTik RouterOS
- NetFlow / IPFIX
- SNMP

## How to Run
1. Import the GNS3 project
2. Apply device configurations
3. Start collectors
4. Generate network traffic

## Screenshots

### GNS3 Topology
<img width="1898" height="841" alt="GNS3 Topology" src="https://github.com/user-attachments/assets/2a585ae5-2d0e-4f74-984c-3fdfbf14424a" />

### Proxmox Cluster Hosting
<img width="1901" height="905" alt="Proxmox Cluster" src="https://github.com/user-attachments/assets/a686ab88-aac6-42c8-acd4-a5e0c3cccd7c" />

### Project Flow Diagram
<img width="2890" height="3940" alt="Project Flow Diagram" src="https://github.com/user-attachments/assets/10ca388b-07ae-4cfc-a06d-e689e1649ffb" />
