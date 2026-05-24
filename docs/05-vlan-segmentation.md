# VLAN Segmentation

## Purpose

This document defines the proposed VLAN segmentation strategy for the SMB modernization project.

The goal is to separate devices and services by trust level, operational role, and security risk.

---

## Proposed VLAN Layout

| VLAN | Name | Purpose |
|---|---|---|
| 10 | Management | Network device administration |
| 20 | Core Infrastructure | Firewalls, switches, controllers, infrastructure services |
| 30 | Storage | NAS and storage-related systems |
| 40 | Services | Internal application and utility services |
| 50 | Trusted Clients | Business workstations and trusted user devices |
| 60 | Media Devices | TVs, displays, and media endpoints |
| 70 | IoT | Cameras, smart devices, and low-trust endpoints |
| 80 | Lab | Testing, staging, and experimental systems |
| 90 | Quarantine | Unknown, untrusted, or temporary devices |
| 99 | Guest | Guest wireless access |

---

## Segmentation Goals

- Reduce lateral movement risk
- Isolate guest and IoT traffic
- Protect management interfaces
- Separate storage from general client traffic
- Simplify firewall rule design
- Improve troubleshooting visibility

---

## Trust Boundary Model

| Zone | Trust Level |
|---|---|
| Management | Highest |
| Core Infrastructure | High |
| Storage | High |
| Services | Medium |
| Trusted Clients | Medium |
| Media | Low |
| IoT | Low |
| Guest | Untrusted |
| Quarantine | Restricted |

---

## Firewall Policy Direction

Default approach:

- Deny inter-VLAN traffic by default
- Allow only required communication paths
- Restrict management access to administrative devices
- Allow guest traffic to internet only
- Allow IoT devices only to required services
- Log and review exceptions

---

## Summary

The VLAN strategy creates clear trust boundaries and supports a more secure, scalable, and manageable network architecture.