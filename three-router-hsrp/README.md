# HSRP high-availability lab utilizing three routers and two VLANs

## Overview 

- Demonstration of the behavior of HSRP utilizing three routers configured across two VLANs. One router is active in each VLAN, and the priorities are set to control failover behavior.

## Topology
- PC1: VLAN 10 - 192.168.10.10/24 DG 192.168.10.254
- PC2: VLAN 20 - 192.168.20.10/24 DG 192.168.20.254
- SW1: VLANs 10 and 20
- R1: VLAN 10 - 192.168.10.1 VLAN 20 - 192.168.20.1
- R2: VLAN 10 - 192.168.10.2 VLAN 20 - 192.168.20.2
- R3: VLAN 10 - 192.168.10.3 VLAN 20 - 192.168.20.3

## HSRP Configuration Summary
- VLAN 10
  HSRP Group: 10
  HSRP VIP: 192.168.10.254
  R1 Priority: 120 (Active)
  R2 Priority: 100 (Standby)
  R3 Priority: 90 (Backup)
- VLAN 20
  HSRP Group: 20
  HSRP VIP: 192.168.20.254
  R1 Priority: 100 (Standby)
  R2 Priority: 120 (Active)
  R3 Priority: 90 (Backup)

## Files Included
- README.md: This documentation
- R1-config.txt, R2-config.txt, R3-config.txt: Device configurations
- three-router-hsrp.drawio: Network diagram
- three-router-hsrp.drawio.png: Network diagram
- three-router-hsrp.pkt: Packet Tracer file

