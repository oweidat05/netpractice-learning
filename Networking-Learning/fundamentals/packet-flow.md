# Packet Flow in Networks

## 📘 How Packets Actually Travel

Packets do not jump directly from source to destination.

They move step by step across devices.  
This process is called **hop-by-hop forwarding**.

---

# 🧠 Step 1 – Host Decision

The source host checks:

1. Is destination inside my subnet?
2. If yes → send directly
3. If no → send to gateway

If sending to gateway:

- host resolves gateway MAC using ARP
- frame is sent to gateway MAC address

---

# 🟢 Step 2 – Frame vs Packet

Important distinction:

- IP packet contains destination IP
- Ethernet frame contains destination MAC

At each hop:

- IP packet stays the same
- MAC addresses change

This is why routing works across networks.

---

# 🔵 Step 3 – Gateway Router

When the router receives the frame:

1. Removes Ethernet header
2. Reads destination IP
3. Looks up routing table
4. Selects best route
5. Encapsulates packet in new frame
6. Sends to next hop MAC

---

# 🔎 Step 4 – Intermediate Routers

Each router repeats:


Check destination → choose route → forward packet


The packet moves hop by hop.

Routers never guess the full path in advance.

---

# 🟣 Step 5 – Final Router

When the packet reaches destination subnet:

1. Router uses ARP to find host MAC
2. Sends packet locally
3. Host receives packet

Communication succeeds.

---

# 💡 What Happens Internally

During packet travel:

- Source IP never changes
- Destination IP never changes
- MAC address changes at every hop
- TTL decreases at each router
- Routing decision happens every hop

---

#  Real Internet Behavior

The Internet works exactly this way:

- billions of packets
- thousands of routers
- hop-by-hop decisions
- no device knows the full path

Packet flow is the core of real-world networking.
