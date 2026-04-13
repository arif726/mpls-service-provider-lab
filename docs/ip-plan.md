# IP Addressing Plan

## Loopback Addresses

| Router | Loopback       |
| ------ | -------------- |
| R1     | 1.1.1.1/32     |
| R2     | 2.2.2.2/32     |
| R3     | 3.3.3.3/32     |
| R4     | 4.4.4.4/32     |
| R5     | 5.5.5.5/32     |
| R6     | 6.6.6.6/32     |
| R7     | 7.7.7.7/32     |
| R8     | 8.8.8.8/32     |
| R9     | 9.9.9.9/32     |
| R10    | 10.10.10.10/32 |

---

## Core Links (/30)

| Link   | Network       |
| ------ | ------------- |
| R1–R2  | 10.12.0.0/30  |
| R1–R3  | 10.13.0.0/30  |
| R1–R6  | 10.16.0.0/30  |
| R1–R9  | 10.19.0.0/30  |
| R2–R4  | 10.24.0.0/30  |
| R2–R7  | 10.27.0.0/30  |
| R2–R9  | 10.92.0.0/30  |
| R3–R4  | 10.34.0.0/30  |
| R3–R8  | 10.38.0.0/30  |
| R3–R10 | 10.31.10.0/30 |
| R4–R7  | 10.47.0.0/30  |
| R4–R8  | 10.84.0.0/30  |
| R4–R10 | 10.10.4.0/30  |

---

## Design Notes

* Loopbacks are used for router-id, BGP, and MPLS control plane
* /30 addressing is used for point-to-point links
* Core network is designed for redundancy and scalability

