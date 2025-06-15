# HSRP, LACP, DHCP, DNS, and Simulated 8.8.8.8 Lab

The purpose of this lab was to simulate a small enterprise network with the following features:
- HSRP failover for gateway redundancy
- LACP between switches and distribution layer
- Basic DNS services
- Basic DHCP services

## Lab Features

- HSRP on MLS1 and MLS2 attached to VLAN 10 and VLAN 20
- LACP (2 port) between SW1 and MLS1 and MLS2
- LACP (2 port) between SW2 and MLS1 and MLS2
- DHCP server assigning addresses to 10.10.0.0/24 and 10.20.0.0/24
- DNS server with static A record mapping google.com to 8.8.8.8 (this is not real-world accurate)
- Simulated 8.8.8.8 server

## IP Addressing and Subnets

Device - Interface - IP Address    - Description
PC1    - Fa0       - DHCP          - VLAN 10
PC2    - Fa0       - DHCP          - VLAN 20
MLS1   - VLAN 10   - 10.10.0.11    - VLAN 10
MLS1   - VLAN 10   - 10.10.0.254   - HSRP Active (Priority 110)
MLS1   - VLAN 20   - 10.20.0.11    - VLAN 20
MLS1   - VLAN 20   - 10.20.0.254   - HSRP Backup (Priority 90)
MLS1   - F0/3      - 10.40.0.1     - R1/MLS1 Subnet
MLS2   - VLAN 10   - 10.10.0.12    - VLAN 10
MLS2   - VLAN 10   - 10.10.0.254   - HSRP Backup (Priority 90)
MLS2   - VLAN 20   - 10.10.0.12    - VLAN 20
MLS2   - VLAN 20   - 10.10.0.254   - HSRP Active (Priority 110)
MLS2   - F0/4      - 10.50.0.1     - R1/MLS2 Subnet
R1     - G6/0      - 8.8.8.9       - Simulated 8.8.8.8 Subnet
R1     - G7/0      - 10.40.0.2     - R1/MLS1 Subnet
R1     - G8/0      - 10.50.0.2     - R1/MLS2 Subnet
R1     - G9/0      - 10.60.0.1     - R1/DHCP Subnet
MLS1   - F0/1      - 10.30.0.5/24  - DHCP Server

## Files

- hsrp, lacp, dhcp, dns, and simulated 8.8.8.8.pkt
- hsrp, lacp, dhcp, dns, and and simulated 8.8.8.8.drawio
- hsrp, lacp, dhcp, dns, and and simulated 8.8.8.8.drawio.png

## Notes

- This lab is designed for Cisco Packet Tracer
- HSRP priorities are intentionally asymmetrical
- DNS record for google.com refrencing 8.8.8.8 does not reflect real-world behavior


