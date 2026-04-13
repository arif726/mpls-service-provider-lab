# IP Addressing Plan

This document defines the complete IP addressing scheme for the MPLS Service Provider Lab.

---

## 🧠 Design Principles

* Loopbacks are used for router-id, BGP, and MPLS control plane
* /30 subnets are used for point-to-point links
* Provider core is separated from customer networks
* IP scheme is structured for easy identification

---

# 🔵 Loopback Addressing

| Router | Role | Loopback0      |
| ------ | ---- | -------------- |
| R1     | P    | 1.1.1.1/32     |
| R2     | P    | 2.2.2.2/32     |
| R3     | P    | 3.3.3.3/32     |
| R4     | P    | 4.4.4.4/32     |
| R5     | PE   | 5.5.5.5/32     |
| R6     | PE   | 6.6.6.6/32     |
| R7     | PE   | 7.7.7.7/32     |
| R8     | PE   | 8.8.8.8/32     |
| R9     | RR   | 9.9.9.9/32     |
| R10    | RR   | 10.10.10.10/32 |

---

# 🟢 Provider Core Links (/30)

| Link   | Network       | Side A | IP         | Side B | IP         |
| ------ | ------------- | ------ | ---------- | ------ | ---------- |
| R5–R1  | 10.51.0.0/30  | R5     | 10.51.0.1  | R1     | 10.51.0.2  |
| R5–R3  | 10.53.0.0/30  | R5     | 10.53.0.1  | R3     | 10.53.0.2  |
| R1–R6  | 10.16.0.0/30  | R1     | 10.16.0.1  | R6     | 10.16.0.2  |
| R6–R2  | 10.62.0.0/30  | R6     | 10.62.0.1  | R2     | 10.62.0.2  |
| R1–R2  | 10.12.0.0/30  | R1     | 10.12.0.1  | R2     | 10.12.0.2  |
| R1–R9  | 10.19.0.0/30  | R1     | 10.19.0.1  | R9     | 10.19.0.2  |
| R9–R2  | 10.92.0.0/30  | R9     | 10.92.0.1  | R2     | 10.92.0.2  |
| R1–R3  | 10.13.0.0/30  | R1     | 10.13.0.1  | R3     | 10.13.0.2  |
| R2–R4  | 10.24.0.0/30  | R2     | 10.24.0.1  | R4     | 10.24.0.2  |
| R3–R10 | 10.31.10.0/30 | R3     | 10.31.10.1 | R10    | 10.31.10.2 |
| R10–R4 | 10.10.4.0/30  | R10    | 10.10.4.1  | R4     | 10.10.4.2  |
| R3–R4  | 10.34.0.0/30  | R3     | 10.34.0.1  | R4     | 10.34.0.2  |
| R3–R8  | 10.38.0.0/30  | R3     | 10.38.0.1  | R8     | 10.38.0.2  |
| R8–R4  | 10.84.0.0/30  | R8     | 10.84.0.1  | R4     | 10.84.0.2  |
| R2–R7  | 10.27.0.0/30  | R2     | 10.27.0.1  | R7     | 10.27.0.2  |
| R4–R7  | 10.47.0.0/30  | R4     | 10.47.0.1  | R7     | 10.47.0.2  |

---

# 🔴 Customer Edge Links (/30)

| Link   | Network        | Side A | IP          | Side B | IP          |
| ------ | -------------- | ------ | ----------- | ------ | ----------- |
| R5–R15 | 172.16.15.0/30 | R5     | 172.16.15.1 | R15    | 172.16.15.2 |
| R5–R11 | 172.16.11.0/30 | R5     | 172.16.11.1 | R11    | 172.16.11.2 |
| R6–R13 | 172.16.13.0/30 | R6     | 172.16.13.1 | R13    | 172.16.13.2 |
| R7–R12 | 172.16.12.0/30 | R7     | 172.16.12.1 | R12    | 172.16.12.2 |
| R8–R14 | 172.16.14.0/30 | R8     | 172.16.14.1 | R14    | 172.16.14.2 |

---

# 📌 Notes

* Core links are used for IGP, MPLS, and BGP control plane
* CE links are used for customer routing (no MPLS)
* Loopbacks will be used for:

  * OSPF Router-ID
  * LDP Router-ID
  * BGP peering (RR design)

---
