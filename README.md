## 🌐 Project Overview

In this project I wanted to demonstrate a Layer 3 switched network architecture designed for fast and efficient traffic management. It features a segmented network environment using **VLANs**, automated IP addressing via **DHCP**, and loop prevention through **Spanning Tree Protocol (STP)** as well as **Acess Control List (ACL)** for VLAN privacy and safety.

The core of the design relies on **Inter-VLAN routing** configured on three L3 switches, removing the need for an external router for internal traffic.

### 🚀 Key Features
*   **VLAN Segmentation:** Network split into 3 distinct VLANS to improve security and reduce traffic congestion.
*   **Inter-VLAN Routing:** High-speed routing between subnets performed directly at the hardware level by using(SVI).
*   **Redundancy & Loop Prevention:** STP (IEEE 802.1D/802.1w) implementation to ensure a loop-free topology.
*   **Dynamic Addressing:** Automated IPv4 allocation for end-devices across all VLANs.
*   **Acess Control List:** Actively controls & makes sure VLANS communicate only with the allowed ip domains.

### 🛠️ Technologies Used
*   **Hardware:** 3x Layer 3 Managed Switches (e.g., Cisco 3560 series).
*   **Protocols:** 802.1Q (Trunking), STP, DHCP, SVI (Switch Virtual Interfaces).
*   **Tools:** Cisco Packet Tracer.

### 🌟 Future improvements
*  **ACL Optimisation:** Use object groups to make the network more scalable and easier to manage.
* **Firewall:** Firewall is useful for L3 switches to act as their NAT for security.


## A brief overlook of the main configurations.
# VLANS, Subnets, gateways and DHCP
| VLAN ID & NAME  | Subnet /24| Gateway IP /24 | DHCP Range /24 |   
| ------------- | ------------- | ------------- | ------------- |
| VLAN10 - HR  | 192.168.10.0 | 192.168.10.1 (F1_SW1), 192.168.10.2 (F2_SW1), 192.168.10.3 (F2_SW1) | 192.168.10.4 - 192.168.10.255 |
| VLAN20 - Engineering  | 192.168.20.0 | 192.168.20.1 (F1_SW1), 192.168.20.2 (F2_SW1), 192.168.20.3 (F2_SW1)| 192.168.20.4 - 192.168.20.255 |
| VLAN30 - Management  | 192.168.30.0 | 192.168.30.1 (F3_SW1, 192.168.30.2 (F2_SW1), 192.168.30.3 (F3_SW1))| 192.168.30.4 - 192.168.30.255| 

# ACL
I used ACL because in this particular topology it was crucial because by defualt L3 switches don't isolate VLAN traffic so without ACL you could ping devices that weren't in in same VLAN as you (which isn't supposed to happen), therefore I had to implement ACL policies for each of the VLANS to ensure proper traffic filtering.
# Access Control Policies:
All the policies were using Extended ACL and filtering the incoming packets.  
VLAN 10 has perminion to communicate with any ip besides the ones from the VLAN 20 and VLAN 30 subnet.  
VLAN 20 has perminion to communicate with any ip besides the ones from the VLAN 10 and VLAN 30 subnet.  
VLAN 30 has perminion to communicate with any ip besides the ones from the VLAN 20 and VLAN 10 subnet.  

## Config Hierarchy
/topologies - visual plan of the topology.  
/configs - detailed lists with configs for each switch.  
/labs - a ready Packet Tracer file.  





