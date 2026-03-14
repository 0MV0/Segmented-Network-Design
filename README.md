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
*  **Router:** Add a router and set a default gateway to simulate a "true" network and internet connection.
* **Firewall:** Firewall is crutial to any scalable network.
