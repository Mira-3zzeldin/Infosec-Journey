## DoD Model Layers

| Layer | Maps to OSI | Protocols |
|---|---|---|
| Process/Application | Application, Presentation, Session | HTTP, HTTPS, FTP, SSH, Telnet, SMTP, DNS, DHCP, POP3, IMAP4, NetBIOS/NetBT, SNMP, LDAP, SMB/CIFS, RDP |
| Host-to-Host | Transport | TCP, UDP |
| Internet | Network | IP, ICMP, ARP, RARP |
| Network Access | Data Link, Physical | No protocols — describes access method (Ethernet, Fast Ethernet, 802.11, SONET) |

---

## Internet Layer Protocols

| Protocol | Function |
|---|---|
| IP | Logical addressing; delivers data point A to point B |
| ICMP | Error messages; used by `ping` |
| ARP | Resolves IP address → MAC address |
| RARP | Resolves MAC address → IP address |

---

## TCP vs. UDP

| Attribute | TCP | UDP |
|---|---|---|
| Connection type | Connection-oriented | Connectionless |
| Delivery guarantee | Yes (virtual circuit + acknowledgments) | No |
| Speed | Slightly slower | Slightly faster |

---

## Ports & Sockets

| Concept | Detail |
|---|---|
| Total ports | 65,536 (0–65535) |
| Well-known ports | 0–1023 |
| Registered ports | 1024–49151 |
| Free/vendor ports | 49152–65535 |
| Socket | IP address + port, e.g. `192.168.2.115:443` |

---

## Common Port Numbers (Exam-Critical)

| Service | Protocol | Port(s) |
|---|---|---|
| FTP | TCP | 20, 21 |
| SSH | TCP | 22 |
| Telnet | TCP | 23 |
| SMTP | TCP | 25 |
| DNS | TCP/UDP | 53 |
| DHCP | UDP | 67, 68 |
| HTTP | TCP | 80 |
| POP3 | TCP | 110 |
| NetBIOS/NetBT | TCP | 137–139 |
| IMAP4 | TCP | 143 |
| SNMP (not a current exam objective) | UDP | 161, 162 |
| LDAP | TCP | 389 |
| HTTPS | TCP | 443 |
| SMB/CIFS | TCP | 445 |
| RDP | TCP | 3389 |

---

## Process/Application Protocol Notes

| Protocol | Key Fact |
|---|---|
| FTP | Uploads/downloads files; plaintext credentials; anonymous login uses email as password |
| SSH | Secure replacement for Telnet; common client: OpenSSH |
| Telnet | Terminal emulation; plaintext credentials |
| SMTP | Push protocol; sends mail; uses DNS MX record to find destination server |
| DNS | Resolves hostnames → IP addresses |
| DHCP | Dynamically assigns IP configuration |
| HTTP | Plaintext web traffic |
| POP3 | Downloads mail; disconnects after download; mostly replaced by IMAP4 |
| NetBIOS/NetBT | API at OSI Layer 5; naming, datagram, session services; resolved via WINS/LMHOSTS (legacy) |
| IMAP4 | Connected mode, server-side storage, multi-client sync |
| SNMP | Monitors network devices ("agents"); current version SNMPv3 (AES, HMAC-SHA, HMAC-MD5) |
| LDAP | Directory services, based on X.500 standard; governed by ACLs |
| HTTPS | Encrypted web traffic via SSL/TLS; requires CA-issued certificate; protects data in transit only |
| SMB | File/printer sharing; originally IBM, enhanced by Microsoft |
| CIFS | Microsoft's cross-OS enhancement of SMB; Windows default file/print sharing |
| RDP | Full remote desktop control; client = Remote Desktop Connection |

---

## IPv4 Address Structure

| Concept | Detail |
|---|---|
| Address length | 32 bits, 4 octets, dotted-decimal (e.g. `192.168.10.55`) |
| Octet range | 0–255 |
| Network ID | Cannot be all 0s or all 1s |
| Host ID all 0s | Means "this network" |
| Host ID all 1s | Broadcast address ("all hosts on this network") |
| Subnet mask | Marks network vs. host bits; 1s set left to right |
| Default gateway | Router IP; required to reach outside the local network |

---

## Binary Bit Values (Single Octet)

| Position | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 |
|---|---|---|---|---|---|---|---|---|
| Decimal value | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

**Cumulative left-to-right totals:** 128, 192, 224, 240, 248, 252, 254, 255

---

## IPv4 Address Classes

| Class | First Octet | Default Mask | Networks Available | Hosts per Network |
|---|---|---|---|---|
| A | 1–127 | 255.0.0.0 | 126 | 16,777,214 |
| B | 128–191 | 255.255.0.0 | 16,384 | 65,534 |
| C | 192–223 | 255.255.255.0 | 2,097,152 | 254 |
| D | 224–239 | N/A (multicast) | — | — |
| E | 240–255 | N/A (testing) | — | — |

**Formulas:** Networks = 2ⁿ (n = network bits available) | Hosts = 2ⁿ − 2 (n = host bits)

**Loopback:** `127.0.0.1` (Class A range reserved)

---

## CIDR Notation Reference

| Subnet Mask | Notation | Subnet Mask     | Notation |
| ----------- | -------- | --------------- | -------- |
| 255.0.0.0   | /8       | 255.255.128.0   | /17      |
| 255.128.0.0 | /9       | 255.255.192.0   | /18      |
| 255.192.0.0 | /10      | 255.255.224.0   | /19      |
| 255.224.0.0 | /11      | 255.255.240.0   | /20      |
| 255.240.0.0 | /12      | 255.255.248.0   | /21      |
| 255.248.0.0 | /13      | 255.255.252.0   | /22      |
| 255.252.0.0 | /14      | 255.255.254.0   | /23      |
| 255.254.0.0 | /15      | 255.255.255.0   | /24      |
| 255.255.0.0 | /16      | 255.255.255.128 | /25      |
| —           | —        | 255.255.255.192 | /26      |
| —           | —        | 255.255.255.224 | /27      |
| —           | —        | 255.255.255.240 | /28      |
| —           | —        | 255.255.255.248 | /29      |
| —           | —        | 255.255.255.252 | /30      |

**Class restrictions:** /8–/15 → Class A only | /16–/23 → Class A or B | /24–/30 → Class A, B, or C | Nothing beyond /30 (minimum 2 host bits required)

---

## Public vs. Private Addressing

| Concept         | Detail                                                       |
| --------------- | ------------------------------------------------------------ |
| Public address  | Globally unique, routable on the Internet, must be purchased |
| Private address | Not routable on the Internet; internal use only              |

### Private IP Address Ranges

| Class | IP Range                    | Default Mask (CIDR) | Hosts        |
| ----- | --------------------------- | ------------------- | ------------ |
| A     | 10.0.0.0–10.255.255.255     | 255.0.0.0 (/8)      | 16.7 million |
| B     | 172.16.0.0–172.31.255.255   | 255.240.0.0 (/12)   | 1 million    |
| C     | 192.168.0.0–192.168.255.255 | 255.255.0.0 (/16)   | 65,534       |

---

## NAT & APIPA

| Concept               | Detail                                                   |
| --------------------- | -------------------------------------------------------- |
| NAT                   | Translates private ↔ public IP addresses; runs on router |
| Standard NAT          | One-to-one translation                                   |
| NAT Overload / PAT    | Many private addresses → one public address              |
| APIPA range           | 169.254.0.0–169.254.255.255                              |
| APIPA subnet mask     | 255.255.0.0                                              |
| APIPA trigger         | DHCP server unreachable                                  |
| APIPA behavior        | Client keeps broadcasting for DHCP server in background  |
| APIPA alternate names | Zero configuration networking, address autoconfiguration |

---

## IPv6 Address Structure

| Concept                 | Detail                                                                    |
| ----------------------- | ------------------------------------------------------------------------- |
| Address length          | 128 bits, 8 fields of 4 hex digits, colon-separated                       |
| Case sensitivity        | Not case-sensitive                                                        |
| Address types           | Unicast (one node), Anycast (nearest of several nodes), Multicast (group) |
| Interface ID length     | Last 64 bits (4 fields)                                                   |
| Network/subnet portion  | First 64 bits (typically 56-bit routing prefix + 8-bit subnet ID)         |
| Interface ID generation | Auto (MAC-based), DHCPv6, random, or manual                               |
| Broadcast               | Does not exist in IPv6; replaced by multicast                             |

### IPv6 Shorthand Rules

| Rule                                         | Example                                                                      |
| -------------------------------------------- | ---------------------------------------------------------------------------- |
| Drop leading zeroes per field                | `2001:0db8:3c4d:0012:0000:0000:1234:56ab` → `2001:db8:3c4d:12:0:0:1234:56ab` |
| Replace ONE run of all-zero fields with `::` | → `2001:db8:3c4d:12::1234:56ab`                                              |
| Double colon usage                           | Only once per address — reused = invalid/ambiguous                           |
| Slash notation                               | Same convention as IPv4, e.g. `2001:db8:3c4d:/48`                            |
| Embedded IPv4                                | `::ffff:c0a8:173` = `::ffff:192.168.1.115`                                   |

### IPv6 Reserved Address Ranges

| Address          | Use                                                               |
| ---------------- | ----------------------------------------------------------------- |
| `::` (all zeros) | Host not configured; equivalent to IPv4 0.0.0.0                   |
| `::1`            | Loopback; equivalent to IPv4 127.0.0.1                            |
| `2000::/3`       | Global unicast (Internet use)                                     |
| `FC00::/7`       | Unique local unicast                                              |
| `FE80::/10`      | Link local (IPv6's APIPA equivalent); required on every interface |
| `FF00::/8`       | Multicast                                                         |

---

## VLAN vs. VPN

| Attribute | VLAN | VPN |
|---|---|---|
| Full name | Virtual Local Area Network | Virtual Private Network |
| OSI Layer | 2 (MAC addresses) | 7 (SSL/TLS) or 3 (IPSec) |
| Device required | Managed switch | Router/firewall/VPN client-server |
| Loop prevention | Spanning Tree Protocol (STP) | N/A |
| Purpose | Segment one physical network into logical networks | Encrypt data across a public network |
| Multi-location support | Yes — same VLAN across multiple switches/buildings | Yes — connects remote users/LANs |

### VLAN + Subnet Relationship

| Concept | Detail |
|---|---|
| Recommended ratio | 1 subnet : 1 VLAN |
| Multiple subnets, one VLAN | "Super scope" — valid but harder to manage |
| Shared trait | Both break up broadcast domains |

### VPN Types

| Type | OSI Layer | Scope |
|---|---|---|
| SSL/TLS VPN | 7 (Application) | Single application only |
| IPSec VPN | 3 (Network) | Entire packet stream |

### IPSec Components

| Protocol | Function |
|---|---|
| AH (Authentication Header) | Data integrity, origin verification |
| ESP (Encapsulating Security Payload) | Encryption |

### IPSec Modes

| Mode | IP Header | Typical Use |
|---|---|---|
| Transport mode | Unencrypted (intact) | Client-to-office VPN (remote/traveling users) |
| Tunnel mode | Encrypted | Entire network behind NAT |

### Packet Structure (Layer 3)

| Part | Contains |
|---|---|
| IP header | Source/destination IP, protocol (TCP/UDP) |
| Data/payload | Actual transmitted information |
| Trailer (optional) | End-of-packet marker, error detection |
