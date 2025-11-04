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
| DENOG17 | pe | as65107-1 | 172.100.100.125/24 | cEOS-lab | Provisioned | DENOG17BEEF128 |
| DENOG17 | pe | as65107-2 | 172.100.100.126/24 | cEOS-lab | Provisioned | DENOG17BEEF129 |
| DENOG17 | pe | as65107-3 | 172.100.100.127/24 | cEOS-lab | Provisioned | DENOG17BEEF130 |
| DENOG17 | p | as65207-cust | 172.100.100.128/24 | cEOS-lab | Provisioned | DENOG17BEEF131 |

> Provision status is based on Ansible inventory declaration and do not represent real status from CloudVision.

### Fabric Switches with inband Management IP

| POD | Type | Node | Management IP | Inband Interface |
| --- | ---- | ---- | ------------- | ---------------- |

## Fabric Topology

| Type | Node | Node Interface | Peer Type | Peer Node | Peer Interface |
| ---- | ---- | -------------- | --------- | ----------| -------------- |
| pe | as65107-1 | Ethernet1 | pe | as65107-2 | Ethernet1 |
| pe | as65107-1 | Ethernet2 | pe | as65107-3 | Ethernet1 |
| pe | as65107-2 | Ethernet2 | pe | as65107-3 | Ethernet2 |
| pe | as65107-3 | Ethernet3 | p | as65207-cust | Ethernet1 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| Uplink IPv4 Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ---------------- | ------------------- | ------------------ | ------------------ |

### Point-To-Point Links Node Allocation

| Node | Node Interface | Node IP Address | Peer Node | Peer Interface | Peer IP Address |
| ---- | -------------- | --------------- | --------- | -------------- | --------------- |
| as65107-1 | Ethernet1 | 10.107.0.0/31 | as65107-2 | Ethernet1 | 10.107.0.1/31 |
| as65107-1 | Ethernet2 | 10.107.0.2/31 | as65107-3 | Ethernet1 | 10.107.0.3/31 |
| as65107-2 | Ethernet2 | 10.107.0.4/31 | as65107-3 | Ethernet2 | 10.107.0.5/31 |
| as65107-3 | Ethernet3 | 10.107.0.14/31 | as65207-cust | Ethernet1 | 10.107.0.15/31 |

### Loopback Interfaces (BGP EVPN Peering)

| Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------- | ------------------- | ------------------ | ------------------ |
| 10.107.1.0/24 | 256 | 3 | 1.18 % |
| 10.207.2.0/24 | 256 | 1 | 0.4 % |

### Loopback0 Interfaces Node Allocation

| POD | Node | Loopback0 |
| --- | ---- | --------- |
| DENOG17 | as65107-1 | 10.107.1.1/32 |
| DENOG17 | as65107-2 | 10.107.1.2/32 |
| DENOG17 | as65107-3 | 10.107.1.3/32 |
| DENOG17 | as65207-cust | 10.207.2.1/32 |

### ISIS CLNS interfaces

| POD | Node | CLNS Address |
| --- | ---- | ------------ |
| DENOG17 | as65107-1 | 49.0001.0101.0700.1001.00 |
| DENOG17 | as65107-2 | 49.0001.0101.0700.1002.00 |
| DENOG17 | as65107-3 | 49.0001.0101.0700.1003.00 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)

| VTEP Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------ | ------------------- | ------------------ | ------------------ |

### VTEP Loopback Node allocation

| POD | Node | Loopback1 |
| --- | ---- | --------- |
