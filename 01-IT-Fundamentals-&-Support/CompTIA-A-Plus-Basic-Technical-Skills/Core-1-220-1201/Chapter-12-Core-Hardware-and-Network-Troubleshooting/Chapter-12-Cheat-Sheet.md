## Troubleshooting Methodology

| Stage | Detail |
|---|---|
| 1. Identify the problem | Isolate what user can/can't do; ask what changed and how long |
| 2. Establish theory of probable cause | Question the obvious first; eliminate possibilities |
| 3. Test the theory | Confirm or reject; check simple stuff/user error first |
| 4. Establish plan of action / implement | One change at a time; verify → retry → roll out to others |
| 5. Verify full system functionality | Confirm symptom gone; implement preventive measures |
| 6. Document findings, actions, outcomes | Personal notebook + system-based logs |

| Best Practice | Detail |
|---|---|
| Check easy stuff first | Connections, reboot |
| Create a backup | Before major changes; validate with test restore |
| Prioritize tasks | By business impact, not order received |
| Document your process | What was tried, what worked, outcome |

---

## General Hardware Symptoms

| Symptom | Likely Cause |
|---|---|
| Grinding noise | Motor/spindle failure or head crash into platter (mechanical HDD) |
| Rhythmic ticking/clicking | Failing/failed mechanical drive |
| Constant whining, varies loud/quiet | Failing fan |
| Electrical pop | Fried SSD |
| Components that CAN make noise | HDD, optical drive, power supply fan, case fan, CPU fan |
| Components that CANNOT make noise | RAM, SSD, CPU |
| Random shutdowns / lockups after a few minutes | Overheating (heat sink/fan failure) |
| Burning smell / smoke | Shut down immediately; inspect for melted plastic/burn marks |
| Solid (non-blinking) HDD activity light | Drive constantly busy or system frozen |
| No link light on NIC | NIC, cable, or far-end device problem |

---

## Overheating & Cooling

| Concept | Detail |
|---|---|
| Heat sink | Finned metal block dissipating heat from any component with its own processor |
| Never do | Run a processor without a heat sink |
| Case fans | Exhaust hot air from inside case |
| Blanks/slot covers | Keep dust out; maintain airflow in unused expansion slots |
| Case cover removed | Can INCREASE overheating risk (disrupts designed airflow path) |
| Most common overheating component | CPU, then video card (high-end graphics use) |
| Liquid cooling risks | Pump obstruction/failure; leaks; dust in heat sinks |
| Chip creep | Components migrate out of sockets from repeated heat cycles; fix = reseat |

---

## BIOS/UEFI and POST

| Concept | Detail |
|---|---|
| BIOS/UEFI role | Interface between hardware and OS; first firmware to load |
| BIOS vs UEFI | UEFI is newer, has more features |
| Flashing the BIOS | Updating firmware via EEPROM; failed flash can brick the system |
| CMOS battery | Watch-battery-style; retains BIOS/UEFI settings (date/time) when powered off |
| CMOS battery failure symptom | Inaccurate system date/time; lost settings |
| Boot priority / boot sequence | Order of devices system attempts to boot from; set in firmware |
| POST | Power-on self-test; runs at every boot before OS loads |
| Successful POST | Typically one beep |
| Beep code | Series of beeps; pattern varies by BIOS vendor (e.g., AMI) |
| POST card | Expansion card (USB/PCIe/PCI) showing numeric code of boot stage reached |

---

## Motherboard, CPU, and Related Failures

| Symptom | Likely Cause |
|---|---|
| System completely dead | Motherboard, CPU, RAM, or power supply |
| System hangs/requires hard reboot | Motherboard or CPU |
| Continuous reboots | Motherboard or CPU |
| Motherboard damage causes | Physical trauma, ESD, short-circuiting |
| Motherboard handling | Antistatic bag/wrist strap; keep liquids away; brass standoffs w/ washers |
| CPU failure — most common cause | Overheating, usually from installation error |
| CPU installation errors | Air gaps in thermal paste; misaligned PGA/LGA; incomplete SECC/ZIF seating |
| Capacitor swelling / distended capacitor | Bulging top, brownish-red electrolyte residue; motherboard failing |
| Capacitor swelling fix | Replace motherboard (preferred); DO NOT touch residue |
| Blank screen — check order | Monitor power/sleep → cable → different monitor → different video card |
| Expansion video card installed | Onboard motherboard video typically auto-disabled |
| I/O port test tool | Loopback plug |
| Cable test tool (no spare cable) | Multimeter set to ohms |

---

## Memory (RAM) and Performance

| Concept | Detail |
|---|---|
| Physical RAM failure symptoms | App crashes, GPFs, BSOD (Windows), pinwheel (macOS) |
| Virtual memory | Paging file (`PAGEFILE.SYS` in Windows) on hard drive |
| Free disk space rule of thumb | Keep ≥10% free (affects paging file / performance) |
| Sluggish performance — possible causes | Low RAM/virtual memory, low disk space, failing MB/CPU/drive, bad software, too many apps, malware |
| Task Manager open methods | Ctrl+Alt+Del, right-click Taskbar, Ctrl+Shift+Esc |
| Sluggish threshold | CPU/Memory/Disk sustained >80% usage |
| Low disk space threshold | System slows once primary drive <10% free |

---

## Power Supply

| Concept | Detail |
|---|---|
| PSU failure — presentation 1 | Obvious: electrical arc, flash, fire |
| PSU failure — presentation 2 | No response at all when powered on |
| "No power" first checks | Wall outlet, new power cable |
| Same symptoms as failed PSU | Bad outlet, failed UPS/power strip, loose cord, motherboard short |
| Voltage switch | Some PSUs: 110v–120v vs 220v–240v (international travel) |
| Fan spins, no power to rest of system | PSU or motherboard issue |
| Isolate faulty component | Disconnect all peripherals (leave MB+CPU+RAM); reconnect one at a time |
| Test tools | Hardware PSU tester (~$10+), multimeter |
| Never do | Open/repair a power supply — lethal capacitor charge even unplugged |

---

## Storage Drives — Lights, Sounds, and Detection

| Concept | Detail |
|---|---|
| Drive not found — first question | BIOS/UEFI level, or OS level? |
| Complete boot failure | Bad connection or dead drive |
| Boots but OS not found | Damaged MBR or boot sector |
| Fix MBR (WinRE) | `bootrec /fixmbr` |
| Fix boot sector (WinRE) | `bootrec /fixboot` |
| Drive seen by BIOS/Disk Mgmt but not File Explorer/Finder | Needs initializing, partitioning, drive letter assignment |
| Windows drive management utility | Disk Management |
| macOS drive management utility | Disk Utility |

---

## Storage Performance, IOPS, and S.M.A.R.T.

| Concept | Detail |
|---|---|
| IOPS | Input/output operations per second; industry-standard throughput measure |
| IOPS measurement tool | Iometer (free, open source, Windows/Linux) |
| IOPS best signal | Declining trend over time, not a single absolute number |
| S.M.A.R.T. | Self-Monitoring, Analysis, and Reporting Technology |
| S.M.A.R.T. since | 2004 (nearly all hard drives) |
| S.M.A.R.T. metrics reported | ~70 |
| S.M.A.R.T. tools | GSmartControl, SpeedFan, HD Tune Pro, CrystalDiskInfo |
| NVMe-specific S.M.A.R.T. metric | Percentage Used (write endurance consumed) |
| Google/Backblaze study year | 2014 |

| S.M.A.R.T. ID | Attribute | Most Correlated with Failure |
|---|---|---|
| 05 | Reallocated Sector Count | Yes |
| 187 | Reported Uncorrectable Errors | Yes |
| 188 | Command Timeout | Yes |
| 197 | Current Pending Sector Count | Yes |
| 198 | Uncorrectable Sector Count | Yes |
| — | Temperature | NOT correlated (per study) |
| — | Reboot count | NOT correlated (per study) |

---

## RAID Levels

| RAID | Name | Min Drives | Fault Tolerance |
|---|---|---|---|
| RAID 0 | Striping | 2 | None — any single drive failure loses entire array |
| RAID 1 | Mirroring | 2 | Survives 1 drive failure, no data loss |
| RAID 5 | Striping with parity | 3 | Survives 1 drive failure; 2+ simultaneous = array lost |
| RAID 6 | Striping, dual parity | 4 | Survives 2 simultaneous drive failures |
| RAID 10 | Mirrored stripe | 4 | Survives failure if 1 drive per mirrored pair still works |

---

## Optical Drives

| Symptom | Cause / Fix |
|---|---|
| Disc unreadable | Clean disc (approved cleaner, lint-free cloth); scratch-removal kit |
| OS doesn't see drive | Check power (tray ejects = powered); check BIOS/UEFI detection |
| PATA-specific check | Primary/secondary jumper; pin-1 stripe alignment near power connector |
| Data discs read, movies won't play | Missing/broken MPEG decoding capability |
| Won't burn discs | May need burning software installed |

---

## Networking Hardware Tools (Exam Objective 2.8)

| Tool | Purpose |
|---|---|
| Multimeter | Measures voltage, current, resistance (not on exam objectives, but useful) |
| Crimper | Attaches connectors to cable ends; usually strips + cuts + crimps |
| Cable stripper | Strips/cuts cable only, no connector crimping |
| Wi-Fi analyzer | Detects/analyzes wireless signals; handheld or software |
| Toner probe ("fox and hound") | Tone generator + probe; traces unlabeled cable runs |
| Punchdown tool | Punches wire ends into wiring harness (e.g., 110 block) |
| Cable tester | Verifies cable works; identifies cable type |
| Loopback plug | Tests NIC send/receive capability (Ethernet and fiber versions exist) |
| Network tap | Test access port; copies traffic for monitoring without disruption |

---

## Networking Software Commands

| Command | Purpose |
|---|---|
| `ipconfig /all` | Full IP configuration + DHCP lease info |
| `ipconfig /release` → `/renew` | Test DHCP client-server connectivity |
| `ipconfig /flushdns` | Clears DNS resolver cache |
| `ip` | macOS/Linux/UNIX equivalent of `ipconfig` |
| `ping` | ICMP echo request/reply; tests reachability + latency |
| `ping -t` | Persistent ping (Ctrl+C to stop) |
| `ping -n count` | Number of echo requests |
| `ping -l size` | Packet size |
| `hostname` | Returns local machine's name |
| `netstat -a` | All connections and listening ports |
| `netstat -b` | Executable behind each connection (slow, needs elevation) |
| `netstat -n` | Numerical addresses/ports |
| `netstat -r` | Routing table |
| `netstat -s` | Per-protocol statistics |
| `nslookup` | Query DNS server (interactive or noninteractive mode) |
| `net share name=drive:\path` | Create a share |
| `net share name /delete` | Stop sharing |
| `net use` | Connect to a share |
| `net view` | List available resources |
| `tracert` (Windows) | Maps route + hop count to destination |
| `traceroute` (macOS/Linux) | Same as tracert |
| `pathping` | tracert + ping combined; shows packet loss per hop |
| `mtr` | Linux equivalent of pathping |

| Value/Range | Meaning |
|---|---|
| `169.254.x.x` | APIPA address (DHCP unreachable) |
| `fe80::/10` | IPv6 link-local address range |
| ~10 ms or less | Good LAN ping round-trip |
| ~25 ms | Good internet ping round-trip |
| >5% packet loss | Considered high (pathping) |
| pathping default `-p` | 250 ms between pings |
| pathping default `-q` | 100 queries per hop |
| pathping default `-w` | 3,000 ms wait per reply |

---

## Connectivity Symptoms and Resolutions

| Symptom | Key Cause / Fix |
|---|---|
| No connectivity (wired) | Most common: bad/unplugged patch cable |
| No SSID found | SSID changed, broadcast disabled, or out of range |
| Limited/local connectivity | Rules out client hardware; check config or connectivity device |
| APIPA (169.254.x.x) | DHCP server unreachable |
| Link-local (fe80::) | IPv6 equivalent of APIPA; local network only |
| IP address conflict | Usually a static IP inside the DHCP pool range |
| IP conflict fix note | Reboot/renew does NOT fix it — DHCP re-issues same address |
| Latency | Delay on the network |
| Jitter | Variable (inconsistent) latency |
| Port flapping (Cisco definition) | Port opens/closes ≥3 times/sec for ≥10 seconds |
| Port flapping fix | Check switch logs for Layer 1 issue; reseat/swap SFPs |
| Wireless client overload | >30 clients per AP (60–100 max on Wi-Fi 6+) |
| 802.11ac max indoor range | ~35 meters (115 feet) |
| Wireless interference sources | Radio signals, microwaves, motors, fluorescent lights, concrete/steel |
| Poor VoIP quality fix | Enable QoS to prioritize voice traffic |
| Authentication failure — most common cause | Mistyped password (check Caps Lock) |
| Authentication handled by | Active Directory domain controllers (Windows Server) |

---

## Crash Screens and Diagnostics Quick Reference

| OS | Proprietary Crash Screen |
|---|---|
| Windows | Blue Screen of Death (BSOD) |
| macOS | Pinwheel |

| Metric | Threshold |
|---|---|
| Free disk space (general) | Keep ≥10% free |
| Task Manager resource usage | >80% sustained = likely sluggish |
| S.M.A.R.T. adoption | Standard since 2004 |
