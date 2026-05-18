# Day 2 — Technology Primer: Basic Networking

> **Source:** Simply Cyber — "Cybersecurity for Beginners" Playlist (Videos 1 & 2)  
> **Date:** 2026-05-13 

---

## 1. The OSI Model

The OSI (Open Systems Interconnection) model describes how data communicates across a network. It flows **top-down** through 7 layers.

> 💡 **Tip:** Treat the first 3 layers (Application, Presentation, Session) as one — e.g. the Web/Application Layer (browser).

---

### a) Application Layer (Layers 5–7 grouped)

The interface layer — what the user interacts with directly (e.g. a web browser).

---

### b) Transport Layer — Layer 4 (Segment Layer)

Where **transport** happens. Made up of two protocols:

| Protocol | Full Name | Type | Behaviour |
|---|---|---|---|
| **TCP** | Transmission Control Protocol | Connection-oriented | Establishes a confirmed connection before sending data |
| **UDP** | User Datagram Protocol | Connectionless | Sends traffic without confirming receipt |

**TCP vs UDP:**
- TCP is connection-oriented — it uses the **TCP Handshake** to confirm both ends are ready
- UDP sends traffic and does not verify if the other end receives it — useful for **streaming services**
- TCP is useful for **web servers** where data integrity matters

**TCP Three-Way Handshake:**

```
SYN     → 1st flag: sender initiates connection
SYN-ACK → 2nd flag: receiver acknowledges the SYN
ACK     → 3rd flag: sender confirms acknowledgement
```

**Ports** — transportation occurs through ports. A port is a unique number on a server (range: 1–65,535):

| Port | Service |
|---|---|
| **80** | Web Server (HTTP) |
| **443** | Encrypted Web Server (HTTPS) |
| **22** | Secure Shell (SSH) |

---

### c) Network Layer — Layer 3

Contains the **IP address**. Two versions exist:

| Version | Structure |
|---|---|
| **IPv4** | 4 octets; each octet is a number between 0–255 (8 bits); e.g. `192.168.1.1` |
| **IPv6** | Expanded format to accommodate more addresses |

**DNS (Domain Name Server):** Translates host names (e.g. `google.com`) into IP addresses, since the internet operates on IP addresses.

```bash
# Check the IP address of any domain
nslookup google.com
```

**RFC 1918 — Private (Non-Routable) IP Ranges:**  
Allocated non-routable IP ranges that allow organisations to control their own internal IP space.

| Range | Use Case |
|---|---|
| `10.x.x.x` | Gives the most number of IP addresses |
| `192.168.x.x` | Fewer addresses to assign — mostly home networks |

**Localhost / Loopback:** `127.0.0.1`  
Used for one's own machine — traffic goes down and back up the OSI model but stays within the same machine.

---

### d) Data Link Layer — Layer 2

Contains the **MAC (Media Access Control) address** — the wireless/wired network card identifier on a computer.

- MAC addresses are **built into the network card** and are unique to each device
- A MAC address is **6 octets of hexadecimal values**
- The **first 3 octets** identify the vendor (manufacturer)

---

### e) Physical Layer — Layer 1

Made up of **wired and wireless** transmission media — the actual cables, radio signals, and hardware.

---

## 2. Key Tools

### Wireshark

Listens to one's network stack and **copies all data as it passes over the OSI model** — used to inspect and analyse network traffic in real time.

---

## 3. One Cool Thing

> 🎙️ **CISO Cyber Security Headlines Podcast** — recommended resource for daily threat intelligence consumption.

---

## 4. Key Takeaways

- The OSI model is the foundation for understanding how data moves across any network
- TCP guarantees delivery; UDP prioritises speed over reliability
- Every device on a network has both an IP address (logical, Layer 3) and a MAC address (physical, Layer 2)
- DNS is what makes human-readable web addresses work — it is the internet's phone book
- Private IP ranges (RFC 1918) keep internal networks separate from the public internet
- Wireshark is a practical tool GRC analysts use to understand and verify network behaviour