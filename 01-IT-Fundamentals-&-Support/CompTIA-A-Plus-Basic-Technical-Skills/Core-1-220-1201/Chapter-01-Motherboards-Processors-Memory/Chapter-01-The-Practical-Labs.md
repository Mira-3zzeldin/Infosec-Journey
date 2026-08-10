### 🛠️ Lab 1: Motherboard & Component Identification with CPU-Z

**Objective:** Master visual and software-based identification of the "big three" (motherboard, CPU, RAM), including form factor, socket, chipset, and cache hierarchy — core troubleshooting-isolation skills.

**Environment/Tools Needed:** A Windows physical PC or Windows VM (VMware Workstation/VirtualBox), internet access, [CPU-Z](https://www.cpuid.com/) freeware.
- Note on Virtual Machines (VMs): While CPU-Z will run inside a Windows VM (VMware/VirtualBox), the hypervisor will mask the physical motherboard chipset, model, and BIOS vendor with generic virtualized strings, and the **SPD tab will be completely empty/disabled**. A native hardware boot is required for full inventory validation.

**Step-by-Step Instructions:**

1. Download and install the latest version of CPU-Z from the official site (www.cpuid.com) on your Windows machine.
2. Launch CPU-Z. On the **CPU** tab, record the following metrics: processor name/number, core speed, supported instruction sets (look for `EM64T` or `AMD64` indicating x64 support), and the core/thread count.
3. Switch to the **Caches** tab. Record the L1, L2, and L3 sizes. Compare them against typical industry scaling baselines (Legacy systems: L2 ~512 KB, L3 8–16 MB; Modern high-performance architectures: L2 1–2 MB per core, L3 32–96 MB+).
4. Switch to the **Mainboard** tab. Record the motherboard manufacturer, model, and chipset designation (e.g., Z790, B650). Note the BIOS vendor, version, and release date listed — critical data points for checking firmware upgrade compatibility.
5. Switch to the **Memory** tab. Record the memory type (DDR4/DDR5) and total size. Pay close attention to the **Channel #** field:
   - For DDR4, record whether it reads *Single* or *Dual*.
   - For modern DDR5, note that a single stick natively operates on two subchannels (will display as **2x32-bit**), while two sticks running in dual-channel topology will display as **4x32-bit**.
6. Switch to the **SPD** tab. Select each memory slot from the dropdown interface. For each populated slot, record the module size, max bandwidth rating, and the actual DRAM manufacturer (e.g., Samsung, SK Hynix, Micron). If a slot dropdown yields blank fields, that slot is physically unpopulated.
7. Cross-reference your captured chipset name against Intel's or AMD's official ark/product databases online to identify the underlying CPU socket infrastructure (e.g., searching "Intel Z790 specifications" to verify its LGA 1700 mating architecture).

**Expected Result:** A completed component inventory sheet showing CPU model/socket/core-thread count, cache sizes at each level, motherboard chipset, and memory type/channel configuration/per-slot capacity — everything needed to diagnose a "will this upgrade physically fit" question without opening the case.

---

### 🛠️ Lab 2: Bus & Interface Speed Auditing with CLI Tools

**Objective:** Practice identifying real PCIe link widths/generations and SATA/NVMe link speeds from the command line — a skill directly tied to diagnosing "why is my new GPU or SSD running slower than advertised."

**Environment/Tools Needed:** 
- A native, bare-metal Linux installation (Ubuntu, Debian, Fedora, or Kali, Avoid Virtual Machines for this lab).
- Terminal access with `sudo` privileges.

**Step-by-Step Instructions:**

1. Open your terminal (`Ctrl + Alt + T`).
2. Run the following command with root privileges to locate your graphics adapter (VGA) and NVMe storage controllers, along with their precise physical link capabilities: `sudo lspci -vv | grep -E "VGA|Non-Volatile|LnkCap:|LnkSta:"
   - Note: If the output is too condensed, you can target your GPU directly by running `sudo lspci -v -v -s $(lspci | grep VGA | cut -d' ' -f1)` to view its standalone matrix.

3. Within the terminal printout, locate and analyze the **LnkCap** (Link Capability) and **LnkSta** (Link Status) lines for your hardware:
   - **LnkCap:** Displays the maximum PCIe generation and lane width that the physical component and slot *safely support*.
   - **LnkSta:** Displays the operational speed and lane width that the device is *actually running at right now* (e.g., `Speed 8GT/s, Width x16`).
   - **Exam Cram Tip:** `2.5GT/s` = Gen 1, `5GT/s` = Gen 2, `8GT/s` = Gen 3, `16GT/s` = Gen 4, `32GT/s` = Gen 5).

4. **Flag any mismatch:** If `LnkSta` reports a lower speed or fewer lanes (e.g., running at `x4` instead of a capability of `x16`), you have uncovered a real-world performance bottleneck. This often indicates a degraded slot, poor seating, or PCIe lane-sharing on the motherboard (such as populating a specific M.2 slot that steals bandwidth from the primary PCIe slot). Note this as a troubleshooting flag.

5. To inspect your storage subsystem links, query your drive hardware using `lshw` or `hdparm`:
   - For NVMe/SATA mapping, run: `sudo lshw -class disk -class storage`
   - For native SATA drives, run the following to audit negotiated link speeds (adjust `/dev/sda` to match your target drive identifier): `sudo hdparm -I /dev/sda | grep -i "speed"`
   - Compare the negotiated speed against the standard SATA limits taught in this chapter (SATA I: 1.5 Gbps, SATA II: 3.0 Gbps, SATA III: 6.0 Gbps).

6. **Calculate theoretical throughput:** Using the PCIe throughput doubling rule from this chapter (where each iteration doubles the bandwidth capability of its predecessor):

| Generation | Per-Lane Throughput (Per Direction) |
| :--- | :--- |
| **Gen 1** | 250 MB/s |
| **Gen 2** | 500 MB/s |
| **Gen 3** | ~1 GB/s (985 MB/s) |
| **Gen 4** | ~2 GB/s (1.97 GB/s) |
| **Gen 5** | ~4 GB/s (3.94 GB/s) |

   Take the **Lane Width** (e.g., `x4`, `x16`) and the **Generation** you captured from your active `LnkSta` in Step 3. Manually multiply the per-lane throughput by the active width to determine your device's maximum theoretical unidirectional throughput. Cross-verify your mathematical product using an online PCIe bandwidth calculator.

**Expected Result:** A clean terminal log explicitly confirming your GPU's or NVMe drive's active vs. maximum PCIe lane topology, coupled with an accurate manual bandwidth calculation matching the scenario-based throughput questions commonly featured on the CompTIA A+ certification exam.


---

### 🛠️ Lab 3: UEFI Firmware Exploration & Secure Boot / TPM Verification

**Objective:** Build muscle memory for navigating a UEFI setup utility safely, and verify the presence and status of Secure Boot and TPM — a frequently tested real-world security workflow.

**Environment/Tools Needed:** 
- A physical Windows 10/11 PC (UEFI features generally do not pass through cleanly to VMs).
- No additional software required (Windows built-in tools only).
- **CRITICAL SECURITY WARNING:** If your system drive is encrypted with BitLocker, ensure you have your **BitLocker Recovery Key** backed up before proceeding. Firmware status checks can sometimes trigger BitLocker recovery mode.

**Step-by-Step Instructions:**

1. In the Windows search bar, type **Advanced startup** and press Enter to open the System Recovery settings page.
2. Next to Advanced Startup, click **Restart Now**. Confirm the reboot.
3. On the **Choose an option** screen, click **Troubleshoot**, then **Advanced options**, then **UEFI Firmware Settings**, then confirm the reboot into UEFI.
4. Inside the UEFI setup utility, locate the **Boot** tab and record the current boot device order **without changing it**. 
   *(Take a smartphone photo of this screen if needed for your lab records).*
5. Locate the security or advanced tab (often labeled *Security*, *Trusted Computing*, *Advanced*, or *Peripherals*). Look for **TPM** (Note: Intel platforms may label this as **PTT** or *Platform Trust Technology*, while AMD platforms may label it as **fTPM**). Record whether it is enabled.
6. Look for **Secure Boot** within the security or boot section and record whether it is enabled.
7. Exit the UEFI utility **without saving changes** (Select *Exit Discarding Changes* or *Save & Exit* ONLY if you made zero modifications) to guarantee no accidental setting changes persist. Allow the PC to boot normally into Windows.
8. Back in Windows, type `tpm.msc` directly into the Windows search box or the Run dialog (`Win + R`) and press Enter to open the TPM Management console. Confirm that the TPM's manufacturer, specification version (e.g., 20), and status match what you saw in UEFI.
9. Type **System Information** in the Windows search bar (or press `Win + R`, type `msinfo32`, and hit Enter). On the System Summary page, check the following fields to cross-verify against your UEFI findings:
   - **BIOS Mode:** (Should read "UEFI")
   - **Secure Boot State:** (Should read "On" or "Off" matching step 6)

**Expected Result:** A short written comparison table showing TPM status and Secure Boot status as reported by (a) the UEFI setup screen itself, and (b) two independent Windows tools (`tpm.msc` and `msinfo32`) — all three should agree, demonstrating the "sealing" relationship between firmware and OS-level security reporting described in this chapter.