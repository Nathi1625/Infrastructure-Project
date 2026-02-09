# Network Operations Runbook

## Project Overview
This runbook applies to the Core–Branch enterprise topology with VLAN segmentation, OSPF routing, secure SSH management access, and NetFlow-based traffic monitoring.  
Devices include Cisco IOS and MikroTik RouterOS platforms operating together.

---

## VLAN Troubleshooting (Cisco & MikroTik)

Verify VLAN existence (Cisco):
show vlan brief


Verify VLAN interfaces (MikroTik):
/interface vlan print


Verify trunk links (Cisco):
show interfaces trunk


Verify bridge VLAN tagging (MikroTik):
/interface bridge vlan print


Check access port VLAN assignment (Cisco):
show interfaces switchport


Check bridge ports (MikroTik):
/interface bridge port print


Verify SVI or VLAN IP status (Cisco):
show ip interface brief


Verify VLAN IP addresses (MikroTik):
/ip address print


Verify MAC learning (Cisco):
show mac address-table


Verify ARP entries (MikroTik):
/ip arp print


---

## OSPF Troubleshooting (Cisco & MikroTik)

Check OSPF neighbor state (Cisco):
show ip ospf neighbor


Check OSPF neighbors (MikroTik):
/routing ospf neighbor print


Verify OSPF process details (Cisco):
show ip ospf


Verify OSPF instance (MikroTik):
/routing ospf instance print


Verify OSPF-enabled interfaces (Cisco):
show ip ospf interface


Verify OSPF interfaces (MikroTik):
/routing ospf interface print


Verify learned OSPF routes (Cisco):
show ip route ospf


Verify learned OSPF routes (MikroTik):
/ip route print where ospf=yes


Restart OSPF process (Cisco – caution):
clear ip ospf process


Restart OSPF instance (MikroTik):
/routing ospf instance disable 0
/routing ospf instance enable 0


---

## SSH Access Troubleshooting (Cisco & MikroTik)

Verify SSH status (Cisco):
show ip ssh


Verify SSH service (MikroTik):
/ip service print


Verify VTY access configuration (Cisco):
show running-config | section line vty


Verify SSH service enablement (MikroTik):
/ip service enable ssh


Verify RSA keys exist (Cisco):
show crypto key mypubkey rsa


Verify firewall is not blocking SSH (MikroTik):
/ip firewall filter print


Test SSH connectivity:
ssh admin@172.16.10.1


---

## NetFlow / Traffic Flow Troubleshooting (Cisco & MikroTik)

Verify NetFlow export status (Cisco):
show ip flow export


Verify flow cache (Cisco):
show ip cache flow


Verify Traffic Flow is enabled (MikroTik):
/ip traffic-flow print


Verify NetFlow collector target (MikroTik):
/ip traffic-flow target print


Verify interfaces exporting flows (Cisco):
show running-config interface <interface>


Enable Traffic Flow on all interfaces (MikroTik):
/ip traffic-flow set enabled=yes interfaces=all


---

## General Routing & Connectivity Checks

Check routing table (Cisco):
show ip route


Check routing table (MikroTik):
/ip route print


Verify interface status (Cisco):
show ip interface brief


Verify interface status (MikroTik):
/interface print


Test reachability:
ping <destination-ip>


Trace path:
traceroute <destination-ip>


---

## Operational Checklist

- Physical links are UP
- VLANs exist and are correctly assigned
- Gateways are reachable
- OSPF neighbors are FULL
- Routes are present
- SSH access is secured and reachable
- NetFlow exports are received by the collector

---

## Recommended Troubleshooting Flow

1. Check interface and link status
2. Verify VLAN and IP configuration
3. Confirm OSPF neighbor relationships
4. Validate routing tables
5. Test SSH access
6. Confirm NetFlow export
7. Perform end-to-end testing
