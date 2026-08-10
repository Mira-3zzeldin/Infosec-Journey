### 🛠️ Lab 1: Mapping the Kingdom's Roads — Topology Diagramming & Workgroup vs. Domain Inspection

**Objective:** Reinforce the five network topologies by diagramming each one, then inspect whether your own PC is configured as part of a peer-to-peer workgroup or a client-server domain, connecting the chapter's governance models to a real Windows setting.

**Environment/Tools Needed:** A Windows 11 PC (physical or VM), a free diagramming tool (draw.io / diagrams.net, used in-browser, no install required), and PowerShell (no admin rights needed for this lab).

**Step-by-Step Instructions:**

1. Open [draw.io](https://app.diagrams.net) (or any diagramming tool of your choice) and create five small diagrams, one per topology: **Bus** (one horizontal trunk line, 5 devices tapped off it), **Star** (5 devices each connected by their own line to one central switch icon), **Ring** (5 devices connected in a closed circle, arrows showing unidirectional flow), **Mesh** (5 devices with a line connecting every device to every other device — count your lines and confirm you get 10, matching the x(x−1)÷2 formula), and **Hybrid** (any combination of two of the above).
2. Label the single point of failure on your Star diagram, and annotate your Mesh diagram with the cable-count formula and the resulting number for 5 nodes.
3. Save or export all five diagrams as PNG files into a `topology-diagrams` folder.
4. Open **Start**, type `powershell`, and open a normal (non-admin) PowerShell window.
5. Run `Get-ComputerInfo | Select-Object CsDomain, CsWorkgroup, CsPartOfDomain` and record the output. If `CsPartOfDomain` is `False`, your PC is part of a **workgroup** (the peer-to-peer model this chapter describes). If `True`, it's joined to a **domain** (the client-server model, with a domain controller somewhere on the network).
6. Alternatively, open **Settings ➤ System ➤ About** and look at the **Related settings ➤ Domain or workgroup** link (or **Rename this PC (advanced)** on older builds) to see the same information through the GUI.
7. In your lab notes, write two to three sentences explaining, in your own words, why a home PC is almost always in a workgroup, while a corporate laptop is almost always domain-joined — tie your answer back to this chapter's 10–20 computer rule of thumb for peer-to-peer.

**Expected Result:** Five saved topology diagrams (one correctly showing 10 mesh connections for 5 nodes), a recorded PowerShell output showing your PC's actual workgroup/domain status, and a short written explanation connecting that status to the peer-to-peer vs. client-server resource models.

---

### 🛠️ Lab 2: Wiring the Standard Main — T568A/B Pinout Practice & Cable Type Identification

**Objective:** Build hands-on familiarity with the T568A/T568B wiring standards and practice distinguishing patch, crossover, coax, and fiber cabling by sight — the core visual-identification skill this chapter's connector coverage builds toward.

**Environment/Tools Needed:** No special hardware required — this lab uses a printable pinout worksheet and (optionally) any real Ethernet cables, coax cables, or fiber patch cables you have access to at home, school, or work.

**Step-by-Step Instructions:**

1. On paper or in a spreadsheet, draw two blank 8-pin connector diagrams side by side, labeled T568A and T568B. From memory (then checked against this chapter), fill in all 8 pin colors for each standard.
2. Circle the two pin pairs that **change position** between T568A and T568B (pins 1/2 and 3/6, the orange and green pairs), and label the two pairs that **never change** (pins 4/5 and 7/8, blue and brown).
3. On a third diagram, draw a **crossover cable**: one end using T568A pinout, the other end using T568B pinout on the same physical cable. Annotate which pins get crossed (1↔3, 2↔6) and explain in one sentence why this crossing is necessary (matching "send" pins to "receive" pins).
4. If you have access to real cables (a home router, an old parts drawer, a friend's PC setup), examine at least three physical cables and identify each as coax, twisted pair, or fiber based on this chapter's descriptions — record the connector type you see on each end (F-type, RJ45, ST/SC/LC, etc.).
5. If you own or can borrow a network cable tester (many are inexpensive), plug both ends of an Ethernet patch cable into the tester and confirm all 8 pins light up in matching order — this is the real-world check for whether a cable is wired straight-through (patch) correctly.
6. Write a short note explaining when you would reach for a patch cable versus a crossover cable, based on this chapter's device-to-device pairing rules (host-to-switch vs. host-to-host, switch-to-switch, host-to-router).

**Expected Result:** Two correctly completed T568A/T568B pinout diagrams, a correctly annotated crossover diagram, an identification log of at least three real-world cables (if available), and a written explanation of when each cable type is used.

---

### 🛠️ Lab 3: Touring the Pumping Stations — Mapping Your Own Home Network's Hardware Chain

**Objective:** Trace the actual chain of connectivity devices between your computer and the internet, identifying which chapter concepts (NIC, switch, router, modem/ONT, firewall) correspond to real hardware sitting in your home or lab environment.

**Environment/Tools Needed:** A Windows 11 PC connected to a home or lab network, PowerShell, and physical access to (or at least a memory/photo of) your router/modem setup.

**Step-by-Step Instructions:**

1. Open PowerShell and run `Get-NetAdapter | Select-Object Name, InterfaceDescription, Status, LinkSpeed` to identify your active NIC and its negotiated link speed. Record this — it's your "House Valve" from this chapter's NIC section.
2. Run `ipconfig` and record your **Default Gateway** IP address — this is almost always your router.
3. Run `tracert 8.8.8.8` (or `tracert google.com`) and record the first two or three hops. The very first hop is typically your router; each hop after that is a device somewhere in your ISP's own connectivity chain, conceptually similar to the routers this chapter describes connecting network to network.
4. Physically inspect (or recall) your home setup and identify which real device plays each of these chapter roles: the **modem or ONT** (the box connecting to your ISP's cable, phone, or fiber line), the **router** (may be combined into the same box as the modem — common in home setups), and any **switch** (a separate box with multiple Ethernet ports, if present) or **wireless access point** (may be built into your router).
5. If your router has a web-based admin page (commonly `192.168.1.1` or `192.168.0.1` — check your Default Gateway from Step 2), log in and look for a section related to **firewall** or **security** settings. Note whether it mentions an ACL, port filtering, or similar rule-based traffic control, and record what you find.
6. Draw a simple left-to-right diagram: **Your PC's NIC → cabling → [switch/AP if present] → router → modem/ONT → ISP**, labeling each box with the chapter term it matches (Layer 1/2/3 device, as applicable).

**Expected Result:** A completed device-chain diagram of your actual home or lab network, correctly labeling each physical box with its chapter-defined role (NIC, switch, router, modem/ONT, firewall), backed by real `ipconfig`/`tracert` output.