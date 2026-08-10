## Chapter 11: Virtualization and Cloud Computing | 60 Questions

> **Instructions:** Answer all questions before checking the Answer Key at the bottom of this file.

---

## Section 1: Direct/Basic Recall (Q1–20)

**1.** In what year did virtualization first appear as a computer industry technology?

- A. 1967
- B. 1991
- C. 2008
- D. 2016

---

**2.** What is the correct term for a virtualized copy of a computer running its own OS?

- A. Container
- B. Virtual machine (VM)
- C. Hypervisor
- D. Sandbox

---

**3.** Which purpose of a virtual machine is defined as a temporary, isolated desktop environment where an app's files are never written to the real hard drive?

- A. Test development
- B. Cross-platform virtualization
- C. Sandbox
- D. Legacy software virtualization

---

**4.** Where would a technician go to enable Windows Sandbox on Windows 11?

- A. Control Panel → Programs and Features
- B. Turn Windows Features On Or Off
- C. Windows Update settings
- D. Task Manager → Startup apps

---

**5.** Which term describes virtualizing an old application that only runs correctly on an equally old operating system?

- A. Cross-platform virtualization
- B. Test development
- C. Legacy software/OS virtualization
- D. Application streaming

---

**6.** A macOS-only application is run inside a virtualized copy of macOS hosted on a Windows server. What is this an example of?

- A. Sandboxing
- B. Cross-platform virtualization
- C. Legacy OS virtualization
- D. Desktop as a Service

---

**7.** What is another accepted name for a hypervisor?

- A. Container engine
- B. Virtual machine manager (VMM)
- C. Emulator only
- D. Resource pool

---

**8.** Which type of hypervisor sits directly on hardware with no separate host OS underneath it?

- A. Type 1
- B. Type 2
- C. Container engine
- D. Emulator

---

**9.** Which of the following is a named example of a Type 1 hypervisor?

- A. Oracle VM VirtualBox
- B. VMware Workstation
- C. VMware ESXi
- D. Windows Virtual PC

---

**10.** A Type 2 hypervisor is installed on top of what?

- A. A container engine
- B. An existing host OS
- C. Bare hardware directly
- D. A virtual switch

---

**11.** Which of the following is a named example of a Type 2 hypervisor?

- A. Citrix Hypervisor
- B. Microsoft Hyper-V
- C. Oracle VM VirtualBox
- D. VMware ESXi

---

**12.** What is the minimum amount of RAM Microsoft recommends before attempting to enable Hyper-V on Windows 11?

- A. 2 GB
- B. 4 GB
- C. 8 GB
- D. 16 GB

---

**13.** Which editions of Windows 11 support enabling Hyper-V?

- A. Home and Pro
- B. Pro and Enterprise
- C. Home only
- D. Any edition, with no restriction

---

**14.** What does Intel call its chip-level virtualization support?

- A. AMD-V
- B. SLAT
- C. VT (virtualization technology)
- D. VMM

---

**15.** What does AMD call its equivalent chip-level virtualization support?

- A. VT-c
- B. AMD-V
- C. SLAT
- D. VDI

---

**16.** What is a container, as defined in this chapter?

- A. A full replica of a physical computer, including all hardware
- B. An app packaged together with its runtime dependencies
- C. A type of bare-metal hypervisor
- D. A cloud storage bucket

---

**17.** Which of the following is described as the original and still most popular container engine?

- A. Kubernetes
- B. Docker
- C. LXD
- D. Andy

---

**18.** What is a container image most accurately described as?

- A. A full disk clone of the host OS
- B. A virtualization ISO-like file containing the app plus its dependencies and environment files
- C. A snapshot of RAM usage
- D. A virtual NIC configuration file

---

**19.** What does the acronym VDI stand for?

- A. Virtual Desktop Infrastructure
- B. Virtual Device Interconnect
- C. Variable Data Ingress
- D. Virtualized Disk Image

---

**20.** What is the function of a virtual switch?

- A. It encrypts traffic between virtual NICs
- B. It bridges virtual NICs to the physical NIC and manages traffic between them
- C. It allocates RAM to guest OSs
- D. It converts a Type 2 hypervisor into a Type 1 hypervisor

---

## Section 2: Intermediate/Conceptual (Q21–40)

**21.** A host OS requires 4 GB of RAM, and a guest OS requires 4 GB of RAM. What is the minimum total RAM the physical machine needs?

- A. 4 GB, since the guest borrows unused host RAM
- B. 8 GB, since host and guest RAM requirements are additive
- C. 2 GB, since virtualization compresses memory usage
- D. Unable to determine without knowing disk space

---

**22.** By default, does a virtual NIC need to be connected to the physical NIC?

- A. Yes, always — a VM cannot function without a physical NIC connection
- B. No — an administrator can build an isolated virtual network where VMs only talk to each other
- C. Only Type 1 hypervisors allow disconnected virtual NICs
- D. Only containers support disconnected virtual NICs

---

**23.** How does an emulator technically differ from a hypervisor, even though the terms are often used interchangeably?

- A. An emulator can host unlimited OSs; a hypervisor can only host one
- B. A hypervisor can support multiple OSs, while an emulator is built to behave like one specific system
- C. An emulator only works with containers, never full VMs
- D. There is no technical difference; they are the same thing

---

**24.** Why did attackers shift their focus toward compromising the hypervisor itself rather than individual guest OSs?

- A. Hypervisors have no security updates available
- B. A single successful hit on the hypervisor can expose every guest OS running on top of it at once
- C. Guest OSs cannot be infected with malware
- D. Hypervisors are never patched by vendors

---

**25.** Why does a container image typically measure in megabytes while an equivalent full virtual machine measures in gigabytes?

- A. Containers use a different file system entirely
- B. A container packages only the app and its runtime dependencies, not a full OS and hardware stack
- C. Containers do not include any dependencies at all
- D. VMs are always encrypted, which increases their size

---

**26.** Why does a Type 1 hypervisor generally outperform a Type 2 hypervisor?

- A. Type 1 requires more RAM per guest OS
- B. Type 1 has no host OS competing for the same physical resources
- C. Type 1 only supports one guest OS at a time
- D. Type 2 hypervisors cannot use virtual switches

---

**27.** Which cloud type is generally described as offering the best scalability, reliability, and cost-effectiveness, since it's run by a large IT provider with a deep resource pool?

- A. Private cloud
- B. Public cloud
- C. Community cloud
- D. Hybrid cloud

---

**28.** What is the main trade-off a company accepts when choosing a private cloud over a public one?

- A. It loses full control over its own security
- B. It gains rapid elasticity but loses cost savings
- C. It sacrifices rapid scalability and the "no hardware to manage" benefit in exchange for full security control
- D. It can no longer use virtualization internally

---

**29.** A company wants the flexibility of a public cloud but needs to keep its most sensitive data under tighter internal control. Which cloud type fits this need?

- A. Public
- B. Private
- C. Community
- D. Hybrid

---

**30.** What distinguishes a community cloud from a standard public cloud?

- A. Community clouds have zero security
- B. Community clouds are limited to government use only
- C. Community clouds are shared by a smaller circle of trusted organizations with common interests
- D. Community clouds never use resource pooling

---

**31.** In an IaaS arrangement, who is responsible for managing the software running on top of the provided infrastructure?

- A. The cloud provider
- B. The client
- C. Neither party — it's automated
- D. A third-party PaaS vendor

---

**32.** What does PaaS add on top of the infrastructure layer that IaaS alone does not provide?

- A. Physical server hardware
- B. Software development tools, including runtime environments
- C. End-user applications like word processors
- D. Network cabling

---

**33.** Which of the following is best classified as a SaaS offering?

- A. AWS EC2 virtual machine instances
- B. Google App Engine
- C. Microsoft 365
- D. A private on-premises hypervisor

---

**34.** How does multitenancy differ from resource pooling as described in this chapter?

- A. They are unrelated concepts
- B. Resource pooling describes the provider's pool of resources; multitenancy describes multiple clients using that same pool while keeping data/apps separate
- C. Multitenancy only applies to private clouds
- D. Resource pooling requires dedicated hardware per client

---

**35.** Which cloud type uses dedicated resources rather than shared resources?

- A. Public
- B. Private
- C. Hybrid
- D. Community

---

**36.** A client can scale cloud resources up or down almost instantly without buying new hardware. What characteristic does this describe?

- A. Measured service
- B. Rapid elasticity
- C. Broad network access
- D. File synchronization

---

**37.** Between ingress and egress, which one commonly carries an extra fee from cloud providers?

- A. Ingress, because uploading strains provider bandwidth
- B. Egress, because downloading data out of the cloud is often billed separately
- C. Neither — both are always free
- D. Both are always billed at the same flat rate

---

**38.** A CSP guarantees "five nines" of availability. Approximately how much downtime per year does that allow?

- A. 8.77 hours
- B. 52.6 minutes
- C. 5.26 minutes
- D. 31.56 seconds

---

**39.** A user edits a file on their laptop, and the same edit automatically appears on the cloud copy and vice versa. What cloud characteristic does this describe?

- A. Multitenancy
- B. File synchronization
- C. Rapid elasticity
- D. Broad network access

---

**40.** A team wants to run code automatically whenever a specific triggering event occurs, such as a failed login attempt, without provisioning a full server. Which AWS free-tier service is designed for exactly this?

- A. EC2
- B. S3
- C. RDS
- D. Lambda

---

## Section 3: Advanced/Troubleshooting (Q41–60)

**41.** A technician is setting up client-side virtualization for three guest OSs that each need Internet access, using one physical NIC. What is the most cost-effective way to configure this?

- A. Install three physical NICs, one per guest OS
- B. One physical NIC, one virtual NIC shared directly by all three guest OSs, and no virtual switch
- C. One physical NIC, three virtual NICs, and one virtual switch bridging them to the physical NIC
- D. Three physical NICs and three virtual switches

---

**42.** A Windows 11 host needs 4 GB of RAM to run comfortably, and a Linux guest OS needs 2 GB of RAM. What is the minimum RAM the physical system needs?

- A. 4 GB
- B. 6 GB
- C. 8 GB
- D. Cannot be determined from the information given

---

**43.** A technician is asked to identify legacy devices/software on a network. Which of the following would correctly be classified as legacy? (Choose all that apply.)

- A. A 386 processor
- B. The IPX/SPX protocol
- C. An application developed in 1989 that is still in use
- D. A machine with 1 GB of RAM

---

**44.** A host OS runs Windows 11 with three Windows 11 guest OSs configured via a Type 2 hypervisor. What is true about antivirus protection in this setup?

- A. Only the host OS needs antivirus software; VMs cannot be infected
- B. The host OS antivirus automatically protects all guest OSs as well
- C. Installing antivirus on the virtual switch protects every guest OS
- D. The host OS and each guest OS each need their own antivirus software installed

---

**45.** A manager wants to quickly test a new piece of software before deploying it network-wide, without risking any changes to the test machine's actual files. What should the technician use?

- A. A AAA server
- B. A sandbox
- C. A SCADA system
- D. A community cloud

---

**46.** A manager asks for a Type 2 hypervisor setup on an office computer. What disadvantage should the technician point out?

- A. The guest OS will compete for resources with the host OS, and a host OS failure takes down the guest OS too
- B. The guest OS will always run faster than on a Type 1 hypervisor
- C. The guest OS cannot access the network under any configuration
- D. Type 2 hypervisors require a dedicated physical server

---

**47.** A development team has finished building an app and needs to deploy it quickly across a large number of network users. Which virtualization technology is best suited for fast, lightweight deployment at scale?

- A. Type 1 hypervisor
- B. Type 2 hypervisor
- C. Containers
- D. A full VDI rollout

---

**48.** Which of the following statements about containers is NOT true? (Choose two.)

- A. Containers are generally faster to deploy than full hypervisor-based VMs
- B. Each container has a fixed minimum RAM requirement identical to a full VM
- C. A container can only ever hold exactly one application
- D. Containers virtualize the app and its dependencies, not the full physical infrastructure

---

**49.** A manager is worried about data security because multiple client companies will share the same physical hardware in a public cloud. What is the most accurate response?

- A. Multiple tenants may share the same hardware, but their data and applications are kept separate to avoid data security issues
- B. Data security is not a real concern once resource pooling is in place
- C. Cloud providers guarantee dedicated physical storage per client at no extra cost
- D. Containers automatically eliminate all multitenancy risk

---

**50.** A software developer on a Windows 11 client wants to test their app in three different guest operating systems side by side. What is the best setup for their workstation?

- A. Type 1 hypervisor
- B. Type 2 hypervisor
- C. A single shared container for all three OSs
- D. A public IaaS subscription only

---

**51.** A department manager needs significantly more storage space immediately and doesn't want to purchase or install new physical hardware. Which cloud service type best fits this need?

- A. IaaS
- B. SaaS
- C. PaaS
- D. A private on-premises upgrade

---

**52.** A cloud provider asks if you understand all the software and hardware needed to build an appropriate virtual environment for your organization's users. What term are they referring to?

- A. Type 1 hypervisor specifically
- B. Type 2 hypervisor specifically
- C. Virtual desktop infrastructure (VDI)
- D. A container engine

---

**53.** A monthly cloud invoice shows an unexpected egress surcharge. What most likely caused this charge?

- A. Uploading data to the cloud
- B. Downloading data from the cloud
- C. Creating a new application container
- D. Provisioning a new VDI instance

---

**54.** A CSP is signing contracts with three separate client companies, each requiring 10 TB of storage. Assuming standard contract terms, how much total storage capacity does the CSP need to have available to satisfy all three contracts?

- A. 10 TB, because clients share hardware in a multitenancy environment
- B. 20 TB, assuming heavy resource pooling
- C. 30 TB, matching what was actually contracted
- D. 60 TB, to account for elasticity reserves

---

**55.** A group of universities wants to combine research efforts and store shared data in a cloud environment with other trusted institutions, rather than the general public. Which cloud model fits best?

- A. Public
- B. Private
- C. Community
- D. Hybrid

---

**56.** A software development team needs runtime environments and development tools provided for them, without managing the underlying hardware themselves. Which service model should the technician recommend?

- A. IaaS
- B. PaaS
- C. SaaS
- D. Private cloud

---

**57.** A company negotiating a cloud contract wants the ability to rapidly increase capacity to handle unpredictable peak demand. What should they specifically request in the contract?

- A. Elasticity
- B. Availability
- C. Resource pooling only
- D. Metered utilization only

---

**58.** A company wants to scale resources quickly like a public cloud offers, but is worried about the confidentiality of some of its data. Which cloud model is most appropriate?

- A. Public
- B. Private
- C. Community
- D. Hybrid

---

**59.** A manager, having heard that "everyone is moving to the cloud," asks which benefits to expect. Which of the following should correctly be included? (Choose all that apply.)

- A. Increased security by default
- B. Increased scalability
- C. Lower cost compared to owning equivalent hardware
- D. Improved reliability through provider-managed failure handling

---

**60.** A technician is troubleshooting why a newly deployed VM on a Type 2 hypervisor feels sluggish even though the host machine has plenty of CPU cores. Host RAM usage is at 90% with the guest OS running. What is the most likely root cause?

- A. The physical NIC is misconfigured
- B. The host OS and guest OS RAM requirements were not both accounted for when provisioning total system RAM
- C. The hypervisor is a Type 1 hypervisor and needs no host OS
- D. The container engine is not installed

---

## Answer Key & Explanations

**1. A — 1967.** The chapter states virtualization has existed in the computer industry since 1967, even though its popularity exploded much more recently.

**2. B — Virtual machine (VM).** A VM is the appropriately named virtualized version of a computer, breaking the traditional one-to-one hardware-to-OS relationship.

**3. C — Sandbox.** A sandbox is a temporary, isolated desktop environment; any files or changes an app makes inside it disappear when the sandbox is shut down.

**4. B — Turn Windows Features On Or Off.** Windows Sandbox is enabled through this app by checking its box and rebooting, not through Control Panel's Programs and Features or Windows Update.

**5. C — Legacy software/OS virtualization.** This form of application virtualization specifically addresses old software that typically only runs correctly on an equally old operating system.

**6. B — Cross-platform virtualization.** This lets software built for one platform run on a different one — here, a macOS-only app running virtualized on a Windows host.

**7. B — Virtual machine manager (VMM).** The hypervisor and VMM are the same thing; a container engine and emulator are distinct, related concepts.

**8. A — Type 1.** A Type 1 (bare-metal) hypervisor sits directly on hardware with no separate host OS beneath it, effectively acting as the machine's OS.

**9. C — VMware ESXi.** VMware ESXi is a Type 1 hypervisor; VirtualBox, VMware Workstation, and Windows Virtual PC are all Type 2 examples.

**10. B — An existing host OS.** Type 2 hypervisors install on top of a host OS, which is why they're the standard choice for client-side virtualization.

**11. C — Oracle VM VirtualBox.** VirtualBox is a Type 2 hypervisor; Citrix Hypervisor, Hyper-V, and ESXi are all Type 1 examples.

**12. B — 4 GB.** Hyper-V's minimum stated RAM requirement is 4 GB, alongside a 64-bit SLAT-capable CPU and BIOS/UEFI virtualization support.

**13. B — Pro and Enterprise.** Hyper-V requires Windows 11 Pro or Enterprise; it is not available on the Home edition.

**14. C — VT (virtualization technology).** Intel's chip-level virtualization support is branded VT; AMD's equivalent is AMD-V.

**15. B — AMD-V.** AMD-V is AMD's chip-level virtualization support, paralleling Intel's VT branding.

**16. B — An app packaged together with its runtime dependencies.** This is the chapter's definition of a container — it virtualizes the software layer only, not the underlying physical infrastructure.

**17. B — Docker.** Docker is described as the original and still most popular container engine; Buildah, Podman, LXD, and Containerd are named alternatives.

**18. B — A virtualization ISO-like file containing the app plus its dependencies and environment files.** This is the container image, which gets distributed and then run by a container engine on the receiving end.

**19. A — Virtual Desktop Infrastructure.** VDI encompasses the software and hardware needed to create a virtual desktop environment, whether on-premises or in the cloud.

**20. B — It bridges virtual NICs to the physical NIC and manages traffic between them.** The virtual switch is what typically connects an otherwise-isolated virtual NIC to the outside physical network.

**21. B — 8 GB, since host and guest RAM requirements are additive.** The host OS's RAM needs sit on top of, not shared with, whatever RAM is allocated to the guest OS.

**22. B — No.** An administrator can build a fully isolated virtual network where VMs only talk to each other; bridging to the physical NIC via a virtual switch is common in practice but not required.

**23. B — A hypervisor can support multiple OSs, while an emulator is built to behave like one specific system.** The two terms are often used interchangeably in casual conversation despite this technical distinction.

**24. B — A single successful hit on the hypervisor can expose every guest OS running on top of it at once.** This is why attackers shifted focus away from individually targeting each guest OS.

**25. B — A container packages only the app and its runtime dependencies, not a full OS and hardware stack.** This is exactly why containers stay in the megabyte range while full VMs run into gigabytes.

**26. B — Type 1 has no host OS competing for the same physical resources.** With no host OS layer to share resources with, Type 1 hypervisors generally deliver better performance than Type 2.

**27. B — Public cloud.** Public clouds, run by large providers with big resource pools, offer the strongest scalability, reliability, flexibility, and cost-effectiveness of the four cloud types.

**28. C — It sacrifices rapid scalability and the "no hardware to manage" benefit in exchange for full security control.** A private cloud trades away the public cloud's biggest conveniences in exchange for total internal control.

**29. D — Hybrid.** A hybrid cloud combines public-cloud flexibility with a private-cloud option for storing more sensitive information.

**30. C — Community clouds are shared by a smaller circle of trusted organizations with common interests.** This gives community clouds better security than a fully public cloud, at the cost of some economies of scale.

**31. B — The client.** In IaaS, the provider supplies hardware/infrastructure while the client provides and manages its own software — which is also why IaaS demands the most client-side network management expertise of the three tiers.

**32. B — Software development tools, including runtime environments.** PaaS layers these on top of IaaS so developers can focus on building and scaling their app instead of managing hardware.

**33. C — Microsoft 365.** Microsoft 365 is a SaaS product; Google App Engine is PaaS, and raw EC2 instances are IaaS.

**34. B — Resource pooling describes the provider's pool of resources; multitenancy describes multiple clients using that same pool while keeping data/apps separate.** The two concepts are closely linked but describe the arrangement from different sides.

**35. B — Private.** A private cloud is entirely owned and controlled by one company, making its resources dedicated rather than shared.

**36. B — Rapid elasticity.** Rapid elasticity is the ability to scale resources up or down almost instantly without a hardware purchase cycle.

**37. B — Egress, because downloading data out of the cloud is often billed separately.** Ingress (uploading into the cloud) is typically free aside from the underlying storage cost.

**38. C — 5.26 minutes.** Five nines (99.999%) availability corresponds to roughly 5.26 minutes of downtime per year, per the chapter's availability table.

**39. B — File synchronization.** File synchronization ensures the most current version of a file exists in both locations, with changes propagating automatically in both directions.

**40. D — Lambda.** Lambda is AWS's service specifically designed to run code automatically in response to a triggering event, such as a failed login.

**41. C — One physical NIC, three virtual NICs, and one virtual switch bridging them to the physical NIC.** This gives all three guest OSs independent virtual NICs while sharing a single physical NIC through one virtual switch — the most cost-effective valid configuration.

**42. B — 6 GB.** Host and guest RAM requirements are additive: 4 GB for the Windows 11 host plus 2 GB for the Linux guest equals 6 GB minimum.

**43. A, B, C — A 386 processor, the IPX/SPX protocol, and a 1989 application are all legacy.** 1 GB of RAM alone doesn't make a device legacy; it depends on outdated hardware, protocols, or software rather than a specific RAM figure.

**44. D — The host OS and each guest OS each need their own antivirus software installed.** Virtualization does not remove the need for antimalware protection on every individual OS instance, guest or host.

**45. B — A sandbox.** A sandbox lets the manager test new software in an isolated, temporary environment without risking real files on the test machine.

**46. A — The guest OS will compete for resources with the host OS, and a host OS failure takes down the guest OS too.** This is the core disadvantage of a Type 2 hypervisor compared to a Type 1.

**47. C — Containers.** Containers are smaller, faster to deploy, and easier to scale across a large number of users than a full hypervisor-based VM rollout.

**48. B, C — "Each container has a fixed minimum RAM requirement identical to a full VM" and "a container can only ever hold exactly one application" are NOT true.** Containers are lighter-weight than VMs (no fixed VM-equivalent RAM floor), and while they usually hold one app, the chapter notes they can hold more than one.

**49. A — Multiple tenants may share the same hardware, but their data and applications are kept separate to avoid data security issues.** This is the accurate description of multitenancy's approach to shared-hardware security.

**50. B — Type 2 hypervisor.** A Type 2 hypervisor on the developer's existing Windows 11 client lets them run and test multiple guest OSs alongside their normal desktop environment.

**51. A — IaaS.** IaaS is the service model for exactly this kind of situation — buying processing, storage, and networking capacity without purchasing physical hardware.

**52. C — Virtual desktop infrastructure (VDI).** VDI is the umbrella term for the full software-and-hardware package needed to build a virtual environment for an organization's users.

**53. B — Downloading data from the cloud.** Egress refers to data leaving the cloud (downloads), which is the type of activity that commonly triggers extra charges.

**54. C — 30 TB, matching what was actually contracted.** Multitenancy describes shared hardware, not shared storage allocations — each client's contracted 10 TB is still separately provisioned, so the CSP needs 30 TB total to honor all three contracts.

**55. C — Community.** A community cloud fits multiple organizations with shared interests — like several universities — pooling resources while keeping the circle of participants smaller and more trusted than the general public.

**56. B — PaaS.** PaaS specifically supplies development tools and runtime environments on top of managed infrastructure, exactly what this development team needs.

**57. A — Elasticity.** Elasticity is the specific characteristic that lets a client rapidly scale resources to handle unpredictable demand spikes.

**58. D — Hybrid.** A hybrid cloud lets the company keep its most sensitive data on a private component while still getting the public cloud's rapid scalability for everything else.

**59. B, C, D — Increased scalability, lower cost, and improved reliability are legitimate cloud benefits; increased security is not guaranteed by default.** Security is widely regarded as one of the cloud's persistent challenges, not an automatic benefit, since data lives off-premises and travels over the Internet.

**60. B — The host OS and guest OS RAM requirements were not both accounted for when provisioning total system RAM.** High host RAM usage under a Type 2 hypervisor, with the guest still running, points to insufficient total RAM having been allocated for both the host and the guest simultaneously — a CPU or network issue wouldn't explain 90% RAM usage specifically.
