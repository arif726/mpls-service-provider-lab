# Topology Overview

## 📌 Introduction

This lab represents a full **Service Provider (ISP) network architecture** designed to simulate real-world MPLS-based backbone operations.
The topology includes core, edge, control-plane, and customer layers to reflect how modern ISPs deliver scalable and reliable services.

---

## 🧠 Network Architecture

The network is divided into four logical layers:

1. **Core Layer (P Routers)**
2. **Provider Edge Layer (PE Routers)**
3. **Control Plane Layer (Route Reflectors)**
4. **Customer Layer (CE Routers)**

Each layer has a specific role in maintaining scalability, performance, and service separation.

---

## 🔵 Core Layer (P Routers)

**Routers:** R1, R2, R3, R4

### Role:

* Form the high-speed backbone of the network
* Transport traffic across the provider network
* Forward labeled packets using MPLS

### Characteristics:

* No customer awareness (no VRF)
* Run IGP (OSPF)
* Run MPLS & LDP
* Optimized for fast packet forwarding

### Real-World Analogy:

Core routers in a national ISP backbone connecting major cities or data centers.

---

## 🟢 Provider Edge Layer (PE Routers)

**Routers:** R5, R6, R7, R8

### Role:

* Connect customer networks to the ISP
* Maintain customer separation using VRF
* Exchange routes using MP-BGP
* Impose and remove MPLS labels

### Characteristics:

* Participate in both:

  * Provider network (IGP + MPLS)
  * Customer network (VRF + routing)
* Handle L3VPN services

### Real-World Analogy:

Edge routers located at regional POPs (Points of Presence) serving enterprise customers.

---

## 🟡 Control Plane Layer (Route Reflectors)

**Routers:** R9, R10

### Role:

* Simplify BGP design by eliminating full mesh
* Reflect VPNv4 routes between PE routers
* Maintain scalable control plane

### Characteristics:

* Do not carry customer traffic directly
* Centralized BGP route distribution
* Improve scalability and manageability

### Real-World Analogy:

Route Reflector clusters deployed in ISP core data centers.

---

## 🔴 Customer Layer (CE Routers)

**Routers:** R11, R12, R13, R14, R15

### Role:

* Represent customer networks
* Connect to PE routers
* Exchange routes via static routing, OSPF, or eBGP

### Characteristics:

* No MPLS awareness
* No participation in provider core
* Each CE belongs to a specific customer

### Real-World Analogy:

Enterprise branch routers, bank branches, corporate offices, or remote sites.

---

## 🔗 Connectivity Design

### Core Connectivity

* Full mesh-like structure between P routers for redundancy
* Multiple paths ensure high availability

### PE Connectivity

* Each PE connects to at least two core routers
* Ensures failover and load balancing

### RR Connectivity

* Route Reflectors connect to core routers
* Provide centralized BGP control

### Customer Connectivity

* Each CE connects to a PE router
* Enables service delivery through MPLS L3VPN

---

## 🔄 Redundancy and High Availability

The topology is designed with multiple redundant paths:

* Core routers interconnected
* PE routers connected to multiple core nodes
* Dual Route Reflectors for BGP resilience

This ensures:

* Fault tolerance
* Load balancing
* High network availability

---

## ⚙️ Technologies Implemented

This topology supports the following technologies:

* OSPF (IGP Underlay)
* MPLS & LDP (Label Distribution)
* MP-BGP (VPNv4 Address Family)
* Route Reflector Architecture
* VRF (Virtual Routing and Forwarding)
* L3VPN (Customer Traffic Separation)
* Traffic Engineering (TE)

---

## 🎯 Objective of the Topology

The purpose of this lab is to:

* Understand real-world ISP network design
* Build scalable MPLS backbone architecture
* Implement multi-customer VPN services
* Gain hands-on experience with advanced routing and switching technologies

---

## 📌 Summary

This topology provides a complete simulation of a service provider network, combining:

* Core transport network
* Edge service delivery
* Scalable control plane design
* Customer network integration

It serves as a foundation for learning, experimentation, and real-world network engineering practices.
