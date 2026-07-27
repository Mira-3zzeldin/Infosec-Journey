## Expansion Card Categories

| Category | Key Facts |
|---|---|
| Video | Onboard = shares system RAM, lower-end; Add-on = dedicated GPU + VRAM, PCIe preferred, dual-to-quad slot width |
| Sound | 1/8" (3.55mm) color jacks; onboard ~90kHz/85–90dB SNR vs. add-on ~190kHz/115dB+ SNR; Sound Blaster = de facto standard |
| Capture | Records external video source (console, camera); internal PCIe or external USB; not all record audio |
| NIC | Wired (RJ45/fiber/BNC) vs. wireless (needs AP configured first); PCIe or USB |
| I/O | USB (2/4/7-port), eSATA (1–2 ports), Thunderbolt cards |

---

## Sound Jack Color Codes

| Color | Function |
|---|---|
| Yellow | Digital output |
| Light blue | Line-level stereo input |
| Pink | Microphone input |
| Lime green | Stereo output / headphones |
| Black | Surround left/right |
| Orange | Center channel / subwoofer |
| Gray | Surround rear left/right |

---

## HDD Spindle Speeds & Form Factors

| Spec | Value |
|---|---|
| Common speeds | 5,400 / 7,200 / 10,000 (10k) / 12,000 / 15,000 rpm |
| 7,200 rpm SATA sustained read | ~100 MBps |
| 10,000 rpm SATA sustained read | ~200 MBps |
| Form factors | 3.5" (desktop), 2.5" (laptop) |
| CMR | Separated tracks, better for frequent R/W |
| SMR | Overlapping tracks, higher capacity, cheaper, slower — backup/archive use |
| PATA legacy | 40-pin ribbon (keyed), 4-pin Molex power, ATA/100 = 100 MBps max, 2 drives/controller |

---

## SSD Communication Interfaces

| Interface | Speed(s) | Notes |
|---|---|---|
| SATA 1.x/2.x/3.x | 150 / 300 / 600 MBps | Slowest SSD interface; supports HDD & SSD |
| PCIe 1.0–6.0 | 250 MBps–8 GBps per lane (1-way) | Universal bus (video/sound/NIC too); 8b/10b encoding, rated in GT/s |
| NVMe | Up to ~3.5 GBps (protocol, not a connector) | Rides on SATA/PCIe/M.2; needs mobo/BIOS support to boot |
| SAS 1–4 | 3 / 6 / 12 / 24 Gbps | Server/enterprise; SATA can run on SAS controller, not vice versa |

---

## PCIe Throughput Table

| Version | Date | Transfer Rate | Per-Lane (1-way) | x16 Total (bidir.) |
|---|---|---|---|---|
| 1.0 | 2003 | 2.5 GT/s | 250 MBps | 8 GBps |
| 2.0 | 2006 | 5.0 GT/s | 500 MBps | 16 GBps |
| 3.0 | 2010 | 8.0 GT/s | 1 GBps | 32 GBps |
| 4.0 | 2017 | 16.0 GT/s | 2 GBps | 64 GBps |
| 5.0 | 2019 | 32.0 GT/s | 4 GBps | 128 GBps |
| 6.0 | 2022 | 64.0 GT/s | 8 GBps | 256 GBps |

---

## SAS Standards

| Version | Released | Throughput |
|---|---|---|
| SAS-1 | 2003 | 3 Gbps (375 MBps) |
| SAS-2 | 2009 | 6 Gbps (750 MBps) |
| SAS-3 | 2013 | 12 Gbps (1.5 GBps) |
| SAS-4 | 2017 | 24 Gbps (3.0 GBps) |

**Conversions:** 125 MBps = 1 Gbps · 8 Gbps = 1 GBps · 1000 MBps ≈ 1 GBps

---

## SSD Form Factors

| Form Factor | Connector | Notes |
|---|---|---|
| mSATA | 30mm-wide, 52-pin | Shares layout with mPCIe; SATA protocol only; full 30×50.95mm / half 30×26.8mm |
| M.2 | 66-pin, ~22mm wide | Supports PCIe/SATA/USB/Wi-Fi/BT/GPS/NFC; keyed slots |

---

## M.2 Keying

| Key | Interfaces | Uses |
|---|---|---|
| A | PCIe x2, USB 2.0 | Wi-Fi/BT/cellular |
| B | PCIe x2, SATA, USB 2.0/3.0, audio | SATA & PCIe x2 SSDs |
| E | PCIe x2, USB 2.0 | Wi-Fi/BT/cellular |
| M | PCIe x4, SATA | Fastest PCIe x4 SSDs |

B+M fits B or M sockets; B-only/M-only does not fit B+M sockets. Card size = width+length in mm (e.g., 2280).

---

## RAID Comparison

| Version | Nickname | Fault Tolerant? | Min Drives | Recoverable Failures | Capacity |
|---|---|---|---|---|---|
| RAID 0 | Disk striping | No | 2 | 0 | Sum of all drives |
| RAID 1 | Disk mirroring | Yes | 2 | 1 | Sum ÷ 2 |
| RAID 5 | Stripe + parity | Yes | 3 | 1 | All drives − 1 |
| RAID 6 | Double parity | Yes | 4 | 2 | All drives − 2 |
| RAID 10 | RAID 1+0 | Yes | 4 | 2* | Sum ÷ 2 |

---

## Removable Storage

| Item | Size / Notes |
|---|---|
| SD | 32mm × 24mm; write-protect notch |
| miniSD | 21.5mm × 20mm |
| microSD | 15mm × 11mm |
| CompactFlash | Digital camera use, less common |
| USB flash | Type-A / Type-C; 32GB–1TB+ range |

---

## Swap Categories

| Type | Behavior |
|---|---|
| Hot-swappable | Insert/remove while powered, no conditions |
| Warm-swappable | Active filesystem — stop via Safely Remove first, power stays on |
| Cold-swappable | System must be fully powered off (e.g., motherboard SATA) |
| SCA | Combined power+data connector; ground leads longer than power leads |

---

## Optical Disc Specs

| Tech | Format | Capacity | 1x Rate | Common Rate |
|---|---|---|---|---|
| CD | SS | 700 MB | 150 Kbps | 7.8 Mbps (52x) |
| DVD | SS,SL | 4.7 GB | 1.4 Mbps | 33.6 Mbps (24x) |
| DVD | SS,DL | 8.5 GB | — | — |
| DVD | DS,SL | 9.4 GB | — | — |
| BD | SS,SL | 25 GB | 4.5 Mbps | 72 Mbps (16x) |
| BD | SS,DL | 50 GB | — | — |
| BD | DS,DL | 100 GB | — | — |

---

## Power Supply Fundamentals

| Item | Key Fact |
|---|---|
| AC input (US) | 110–120V standard, 220–240V high-energy appliances |
| DC outputs | +3.3V, +5V, +12V, −12V |
| AC/DC formula | Watts = Volts × Amps |
| DC vs AC danger | DC → prolonged muscle clamping; AC → cardiac fibrillation; both lethal via PSU capacitors even unplugged |
| Wattage need (typical) | 500–600W standard; 800–1300W high-end; up to 2,000W extreme |
| Voltage selector | Dual-voltage switch (110/220, 115/230, 120/240) or auto universal-voltage |

---

## 80 PLUS Efficiency Tiers

| Load | 80 PLUS | Bronze | Silver | Gold | Platinum | Titanium |
|---|---|---|---|---|---|---|
| 20% | 80% | 82% | 85% | 87% | 90% | 90% |
| 50% | 80% | 85% | 88% | 90% | 92% | 92% |
| 100% | 80% | 82% | 85% | 87% | 89% | 94% |

---

## Power Connectors

| Connector | Pins | Notes |
|---|---|---|
| ATX (original) | 20-pin | Original single-block connector |
| ATX12V 2.0 / EPS12V | 24-pin (or 20+4) | Added leads for PCIe-era power demand |
| ATX12V 2.1 PCIe | 6-pin | 75W supplemental |
| ATX12V 2.2 PCIe | 8-pin (6+2 modular) | 150W supplemental |
| SATA power | 15-pin | 3×3.3V, 3×5V, 3×12V + grounds |
| Molex (legacy) | 4-pin | PATA/optical drives; beveled keying |

---

## PSU Types

| Type | Notes |
|---|---|
| Fixed-cable | All connectors hardwired, often unused cable clutter |
| Modular | Only needed cables attached; near-universal today |
| Semi-modular | Mobo/CPU hardwired, peripherals detachable |
| Redundant (RPS) | Dual PSU in one enclosure, hot-swappable, server-focused, protects against PSU failure only |
| UPS | Battery backup, protects against grid outage; surge-only vs. surge+battery outlets |
