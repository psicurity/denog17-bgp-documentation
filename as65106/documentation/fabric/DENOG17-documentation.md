# DENOG17

## Table of Contents

- [Fabric Switches and Management IP](#fabric-switches-and-management-ip)
  - [Fabric Switches with inband Management IP](#fabric-switches-with-inband-management-ip)
- [Fabric Topology](#fabric-topology)
- [Fabric IP Allocation](#fabric-ip-allocation)
  - [Fabric Point-To-Point Links](#fabric-point-to-point-links)
  - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
  - [Loopback Interfaces (BGP EVPN Peering)](#loopback-interfaces-bgp-evpn-peering)
  - [Loopback0 Interfaces Node Allocation](#loopback0-interfaces-node-allocation)
  - [ISIS CLNS interfaces](#isis-clns-interfaces)
  - [VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)](#vtep-loopback-vxlan-tunnel-source-interfaces-vteps-only)
  - [VTEP Loopback Node allocation](#vtep-loopback-node-allocation)

## Fabric Switches and Management IP

| POD | Type | Node | Management IP | Platform | Provisioned in CloudVision | Serial Number |
| --- | ---- | ---- | ------------- | -------- | -------------------------- | ------------- |
| DENOG17 | pe | as65106-1 | 172.100.100.121/24 | cEOS-lab | Provisioned | DENOG17BEEF124 |
| DENOG17 | pe | as65106-2 | 172.100.100.122/24 | cEOS-lab | Provisioned | DENOG17BEEF125 |
| DENOG17 | pe | as65106-3 | 172.100.100.123/24 | cEOS-lab | Provisioned | DENOG17BEEF126 |
| DENOG17 | p | as65206-cust | 172.100.100.124/24 | cEOS-lab | Provisioned | DENOG17BEEF127 |

> Provision status is based on Ansible inventory declaration and do not represent real status from CloudVision.

### Fabric Switches with inband Management IP

| POD | Type | Node | Management IP | Inband Interface |
| --- | ---- | ---- | ------------- | ---------------- |

## Fabric Topology

| Type | Node | Node Interface | Peer Type | Peer Node | Peer Interface |
| ---- | ---- | -------------- | --------- | ----------| -------------- |
| pe | as65106-1 | Ethernet1 | pe | as65106-2 | Ethernet1 |
| pe | as65106-1 | Ethernet2 | pe | as65106-3 | Ethernet1 |
| pe | as65106-2 | Ethernet2 | pe | as65106-3 | Ethernet2 |
| pe | as65106-3 | Ethernet3 | p | as65206-cust | Ethernet1 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| Uplink IPv4 Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ---------------- | ------------------- | ------------------ | ------------------ |

### Point-To-Point Links Node Allocation

| Node | Node Interface | Node IP Address | Peer Node | Peer Interface | Peer IP Address |
| ---- | -------------- | --------------- | --------- | -------------- | --------------- |
| as65106-1 | Ethernet1 | 10.106.0.0/31 | as65106-2 | Ethernet1 | 10.106.0.1/31 |
| as65106-1 | Ethernet2 | 10.106.0.2/31 | as65106-3 | Ethernet1 | 10.106.0.3/31 |
| as65106-2 | Ethernet2 | 10.106.0.4/31 | as65106-3 | Ethernet2 | 10.106.0.5/31 |
| as65106-3 | Ethernet3 | 10.106.0.14/31 | as65206-cust | Ethernet1 | 10.106.0.15/31 |

### Loopback Interfaces (BGP EVPN Peering)

| Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------- | ------------------- | ------------------ | ------------------ |
| 10.106.1.0/24 | 256 | 3 | 1.18 % |
| 10.206.2.0/24 | 256 | 1 | 0.4 % |

### Loopback0 Interfaces Node Allocation

| POD | Node | Loopback0 |
| --- | ---- | --------- |
| DENOG17 | as65106-1 | 10.106.1.1/32 |
| DENOG17 | as65106-2 | 10.106.1.2/32 |
| DENOG17 | as65106-3 | 10.106.1.3/32 |
| DENOG17 | as65206-cust | 10.206.2.1/32 |

### ISIS CLNS interfaces

| POD | Node | CLNS Address |
| --- | ---- | ------------ |
| DENOG17 | as65106-1 | 49.0001.0101.0600.1001.00 |
| DENOG17 | as65106-2 | 49.0001.0101.0600.1002.00 |
| DENOG17 | as65106-3 | 49.0001.0101.0600.1003.00 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)

| VTEP Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------ | ------------------- | ------------------ | ------------------ |

### VTEP Loopback Node allocation

| POD | Node | Loopback1 |
| --- | ---- | --------- |
