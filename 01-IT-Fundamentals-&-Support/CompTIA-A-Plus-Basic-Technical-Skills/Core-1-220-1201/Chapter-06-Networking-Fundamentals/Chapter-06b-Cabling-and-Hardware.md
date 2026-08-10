## 🔧 The Big Idea: Welcome to the Wireworks District

Chapter 6a covered how the Courier Kingdom is organized — its branches, its governance, its seven-checkpoint sorting rules. None of that matters, though, without physical infrastructure to actually move things. Enter the **Wireworks District**: the Kingdom's utility operation, responsible for laying every pipe and running every pumping station that keeps signals flowing from building to building.

Every building taps into the District through its own **House Valve** (its NIC). From there, signals travel through one of three main pipe types — old iron mains, standard copper piping, or cutting-edge glass light-mains — before passing through pumping stations, junction boxes, and a security checkpoint on their way to the rest of the Kingdom.

---

## 🚰 The House Valve (Network Interface Cards)

### The Creative Breakdown

Before a building can draw on anything the District provides, it needs a **House Valve** installed — the fitting that physically bridges the building's internal wiring to the outside network. Get the wrong valve, and the building either can't connect at all or bottlenecks everything behind it.

### Technical Deep-Dive

The **network interface card (NIC)**, also called a network adapter card, is the physical interface between a computer and its cabling — it prepares, sends, controls the flow of, and receives/translates data for the CPU.

- **Compatibility:** A NIC must match the PC's bus type. If a system has multiple bus types available (e.g., PCI and PCI Express), always use the fastest one supported — critical in servers, where a slow NIC quickly becomes a bottleneck. USB NICs are increasingly common, useful both for laptops lacking a built-in adapter and for isolating hardware-vs-software connectivity problems during troubleshooting.
- **Performance:** Always choose the fastest NIC your network standard supports — for example, an 802.11be card on an 802.11ac/ax/be-capable network.
- **Sending and controlling data:** Two communicating NICs must agree on frame size, how much data is sent before confirmation, timing between transmissions, confirmation wait time, and transmission speed — and both must use the same media access method (e.g., CSMA/CD) on the same cable. NICs can run **half-duplex** (only one side transmits at a time) or **full-duplex** (simultaneous send/receive). A Gigabit Ethernet NIC, for example, runs twice as fast in full-duplex (1 Gbps) as in half-duplex (500 Mbps), and full-duplex also avoids collisions entirely. This setting lives on the Advanced tab of the NIC's Windows properties.
- **Drivers:** NIC drivers are OS- and card-specific software operating at the MAC sublayer of the Data Link layer. In Windows, driver details, updates, and rollbacks are managed through **Device Manager ➤ Network adapters ➤ [device] ➤ Driver tab**. Always source drivers from the manufacturer's site first, then point Windows to the downloaded file rather than relying on automatic internet search.

---

## 🛢️ The Old Iron Main (Coaxial Cable)

### The Creative Breakdown

The oldest pipe in the District's system is the **Iron Main** — a thick copper core wrapped in insulation and a braided metal shield, built for durability rather than speed. It's almost entirely retired from data delivery today, surviving mainly as the pipe that still carries cable television into buildings.

### Technical Deep-Dive

**Coaxial cable (coax)** has a copper center conductor wrapped in a plastic jacket, then a braided shield, then an outer PVC or **plenum-rated** (Teflon-type) coating. Plenum coating avoids releasing toxic gas when burned and is required by code in spaces that circulate breathable air (ceilings, wall voids) — this rating applies across all cable types, not just coax.

**Coax specifications (RG system):** Originally developed by the U.S. military, thicker copper cores travel farther but cost more and flex less.

| RG # | Popular Name | Ethernet Standard | Max Distance | Core Type | Impedance |
|---|---|---|---|---|---|
| RG-8 | Thicknet | 10Base5 | 500 m | Solid copper | 50 ohms |
| RG-58 A/U | Thinnet | 10Base2 | 185 m | Stranded copper | 50 ohms |
| RG-6 | Satellite/cable TV | N/A | 304 m | Solid copper (1.0 mm core) | 75 ohms |
| RG-59 | Analog cable TV | N/A | 228 m | Solid copper (0.762 mm core) | 75 ohms |

While RG-6 and RG-59 remain in common use today exclusively for cable television, older RG variants (like RG-8 and RG-58) were actually the original physical medium for early Ethernet networks. This historical connection is embedded in the Ethernet naming convention: the leading number is max speed in Mbps, 'Base' means baseband (**one signal at a time**), and the trailing digit historically indicated the distance supported by those specific RG coax cables in hundreds of meters (e.g., `10Base5` used thick RG-8 for 500m). Today, Ethernet has evolved to use letters instead of numbers to indicate modern mediums (e.g., `10BaseT` = twisted pair), leaving RG cables behind entirely for TV use."

**Coax connectors:** The **BNC connector** (used with thinnet) locks with a quarter-twist motion and attaches to a T-connector, which either continues to another segment or is capped with a terminator. The **F-type connector** is the threaded, screw-on connector used with RG-6/RG-59 for cable TV — this is the specific connector named in Exam Objective 3.2. A **splitter** divides one coax signal into multiple outputs (e.g., for multiple TVs), but weakens the signal in the process — avoid over-splitting, and use quality/amplified splitters when needed.

---

## 🪢 Standard Copper Piping (Twisted Pair Cable)

### The Creative Breakdown

Twisted pair is the District's workhorse pipe — flexible, cheap, and by far the most common connection type run into any modern building. Two copper wires twist around each other inside an insulated jacket, and depending on how much outside interference a building expects, that jacket comes with or without an extra layer of shielding.

> 🛠️ **Hands-on Lab Connection:** Pause here and execute **Lab 2: Wiring the Standard Main** in the Practical Labs file.

### Technical Deep-Dive

**STP vs. UTP:** Shielded twisted pair (STP) adds braided foil shielding around the wire pairs (sometimes around individual pairs too) to cut electrical interference; unshielded twisted pair (UTP) has only its outer PVC/plenum jacket. UTP is by far the more common real-world choice, though newer high-speed shielded standards are pushing STP back into relevance. Both types carry 2 or 4 wire pairs.

**Category specifications.**

| Category | Max Bandwidth | Max Distance | Notes |
|---|---|---|---|
| Cat 3 | 10 Mbps | 100 m | Legacy |
| Cat 5 | 100 Mbps | 100 m | Released 1995 |
| Cat 5e | 1 Gbps | 100 m | First copper cable to hit 1 Gbps; more twists/foot than Cat 5 |
| Cat 6 | 10 Gbps | 55 m | Minimum grade for a backbone connecting building floors |
| Cat 6a | 10 Gbps | 100 m | Same speed as Cat 6, longer distance |
| Cat 7 | 10 Gbps | 100 m | Every pair individually shielded; a.k.a. Class F |
| Cat 8 | 25/40 Gbps or 10 Gbps | 30 m (25/40 Gbps) or 100 m (10 Gbps) | Always shielded |

The industry-standard maximum run for twisted pair is **100 meters (328 feet)** — memorize this. Exceptions run shorter: 10GBaseT over Cat 6 tops out around 55 meters. Cat 8 splits into **Class I (Cat 8.1)** — RJ45-based, backward-compatible with existing RJ45 installs — and **Class II (Cat 8.2)** — uses **TERA (twisted pair enhanced registered jack)** connectors, incompatible with RJ45. Buy nothing older than Cat 5e today. **"Cat 6e" is not an official standard** — the real successor to Cat 6 is Cat 6a.

**Connectors:** Twisted pair uses **RJ (registered jack)** connectors: **RJ11** (2 pairs / 4 wires, standard for landline phones) and **RJ45** (4 pairs / 8 wires, standard for UTP networking), both attached with a crimping tool. **Ethernet splitters** exist but split signal across 2-pair sets, capping the result at 100 Mbps — not recommended; use a hub or switch instead for multi-device connections.

**Punchdown blocks:** Some installs terminate at a central **punchdown block** (in a server room or wiring closet) instead of RJ45 jacks, using a punchdown tool rather than a crimper. Older **66 blocks** were common for analog telephone lines; modern networks favor **110 blocks**, which pack connectors more densely and reduce crosstalk.

**Wiring standards — T568A and T568B:** Both standards perform identically; the difference is purely pinout convention (T568B is more commonly used). A **patch (straight-through) cable** uses the *same* standard on both ends and connects a host to a switch/hub. A **crossover cable** uses one standard on one end and swaps pins 1↔3 and 2↔6 on the *other* end only — used for host-to-host, hub-to-hub, switch-to-switch, or host-to-router direct connections. The blue and brown pairs never change position between the two standards; only green and orange swap.

| Pin | T568A Color | T568B Color |
|---|---|---|
| 1 | White/Green | White/Orange |
| 2 | Green | Orange |
| 3 | White/Orange | White/Green |
| 4 | Blue | Blue |
| 5 | White/Blue | White/Blue |
| 6 | Orange | Green |
| 7 | White/Brown | White/Brown |
| 8 | Brown | Brown |

**Direct burial cable:** STP with added waterproof sheathing, rated for underground runs. Recommended burial depth is **6–8 feet**, away from electrical lines, ideally inside a protective conduit such as PVC pipe.

---

## 💎 The High-Pressure Glass Main (Fiber-Optic Cable)

### The Creative Breakdown

The newest and fastest pipe in the District's arsenal doesn't carry electricity at all — it carries pulses of light down a hair-thin glass or plastic strand. It's immune to electrical interference and effectively impossible to wiretap, but it costs far more to install than copper, which is why it hasn't fully displaced twisted pair for local connections.

### Technical Deep-Dive

**Fiber-optic cable** transmits data as light pulses through a thin glass/plastic fiber, wrapped in a protective jacket, with Kevlar strength members for durability. It's immune to electrical interference and wiretapping, and reaches from 100 Mbps to well beyond 10 Gbps over distances of several kilometers.

**Single-mode (SMF) vs. multimode (MMF):**
- **MMF** has a larger core allowing multiple light paths ("modes") to travel simultaneously, bouncing off the cable walls — this weakens the signal faster, favoring shorter runs but higher available bandwidth. MMF typically uses LEDs (or increasingly lasers, for higher-bandwidth uses like Gigabit Ethernet) as its light source, is used as horizontal cabling to end-user systems — this means it runs from the central telecommunications room on a single floor directly to the work area outlets — and can hit up to 400 Gbps at ~150 m, or 1 Gbps at up to 2 km, depending on quality/standard. Multimode grades run **OM1–OM5** (higher = better).

- **SMF** sends a single light path straight down the fiber with no bouncing, supporting lower bandwidth but far longer distances. SMF uses lasers, and is the standard choice for backbone cabling and telecom equipment-room links. It can reach up to 100 Gbps at 40 km, or 1 Gbps at up to 140 km. Single-mode grades run **OS1–OS2**.

**Naming patterns.** As with copper, the leading number is speed and "Base" means baseband; a letter other than T after "Base" signals fiber. Letter-designation reach categories:

| Abbreviation | Meaning | Max Distance | Typical Cable |
|---|---|---|---|
| VR | Very short reach | 100 m | MMF |
| SR | Short reach | 300 m | MMF |
| DR | Distance reach | 500 m | MMF/SMF |
| FR | Far reach | 2 km | SMF |
| LR | Long reach | 10 km | SMF |
| ER | Extended reach | 40 km | SMF |
| ZR | Zero-dispersion reach | 80–140 km | SMF |

A trailing number (e.g., `400GBase-SR4`) indicates parallel channel count — SR4 uses 4 channels at 100 Gbps each to reach 400 Gbps total; SR8 uses 8 channels at 50 Gbps each.

**Fiber connectors.** The three most common: **straight tip (ST)** — twist-and-lock, developed by AT&T, historically the most widely used; **subscriber connector (SC)** — a latched, push-and-release "square connector" compatible with both SMF and MMF; and **Lucent connector (LC)** — a mini form factor (MFF) connector developed by Lucent Technologies, popular for Fibre Channel, SANs, and Gigabit Ethernet. Connectors are frequently paired for full-duplex communication.

#### 🧠 Active Recall Checkpoint #1: Brain Dump & Self-Explanation

- Name the impedance and popular name for RG-8 and RG-58 A/U
- What's the twisted pair industry-standard max run distance, and what's the notable Cat 6/10GBaseT exception?
- Explain patch vs. crossover cable in one sentence each
- MMF vs. SMF: which uses lasers, which uses LEDs, and which travels farther?
- Match ST, SC, and LC to their defining mechanical feature (twist-lock, latch, mini form factor)

---

## 🏭 Pumping Stations of the District (Connectivity Devices)

### The Creative Breakdown

Cabling alone only connects two points. To actually grow into a real network, the District relies on a chain of pumping and junction stations — some as simple as a basic booster, some smart enough to route traffic intelligently, and some powerful enough to bridge entirely separate districts together.

> 🛠️ **Hands-on Lab Connection:** Pause here and execute **Lab 3: Touring the Pumping Stations** in the Practical Labs file.

### Technical Deep-Dive

**Modems, cable/DSL modems, and ONTs:** A traditional dial-up **modem** modulates/demodulates digital signals into analog for transmission over phone lines, topping out around **56 Kbps** — now obsolete and no longer an A+ objective, though RJ11 (its connector) remains one. **Cable modems** and **DSL modems** replaced it: cable modems connect via TV coax lines (F-type connector), DSL modems via telephone lines — both are technically not true modems since they're digital, not analog. An **optical network terminal (ONT)** serves the same connecting role for fiber-to-the-premises service, converting optical signals into electrical ones for the internal network; typically mounted in a wiring closet or exterior junction box.

**Access points:** Technically, any point letting a user onto a network (a hub or switch qualifies), but the term almost always refers to a **wireless access point (WAP)**, granting 802.11 connectivity — sometimes standalone, sometimes built into a wireless router.

**Repeaters/extenders:** A small powered device that receives, amplifies, and resends a signal to extend a cable run's functional distance — operates at the **Physical layer (Layer 1)**, with no inspection or modification of the data itself.

**Hubs:** A hub links multiple computers with no real intelligence, simply repeating (broadcasting) whatever arrives on one port to every other port — hence "multiport repeater." Hubs work at **Layer 1**. **Passive hubs** just connect ports electrically with no power source of their own; **active hubs** use powered electronics to amplify/clean the signal, letting them extend network length (passive hubs cannot). Hubs are largely obsolete, replaced by switches.

**Patch panels:** Essentially a large, rack-mounted, unintelligent hub — a bank of connectors linking short front-facing patch cables to longer, more permanent cables on the back.

**Switches:** Operate at **Layer 2** (or Layer 3 as well, if a multilayer switch). Unlike hubs, switches read the Layer 2 header of incoming traffic and forward it only to the correct destination port, drastically cutting overhead — though switches still forward broadcasts, since those are addressed to everyone. Switches come in two varieties:
- **Unmanaged switch** — passes traffic to the correct MAC-addressed port, no configuration options.
- **Managed switch** — adds configuration, monitoring, and traffic management (typically via **SNMP**), enabling:
  - **QoS (Quality of Service)** — prioritizes specific traffic (e.g., VoIP) over less time-sensitive traffic.
  - **Redundancy** — multiple switch paths for fault tolerance, implemented via **Spanning Tree Protocol (STP)**.
  - **Port mirroring** — copies one port's traffic to a second port for monitoring without taking the original offline.
  - **VLANs (virtual LANs)** — logically segments computers on one physical switch into separate networks, reducing traffic and optionally isolating segments for security.
  
  A **Layer 2 switch** only cares about MAC addresses; a **Layer 3 (multilayer) switch** also handles IP addresses and can route between VLANs.

**Routers.** Highly intelligent devices operating at **Layer 3**, connecting multiple network types and determining the best path using **routing tables** and logical (IP) addressing. Key traits: they connect separate networks (unique among these devices), they do **not** forward broadcasts (routers break up broadcast domains; switches/bridges break up collision domains), and they're the standard device for linking one LAN to another — WAN setups typically involve at least two routers.

---

## 🛡️ Security Checkpoint and Combined Utility Lines (Auxiliary Devices)

### The Creative Breakdown

Beyond simple connectivity, the District runs two extra services: a security checkpoint that inspects everything crossing between the public network and the internal one, and a combined utility line that delivers both signal *and* power down a single cable — handy for devices stranded far from a power outlet.

### Technical Deep-Dive

**Firewalls:** A hardware or software solution filtering traffic by administrator-defined rules, protecting the internal network from external threats and optionally restricting outbound access to undesirable content. Most firewalls maintain at least two connections — a **public side** (Internet-facing) and a **private side** (internal) — with some adding a third port for a semi-public segment called a **screened subnet** (formerly **demilitarized zone / DMZ**), used for public-facing servers like web/FTP/email relay. Firewalls can be **network-based** (protecting a whole network) or **host-based** (protecting a single machine, e.g., Windows Defender Firewall). Most default to **default deny** — blocking all traffic unless explicitly permitted — configured via an **access control list (ACL)**, which filters by IP address, port number, domain name, or combinations thereof.

**Power over Ethernet (PoE):** A technology which allows us to deliver electrical power to a device over the same Ethernet cable carrying its data — useful for devices (APs, cameras) in locations without a convenient power outlet. Two delivery methods: a **PoE injector** (one inbound data connection from a router, one outbound connection powering + networking a single endpoint device) for single-device needs, or a **PoE-enabled switch** for powering multiple devices at once (costs more, but scales better).

| Standard | Year | IEEE Spec | Max Power | Typical Devices |
|---|---|---|---|---|
| PoE | 2003 | 802.3af | 15.4 W | Wireless APs, static surveillance cameras, VoIP phones |
| PoE+ | 2009 | 802.3at | 30 W | Alarm systems, PTZ cameras, video IP phones |
| PoE++ (Type 3) | 2018 | 802.3bt (Type 3) | 60 W | Multi-radio wireless APs, videoconferencing equipment |
| PoE++ (Type 4) | 2018 | 802.3bt (Type 4) | 100 W | Laptops, flat-screen monitors, LED lighting |

#### 🧠 Active Recall Checkpoint #2: Brain Dump & Self-Explanation

- List the OSI layer each device operates at: repeater, hub, switch, router
- Unmanaged vs. managed switch — name three features exclusive to managed switches
- What's the difference between a screened subnet/DMZ and a normal private network segment?
- PoE injector vs. PoE switch — when would you choose each?
- ONT vs. cable modem vs. DSL modem — what medium does each terminate?