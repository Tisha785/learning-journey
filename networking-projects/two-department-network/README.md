# Two-Department Enterprise Network Design

## Overview
Designed and implemented a routed network in Cisco Packet Tracer connecting 
two departments (ACCOUNTS and DELIVERY) using subnetting and static IP addressing.

## Topology
![Network Topology](topology-screenshot.png)

## Technologies Used
- Cisco Packet Tracer
- Cisco 1941 Router
- Cisco 2960 Switches
- Static Routing / Subnetting (VLSM)

## IP Addressing Table

| Device  | Interface           | IP Address     | Subnet Mask       | Default Gateway |
|---------|---------------------|-----------------|--------------------|------------------|
| Router0 | Gig0/0 (ACCOUNTS)   | 192.168.40.1    | 255.255.255.192    | —                |
| Router0 | Gig0/1 (DELIVERY)   | 192.168.40.65   | 255.255.255.192    | —                |
| PC0     | FastEthernet0       | 192.168.40.2    | 255.255.255.192    | 192.168.40.1     |
| PC1     | FastEthernet0       | 192.168.40.3    | 255.255.255.192    | 192.168.40.1     |
| PC2     | FastEthernet0       | 192.168.40.66   | 255.255.255.192    | 192.168.40.65    |
| PC3     | FastEthernet0       | 192.168.40.67   | 255.255.255.192    | 192.168.40.65    |

## Key Concepts Applied
- Subnetted 192.168.40.0/24 into /26 subnets to segment departmental traffic
- Configured router interfaces with `no shutdown` for interface activation
- Verified inter-departmental connectivity using ICMP (ping)
- Analyzed TTL values to confirm correct routing behavior across network segments

## Verification
Successful ping tests confirmed both intra-department and inter-department 
connectivity, with TTL decrement (128 → 127) validating packet traversal 
through the router.
