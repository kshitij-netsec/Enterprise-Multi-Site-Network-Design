# Enterprise Multi-Site Network Design and Implementation

## 1. Project Overview

This project demonstrates the design and implementation of an enterprise multi-site network using Cisco Packet Tracer.

The network connects multiple sites through routers and switches, providing communication between different departments, centralized server access, VLAN segmentation, dynamic routing, and redundant Layer 2 connectivity.

The primary objective is to build and test a structured enterprise network while applying practical networking concepts.

## 2. Project Objectives

- Design a multi-site enterprise network.
- Configure VLANs for departmental segmentation.
- Implement inter-VLAN routing.
- Configure OSPF for dynamic routing between routers.
- Implement EtherChannel using LACP.
- Configure Spanning Tree Protocol (STP).
- Configure DHCP for automatic IP allocation.
- Establish connectivity between different network segments.
- Verify communication through end-to-end connectivity tests.

## 3. Network Infrastructure

The project consists of:

| Device | Quantity |
|---|---:|
| Routers | 5 |
| Layer 2 Switches | 3 |
| Servers | 1 |
| End-user PCs | 3 |

### Network Devices

**Routers:**
- WMR4
- EMR5
- WWR1
- EWR3
- SWR2

**Switches:**
- NWS3
- WWS1
- EWS2

**End Devices:**
- HR-PC
- Guest-PC
- Sales-PC
- SRV1 (Server)

## 4. VLAN Configuration and IP Addressing

The network uses VLANs to separate different departments and services.

| VLAN ID | VLAN Name | Network |
|---|---|---|
| 99 | Management | 10.1.99.0/24 |
| 100 | Server | 10.1.100.0/24 |
| 110 | Guest | 10.1.110.0/24 |
| 120 | HR | 10.1.120.0/24 |

An additional subnet is configured for the Sales network:

- Network: 10.1.80.0/25
- Gateway: 10.1.80.2
- Sales-PC: 10.1.80.3

### Important Device Addresses

| Device | Interface | IP Address |
|---|---|---|
| WMR4 | G0/0/1.100 | 10.1.100.254/24 |
| WMR4 | G0/0/1.110 | 10.1.110.254/24 |
| WMR4 | G0/0/1.120 | 10.1.120.254/24 |
| EMR5 | G0/0/1.99 | 10.1.99.253/24 |
| EWR3 | G0/0/2 | 10.1.80.2/25 |
| SRV1 | Network Interface | 10.1.100.1/24 |
| Sales-PC | Network Interface | 10.1.80.3/25 |

Refer to the separate IP addressing table for the complete interface-level addressing plan.

## 5. Technologies and Protocols Implemented

### VLANs
Virtual LANs are configured to logically separate departments and network services.

### Inter-VLAN Routing
Router subinterfaces are used to provide communication between configured VLANs.

### OSPF (Open Shortest Path First)
OSPF Process ID 1 and Area 0 are configured across the routing infrastructure to exchange network routes dynamically.

### EtherChannel (LACP)
Link Aggregation Control Protocol is used to combine multiple physical switch links into logical port-channel interfaces.

### Spanning Tree Protocol
STP provides Layer 2 loop prevention by controlling redundant paths.

### DHCP
Dynamic Host Configuration Protocol is configured to allocate IP addresses automatically to designated end-user networks.

## 6. WAN Connectivity

The routers are interconnected using point-to-point network links.

The WAN infrastructure uses /30 subnets for router-to-router connectivity.

OSPF distributes routing information across the interconnected sites, enabling communication between remote network segments.

## 7. Testing and Verification

The following commands are used to verify network operation.

| Command | Purpose |
|---|---|
| `show ip interface brief` | Check interface status and IP addresses |
| `show ip route` | Verify routing table |
| `show ip ospf neighbor` | Verify OSPF neighbor relationships |
| `show vlan brief` | Verify VLAN configuration |
| `show interfaces trunk` | Verify trunk links |
| `show etherchannel summary` | Verify EtherChannel status |
| `show spanning-tree` | Verify STP operation |
| `show ip dhcp binding` | Verify DHCP address allocation |

### Connectivity Tests

End-to-end connectivity is tested using ICMP ping.

Examples:

- HR-PC to its default gateway.
- Guest-PC to its default gateway.
- Sales-PC to its default gateway.
- Sales-PC to SRV1.
- Other reachable network devices to the server.

Successful ping responses demonstrate connectivity along the tested network paths.

## 8. Project Files

The GitHub repository contains:

- Cisco Packet Tracer project file (`.pkt`).
- Network topology screenshot.
- Router configuration files.
- Switch configuration files.
- Connectivity verification screenshots.
- IP addressing table.
- Project documentation.

## 9. Learning Outcomes

Through this project, practical experience was gained in:

- Enterprise network architecture.
- Cisco router and switch configuration.
- VLAN creation and segmentation.
- Inter-VLAN routing.
- Dynamic routing using OSPF.
- Link aggregation using LACP.
- Layer 2 loop prevention using STP.
- DHCP configuration.
- Network troubleshooting and connectivity verification.

## 10. Conclusion

This project demonstrates the implementation and testing of a multi-site enterprise network using Cisco Packet Tracer.

It combines routing, switching, VLAN segmentation, dynamic routing, link aggregation, and network troubleshooting in a simulated enterprise environment.

The project provides practical exposure to networking concepts relevant to Network Support, Network Engineering, and Network Administration roles.

---

**Tools Used:** Cisco Packet Tracer  
**Project Category:** Networking / Enterprise Network Design  
**Routing Protocol:** OSPF  
**Switching Technologies:** VLAN, STP, LACP EtherChannel