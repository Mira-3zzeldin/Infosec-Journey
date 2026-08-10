## Wi-Fi Foundational Terms

| Term | Detail |
|---|---|
| Frequency | Range of radio waves used to transmit data; measured in GHz |
| Bands | 2.4 GHz, 5 GHz, 6 GHz |
| Channel | Narrower slice of a frequency band |
| Channel width | Bandwidth of a single channel (20/40/80/160 MHz) |
| Modulation | How signal frequency/amplitude/phase is altered to carry data |
| Coding scheme | Ratio of data bits to error-correction bits |
| Spatial stream | Single data transmission carried across multiple antennas |
| PHY rate | Theoretical maximum throughput (never achieved in practice) |
| Data rate | Actual real-world throughput |
| Guard interval | Pause between transmissions |
| MCS index | Table used to calculate achievable data rate |
| SSID | Service-set identifier; the wireless network's name |
| CSMA/CA | 802.11's collision-avoidance access method |
| Back-off time | Random wait period before retransmitting after a collision |

---

## Frequencies and Channels

| Frequency | Channel Bandwidth | Max 20 MHz Channels |
|---|---|---|
| 2.4 GHz | 20 MHz (FCC defines 22 MHz) | 14 (only 1–11 usable in U.S.) |
| 5 GHz | 20/40/80/160 MHz | 40–45 |
| 6 GHz | 20/40/80/160 MHz | 59 |

| Concept | Detail |
|---|---|
| Nonoverlapping 2.4 GHz channels | 1, 6, 11 (must be ≥5 channel numbers apart) |
| 5 GHz nonoverlapping 20 MHz channels | 25 total, 24 usable |
| 5 GHz nonoverlapping 40 MHz channels (no DFS) | 12 |
| 5 GHz nonoverlapping 40 MHz channels (with DFS) | 4 (36/40, 44/48, 149/153, 157/161) |
| 802.11ac nonoverlapping 80 MHz channels (ignoring DFS) | 6 |
| 802.11ac nonoverlapping 80 MHz channels (with DFS) | 2 |
| 802.11ac nonoverlapping 160 MHz channels (with DFS) | 0 |
| UNII-1 / UNII-3 | Fully available 5 GHz Wi-Fi channels |
| UNII-2 / UNII-2 Extended | DFS-restricted 5 GHz channels |
| DFS | Dynamic Frequency Selection; detects/avoids radar interference |
| Multi-AP overlap | Minimum 10%, recommended 20% |

---

## Legacy 802.11 Standards

| Type | Frequency | PHY Rate | Modulation | Indoor Range | Outdoor Range | Ratified |
|---|---|---|---|---|---|---|
| — (original) | 2.4 GHz | 2 Mbps | FHSS/DSSS | 20 m | 100 m | 1997 |
| a | 5 GHz | 54 Mbps | OFDM | 35 m | 120 m | 1999 |
| b | 2.4 GHz | 11 Mbps | DSSS | 40 m | 140 m | 1999 |
| g | 2.4 GHz | 54 Mbps | DSSS/OFDM (64-QAM) | 40 m | 140 m | 2003 |
| n (Wi-Fi 4) | 5/2.4 GHz | 600 Mbps | OFDM/DSSS (64-QAM) | 70 m | 250 m | 2010 |

---

## Gigabit 802.11 Standards

| Version | Wi-Fi 5 | Wi-Fi 6 | Wi-Fi 6E | Wi-Fi 7 |
|---|---|---|---|---|
| Year | 2013 | 2019 | 2020 | 2024 |
| Standard | 802.11ac | 802.11ax | 802.11ax | 802.11be |
| Frequencies | 5 GHz | 2.4/5 GHz | 2.4/5/6 GHz | 2.4/5/6 GHz |
| PHY Speed | 6.9 Gbps | 9.6 Gbps | 9.6 Gbps | 46 Gbps |
| Max Channel | 160 MHz | 160 MHz | 160 MHz | 320 MHz |
| Spatial Streams | 4 | 8 | 8 | 16 |
| Modulation | 256-QAM | 1024-QAM | 1024-QAM | 4096-QAM |
| MU-MIMO | Downlink only | Up/Down | Up/Down | Up/Down |
| Security | WPA2 | WPA3 | WPA3 | WPA3 |
| Key New Feature | Beamforming | OFDMA, BSS coloring | 6 GHz band | MLO, Multi-AP |

| Concept | Detail |
|---|---|
| Wi-Fi 8 (802.11bn UHR) | Expected ratification 2028; reliability-focused, not speed |
| Real-world 802.11ac throughput | ~1.3 Gbps peak, ~800 Mbps common |
| Gigabit-class Wi-Fi range | ~30 m indoor, ~120 m outdoor (all versions) |
| Beamforming | Directs signal at client instead of broadcasting omnidirectionally |
| OFDMA | Multi-client version of OFDM; introduced in Wi-Fi 6 |
| BSS coloring | Frame tag reducing co-channel interference; Wi-Fi 6+ |
| Preamble puncturing | Isolates/ignores interference-hit channel portion; Wi-Fi 7 |

---

## 802.11 Devices

| Device | Function |
|---|---|
| Wireless router | Central connectivity + DHCP + security management |
| WAP (Wireless Access Point) | Central connectivity only; no DHCP or security management (switch analog) |
| Wireless NIC form factors | USB, PCIe, PCI |

---

## Bluetooth

| Concept | Detail |
|---|---|
| Released | 1998 |
| Use case | PAN (personal area network); not a WLAN competitor |
| Frequency | 2.4 GHz (unlicensed) |
| Classic modulation | FHSS |
| LE modulation | DSSS |
| Shared modulation scheme | GFSK (Gaussian frequency shift keying) |
| Current version | 5.4 (2023) |
| Piconet | Ad hoc network: 1 primary + up to 7 secondaries |
| Scatternet | Multiple piconets bridged by a shared device |
| Bluetooth beacon | Broadcast-only LE transmitter (marketing/navigation) |

### Bluetooth Feature by Version

| Version | BR | EDR | HS | LE | SAM |
|---|---|---|---|---|---|
| 1.x | ✓ | | | | |
| 2.x | ✓ | ✓ | | | |
| 3.x | ✓ | ✓ | ✓ | | |
| 4.x | ✓ | ✓ | ✓ | ✓ | |
| 5.x | ✓ | ✓ | ✓ | ✓ | ✓ |

| Feature | Introduced | Throughput | Notes |
|---|---|---|---|
| BR (Basic Rate) | v1.0 | 1.0 Mbps (721 Kbps real) | |
| EDR (Enhanced Data Rate) | v2.0 | 3.0 Mbps (2.1 Mbps real) | More power than BR |
| HS (High Speed) | v3.0 | 24 Mbps | Requires nearby 802.11 signal |
| LE (Low Energy) | v4.0 (IoT features in 4.2) | 270 Kbps | 1–50% power of Classic mode |
| SAM | v5.x | — | Avoids interference via sub-band switching |
| v5 range (LE) | v5.0 | — | ~240 m (800 ft) outdoor LOS; ~40 m (133 ft) indoor |

### Bluetooth Device Classes

| Class | Distance | Power Usage |
|---|---|---|
| 1 | 100 m | 100 mW |
| 2 | 10 m | 2.5 mW |
| 3 | 1 m | 1 mW |
| 4 | 0.5 m | 0.5 mW |

---

## RFID and NFC

| Name | Frequency | Distance |
|---|---|---|
| RFID Low Frequency (LF) | 125–134 kHz | 10 cm |
| RFID High Frequency (HF) | 13.56 MHz | 30 cm |
| RFID Ultra-High Frequency (UHF) | 856–960 MHz | 100 m |

| Concept | Detail |
|---|---|
| RFID components | Tag, reader, antenna |
| Passive RFID tag | No power source; draws from reader; ~25 m max range |
| Active RFID tag | Own battery/antenna; ~100 m max range |
| NFC frequency | 13.56 MHz (same as HF RFID) |
| NFC range | ~10 cm (4 in) |
| NFC data rates | 106 / 212 / 424 Kbps |
| NFC tag capacity | ~8 KB |
| NFC modes | Card Emulation, Reader/Writer, Peer-to-Peer |
| NFC P2P format/protocol | NDEF via SNEP over LLCP |
| NFC coding (106 Kbps) | Modified Miller coding |
| NFC coding (faster speeds) | Manchester coding |
| NFC encryption | None (vulnerable to on-path/relay attacks at close range) |

---

## SOHO Network Planning

| Concept | Detail |
|---|---|
| Users per AP (Wi-Fi 5 and older) | ≤30 |
| UTP max segment distance | 100 meters |
| Repeater use case | Cable run exceeds max distance |
| Router use case | Segmenting large networks |
| PoE | Power + Ethernet over one cable; fewer ports typically supported |

---

## Internet Connection Types

| Connection Type | Approx. Cost | Download Speed | Connector/Device |
|---|---|---|---|
| DSL | $20–$30 | Up to 70 Mbps | DSL modem, RJ11 to wall, RJ45 to computer |
| Cable | $20–$30 | Up to 1+ Gbps | Cable modem, F-type connector |
| Fiber | $40–$50 | Up to 2 Gbps | ONT |
| Satellite | $40–$50 | Up to 250 Mbps | Satellite dish |
| Cellular | $30–$50 | Up to 100 Mbps (LTE) / 1 Gbps (mmWave) | Cell tower |
| WISP | $40–$150 | 6–50 Mbps | Fixed dish/antenna, line-of-sight |

| Concept | Detail |
|---|---|
| DSL upload/download | ~20 Mbps up / ~70 Mbps down max (asymmetric) |
| DSL voice frequency | 0–4 kHz |
| DSL upstream frequency | 25.875–138 kHz |
| DSL downstream frequency | 138–1,104 kHz |
| Naked DSL | DSL without active landline (surcharge applies) |
| Dial-up (POTS) max speed | 56 Kbps |
| Cable spec | DOCSIS |
| Cable shared network size | 100–2,000 customers |
| Fiber types | FTTH (full fiber), FTTN (fiber to node), FTTC (fiber to curb) |
| Fiber max length | ~40 km (25 mi) |
| Satellite latency | 250–350 ms (vs. 10–30 ms cable/DSL) |
| Satellite orbit round trip | ~35,000 km |
| Satellite architecture | Point-to-multipoint |
| Ping time | Gaming term for propagation delay |
| 3G max throughput | ~500 Kbps (theoretical ~7 Mbps later) |
| 4G introduced | 2008 |
| 4G IMT-Advanced spec | 100 Mbps high-mobility / 1 Gbps low-mobility |
| 4G LTE real-world | 10–20 Mbps down / 3–10 Mbps up |
| 4G LTE theoretical max | 300 Mbps down / 75 Mbps up |
| 4G LTE cell range | ~3.1 mi (5 km) optimal rural; ~19 mi (30 km) usable |
| WiMAX standard | 802.16 (lost to LTE) |
| 5G first modem | 2016 |
| 5G broad rollout | 2019 |
| 5G theoretical peak | 20 Gbps |
| 5G LTE average speed | ~490 Mbps (7–9x faster than 4G) |
| 5G LTE frequency range | 600 MHz–6 GHz |
| 5G mmWave frequency range | 24–86 GHz |
| 5G mmWave range limit | ~0.5 mile |
| 5G categories | eMBB, URLLC, mMTC |
| 6G expected specs / networks | ~2028 specs / ~2030 networks |
| WISP frequency options | Unlicensed: 900 MHz, 2.4/5/24/60 GHz; Licensed: 6–80 GHz |

---

## Internal Network Connections: Cable Comparison

| Characteristic | Twisted Pair | Fiber-Optic |
|---|---|---|
| Transmission rate | Cat 5e: 1 Gbps; Cat 6/6a/7: 10 Gbps; Cat 8: 25–40 Gbps | 1–40 Gbps |
| Max length | 100 m (328 ft) | ~40 km (25 mi) |
| Flexibility | Very flexible | Fair |
| Ease of installation | Very easy | Difficult |
| Connector | RJ45 | SC, ST, LC, and others |
| Interference (security) | Susceptible | Not susceptible |
| Overall cost | Inexpensive | Expensive |

| Concept | Detail |
|---|---|
| Minimum recommended cabling today | Cat 6 |
| EMI sources | Fluorescent lights, microwaves, motors, power lines |
| Wired vs. wireless speed/security | Wired generally faster and more secure |
| Realistic current Wi-Fi choices | Wi-Fi 7, Wi-Fi 6, Wi-Fi 5 |

---

## Installing Network Infrastructure

| Concept | Detail |
|---|---|
| Static IP requirement | Must also manually set DNS server |
| Broadcast limitation | Clients can broadcast for DHCP, not for DNS |
| Default gateway | Required for any Internet/remote access |
| APIPA range | 169.254.x.x |
| APIPA capability | Local communication only; no Internet/remote access |
| Plenum cable | Required in air-handling spaces (non-PVC, non-toxic when burned) |
| Fluorescent light rule | Never route cable directly across them (EMI) |
| Cable labeling | Always label both ends |
| DSL/cable modem/ONT config | Minimal; ISP-managed |

---

## Wireless Router Security Configuration

| Concept | Detail |
|---|---|
| Wi-Fi Alliance 5-step setup | Change SSID → change admin credentials → select security (WPA3/WPA2/AES) → set strong passphrase → configure clients to match |
| Default router IP (common) | 192.168.1.1 or 192.168.0.1 |
| Open access point | Default SSID/credentials/IP scheme, no encryption |
| SSID hiding | Does NOT increase security |
| MAC filtering | Light security; defeated by MAC spoofing |

### Wireless Encryption Protocols

| Protocol | Year | Key Mechanism | Notes |
|---|---|---|---|
| WEP | — | Static 40/128-bit key | Deprecated/flawed |
| WPA | 1999 (adoption ~2003) | TKIP — 128-bit dynamic per-packet key | Replaced WEP; stopgap to WPA2 |
| WPA2 | — | CCMP (based on AES) | AES/CCMP terms interchangeable |
| WPA3 | 2018 (mandatory July 2020) | SAE (Personal); AES-GCM, 256-bit key derivation (Enterprise) | Resistant to dictionary attacks |

| Concept | Detail |
|---|---|
| Personal mode | Local device handles authentication (SOHO) |
| Enterprise mode | Centralized via RADIUS server (larger networks) |
| Nonoverlapping 2.4 GHz trio | 1, 6, 11 |
| Multi-AP overlap | Min 10%, recommended 20% |
| Firmware updates | Apply after initial configuration; patch security holes |

---

## Firewalls, NAT, and UPnP

| Concept | Detail |
|---|---|
| Firewall sides | Public (Internet-facing), Private (internal) |
| Screened subnet | Optional third firewall port/zone for public+private resources |
| Network-based firewall | Protects entire network; standalone hardware |
| Host-based firewall | Protects single machine; software (e.g., Windows Defender Firewall) |
| ACL | Access control list; filters by IP, port, domain |
| Default deny | Block all unless explicitly allowed |
| Default allow | Allow all unless explicitly blocked |
| Whitelist (allow list) | Default deny except listed entries |
| Blacklist (block list) | Default allow except listed entries |
| Port triggering | Inbound allowed on a port only after matching outbound request |
| NAT | Private IP → public IP (technically one-to-one) |
| Overloading / PAT / port forwarding | Many-to-one NAT (multiple private clients, one public IP) |
| DNAT | Private address pool → routable address pool; exposes internal resource externally |
| UPnP port | UDP 1900 |
| UPnP protocol | Simple Service Discovery Protocol |
| UPnP requirement | Client must be a DHCP client |
| UPnP risk | No authentication mechanism |
| UPnP best practice | Disable, especially on WAN-facing interface |
