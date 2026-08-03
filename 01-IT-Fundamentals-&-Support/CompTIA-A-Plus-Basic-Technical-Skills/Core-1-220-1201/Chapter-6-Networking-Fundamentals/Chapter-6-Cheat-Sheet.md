## Network Types

|Type|Scope|Key Notes|
|---|---|---|
|LAN|Single office/building|First PC LAN: ShareNet (Novell); early LANs capped ~30 computers/1 floor|
|WAN|Buildings, states, countries, continents|Multiple dispersed LANs connected; emerged late 1980s|
|PAN|Personal/small scale|Bluetooth (IEEE 802.15.1); ad hoc; also infrared|
|MAN|City or large campus|Managed by internal IT staff (vs. WAN's public carrier)|
|SAN|Storage-only network segment|No clients/general servers; uses Fibre Channel; block storage|
|WLAN|Wireless LAN|Clients connect via WAP (wireless access point)|

---

## Bluetooth / PAN Specs

|Term|Detail|
|---|---|
|Standard|IEEE 802.15.1 (WPAN)|
|Connection mode|Ad hoc (no central AP required)|
|Piconet|Up to 7 connected devices|
|Scatternet|Two or more linked piconets|

---

## SAN / Storage Model

|Concept|Detail|
|---|---|
|SAN transport|Fibre Channel (high-speed)|
|Storage model|Block storage — fixed-size chunks, unique IDs, no folder hierarchy needed|
|Contrast|File storage — named files in folder hierarchy (Windows/macOS default)|
|SAN benefits|Relieves other network loads, fast access, easily expandable/hot-swappable|
|SAN downsides|Complex setup, higher cost|
|Best use case|Large structured databases|

---

## Network Components

|Component|Definition|
|---|---|
|Server|Centralizes control of resources/security|
|Dedicated server|One specific service only (e.g., web server)|
|Nondedicated server|Provides service(s) + local access (dual workstation/server role)|
|Workstation / client|Needs NIC + cabling (or wireless) + client software|
|Resource|Printers, disk storage/file access, applications|
|AUP|Acceptable Use Policy — expected user behavior|
|SLA|Service Level Agreement|
|NDA|Nondisclosure Agreement|

---

## Resource Access Models

|Model|Also Called|Admin|Best Fit|
|---|---|---|---|
|Peer-to-peer|Workgroup|None centralized; each PC self-managed|≤10–20 computers, no growth expected|
|Client-server|Server-based / Domain|Centralized via domain controller|>10–20 computers, growth/security priority|

---

## Topologies — Advantages & Disadvantages

|Topology|Advantages|Disadvantages|
|---|---|---|
|Bus|Cheap, easy to install|Hard to reconfigure; 1 break = network down|
|Star|Cheap, easy install/reconfigure, resilient to single cable failure|Central device = single point of failure; costlier than bus|
|Ring|Efficient, easy to install|Hard/expensive to reconfigure; 1 node loss = ring down|
|Mesh|Best fault tolerance|Extremely complex/expensive to reconfigure|
|Hybrid|Combines best features of others|Complex (less than mesh)|

---

## Topology Details

|Topology|Layout|Formula/Note|
|---|---|---|
|Bus|Single shared trunk cable|Least cabling used|
|Star|Hub-and-spoke, central switch/hub|Most common today|
|Ring|Circular, unidirectional|Token Ring = physical star, logical ring|
|Mesh|Every device to every device|Cables = x(x − 1) ÷ 2|
|Hybrid|Mix of topologies|Most real networks today are hybrid + heterogeneous|

---

## OSI Model — 7 Layers (Top to Bottom)

|#|Layer|Function|
|---|---|---|
|7|Application|Network service access (file/print services, apps)|
|6|Presentation|Format, protocol conversion, compression, encryption, character sets|
|5|Session|Establish/maintain/end sessions|
|4|Transport|Flow control, segmentation; TCP verifies delivery|
|3|Network|Logical addressing, packets, routing/path selection|
|2|Data Link|Frames, MAC address; sublayers = MAC + LLC|
|1|Physical|Bits as electrical/light/radio signals|

**Mnemonic:** All People Seem To Need Data Processing (Layer 7 → 1)

**Published:** ISO, 1984. Theoretical reference model — no real network runs "the OSI protocol."

**Encapsulation:** Each layer adds a header (sometimes trailer) going down the stack (sender); each layer strips its own header/trailer going up the stack (receiver).

---

## IEEE 802 Standards

| Standard         | Covers                 | Key Facts                                                                        |
| ---------------- | ---------------------- | -------------------------------------------------------------------------------- |
| 802.3            | Ethernet (CSMA/CD)     | Original: bus topology, 50-ohm coax, 10 Mbps baseband; now up to 400 Gbps on MMF |
| 802.11n/ac/ax/be | Wireless               | ac = Wi-Fi 5, ax = Wi-Fi 6, be = Wi-Fi 7                                         |
| 802 (general)    | Splits Data Link layer | LLC sublayer (data link mgmt) + MAC sublayer (collisions, physical addressing)   |

---

## Media Access Methods

|Method|Type|How It Works|
|---|---|---|
|CSMA/CD|Contention-based|Carrier Sense + Multiple Access + Collision Detection; retry after random wait|
|CSMA/CA|Contention-based|Avoids collisions proactively (listen before send); used by wireless Ethernet|
|Token passing|Controlled access|Only token holder may transmit (e.g., Token Ring)|

**CSMA/CD weakness:** >100 computers/segment → collisions outnumber successful transmissions.

---

## MAC Address

|Attribute|Detail|
|---|---|
|Length|48 bits|
|Format|Hexadecimal, e.g. `40-61-86-E4-5A-9A`|
|Assigned by|IEEE (blocks to manufacturers) → hardwired into NIC|
|OUI|First 24 bits / 3 hex pairs = manufacturer identifier|
|OSI Layer|2 (Data Link) — MAC sublayer|
|Mutability|Physically permanent; software spoofing possible (legit + malicious uses)|
|View command (Windows)|`ipconfig /all` → Physical Address|
|View command (macOS)|`ifconfig` → HWaddr / ether|
|View command (Linux)|`ip link show` → link/ether|

---

## NIC (Network Interface Card)

|Aspect|Detail|
|---|---|
|Role|Physical computer-to-cabling interface; prepares/sends/receives/controls data flow|
|Compatibility|Match fastest available bus type (e.g., PCIe over PCI); USB NICs for laptops/troubleshooting|
|Duplex|Half-duplex = one direction at a time; Full-duplex = simultaneous send/receive (2x throughput on Gigabit: 1 Gbps vs. 500 Mbps)|
|Drivers|OS/card-specific; operate at MAC sublayer of Data Link layer; managed via Device Manager ➤ Driver tab|
|Agreement needed between NICs|Frame size, data-before-confirmation amount, inter-transmission timing, confirmation wait time, transmission speed, same media access method|

---

## Coaxial Cable — RG Types

|RG #|Popular Name|Ethernet Std|Max Distance|Core|Impedance|
|---|---|---|---|---|---|
|RG-8|Thicknet|10Base5|500 m|Solid copper|50 ohms|
|RG-58 A/U|Thinnet|10Base2|185 m|Stranded copper|50 ohms|
|RG-6|Satellite/cable TV|N/A|304 m|Solid copper (1.0mm)|75 ohms|
|RG-59|Analog cable TV|N/A|228 m|Solid copper (0.762mm)|75 ohms|

**Connectors:** BNC (quarter-twist lock, thinnet) | F-type (threaded/screw, RG-6/RG-59, cable TV) — *F-type is the named Exam Objective 3.2 connector*

**Ethernet naming:** Leading number = max Mbps | "Base" = baseband | Trailing char = distance (×100m) or medium (T = twisted pair)

**Plenum rating:** Teflon-type coating, no toxic gas when burned, required in air-circulating spaces (applies to ALL cable types)

---

## Twisted Pair Cable — Category Specs

|Category|Max Bandwidth|Max Distance|Notes|
|---|---|---|---|
|Cat 3|10 Mbps|100 m|Legacy|
|Cat 5|100 Mbps|100 m|Released 1995|
|Cat 5e|1 Gbps|100 m|First copper cable at 1 Gbps|
|Cat 6|10 Gbps|55 m|Min. backbone grade|
|Cat 6a|10 Gbps|100 m|Official Cat 6 successor (NOT "Cat 6e" — unofficial)|
|Cat 7|10 Gbps|100 m|Every pair shielded; a.k.a. Class F|
|Cat 8|25/40 Gbps or 10 Gbps|30 m or 100 m|Always shielded; Class I (8.1)=RJ45; Class II (8.2)=TERA|

**Standard max UTP/STP run: 100 meters (328 ft).** Buy nothing older than Cat 5e.

**STP vs UTP:** STP = extra braided foil shielding (less interference); UTP = no outer shield (most common in practice)

---

## Twisted Pair Connectors & Terminations

|Item|Detail|
|---|---|
|RJ11|2 pairs / 4 wires — landline phones|
|RJ45|4 pairs / 8 wires — UTP networking|
|Attachment tool|Crimper (RJ connectors) / Punchdown tool (blocks)|
|66 block|Older, analog telephone|
|110 block|Modern, higher density, less crosstalk|
|Ethernet splitter|Splits 2-pair sets — caps at 100 Mbps, not recommended|

---

## T568A / T568B Wiring Standards

|Pin|T568A|T568B|
|---|---|---|
|1|White/Green|White/Orange|
|2|Green|Orange|
|3|White/Orange|White/Green|
|4|Blue|Blue|
|5|White/Blue|White/Blue|
|6|Orange|Green|
|7|White/Brown|White/Brown|
|8|Brown|Brown|

**Patch (straight-through):** same standard both ends → host-to-switch/hub
**Crossover:** T568A one end / T568B other end (crosses pins 1↔3, 2↔6) → host-to-host, switch-to-switch, hub-to-hub, host-to-router
**Never changes between standards:** Blue & Brown pairs (pins 4,5,7,8)

---

## Direct Burial

|Spec|Detail|
|---|---|
|Cable type|STP + waterproof sheathing|
|Burial depth|6–8 feet|
|Placement|Away from electrical lines; use conduit (e.g., PVC)|

---

## Fiber-Optic Cable

|Type|Core Size|Light Source|Distance|Bandwidth Behavior|
|---|---|---|---|---|
|Multimode (MMF)|Larger|LED (or laser for high-BW)|Shorter (~150m–2km)|Higher available bandwidth, shorter range|
|Single-mode (SMF)|Smaller|Laser|Longer (40–140km)|Lower bandwidth, longer range|

**Grading:** SMF = OS1/OS2 | MMF = OM1–OM5 (higher = more capable)

**Letter Designations:**

|Abbrev|Meaning|Max Distance|Cable|
|---|---|---|---|
|VR|Very short reach|100 m|MMF|
|SR|Short reach|300 m|MMF|
|DR|Distance reach|500 m|MMF/SMF|
|FR|Far reach|2 km|SMF|
|LR|Long reach|10 km|SMF|
|ER|Extended reach|40 km|SMF|
|ZR|Zero-dispersion reach|80–140 km|SMF|

Trailing number (e.g., SR4) = parallel channel count.

**Fiber Connectors:**

| Connector | Full Name            | Mechanism              | Notes                                                   |
| --------- | -------------------- | ---------------------- | ------------------------------------------------------- |
| ST        | Straight Tip         | Twist-and-lock         | Developed by AT&T; historically most-used               |
| SC        | Subscriber Connector | Latched/push-release   | "Square connector"; works with SMF or MMF               |
| LC        | Lucent Connector     | Mini form factor (MFF) | Developed by Lucent; popular for Fibre Channel/SAN/GigE |

---

## Connectivity Devices by OSI Layer

|Device|OSI Layer|Function|
|---|---|---|
|Repeater/Extender|1|Amplify & resend signal, no data inspection|
|Hub (passive)|1|Electrically connects ports, no power source, no extension capability|
|Hub (active)|1|Powered amplification, can extend network length|
|Patch panel|—|No intelligence, just connects cables (rack-mounted)|
|Switch (unmanaged)|2|Forwards by MAC address, no configuration|
|Switch (managed)|2 (or 3 if multilayer)|Adds QoS, redundancy (STP), port mirroring, VLANs, via SNMP|
|Router|3|Connects networks, routing tables, IP-based, breaks up broadcast domains|

---

## Modems / Fiber / Wireless Terminal Devices

|Device|Medium|Notes|
|---|---|---|
|Dial-up modem|Phone line|Modulates/demodulates analog; max 56 Kbps; obsolete (not an exam objective; RJ11 still is)|
|Cable modem|TV coax (F-type)|Digital, not a true modem|
|DSL modem|Telephone line|Digital, not a true modem|
|ONT|Fiber|Converts optical → electrical for internal network|
|WAP|Wireless (802.11)|Lets clients join network wirelessly|

---

## Switch Managed Features

|Feature|Purpose|
|---|---|
|QoS|Prioritize specific traffic (e.g., VoIP)|
|Redundancy|Multiple paths via Spanning Tree Protocol (STP)|
|Port mirroring|Copy port traffic to a second port for monitoring|
|VLAN|Logically segment one physical switch into isolated networks|

---

## Firewalls

|Concept|Detail|
|---|---|
|Sides|Public (Internet-facing) / Private (internal) / optional 3rd port = screened subnet (formerly DMZ)|
|Screened subnet use|Web/FTP/email relay servers needing partial external access|
|Types|Network-based (protects group/whole network) / Host-based (protects one machine, e.g. Windows Defender Firewall)|
|Default behavior|Default deny — block all unless explicitly authorized|
|Rule set|ACL (Access Control List) — filters by IP, port, domain name|

---

## Power over Ethernet (PoE) Standards

|Name|Year|IEEE Standard|Max Power|Devices|
|---|---|---|---|---|
|PoE|2003|802.3af|15.4 W|Wireless APs, static cameras, VoIP phones|
|PoE+|2009|802.3at|30 W|Alarm systems, PTZ cameras, video IP phones|
|PoE++ (Type 3)|2018|802.3bt (Type 3)|60 W|Multi-radio APs, videoconferencing equipment|
|PoE++ (Type 4)|2018|802.3bt (Type 4)|100 W|Laptops, flat-screen monitors, LED lighting|

**Delivery methods:** PoE injector (single device) vs. PoE-enabled switch (multiple devices, costs more)

---

## Windows Commands Referenced

|Command|Purpose|
|---|---|
|`Get-NetAdapter \| Select Name, InterfaceDescription, Status, LinkSpeed`|View NIC info|
|`ipconfig`|View Default Gateway (router)|
|`tracert <host>`|Trace router hops to destination|
|`wf.msc`|Open Windows Defender Firewall (Advanced Security)|
|`Get-NetFirewallRule`|Query firewall rules|
|`Get-NetFirewallProfile \| Select Name, DefaultInboundAction`|Check default deny/allow per profile|
