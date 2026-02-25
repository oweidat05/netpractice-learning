# Level 8 – Longest Prefix Match

## 🖼️ Network Diagram
![Level 8 Diagram](../diagrams/level8.jpg)
## 📘 Overview

This example introduces one of the most important routing concepts:  
**Longest Prefix Match**.

Routers may know multiple routes that could match the same destination.  
To choose the correct one, the router selects the route with the most specific subnet mask.

---

## 🟢 Example Routes

A router might have these routes:


10.0.0.0/8

10.0.0.0/24


Both routes match the destination **10.0.0.5**.

---

##  Which Route Is Used?

The router selects:


10.0.0.0/24


because `/24` is more specific than `/8`.

This rule is called **Longest Prefix Match**.

---
