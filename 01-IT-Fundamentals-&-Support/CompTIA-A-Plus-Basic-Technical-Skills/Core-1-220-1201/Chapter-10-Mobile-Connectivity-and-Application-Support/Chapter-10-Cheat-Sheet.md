## Cellular Generations

| Generation | Launched/Available | Max/Typical Speed | Notes |
|---|---|---|---|
| 1G | 1979 | Analog, voice only | Original analog standard |
| 2G | 1991 (commercial) | 64 Kbps max | First digital standard |
| 3G | 1998 | 200 Kbps min spec (up to ~7 Mbps under 3.5G) | GSM vs. CDMA split |
| 4G | 2008 | 10–20 Mbps down / 3–10 Mbps up typical; 300/75 Mbps theoretical max | All-IP; LTE beat WiMAX |
| 5G | 2016 modem announced / 2019 broad rollout | ~490 Mbps avg; 20 Gbps theoretical peak | eMBB, URLLC, mMTC |

| Concept | Detail |
|---|---|
| GSM | Global System for Mobile Communications; 1.5B+ users, 210 countries |
| CDMA | Code-division multiple access; Qualcomm; U.S.-only |
| GSM carriers (US) | AT&T, T-Mobile |
| CDMA carriers (US) | Verizon, Sprint (merged into T-Mobile, 2020) |
| 3G shutdowns began | 2022 |
| 4G expected end-of-life | ~2035 |
| 4G optimal rural range | 3.1 mi (5 km) |
| 4G usable range | 19 mi (30 km) |
| 5G frequency range (sub-6) | 600 MHz–6 GHz |
| 5G mmWave frequency range | 24–86 GHz |
| 5G mmWave range limit | ~0.5 mile |
| eMBB | Enhanced Mobile Broadband — phones/general mobile |
| URLLC | Ultra-Reliable Low-Latency Comms — autonomous vehicles, industrial |
| mMTC | Massive Machine Type Comms — IoT sensors |

---

## Hotspots and Tethering

| Concept | Detail |
|---|---|
| Mobile hotspot | Shares cellular connection over Wi-Fi to nearby devices |
| iOS hotspot path | Settings → Personal Hotspot (or Settings → Cellular → Set Up Personal Hotspot) |
| Android hotspot path | Settings → Connections → Mobile Hotspot And Tethering |
| Android hotspot side effect | Auto-disables device's own Wi-Fi |
| Android hotspot security default | WPA2-Personal (also WPA3-Personal, Open) |
| iOS WPA2 support | iOS 7+ |
| iOS WPA3 support | iPhone 11+ |
| Verizon hotspot device limit (4G LTE) | 10 devices |
| Tethering (historical meaning) | USB-cable connection specifically |
| Hotspot drawbacks | Speed, cost, security |

---

## Wireless Enable/Disable

| Concept | Detail |
|---|---|
| Airplane mode | Disables multiple wireless radios at once |
| iOS airplane mode memory | Remembers last radio configuration (e.g., Bluetooth left on) |
| Quick access (iOS) | Control Center |
| Quick access (Android) | Notification shade (swipe down twice for full panel) |

---

## Baseband, SIM OS, and Cellular Updates

| Concept | Detail |
|---|---|
| # of OSs on a typical smartphone | 3 (primary + baseband RTOS + SIM RTOS) |
| RTOS | Real-time operating system; a few hundred KB; minimizes transfer lag |
| Baseband OS | Manages wireless communication (radio/modem) |
| Baseband update aliases | Radio firmware update, modem update, baseband update |
| Apple manual baseband update | Not supported (jailbreak voids warranty) |
| Android manual baseband update | Possible (open source); risk of bricking |
| Bricking | Rendering a device inoperable, often via interrupted firmware update |
| SIM OS | Manages data transfer between phone and SIM chip |
| PRI | Product Release Instruction — network-specific config settings |
| PRL | Preferred Roaming List — guides connection to correct tower while roaming |
| Verizon manual PRL update | Dial *228 |

---

## Cellular/Device Identifiers

| Identifier | Length | Detail |
|---|---|---|
| IMEI | 15 digits | Unique per physical device; dial *#06# to view |
| MEID | 14 digits | = first 14 digits of IMEI |
| IMSI | 15 digits | = MCC + MNC + MSIN |
| MCC | 3 digits | Country code (US = 310, UK = 234) |
| MNC | 2–3 digits | Carrier code (US Verizon = 006; AT&T = 170, 410, others) |
| MSIN | Variable | Sequential subscriber serial number |
| ICCID | 19–20 digits | Global SIM card serial number |
| SEID | Long hex | Security/NFC/Apple Pay identifier |

| Concept | Detail |
|---|---|
| IMEI first adopters | AT&T, T-Mobile |
| MEID first adopters | Sprint (now T-Mobile), Verizon |
| SIM | Removable chip; account/ID/security data; carrier-tied |
| eSIM | Motherboard-embedded, reprogrammable like BIOS/UEFI flash |
| Identifier location (iOS) | Settings → General → About |
| Identifier location (Android) | Settings → About Phone |

---

## Wi-Fi and Cellular Data Control

| Concept | Detail |
|---|---|
| SSID | Service-set identifier; network name |
| iOS Wi-Fi path | Settings → Wi-Fi → toggle on → select network → password → Join |
| iOS "Ask To Join Networks" options | Off, Notify, Ask |
| Android Wi-Fi path | Settings → Connections → Wi-Fi → select network → password → Connect |
| iOS disable cellular data | Settings → Cellular → toggle off Cellular Data |
| iOS Low Data Mode | Cellular Data Options → reduces cellular usage |
| Android disable cellular data | Settings → Connections → Data Usage → toggle off Mobile Data |
| Android Data Saver | Forces background data to Wi-Fi-only unless app exempted |

---

## VPN

| Concept | Detail |
|---|---|
| VPN | Secured connection over an unsecure network |
| iOS VPN path | Settings → General → VPN & Device Management → VPN → Add VPN Configuration |
| iOS protocol choices | IKEv2, IPsec, L2TP |
| IKEv2 | Fastest, most secure; narrower OS support than L2TP |
| L2TP / IKEv2 relationship | Both extensions of IPsec suite |
| Android VPN path | Settings → Connections → More Connection Settings → VPN → Add VPN Profile |
| IKEv2/IPsec/MSCHAPv2 roles | IKEv2 = connection protocol; IPsec = tunneling/encryption; MSCHAPv2 = authentication |
| PSK | Server-generated shared key; brute-force vulnerable |
| RSA (VPN) | Asymmetric keys; more secure; needs RSA server |
| Android VPN apps | TunnelBear (McAfee), Hola Free VPN |
| OpenVPN native support | None on iOS/Android — requires 3rd-party app (e.g., OpenVPN Connect) |
| VPN works over | Cellular and Wi-Fi |

---

## Bluetooth

| Concept | Detail |
|---|---|
| Governing standard | IEEE 802.15 (WPAN) |
| Pairing sequence (Exam Obj. 1.3) | Enable Bluetooth → Enable pairing → Find device → Enter PIN → Test connectivity |
| iOS Bluetooth path | Settings → Bluetooth (My Devices / Other Devices) |
| Android Bluetooth path | Settings → Connections → Bluetooth |
| AirDrop transport | Bluetooth Low Energy (BLE) |
| iOS→non-iOS file transfer | Not native; needs 3rd-party app |
| Android↔Windows file transfer | Windows Settings → Bluetooth & Devices → Send/Receive Files |

---

## Location Services

| Concept | Detail |
|---|---|
| GPS development start | Early 1970s (U.S. DoD) |
| First GPS satellite | 1978 |
| Total GPS satellites (US) | 31 (24 active + backups) |
| GPS orbit altitude | ~11,000 miles |
| GPS cost | Free (commercial use) |
| Triangulation (location only) | 3 satellites |
| Triangulation (location + elevation) | 4 satellites |

| GNSS | Managed By | Satellites |
|---|---|---|
| GPS | United States | 31 |
| GLONASS | Russia | 24 |
| Galileo | European Space Agency | 30 |
| BeiDou (BDS) | China | 45 |
| IRNSS | India | 7 |

| GPS Service | Access | Accuracy | Code | Use |
|---|---|---|---|---|
| SPS | Free | 3–10 m (95% within 2 m) | C/A | Navigation |
| PPS | DoD authorization + encryption | Few cm | P (Y on L2) | Military, surveying |

| Concept | Detail |
|---|---|
| L1 frequency | 1,575.42 MHz (C/A + military P code) |
| L2 frequency | 1,227.60 MHz (encrypted P/Y code only) |
| Garmin example screen | 4.5" (5"–8" also available) |
| Cellular location cost | Paid carrier subscription |
| Cellular location accuracy | ~100 m (improves with multiple towers) |
| GPS accuracy (typical) | ~10 m |
| Indoor location aids | Wi-Fi, Bluetooth |
| iOS location path | Settings → Privacy & Security → Location Services |
| iOS per-app options | Never, Ask Next Time/When I Share, While Using, Always |
| iOS exception when disabled | Find My iPhone |
| Android location path | Settings → Location |
| Android per-app options | Allow All The Time, Allow Only While Using, Ask Every Time, Don't Allow |

---

## MDM and MAM

| Concept | Detail |
|---|---|
| MDM | Server software; enrolls devices; manages security (track/lock/unlock/encrypt/wipe) |
| MAM | Manages corporate apps specifically; install/delete/encrypt/wipe apps + data |
| Corporate device | Company-owned; business use only; approved apps only |
| BYOD | Employee-owned; must meet security requirements; MDM grants access |
| BYOD wipe practice | Selective (MAM) wipe preferred; full wipe = last resort |
| MDM AUP topics | Auth/encryption, approved apps, PII storage, lost/stolen procedures, public Wi-Fi use |
| MDM compliance response | Auto-lock/remove offending content; notify admin/manager |
| Example MAM platform | VMware AirWatch (corporate app store) |

---

## Email Protocols and Ports

| Protocol | Function | Default Port |
|---|---|---|
| SMTP | Send (push) | TCP 25 |
| POP | Retrieve, minimal interaction | TCP 110 |
| IMAP | Retrieve, extensive interaction | TCP 143 |

| Secure Variant | Port |
|---|---|
| SMTP with SSL | 465 |
| SMTP with TLS | 587 |
| IMAP with SSL/TLS | 993 |
| POP with SSL/TLS | 995 |

| Concept | Detail |
|---|---|
| STARTTLS | Secures SMTP/POP/IMAP without changing port numbers; can use SSL or TLS |
| Current protocol versions | POP3, IMAPv4 |
| IMAP advantage | Changes message state on server; no download/delete needed |
| POP limitation | Downloads/deletes only; causes multi-device copy inconsistency |
| iOS email setup path | Settings → Apps → Mail → Mail Accounts → Add Account |
| Android email setup path | Settings → Accounts And Backup → Manage Accounts → Add Account |
| Android SSL/TLS auto-port | Switching to SSL/TLS sets port to 993 |

| Service | Direction/Protocol | Server |
|---|---|---|
| Gmail | SMTP (SSL/TLS) | smtp.gmail.com |
| Gmail | IMAP (SSL) | imap.gmail.com |
| Gmail | POP (SSL) | pop.gmail.com |
| iCloud | SMTP (SSL) | smtp.mail.me.com |
| iCloud | IMAP (SSL) | imap.mail.me.com |
| Exchange Online | SMTP (TLS) | smtp.office365.com |
| Exchange Online | IMAP/POP | outlook.office365.com |
| Yahoo Mail | SMTP (SSL) | smtp.mail.yahoo.com |
| Yahoo Mail | IMAP (SSL) | imap.mail.yahoo.com |
| Yahoo Mail | POP (SSL) | pop.mail.yahoo.com |

---

## Mobile Device Synchronization

| Concept | Detail |
|---|---|
| Synchronization | Mirrors changes bidirectionally between devices |
| Backup | One-way duplicate copy |
| Common sync connections | USB, Wi-Fi, Bluetooth, cellular |
| Common synced data | Calendars, contacts, business apps, cloud storage |
| Data cap check (iOS) | Settings → Cellular |
| Data cap check (Android) | Settings → Connections → Data Usage → Mobile Data Usage |
| iOS sync tools | iCloud, iTunes |
| iCloud free tier | 5 GB |
| iCloud+ paid tiers | 50 GB, 200 GB, 2 TB |
| iCloud sync trigger conditions | Plugged in + locked + Wi-Fi connected |
| iTunes availability | Default on Mac; downloadable elsewhere |
| iTunes auto-sync disable path | Edit → Preferences → Devices → Prevent...Syncing Automatically |
| Android manufacturer sync tools | Samsung SideSync, LG PC Suite/Sync, HTC Sync Manager |
| Android common cloud target | Google Drive |
| Samsung backup path | Settings → Accounts And Backup → Back Up Data |
| iOS mail account sync check | Settings → Apps → Mail → [account] |
| Android account sync check | Settings → Accounts and Backup → Manage Accounts → [account] → Sync account |
| iOS Calendar sync path | Settings → Apps → Calendar → Calendar Accounts |
| Android default calendar sync | @gmail.com account |
| Android calendar management | Settings → Apps → Calendar → Calendar Settings → Manage Calendars |
| Manual sync term (iOS) | Fetch New Data |
| Manual sync term (Android) | Sync Now |
| Microsoft 365 sync path | Start → Settings → Accounts → Windows Backup |
| Microsoft sync removal | Disable on all PCs → account.microsoft.com/devices → Clear Stored Settings |
| Mobile OneDrive sync | Requires OneDrive app |

| Cloud Provider | Free | Premium | Cost/Year |
|---|---|---|---|
| Google Drive | 15 GB | 2 TB | $120 |
| Apple iCloud | 5 GB | 2 TB | $120 |
| Microsoft OneDrive | 5 GB | 1 TB | $100 |
| Dropbox | 2 GB | 3 TB | $199 |
| Box | 10 GB | 100 GB | $60 |
