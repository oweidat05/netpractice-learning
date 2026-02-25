# Level 1 – Same Subnet Communication

![Same Subnet Diagram](../diagrams/level1.png)

## 📘 Overview

This example shows two independent local networks (LAN 1 and LAN 2).  
In each LAN, devices can communicate directly without a router because they belong to the same subnet.

Understanding this concept is essential in networking, since direct communication only happens when devices share the same network range.

---

## 🟢 Network 1 – LAN 1

- **Host A:** 192.168.10.2/24  
- **Host B:** 192.168.10.3/24  

With a `/24` subnet mask, the network address becomes:

```
192.168.10.0/24
```

This means both devices are inside the same subnet.  
Because of that, they can communicate directly using ARP without any intermediate device.

---

## 🔵 Network 2 – LAN 2

- **Host C:** 172.16.5.10/16  
- **Host D:** 172.16.8.20/16  

With a `/16` mask, the network becomes:

```
172.16.0.0/16
```

Both devices belong to the same network range, so they can also communicate directly without a router.
