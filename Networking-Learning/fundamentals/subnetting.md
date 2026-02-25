# Subnetting Fundamentals

## 📘 What Is a Subnet?

A subnet is a logical division of an IP network.

Instead of using one large network, subnetting splits it into smaller segments.  
This improves organization, reduces broadcast traffic, and allows routers to make better routing decisions.

Subnetting is the foundation of modern IP networking.

---

# 🧠 Understanding the Subnet Mask

The subnet mask determines:

- Which bits belong to the network
- Which bits belong to hosts

Example:

IP: `192.168.10.15`  
Mask: `/24`

This means:

- first 24 bits = network
- remaining 8 bits = hosts

Network becomes:


192.168.10.0/24


---

# 🔢 Core Subnetting Formulas

## 1️⃣ Number of Hosts


Hosts = 2^(host bits) - 2


We subtract 2 because:

- one address is the network address
- one address is the broadcast address

Example:

Mask `/26`


32 - 26 = 6 host bits
2^6 - 2 = 62 usable hosts


---

## 2️⃣ Number of Subnets

When subnetting inside a larger network:


Subnets = 2^(borrowed bits)


Example:

Original `/24`, changed to `/27`


27 - 24 = 3 borrowed bits
2^3 = 8 subnets


---

# 🔢 Block Size Formula

The block size determines how the network increments.


Block Size = 256 - Mask Value (in the interesting octet)


Example:

Mask: `255.255.255.192`


256 - 192 = 64


So networks increment by **64**:


192.168.1.0
192.168.1.64
192.168.1.128
192.168.1.192


---

# 🧩 Subnet Mask Table (Important)

| Prefix | Mask              | Block Size | Usable Hosts |
|--------|-------------------|------------|--------------|
| /30    | 255.255.255.252   | 4          | 2            |
| /29    | 255.255.255.248   | 8          | 6            |
| /28    | 255.255.255.240   | 16         | 14           |
| /27    | 255.255.255.224   | 32         | 30           |
| /26    | 255.255.255.192   | 64         | 62           |
| /25    | 255.255.255.128   | 128        | 126          |
| /24    | 255.255.255.0     | 256        | 254          |
| /23    | 255.255.254.0     | 512        | 510          |
| /22    | 255.255.252.0     | 1024       | 1022         |
| /21    | 255.255.248.0     | 2048       | 2046         |
| /20    | 255.255.240.0     | 4096       | 4094         |
| /19    | 255.255.224.0     | 8192       | 8190         |
| /18    | 255.255.192.0     | 16384      | 16382        |
| /17    | 255.255.128.0     | 32768      | 32766        |
| /16    | 255.255.0.0       | 65536      | 65534        |

---

#  How to Find Subnet Ranges

Example:

Network: `192.168.1.0/26`

Block size = 64

Subnets:


192.168.1.0
192.168.1.64
192.168.1.128
192.168.1.192


Pick subnet:


192.168.1.64/26


Range becomes:


Network: 192.168.1.64
First Host: 192.168.1.65
Last Host: 192.168.1.126
Broadcast: 192.168.1.127


---

# 💡 Quick Mental Tricks

### ✔ If mask ends with:
- 128 → jump 128
- 192 → jump 64
- 224 → jump 32
- 240 → jump 16
- 248 → jump 8
- 252 → jump 4

### ✔ Smaller subnet mask → more hosts  
### ✔ Larger prefix number → smaller network  

---

#  Why Subnetting Is Important

Subnetting enables:

- scalable network design
- smaller broadcast domains
- easier troubleshooting
- efficient IP allocation
- proper routing decisions

Without subnetting, large networks become slow, messy, and hard to route.

Subnetting is one of the most important skills in networking.
