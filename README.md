# VLAN Trunk Configuration – Cisco Packet Tracer

## 📌 Project Overview

This project demonstrates **VLAN configuration and trunking between Cisco switches** using Cisco Packet Tracer.

The lab focuses on creating multiple VLANs, assigning switch ports to the appropriate VLANs, and configuring a **trunk link** between switches to carry traffic from multiple VLANs.

## 🎯 Objectives

- Create and configure VLANs
- Assign switch ports to VLANs
- Configure an IEEE 802.1Q trunk link
- Connect multiple switches using a trunk
- Understand VLAN traffic across switches
- Verify VLAN and trunk configurations
- Troubleshoot VLAN connectivity

## 🖥️ Network Topology

```text
                 Trunk Link
        =========================
        |                       |
   +---------+              +---------+
   | Switch 1|--------------| Switch 2|
   +---------+              +---------+
      |   |                    |   |
    VLAN 10                 VLAN 10
    VLAN 20                 VLAN 20
```

The trunk link allows traffic from multiple VLANs to travel between the switches over a single physical connection.

## 🧩 VLAN Configuration

The lab uses multiple VLANs to logically separate network traffic.

| VLAN | Purpose |
|------|---------|
| VLAN 10 | Network Segment 1 |
| VLAN 20 | Network Segment 2 |
| VLAN 30 | Network Segment 3 |

> VLAN IDs and port assignments can be modified according to the lab requirements.

## ⚙️ Configuration

### 1. Create VLANs

```bash
enable
configure terminal

vlan 10
name VLAN10

vlan 20
name VLAN20

vlan 30
name VLAN30
```

### 2. Assign Access Ports

Example:

```bash
interface fa0/1
switchport mode access
switchport access vlan 10
```

Another VLAN:

```bash
interface fa0/2
switchport mode access
switchport access vlan 20
```

### 3. Configure Trunk Port

The connection between the switches is configured as a trunk:

```bash
interface fa0/24
switchport mode trunk
```

The trunk allows multiple VLANs to pass between the switches.

## 🔍 Verification Commands

### Check VLANs

```bash
show vlan brief
```

### Check Trunk Configuration

```bash
show interfaces trunk
```

### Check Interface Status

```bash
show ip interface brief
```

### Test Connectivity

```bash
ping <destination-ip>
```

## 📚 Key Learnings

Through this lab, I practiced:

- VLAN creation and configuration
- Access port configuration
- Trunk port configuration
- Switch-to-switch connectivity
- VLAN segmentation
- 802.1Q trunking
- VLAN troubleshooting
- Basic Cisco IOS commands

## ⚠️ Important Concept

A **trunk link does not remove VLAN separation**.

For example:

```text
VLAN 10 ─────────────┐
                     │
                     │ Trunk
                     │
VLAN 20 ─────────────┤──────── Switch 2
                     │
VLAN 30 ─────────────┘
```

Multiple VLANs can travel through the trunk, but the VLANs remain logically separated.

If devices in **different VLANs** need to communicate with each other, **Inter-VLAN Routing** is required using a router or Layer 3 switch.

## 🧪 Lab Practice

This Packet Tracer project was created as part of my **CCNA hands-on networking practice**.

The lab helped me understand how VLANs are created, how access ports are assigned, and how trunk links carry multiple VLANs between switches.

## 📁 Project File

```text
Vlan Trunk Task.pkt
```

Open the `.pkt` file using **Cisco Packet Tracer** to view and test the complete topology.

## 🚀 Skills Practiced

- Cisco Packet Tracer
- VLAN Configuration
- Trunk Configuration
- Access Ports
- Switch Configuration
- 802.1Q
- Network Segmentation
- Connectivity Testing
- Basic Network Troubleshooting
- Cisco IOS CLI

## 👨‍💻 CCNA Journey

This project is part of my **CCNA Journey** and hands-on networking practice.

> **Learning networking one lab at a time. 🌐**
