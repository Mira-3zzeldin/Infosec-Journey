## Chapter 12: Core Hardware and Network Troubleshooting | 60 Questions

> **Instructions:** Answer all questions before checking the Answer Key at the bottom of this file.

---

## Section 1: Direct/Basic Recall (Q1–20)

**1.** What does the acronym POST stand for?

- A. Power-On System Trace
- B. Power-On Self-Test
- C. Primary Operating System Trigger
- D. Peripheral Output Signal Test

---

**2.** Which small battery on the motherboard is responsible for retaining BIOS/UEFI settings such as date and time while the system is powered off?

- A. The lithium backup cell
- B. The CMOS battery
- C. The bootstrap battery
- D. The NVRAM cell

---

**3.** A technician notices that a desktop's system clock resets to an incorrect date every time it's unplugged. What is the most likely cause?

- A. A failing power supply
- B. A corrupted boot sector
- C. A dying CMOS battery
- D. An out-of-date BIOS/UEFI

---

**4.** What is the purpose of a POST card?

- A. It stores the boot priority order permanently
- B. It displays a numeric code corresponding to the current stage of the boot process
- C. It generates the beep code pattern used by AMI BIOS
- D. It replaces the CMOS battery when it fails

---

**5.** What is the term for socketed components (such as RAM or expansion cards) gradually working loose from repeated heating and cooling cycles?

- A. Thermal drift
- B. Capacitor swelling
- C. Chip creep
- D. Contact fatigue

---

**6.** What is the primary purpose of a heat sink?

- A. To regulate voltage delivered to the CPU
- B. To dissipate heat away from a processor or chip
- C. To filter dust from intake air
- D. To store excess electrical charge

---

**7.** Which of the following components does NOT produce sound during normal or failing operation, because it has no moving parts?

- A. Mechanical hard disk drive
- B. Optical drive
- C. Power supply fan
- D. RAM

---

**8.** What term describes a motherboard capacitor that has bulged and possibly leaked brownish-red electrolyte from its top vents?

- A. A blown fuse
- B. A distended (swollen) capacitor
- C. A grounded trace
- D. A shorted rail

---

**9.** What is the proprietary crash screen displayed by Windows when the operating system encounters a fatal error?

- A. Kernel Panic
- B. Blue Screen of Death (BSOD)
- C. Stop Sign
- D. Black Screen of Death

---

**10.** What is the proprietary crash indicator displayed by macOS during a fatal system error?

- A. A spinning pinwheel
- B. A red X icon
- C. A blue screen
- D. A flashing question mark folder

---

**11.** As a general rule of thumb, what percentage of a hard drive's space should remain free to avoid performance degradation?

- A. At least 25 percent
- B. At least 10 percent
- C. At least 50 percent
- D. At least 5 percent

---

**12.** What does the acronym IOPS stand for?

- A. Internal Operations Per Session
- B. Input/Output Operations Per Second
- C. Indexed Object Positioning System
- D. Integrated Onboard Performance Standard

---

**13.** Since what year has S.M.A.R.T. technology been included in nearly every hard drive manufactured?

- A. 1998
- B. 2004
- C. 2010
- D. 2014

---

**14.** Approximately how many individual metrics does S.M.A.R.T. report on a typical drive?

- A. 12
- B. 25
- C. 70
- D. 150

---

**15.** Which RAID level uses disk striping with parity and requires a minimum of three drives?

- A. RAID 0
- B. RAID 1
- C. RAID 5
- D. RAID 10

---

**16.** Which networking tool, sometimes nicknamed a "fox and hound," is used to trace an unlabeled cable from one location to another?

- A. Cable tester
- B. Toner probe
- C. Punchdown tool
- D. Network tap

---

**17.** Which tool tests whether a network adapter is capable of both sending and receiving data?

- A. Loopback plug
- B. Crimper
- C. Multimeter
- D. Wi-Fi analyzer

---

**18.** What is the primary function of a network tap?

- A. To physically connect exposed wire ends into a 110 block
- B. To create a copy of network traffic for monitoring devices without disrupting normal traffic
- C. To measure voltage and resistance on a cable run
- D. To attach RJ-45 connectors to the end of a cable

---

**19.** An IPv4 address in which range indicates that a client has fallen back to Automatic Private IP Addressing (APIPA) because it could not reach a DHCP server?

- A. 10.0.0.x
- B. 172.16.x.x
- C. 169.254.x.x
- D. 192.168.x.x

---

**20.** IPv6 link-local addresses, the equivalent of APIPA, always fall within which address range?

- A. 2001::/32
- B. fe80::/10
- C. ::1/128
- D. fc00::/7

---

## Section 2: Intermediate/Conceptual (Q21–40)

**21.** A technician types `ipconfig /release` followed by `ipconfig /renew` at a client's command prompt. What is this sequence primarily used to test?

- A. Whether the DNS resolver cache is corrupted
- B. Whether the client can successfully obtain an address from a DHCP server
- C. Whether the client's NIC driver is installed correctly
- D. Whether the default gateway is reachable

---

**22.** Which `netstat` switch displays the local routing table?

- A. -a
- B. -n
- C. -r
- D. -e

---

**23.** Which two utilities does `pathping` functionally combine into a single command?

- A. `ipconfig` and `netstat`
- B. `tracert` and `ping`
- C. `nslookup` and `hostname`
- D. `net` and `netstat`

---

**24.** Which RAID level provides absolutely no fault tolerance, meaning a single drive failure causes the loss of the entire array?

- A. RAID 0
- B. RAID 1
- C. RAID 5
- D. RAID 10

---

**25.** According to the large-scale Google/Backblaze study referenced in this chapter, which of the following S.M.A.R.T. attributes was found to be strongly correlated with drive failure?

- A. Drive operating temperature
- B. Total number of system reboots
- C. Reallocated Sector Count
- D. Time since last defragmentation

---

**26.** A technician discovers a distended capacitor on a motherboard. What is the recommended course of action?

- A. Drain the capacitor's charge with a multimeter and continue using the board
- B. Wipe away the electrolyte residue with a cloth and monitor the system
- C. Replace the motherboard, and avoid touching any leaked residue
- D. Reflash the BIOS/UEFI to reset the capacitor's charge state

---

**27.** Why can running a desktop PC with its case cover removed actually make overheating worse, even though the components seem to be getting more open air?

- A. Removing the cover disables the power supply's cooling fan automatically
- B. The case is engineered to direct airflow along a specific path, which the cover's removal disrupts
- C. An open case increases static electricity buildup on internal components
- D. Removing the cover voids the CPU's thermal warranty and disables throttling

---

**28.** A technician hears a sound described as "fingernails on a chalkboard" coming from a mechanical hard drive. What does this most likely indicate?

- A. A failing cooling fan bearing
- B. The read/write heads have crashed into the platter
- C. A loose SATA data cable vibrating against the case
- D. Normal platter spin-up noise

---

**29.** Why does structured troubleshooting methodology recommend changing only one variable at a time when attempting a fix?

- A. It reduces the total number of steps documented in the service log
- B. Changing multiple things at once makes it impossible to know which change fixed the problem and risks introducing new issues
- C. Most operating systems only allow one configuration change per reboot cycle
- D. Manufacturers void warranties if more than one component is changed per visit

---

**30.** A drive is confirmed visible in both BIOS/UEFI and in Windows Disk Management, but it still does not appear in File Explorer. What is the most likely next step?

- A. Reflash the motherboard BIOS/UEFI
- B. Initialize the disk, create a partition, and assign it a drive letter
- C. Replace the SATA or M.2 adapter
- D. Run `bootrec /fixmbr` from WinRE

---

**31.** On an NVMe SSD, what does the S.M.A.R.T. metric "Percentage Used" indicate?

- A. The percentage of the drive's total storage capacity currently occupied by data
- B. The percentage of the drive's finite write endurance that has been consumed
- C. The percentage of read/write requests that resulted in an error
- D. The percentage of time the drive has spent in a low-power state

---

**32.** A user can successfully ping `8.8.8.8` but cannot ping `google.com`. What does this indicate?

- A. A hardware failure in the NIC
- B. A DNS resolution problem
- C. A duplex mismatch on the switch port
- D. An IP address conflict

---

**33.** According to Cisco's definition referenced in this chapter, what qualifies as port flapping?

- A. A port that stays disabled for more than 10 minutes
- B. A port opening and closing three or more times per second for at least 10 seconds
- C. A port that negotiates the wrong duplex setting once per session
- D. A port that drops a single packet during a firmware update

---

**34.** Roughly how many client devices should ideally share a single legacy (pre-Wi-Fi 6) wireless access point before intermittent access problems become likely?

- A. No more than 10
- B. No more than 30
- C. No more than 100
- D. No more than 250

---

**35.** What is the key distinction between latency and jitter on a network?

- A. Latency only affects wireless connections; jitter only affects wired connections
- B. Latency is a consistent measure of delay, while jitter is variability in that delay over time
- C. Latency is measured in packets lost, while jitter is measured in milliseconds
- D. Jitter only occurs during VoIP calls; latency occurs on all traffic types

---

**36.** A user's computer was manually assigned a static IP address that falls within the DHCP server's active scope, creating an intermittent conflict with another host. Why does simply rebooting the affected machine fail to resolve it?

- A. Static IP addresses cannot be changed without reinstalling the OS
- B. The DHCP server is unaware of the conflict and will hand out the same overlapping address again
- C. Rebooting clears the ARP cache, which makes the conflict worse
- D. Static addresses require a firmware update to release properly

---

**37.** What is the purpose of enabling Quality of Service (QoS) on a router experiencing poor VoIP call quality?

- A. It increases the router's total available bandwidth
- B. It prioritizes voice traffic over other network traffic during periods of congestion
- C. It automatically upgrades the WAN connection speed
- D. It encrypts voice packets to prevent interception

---

**38.** On most motherboards with built-in video circuitry, what typically happens when a dedicated expansion video card is installed?

- A. Both the onboard and expansion video outputs remain active simultaneously
- B. The onboard video circuitry is automatically disabled
- C. The expansion card is disabled until the onboard video is manually turned off
- D. The system defaults to the onboard video until a driver is installed

---

**39.** What is the functional difference between a cable tester and a loopback plug?

- A. A cable tester verifies a cable's integrity, while a loopback plug tests a NIC's ability to send and receive
- B. A cable tester only works on fiber, while a loopback plug only works on copper
- C. A cable tester requires a network connection, while a loopback plug does not
- D. There is no meaningful difference; they test the identical function

---

**40.** A user reports that their computer feels sluggish. Task Manager shows disk usage sustained at 95 percent even though CPU and memory usage are both under 30 percent. What does this pattern most strongly suggest?

- A. A failing or overloaded CPU
- B. A storage-related bottleneck, such as a nearly full or failing drive
- C. Insufficient physical RAM
- D. A malfunctioning power supply

---

## Section 3: Advanced/Troubleshooting Scenarios (Q41–60)

**41.** A desktop computer won't boot. The technician hears a consistent, rhythmic ticking sound from inside the case, and the system never displays anything on screen. What is the most likely problem?

- A. A failing mechanical hard drive
- B. A failing power supply fan
- C. A dislodged RAM module
- D. A corrupted BIOS/UEFI

---

**42.** A user powers on their desktop and hears a loud, high-pitched squealing sound coming from inside the case. Which components are plausible sources of this noise? (Choose two.)

- A. CPU fan
- B. RAM
- C. Power supply fan
- D. SSD

---

**43.** A technician smells a distinct burning odor and notices a thin trail of smoke coming from the rear of a desktop computer. What should the technician do first?

- A. Open the case immediately while the system is still powered on to locate the source
- B. Shut the system down immediately, then open the case to inspect for damage
- C. Run a S.M.A.R.T. diagnostic to rule out a failing drive
- D. Continue using the system but monitor Task Manager for unusual activity

---

**44.** A desktop reaches the BIOS/UEFI splash screen and then reboots, repeating this cycle indefinitely. Which two components are the most likely causes? (Choose two.)

- A. RAM
- B. Motherboard
- C. Network interface card
- D. Optical drive

---

**45.** A user presses the power button on their desktop and nothing happens at all. They've confirmed the outlet works and the cable is firmly seated. Which two components are the most likely culprits? (Choose two.)

- A. Power supply
- B. Power cord
- C. RAM
- D. CPU

---

**46.** A technician is told a system has been experiencing overheating. Which single component is statistically the most likely to be the source of the problem?

- A. Power supply
- B. Motherboard
- C. CPU
- D. RAM

---

**47.** A laptop user with an 802.11ax wireless card recently moved to a new desk. They now report intermittent connectivity drops and noticeably slower transfer speeds in the new location. What is the most likely resolution?

- A. Replace the wireless network card
- B. Run `ipconfig` to confirm the DHCP-assigned address
- C. Install a new wireless access point closer to the new desk location
- D. Use a network tap to monitor for IP address conflicts

---

**48.** While troubleshooting a client's connectivity issue, a technician wants to obtain a fresh IP address from the DHCP server after having already released the current one. Which command accomplishes this?

- A. `ipconfig /refresh`
- B. `ipconfig /renew`
- C. `ip /release`
- D. `ip /start`

---

**49.** A technician suspects a network card is beginning to fail and wants to confirm it can send and receive data through its RJ-45 port. Which tool is designed for this specific test?

- A. Toner probe
- B. Loopback plug
- C. Multimeter
- D. Cable tester

---

**50.** A technician is sent into a wiring closet to troubleshoot a connectivity issue and finds that none of the patch cables are labeled, with several disconnected entirely. Which tool would most efficiently help identify where each cable runs?

- A. Loopback plug
- B. Punchdown tool
- C. Cable tester
- D. Toner probe

---

**51.** A critical server's network cable has failed. No pre-made replacement cables are available, but there is bulk cable and a supply of connectors on hand. Which tool is required to build a new cable?

- A. Crimper
- B. Punchdown tool
- C. Cable tester
- D. Loopback plug

---

**52.** A technician troubleshooting a server discovers that one drive in a RAID 0 array has failed. What is the correct next step?

- A. Replace the drive; the data is intact because RAID 0 mirrors data
- B. Replace the drive; the data is intact because RAID 0 stripes with parity
- C. Replace the drive; the data on the array has been lost
- D. No action is needed, since RAID 0 tolerates single-drive failures

---

**53.** While troubleshooting intermittent internet connectivity, a technician notices that port 443 on the router repeatedly opens and closes in rapid succession. What is this an example of?

- A. Jitter
- B. High latency
- C. External interference
- D. Port flapping

---

**54.** A laptop boots normally, but the internal hard drive is not recognized anywhere in the system. Where should the technician check first to begin troubleshooting?

- A. Windows Event Viewer
- B. BIOS/UEFI Setup
- C. Device Manager only
- D. The paging file configuration

---

**55.** A server boots and reaches a point where the BIOS/UEFI clearly detects the boot drive, but the operating system fails to load, displaying an error indicating no OS was found. Which command, run from WinRE, is most appropriate as a first step?

- A. `ipconfig /flushdns`
- B. `bootrec /fixmbr`
- C. `netstat -r`
- D. `net share /delete`

---

**56.** Multiple users in the same department report they cannot reach any network resources, internal or external. A technician confirms their own machine has no issue reaching the same resources. What does this pattern suggest?

- A. A single failed NIC on one user's machine
- B. A central issue affecting the shared infrastructure, such as a switch or router
- C. A DNS misconfiguration limited to the technician's machine
- D. A software licensing conflict

---

**57.** A user reports they can reach shared drives and internal email but cannot load any external websites. Their IP address is confirmed to be valid and not in the 169.254.x.x range. What should the technician check next?

- A. Whether the DHCP server is issuing valid leases
- B. Whether they can ping an external site by IP address versus by hostname
- C. Whether the CMOS battery needs replacement
- D. Whether the RAID array is degraded

---

**58.** A technician troubleshooting a wireless dead zone finds that client devices lose connection whenever a nearby microwave oven is running. What is the most accurate description of this issue?

- A. Port flapping
- B. IP address conflict
- C. External interference
- D. Authentication failure

---

**59.** One user in an office reports repeated authentication failures when logging into a Windows domain, while every other user in the office logs in normally. What is the most efficient first step?

- A. Reboot the domain controller
- B. Confirm the user isn't mistyping their password, checking Caps Lock first
- C. Rebuild the RAID array hosting user profiles
- D. Replace the user's network cable

---

**60.** A technician benchmarks a NAS device's IOPS monthly and notices a steady downward trend over the past six months, even though no single reading is alarmingly low. What is the most appropriate interpretation?

- A. IOPS trends are not meaningful without comparing to another manufacturer's drive
- B. The steadily declining trend itself is a warning sign worth investigating, regardless of the absolute numbers
- C. IOPS only matters for SSDs, so a HDD-based NAS can be ignored
- D. A single low reading matters more than any trend over time

---

## Answer Key & Explanations

**1. B — Power-On Self-Test.** POST is the diagnostic routine the BIOS/UEFI executes automatically every time a computer is powered on, checking core hardware before handing off to the OS.

**2. B — The CMOS battery.** This small watch-battery-style cell keeps the BIOS/UEFI's settings, including date and time, intact whenever the system itself has no power.

**3. C — A dying CMOS battery.** Losing date/time settings specifically after every power cycle is the textbook symptom of a CMOS battery that can no longer hold its charge; a simple battery replacement resolves it.

**4. B — It displays a numeric code corresponding to the current stage of the boot process.** Each code maps to a specific checkpoint in the boot sequence, so a POST card lets a technician see exactly where the process is stalling even without a working display.

**5. C — Chip creep.** Repeated thermal expansion and contraction cycles gradually walk socketed components like RAM or expansion cards out of their sockets; the fix is simply reseating them.

**6. B — To dissipate heat away from a processor or chip.** A heat sink is a metal component, typically aluminum or copper, designed to pull heat away from a chip so it doesn't reach damaging temperatures.

**7. D — RAM.** RAM has no moving parts and therefore produces no operational sound, unlike mechanical hard drives, optical drives, and any device with a fan.

**8. B — A distended (swollen) capacitor.** This is the specific named symptom for a capacitor that has bulged and potentially leaked electrolyte, and it strongly indicates the motherboard is failing.

**9. B — Blue Screen of Death (BSOD).** BSOD is Windows' proprietary fatal-error screen; macOS uses a spinning pinwheel for the equivalent situation.

**10. A — A spinning pinwheel.** This is macOS's visual indicator that the system is unresponsive or has hit a fatal error, functioning as the Mac equivalent of Windows' BSOD.

**11. B — At least 10 percent.** This is the standard rule of thumb threshold below which drives, especially those hosting an active paging file, tend to show noticeably degraded performance.

**12. B — Input/Output Operations Per Second.** IOPS is an industry-standard throughput metric frequently quoted on NAS and RAID systems, though it's most useful as a trend over time rather than a single number.

**13. B — 2004.** S.M.A.R.T. has been included in nearly every hard drive manufactured since 2004, giving drives a built-in mechanism for reporting reliability-related metrics.

**14. C — 70.** S.M.A.R.T. reports roughly 70 individual metrics, though not all of them have a clearly agreed-upon relationship to impending drive failure.

**15. C — RAID 5.** RAID 5 stripes data with a parity block distributed across all drives and requires a minimum of three drives, tolerating a single drive failure without data loss.

**16. B — Toner probe.** Its nickname "fox and hound" comes from its two-piece design — a tone generator and a probe — used to trace a specific cable through a bundle of unlabeled wiring.

**17. A — Loopback plug.** A loopback plug connects directly to the NIC and, paired with loopback test software, confirms whether the adapter can both transmit and receive successfully.

**18. B — To create a copy of network traffic for monitoring devices without disrupting normal traffic.** Unlike a punchdown tool or crimper, a network tap is purely a monitoring device that mirrors traffic for analysis.

**19. C — 169.254.x.x.** This range is reserved for Automatic Private IP Addressing, which a client assigns to itself only when it expected a DHCP-issued address but received no response.

**20. B — fe80::/10.** This is the reserved IPv6 range for link-local addresses, functioning as the IPv6 counterpart to IPv4's APIPA mechanism.

**21. B — Whether the client can successfully obtain an address from a DHCP server.** Deliberately releasing the current lease and then requesting a new one is a direct, repeatable test of DHCP server reachability.

**22. C — -r.** The `-r` switch specifically displays the local system's routing table, distinct from connection listings (`-a`) or numerical formatting (`-n`).

**23. B — `tracert` and `ping`.** `pathping` first maps the route like `tracert`, then pings every node along that route to reveal exactly where packet loss is occurring — functionality neither command alone provides.

**24. A — RAID 0.** RAID 0 stripes data across drives purely for performance with zero redundancy, meaning the failure of any single drive causes total data loss across the array.

**25. C — Reallocated Sector Count.** This was one of five S.M.A.R.T. attributes the referenced study found strongly correlated with failure; temperature and reboot count, by contrast, were specifically found not to correlate.

**26. C — Replace the motherboard, and avoid touching any leaked residue.** Replacement is the safe, recommended fix, since the leaked electrolyte can cause chemical burns and capacitors can retain a dangerous charge.

**27. B — The case is engineered to direct airflow along a specific path, which the cover's removal disrupts.** Even though an open case seems more exposed to ambient air, it breaks the deliberate intake/exhaust path the case was designed around.

**28. B — The read/write heads have crashed into the platter.** This specific, memorable sound indicates physical contact between the heads and the spinning platter — a serious mechanical failure.

**29. B — Changing multiple things at once makes it impossible to know which change fixed the problem and risks introducing new issues.** Isolating variables is central to systematic troubleshooting, both for correctly diagnosing the fix and for avoiding unintended side effects.

**30. B — Initialize the disk, create a partition, and assign it a drive letter.** A drive visible at the BIOS and Disk Management level but absent from File Explorer typically just hasn't been prepared for file-system use yet.

**31. B — The percentage of the drive's finite write endurance that has been consumed.** This metric estimates how much of an NVMe drive's total lifetime write capacity has been used, independent of how full the drive currently is.

**32. B — A DNS resolution problem.** Successfully reaching a destination by raw IP address but failing by hostname isolates the failure to name resolution rather than general connectivity.

**33. B — A port opening and closing three or more times per second for at least 10 seconds.** This is the specific threshold Cisco uses to formally define port flapping, distinguishing it from a single, one-off disconnect.

**34. B — No more than 30.** Legacy access points are recommended to serve roughly 30 or fewer clients before intermittent access issues become likely; Wi-Fi 6 and newer can handle a higher load.

**35. B — Latency is a consistent measure of delay, while jitter is variability in that delay over time.** Jitter specifically describes inconsistency in latency, not the presence of delay itself.

**36. B — The DHCP server is unaware of the conflict and will hand out the same overlapping address again.** Because the DHCP server doesn't know the address was manually claimed, releasing and renewing simply re-triggers the same conflict.

**37. B — It prioritizes voice traffic over other network traffic during periods of congestion.** QoS doesn't add bandwidth; it reorders how existing bandwidth is allocated so latency-sensitive voice traffic is less affected by congestion.

**38. B — The onboard video circuitry is automatically disabled.** Installing a dedicated video card typically deactivates a motherboard's built-in video output, which is why the monitor must be reconnected to the new card.

**39. A — A cable tester verifies a cable's integrity, while a loopback plug tests a NIC's ability to send and receive.** These tools solve related but distinct problems — one validates the cable itself, the other validates the network adapter.

**40. B — A storage-related bottleneck, such as a nearly full or failing drive.** High sustained disk usage with low CPU and memory usage points specifically at the storage subsystem rather than processing power or RAM.

**41. A — A failing mechanical hard drive.** A rhythmic ticking sound combined with a failure to boot is the classic signature of a mechanical hard drive on the verge of complete failure.

**42. A, C — CPU fan; Power supply fan.** Squealing sounds at power-on are almost always tied to a moving component under mechanical stress, and both are among the most common fan-related noise sources, along with case fans.

**43. B — Shut the system down immediately, then open the case to inspect for damage.** A burning smell or visible smoke calls for an immediate, safe shutdown before any inspection, never continued operation or investigation while still powered.

**44. A, B — RAM; Motherboard.** Continuous reboots that occur right at the BIOS/UEFI screen point strongly toward a memory or motherboard-level fault rather than a peripheral like a NIC or optical drive.

**45. A, B — Power supply; Power cord.** With the outlet already confirmed functional, a completely unresponsive system most commonly traces back to the power supply itself or a faulty/loose power cord.

**46. C — CPU.** While other components can overheat, the CPU is statistically the most common component to experience overheating-related failures, especially under sustained load.

**47. C — Install a new wireless access point closer to the new desk location.** Since the card itself is a modern 802.11ax adapter, distance-driven signal weakness after the desk move is the most likely cause, making a closer WAP the most direct fix.

**48. B — `ipconfig /renew`.** After releasing an address with `/release`, the `/renew` switch requests a fresh lease from the DHCP server.

**49. B — Loopback plug.** A loopback plug, used with loopback testing software, is specifically designed to verify that a NIC's RJ-45 port can send and receive data correctly.

**50. D — Toner probe.** With cables unlabeled and disconnected, a toner probe's tone-generator-and-probe design is purpose-built for tracing a specific cable's physical run.

**51. A — Crimper.** Building a new cable from bulk cable and loose connectors requires a crimper, which strips, cuts, and attaches the connector in one tool.

**52. C — Replace the drive; the data on the array has been lost.** RAID 0 has no redundancy, so any single drive failure results in the complete loss of data across the entire striped array.

**53. D — Port flapping.** A port rapidly and repeatedly opening and closing matches the specific definition of port flapping, distinct from latency, jitter, or interference.

**54. B — BIOS/UEFI Setup.** Before assuming an OS-level or driver-level problem, the technician must confirm whether the drive is detected at the firmware level at all, since the OS can never see a drive the BIOS/UEFI doesn't detect first.

**55. B — `bootrec /fixmbr`.** With the drive detected but the OS unfound, a damaged master boot record is the likely cause, and `bootrec /fixmbr` (often followed by `bootrec /fixboot`) is the standard first repair command from WinRE.

**56. B — A central issue affecting the shared infrastructure, such as a switch or router.** Multiple simultaneous reports pointing to a shared resource, combined with an unaffected machine elsewhere, strongly suggests a central point of failure rather than isolated client issues.

**57. B — Whether they can ping an external site by IP address versus by hostname.** This comparison is the standard next diagnostic step to separate a DNS problem from a deeper connectivity or port-blocking issue, especially once a valid IP address and internal access are already confirmed.

**58. C — External interference.** Microwave ovens are a well-known source of interference on the 2.4 GHz wireless band, and connectivity dropping specifically while one is running is a textbook interference symptom.

**59. B — Confirm the user isn't mistyping their password, checking Caps Lock first.** Since only one user is affected while everyone else logs in normally, user error is by far the most probable and least invasive first thing to rule out.

**60. B — The steadily declining trend itself is a warning sign worth investigating, regardless of the absolute numbers.** IOPS is most useful as a longitudinal measure; a consistent downward trend over months is meaningful even without any single alarmingly low reading.
