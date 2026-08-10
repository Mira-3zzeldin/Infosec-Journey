## Purpose of Virtual Machines

| Purpose | Detail |
|---|---|
| Sandbox | Temporary, isolated desktop environment; files never saved to disk/memory; gone when shut down |
| Sandbox tools | SandboxiePlus, SHADE Sandbox, VirtualBox, CodeSandbox, ToolWiz TimeFreeze, Windows Sandbox |
| Windows Sandbox install path | Turn Windows Features On Or Off → Windows Sandbox → OK → reboot |
| Test development | Testing in-progress apps in a virtualized target OS |
| Application virtualization — form 1 | Legacy software / legacy OS |
| Application virtualization — form 2 | Cross-platform virtualization (app for OS A running virtualized on OS B) |
| Virtualization industry origin | 1967 |

---

## Hypervisors

| Concept | Detail |
|---|---|
| Hypervisor (alt. name) | Virtual machine manager (VMM) |
| Type 1 | Bare-metal; sits directly on hardware; no host OS; server-side virtualization; best performance |
| Type 1 examples | Microsoft Hyper-V, VMware ESXi, Citrix Hypervisor (formerly XenServer) |
| Type 2 | Hosted; sits on top of host OS; client-side virtualization; host OS competes for resources |
| Type 2 downside | Host OS consumes resources; host OS failure = all guest OS failure |
| Type 2 examples | Windows Virtual PC, Azure Virtual Server, Oracle VM VirtualBox, VMware Workstation, Linux KVM |
| Hyper-V requirement — edition | Windows 11 Pro or Enterprise |
| Hyper-V requirement — CPU | 64-bit with SLAT |
| Hyper-V requirement — CPU extension | VM Monitor Mode Extension (Intel VT-c) |
| Hyper-V requirement — RAM | 4 GB minimum |
| Hyper-V requirement — BIOS/UEFI | Hardware virtualization enabled |
| Intel virtualization tech name | VT (virtualization technology) |
| AMD virtualization tech name | AMD-V |
| Emulator vs. hypervisor | Emulator = mimics one specific system; hypervisor = can host multiple OSs |
| Free Android emulator example | Andy (andyroid.net) |

---

## Containers

| Concept | Detail |
|---|---|
| Container | App + runtime dependencies packaged as one unit |
| Container virtualizes | Only the software/app layer, not physical infrastructure |
| Container engine examples | Docker (original/most popular), Buildah, Podman, LXD, Containerd |
| Container image | Virtualization ISO-like file: app + dependencies + environment files |
| Runtime tools (receiving end) | Docker, Kubernetes, LXD |
| Typical package size | Megabytes (vs. gigabytes for a VM) |
| Apps per container | Usually one (can be more) |
| Deployment speed | Fast (vs. slower for VMs) |
| Scalability | Highly scalable (vs. slow/expensive for VMs) |
| Scope of control | Container only (vs. full hardware+software stack in a VM) |

---

## Client-Side Virtualization Requirements

| Resource | Rule |
|---|---|
| CPU | Each core can be treated as a separate virtual processor; more cores = more/faster VMs |
| RAM | Host RAM + guest RAM requirements are additive (4 GB host + 4 GB guest = 8 GB minimum) |
| Storage | Each OS (host + each guest) needs its own dedicated disk space |
| Network | Each VM typically needs full network access; bandwidth is a common bottleneck |
| VDI | Virtual desktop infrastructure — software + hardware for the virtual environment; on-prem or cloud |
| Virtual NIC | Created per VM; can stay fully isolated (VM-to-VM only) or bridge to physical NIC |
| Virtual switch | Bridges virtual NICs to the physical NIC; manages traffic between them |
| Type 1 pairing | Commonly used with remote administration of virtual desktops |
| Hypervisor security risk | Attacking the hypervisor can compromise all guest OSs at once |
| Guest OS antimalware | Still required — same as any physical machine |
| Cloud security split | Vendor secures hardware/network; client secures its own data |
| Pre-install checklist | CPU virtualization support? Enough RAM? Enough disk space? Fast enough network? |

---

## Types of Clouds

| Cloud Type | Detail |
|---|---|
| Public | Run by large IT providers; best scalability/reliability/flexibility/cost-effectiveness; shared resources |
| Private | Company builds/owns its own cloud internally; full security control; less scalability, no cost savings on hardware |
| Hybrid | Combination of public + private; sensitive data on private, rest on public |
| Community | Multiple orgs w/ shared interest pool a cloud; more secure than public, less economy of scale |
| Shared resources used by | Public, hybrid, community |
| Dedicated resources used by | Private |

---

## Cloud Service Models

| Model | Full Name | What Client Manages | What Provider Manages |
|---|---|---|---|
| IaaS | Infrastructure as a Service | Software | Hardware/processing/storage/network |
| PaaS | Platform as a Service | App code | Hardware + dev tools/runtime environments |
| SaaS | Software as a Service | Nothing (just uses app) | Software + platform + infrastructure |
| PaaS examples | Google App Engine, Microsoft Azure, Red Hat OpenShift, AWS Elastic Beanstalk, Engine Yard, Heroku |
| SaaS examples | Google Docs, Microsoft 365, Dropbox |

| Other "as a Service" Variant | Meaning |
|---|---|
| HaaS | Hardware as a Service — IaaS variant focused on storage |
| CaaS | Communications as a Service — VoIP, IM, video collab |
| NaaS | Network as a Service — network infrastructure |
| DaaS (desktop) | Desktop as a Service — virtual desktops |
| DaaS (data) | Data as a Service — multi-source data mashups |
| BPaaS | Business Processes as a Service — payroll, help desk, etc. |
| XaaS | Anything/Everything as a Service — umbrella term |

| AWS Free-Tier Service | Function |
|---|---|
| EC2 (Elastic Compute Cloud) | Create virtual machines |
| S3 (Simple Storage Service) | Storage buckets |
| RDS (Relational Database Service) | Managed database hosting |
| Lambda | Runs code in response to a triggering event |

| Client-Side Cloud Adoption Steps | |
|---|---|
| 1 | Determine network/user needs |
| 2 | Get bids from CSP(s) |
| 3 | Sign up |
| 4 | Train users |

---

## NIST Cloud Characteristics

| Characteristic | Detail |
|---|---|
| On-demand self-service | User gets more resources automatically, no provider contact needed |
| Broad network access | Reachable from many client types via common software (browsers); a.k.a. ubiquitous access |
| Resource pooling | Provider's resources = one pool divided among clients |
| Shared resources | Pool used by multiple clients (public/hybrid/community) |
| Dedicated resources | Wholly owned by one company (private cloud) |
| Multitenancy | Multiple tenants share hardware pool; data/apps kept separate |
| Rapid elasticity | Scale up/down almost instantly, no new hardware purchase |
| Pay-as-you-grow | Marketing term for elasticity-based subscriptions |
| Measured service / metered utilization | Usage tracked and billed transparently |
| Ingress | Uploading to the cloud — typically free |
| Egress | Downloading from the cloud — often carries a fee |
| Availability | SLA-guaranteed uptime, a.k.a. high availability |
| File synchronization | Most current file version kept in sync between cloud and local copy |
| Governing body | NIST (National Institute of Standards and Technology), U.S. Dept. of Commerce |

| Availability | Downtime/Year | Downtime/Day |
|---|---|---|
| Three nines (99.9%) | 8.77 hours | 1.44 minutes |
| Four nines (99.99%) | 52.6 minutes | 8.64 seconds |
| Five nines (99.999%) | 5.26 minutes | 864 ms |
| Six nines (99.9999%) | 31.56 seconds | 86.4 ms |
| Four nines five (99.995%) | — | 4.32 seconds |
| Typical CSP minimum guarantee | Three nines or three nines five |

---

## Cloud-Based Storage and Applications

| Concept | Detail |
|---|---|
| Cloud storage benefit | File access from any device/location; enables team collaboration |
| Cloud app delivery | Runs in browser; doesn't use local client hardware resources |
| Cloud app cross-platform benefit | Different client OSs can run the app without compatibility issues |
| Google cloud app suite | Google Workspace (accessed via Google Drive) |
| Microsoft cloud app suite | Microsoft 365 |
| Media streaming SaaS examples | Netflix, Amazon, Spotify, Pandora, Apple |
| Off-site/cloud email example | Gmail hosting a company's own .com domain — SaaS example |
