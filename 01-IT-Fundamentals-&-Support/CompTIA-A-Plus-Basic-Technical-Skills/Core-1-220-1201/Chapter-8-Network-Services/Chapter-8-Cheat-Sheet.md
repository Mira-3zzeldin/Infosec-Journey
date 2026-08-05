## Network Placement Basics

| Concept | Detail |
|---|---|
| Screened subnet | Modern term for DMZ; sits between Internet and internal network, firewalled on both sides |
| Three-pronged firewall | One device, three interfaces: Internet, internal, screened subnet |
| Two-pronged firewall | Two separate firewalls with screened subnet sandwiched between them |
| Internet-facing servers (web, mail) | Belong in the screened subnet |
| Internal-only servers (file, print, database, DHCP, syslog) | Belong on the internal network |
| Dedicated server | Performs one job only |
| Nondedicated server | Doubles as another role (e.g., admin's workstation) — not recommended |

---

## Server Roles — Quick Reference

| Server Role | Core Function | Typical Placement |
|---|---|---|
| DNS | Resolves hostnames to IP addresses | Internal (intranet-only) or screened subnet (Internet-facing) |
| DHCP | Dynamically leases IP configuration to clients | Internal network |
| Fileshare/File Server | Centralized file storage, access, backup | Internal (screened subnet only if also FTP) |
| Print Server | Accepts, queues, manages print jobs | Internal network |
| Mail Server | Sends/receives/manages email | Screened subnet |
| Syslog Server | Collects and stores event log messages | Internal network |
| Web Server | Serves web content over HTTPS | Screened subnet |
| AAA Server | Authentication, Authorization, Accounting | Internal network |
| Database Server | Hosts and manages structured/unstructured data | Internal network, behind firewall |
| NTP Server | Synchronizes device clocks | Internal network (if run internally) |

---

## DNS

| Concept | Detail |
|---|---|
| Port | UDP/TCP 53 |
| Zone file | Database of hostname-to-IP mappings |
| Zone file fields | Name, class (`IN`), record type, address, comment (after `;`) |
| Root servers | 13 global root server IP addresses |
| Cache | Temporary store of recently resolved names |
| Resolution order | Local zone file → cache → root server → TLD server → authoritative server |

### DNS Record Types

| Type | Meaning |
|---|---|
| SOA | Start of Authority |
| NS | Name Server |
| MX | Mail Exchange |
| A | IPv4 host record |
| AAAA | IPv6 host record ("quad A") |
| CNAME | Alias for another name |
| TXT | Text record; used for spam prevention, domain verification |

### DNS Spam Management (TXT-Based)

| Standard | Function |
|---|---|
| SPF | Lists legitimate sending mail server IPs for a domain |
| DKIM | Digitally signs outbound mail with a private/public key pair |
| DMARC | Defines policy (pass/quarantine/reject) for mail failing SPF/DKIM; reports spoofing origin |

---

## DHCP

| Concept | Detail |
|---|---|
| Ports | UDP 67, 68 |
| Lease | Temporary, renewable IP configuration grant |
| Lease contents | IP address, subnet mask, default gateway, DNS server |
| Scope | Configured set of parameters/address pool for a subnet |
| Reservation | Permanent IP tied to a specific MAC address (printers, servers, routers) |
| Exclusion | Address range removed from the pool for manual assignment |
| Scope options | Gateway, DNS, NTP, NetBIOS, proxy, domain name |
| Process | DHCP DISCOVER (broadcast) → server replies directly to client MAC |
| Router problem | Broadcasts don't cross routers |
| Fix 1 | Router itself acts as DHCP server |
| Fix 2 | DHCP relay agent on client's subnet |
| Static | Manual IP assignment |
| Dynamic | DHCP-assigned IP |
| Hybrid | Mix of static + DHCP (not recommended — conflict risk) |

---

## Fileshare / Storage

| Term | Detail |
|---|---|
| Fileshare/File Server | Centralized file storage/access/backup |
| NAS | Network-Attached Storage — stand-alone unit with own file-management software |
| SAN | Storage Area Network — dedicated segment/server collection for data at scale |
| Fileshare + FTP | Move to screened subnet; avoid storing highly sensitive data there |

---

## Print Server

| Function | Detail |
|---|---|
| Core job | Accept, queue, manage (sometimes process/store) print requests |
| Form factors | Dedicated server, stand-alone network device, printer-integrated module |
| Placement | Internal network |

---

## Mail Protocols

| Protocol | Port | Direction | Type |
|---|---|---|---|
| SMTP | 25 | Sending / server-to-server transfer | Push |
| POP3 | 110 | Receiving | Pull |
| IMAP4 | 143 | Receiving (newer, more features) | Pull |

---

## Syslog

| Concept | Detail |
|---|---|
| Default port | UDP 514 (unsecured) |
| Secured port | TCP 6514 (over TLS) |
| Message components | Facility code, severity level, text description |
| Facility code range | 0–23 |
| Native OS | UNIX/Linux; Windows uses Event Viewer instead |
| Server components | Listener, database, management/filtering software |
| Placement | Always behind the firewall, internal network |

### Syslog Severity Levels

| Level | Severity | Description |
|---|---|---|
| 0 | Emergency | System unusable |
| 1 | Alert | Immediate action needed |
| 2 | Critical | Major system errors |
| 3 | Error | Normal error conditions |
| 4 | Warning | Less urgent than error |
| 5 | Notice | Normal operation, condition met |
| 6 | Information | General information |
| 7 | Debug | Debugging information |

---

## Web Server

| Concept | Detail |
|---|---|
| Port | TCP 443 (HTTPS) |
| Common platforms | Nginx, Apache, LiteSpeed, Microsoft IIS |
| FTP (download function) | TCP 20, 21 |
| Placement (recommended) | Screened subnet |
| Risk of internal placement | Firewall must open 443 to all internal hosts, not just the web server |

---

## AAA Framework

| Component | Question Answered | Mechanism |
|---|---|---|
| Authentication | Who are you? | Credentials, SFA/MFA |
| Authorization | What can you do? | Permissions, least privilege |
| Accounting | What did you do? | Logs (Event Viewer, browser history, etc.) |

### AAA Implementations

| System | Role |
|---|---|
| Domain Controller | Centralized AD authentication server |
| RRAS | Routing and Remote Access Service |
| RADIUS | Remote Authentication Dial-In User Service |
| TACACS+ | Terminal Access Controller Access-Control System Plus |
| Kerberos | Authentication protocol (used by Windows Server) |

### Authentication Factor Categories

| Factor | Example |
|---|---|
| Something you know | Password, security question, one-time password |
| Something you have | Smartcard, security token (RSA SecurID, PingID) |
| Something you are | Fingerprint, facial, retina biometrics |
| Somewhere you are | Restricted login by IP range/location |

| Term | Detail |
|---|---|
| SFA | Single-factor authentication (username + 1 factor) |
| MFA | Multifactor authentication (2+ factors) |
| Least privilege | Grant only the access required, no more |

---

## Database Servers

| Concept | Detail |
|---|---|
| DBMS examples | Oracle, Microsoft SQL Server, MySQL, AWS, Azure, Google Cloud Platform |
| Storage unit | Table |
| Locking | Record-level (vs. whole-file locking in flat files) |
| Excel row limit | 1,048,576 |
| Excel column limit | 16,384 |
| Excel cell character limit | 32,767 |
| Relational database | Rigid table/column/row structure; governed by schema |
| Non-relational database | Key/value or document databases; for unstructured data (~80% of world data) |
| Offline storage | Local |
| Online storage | Server/cloud |

---

## NTP

| Concept | Detail |
|---|---|
| Port | UDP 123 |
| Function | Synchronizes device clocks across the network |
| Why it matters | Accurate/aligned timestamps critical for AAA accounting/log correlation |
| Public examples | time.google.com, time.aws.com, time.nist.gov, time.windows.com, time.fu-berlin.de |
| Internal NTP reasons | Compliance, offline operation, task sync, reduced public reliance |

---

## Internet Appliances

| Appliance | Function |
|---|---|
| Spam Gateway | Filters inbound/outbound mail for spam signals (pass/quarantine/delete) |
| UTM | Centralizes packet filtering, IDS/IPS, antimalware, spam blocking, site blocking, app control |
| Load Balancer | Distributes requests across multiple servers |
| Proxy Server | Makes requests on a client's behalf |

### IDS vs. IPS

| Type | Behavior | Network-wide | Host-only |
|---|---|---|---|
| IDS | Passive — logs and alerts only | NIDS | HIDS |
| IPS | Active — blocks/resets connections | NIPS | HIPS |

### Load Balancing Configurations

| Configuration | Detail |
|---|---|
| Cross-region | Routes to nearest server region by requester IP |
| Content-based | Splits server banks by request type (web/streaming/downloads) |

### Proxy Server Benefits

| Benefit | Detail |
|---|---|
| Caching | Speeds up repeat requests |
| Content filtering | Blocks prohibited sites |
| Anonymization | Masks client identity from destination |

---

## Legacy/Embedded Systems

| Concept | Detail |
|---|---|
| Legacy system | Old, unsupported hardware/software/protocol |
| Legacy examples | Pick OS, IBM AS/400, VAX, IPX/SPX, 802.11b/g |
| Embedded system | System critical to a larger dependent process |
| SCADA | Supervisory Control and Data Acquisition — controls manufacturing, power grids, pipelines, water treatment, HVAC |
| SCADA risk | Old, open-access design — significant security liability |
| Standard mitigation | Network isolation/segmentation |
| Long-term mitigation | Virtualization (removes 1:1 hardware-software dependency) |

---

## Internet of Things (IoT)

| Device Category | Key Features |
|---|---|
| Smart Thermostat | Remote sensors, energy reports, voice activation, geofencing |
| Home Security/Automation | Cameras, motion sensors, doorbell integration, local/cloud recording |
| Smart Door Lock | Keypad entry, remote lock/unlock, camera/doorbell pairing |
| Smart Light Switch | On/off, dimming, scheduling, geofencing, motion activation |
| Voice Assistant/Smart Speaker | Wake-word activation, Internet-based query/response, device control |

| Concept | Detail |
|---|---|
| IoT controller | Central hub coordinating end devices |
| Connection to controller | Wi-Fi or Bluetooth via administrator's app |
| Geofencing | Adjusts device behavior based on detected location/presence |
