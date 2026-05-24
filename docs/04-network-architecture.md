# Network Architecture

## Architecture Goals

The proposed network architecture is designed around the following principles:

- Security through segmentation
- Simplified management
- Scalability
- Operational consistency
- Centralized visibility
- Reduced lateral network exposure
- Future growth readiness

---

## High-Level Design

The proposed architecture separates infrastructure into dedicated trust zones using VLAN segmentation and managed switching.

Core architecture components include:

- Centralized gateway/firewall
- Managed PoE switching
- Segmented wireless infrastructure
- Dedicated management networks
- Isolated IoT environments
- Dedicated guest access
- Centralized storage connectivity

---

## Core Infrastructure Components

| Component | Role |
|---|---|
| Gateway / Firewall | Routing, segmentation, policy enforcement |
| Managed Switches | VLAN-aware switching and PoE distribution |
| Wireless Access Points | Segmented wireless connectivity |
| NAS Storage | Centralized storage platform |
| UPS Systems | Power protection and graceful shutdown support |

---

## Proposed Logical Topology

### Core Flow

```text id="jlwm83"
Internet
    ↓
Gateway / Firewall
    ↓
Core Managed Switch
    ↓
Access Switches / APs / NAS / Clients