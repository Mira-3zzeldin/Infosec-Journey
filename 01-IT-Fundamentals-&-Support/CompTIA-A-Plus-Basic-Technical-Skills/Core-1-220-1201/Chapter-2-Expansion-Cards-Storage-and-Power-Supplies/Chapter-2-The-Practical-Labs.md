### 🛠️ Lab 1: Device Manager Driver Forensics & Hardware ID Deep-Dive

**Objective:** Master the real diagnostic workflow behind "a device isn't working" tickets — reading hardware IDs, interpreting error-badge codes, and safely updating/rolling back drivers for expansion cards (video, sound, NIC, or capture) without breaking a working system.

**Environment/Tools Needed:** A Windows 10/11 PC or VM (a VM is fine here — you're inspecting driver metadata, not physical bus speeds), Device Manager (built-in), internet access for driver downloads.

**Step-by-Step Instructions:**

1. Open **Device Manager** (type `device manager` into the Windows search box and press Enter, or run `devmgmt.msc` via `Win + R`).
2. Expand **Display adapters**, **Sound, video and game controllers**, and **Network adapters**. Screenshot or note every device listed, including any with a yellow exclamation point (driver problem) or red X (disabled device).
3. Right-click your primary video card (or any adapter card present) → **Properties** → **Driver** tab. Record the following four fields exactly as shown: **Driver Provider**, **Driver Date**, **Driver Version**, and **Digital Signer**.
4. Click **Driver Details** on the same tab. Note the full file path of the primary driver file. Depending on your driver architecture (such as Intel DCH drivers), Windows may point directly to the active kernel-mode path (e.g., `C:\Windows\System32\DRIVERS\...`), or it may point to the staging area inside the secure driver cache (e.g., `C:\Windows\System32\DriverStore\FileRepository\...`). This secure `DriverStore` location is where Windows natively stores verified driver packages separate from the active system directories to protect against system corruption.
5. Switch to the **Details** tab of the device Properties window. From the dropdown, select **Hardware Ids**. Record the full VEN_ (vendor) and DEV_ (device) hex codes shown — these uniquely fingerprint the exact silicon on the card, independent of whatever friendly name Windows displays.
6. Take the VEN_/DEV_ codes from Step 5 and search them online (e.g., "PCI VEN_10DE DEV_2504 lookup") against a public PCI ID database. Confirm the result matches the chipset you expected — this is exactly how a technician identifies an unlabeled or unknown card pulled from a junk-parts bin.
7. Back in the **Driver** tab, click **Update Driver** → **Search automatically for drivers**. Let Windows check for an update. If one installs, immediately reopen the **Driver** tab and confirm the **Driver Date**/**Version** changed from what you recorded in Step 3.
8. **Practice the safety net:** With the Driver tab open, note whether **Roll Back Driver** is grayed out or clickable. It is only enabled if a previous driver version exists in the rollback cache — explain in your lab notes why this button would be grayed out on a freshly imaged machine.
9. **Disable the Device & Observe Effects (Safety Alternative):** Do not disable your video card, as your screen may go entirely black. Instead, expand **Sound, video and game controllers**, right-click your audio device (e.g., _Realtek High Definition Audio_), and select **Disable device**. Click **Yes** on the warning prompt, then observe two key effects:
	- **Visual Indicator:** A small black down arrow (⬇️) will appear on the device icon, which is the universal Windows symbol indicating that the hardware was intentionally shut down by the administrator.
	- **Real-World Impact:** A red "x" (❌) will appear over the volume icon in your taskbar, and all system sound will instantly cut off because Windows blocked the data path to the audio chip.
_Immediately afterward, right-click the audio device again and select **Enable device** to safely restore your sound._

**Expected Result:** A completed device inventory table (Device Name → Driver Provider/Date/Version → Hardware ID → Confirmed Chipset) demonstrating that you can identify, verify, update, and safely roll back a driver — the exact skill set tested in "device not recognized" and "driver causing instability" A+ scenario questions.

---

### 🛠️ Lab 2: Storage Interface & Throughput Benchmarking Lab

**Objective:** Practice identifying real SATA/NVMe link speeds from the command line and manually calculating theoretical PCIe throughput — the skill directly tied to "why is my SSD not running at advertised speed" troubleshooting.

**Environment/Tools Needed:** A native, bare-metal Linux installation (Ubuntu, Debian, Fedora, or Kali — avoid VMs, since a hypervisor will mask real physical link negotiation), terminal access with `sudo` privileges. (Windows users can substitute `CrystalDiskInfo` for Steps 3–4, though the negotiated-link data will be less granular.)

**Step-by-Step Instructions:**

1. Open a terminal (`Ctrl + Alt + T`).
2. Identify your storage controllers and their PCIe link status:
   `sudo lspci -vv | grep -E "Non-Volatile|SATA|LnkCap:|LnkSta:"`
3. For any NVMe controller found, note the **LnkCap** (maximum supported speed/width) versus **LnkSta** (actual negotiated speed/width) lines. Recall the generation cram tags: `2.5GT/s` = Gen 1, `5GT/s` = Gen 2, `8GT/s` = Gen 3, `16GT/s` = Gen 4, `32GT/s` = Gen 5, `64GT/s` = Gen 6.
4. **Flag any mismatch.** If LnkSta reports fewer lanes or a lower generation than LnkCap (e.g., negotiated at `x2` instead of a capability of `x4`), that's a real bottleneck — often caused by a shared/lane-stealing M.2 slot or a degraded connection. Note this as a troubleshooting flag, exactly as you would for a customer reporting "my new NVMe drive feels slow."
5. Query your SATA drive's negotiated link speed:
   `sudo hdparm -I /dev/sda | grep -i "speed"`
   (adjust `/dev/sda` to your actual drive identifier from `lsblk`)
   Compare the result against the SATA ceiling table: SATA-150 (`1.5 Gbps`/`150 MBps`), SATA-300 (`3.0 Gbps`/`300 MBps`), SATA-600 (`6.0 Gbps`/`600 MBps`).
6. **Manual PCIe bandwidth calculation:** Using the active **LnkSta** width and generation captured in Step 3, and the per-lane throughput table below, manually calculate your NVMe drive's maximum theoretical one-directional throughput (lane throughput × active width):

| Generation | Per-Lane Throughput (one direction) |
| ---------- | ----------------------------------- |
| Gen 1      | 250 MBps                            |
| Gen 2      | 500 MBps                            |
| Gen 3      | ~1 GBps                             |
| Gen 4      | ~2 GBps                             |
| Gen 5      | ~4 GBps                             |

   Example: a drive negotiated at Gen 3 x4 = `1 GBps × 4 lanes` = **4 GBps** theoretical one-directional throughput.
7. Run a real-world benchmark to compare theory against reality:
   `sudo hdparm -Tt /dev/nvme0n1` (adjust device name as needed) — or install and run a simple sequential read test with `fio` if available.
8. Write a one-paragraph comparison: how close did the real benchmark come to your Step 6 theoretical maximum, and if there's a large gap, what factors (drive controller quality, thermal throttling, filesystem overhead, queue depth) might explain it?

**Expected Result:** A terminal log and short written report showing your drive's actual vs. maximum PCIe lane topology, a correct manual bandwidth calculation, and a real benchmark result — mirroring the scenario-based throughput math questions common on the A+ exam.

---

### 🛠️ Lab 3: RAID Array Simulation & Failure-Recovery Drill

**Objective:** Build, stress, and deliberately break a software RAID array to build real intuition for the fault-tolerance/performance trade-offs between RAID 0, 1, and 5 — instead of just memorizing the comparison table.

**Environment/Tools Needed:** A Linux VM (VirtualBox or VMware) with **four virtual disks attached** (each can be a small 2–4 GB virtual disk — no need for real hardware), `mdadm` package (`sudo apt install mdadm` on Debian/Ubuntu-based distros). **Do this in a disposable VM only — never practice failure injection on a system with real data.**

**Step-by-Step Instructions:**

1. Confirm your four virtual disks are visible: `lsblk` (they'll likely appear as `/dev/sdb`, `/dev/sdc`, `/dev/sdd`, `/dev/sde` — adjust all commands below to match your actual device names).
2. Build a **RAID 0** array across two disks to observe striping-only behavior:
   `sudo mdadm --create /dev/md0 --level=0 --raid-devices=2 /dev/sdb /dev/sdc`
   Confirm it built successfully: `cat /proc/mdstat`
3. Format, Mount, and Speed Test: Initialize the new array with an ext4 filesystem, mount it, and run a practical benchmark using a dynamically generated test file to record the sequential write throughput: `sudo mkfs.ext4 /dev/md0` - `sudo mkdir -p /mnt/raid0test` - `sudo mount /dev/md0 /mnt/raid0test` - `sudo dd if=/dev/zero of=/mnt/raid0test/testfile bs=1M count=500 status=progress`
4. **Simulate a drive failure on the RAID 0 array:**
   `sudo mdadm --manage /dev/md0 --fail /dev/sdb`
   Attempt to read a file from the array afterward. Confirm and document that the entire array becomes unusable — this is RAID 0's core lesson: striping speed with **zero** fault tolerance.
5. Tear down the RAID 0 test: `sudo mdadm --stop /dev/md0`

6. Build a **RAID 1** mirror across the same two disks:
   `sudo mdadm --create /dev/md1 --level=1 --raid-devices=2 /dev/sdb /dev/sdc`
   Format, mount, and speed test initialize, write again and compare the speed against Step 3 — RAID 1 should show **no** write speed improvement over a single disk, unlike RAID 0.
7. **Simulate a drive failure on the RAID 1 mirror:**
   `sudo mdadm --manage /dev/md1 --fail /dev/sdb`
   Confirm via `cat /proc/mdstat` that the array is now running in a **degraded** state but the test file is still fully readable — proving the fault-tolerance trade-off in real time.
8. **Simulate recovery:** remove the failed disk and add a replacement:
   `sudo mdadm --manage /dev/md1 --remove /dev/sdb`
   `sudo mdadm --manage /dev/md1 --add /dev/sdb`
   Watch the rebuild progress live: `watch cat /proc/mdstat`

9. Tear down RAID 1, then build a **RAID 5** array across all three remaining disks:
   `sudo mdadm --create /dev/md2 --level=5 --raid-devices=3 /dev/sdb /dev/sdc /dev/sdd`
10. Confirm the usable capacity reported (`all drives minus one`, matching the parity-loss rule from the study guide) via `sudo mdadm --detail /dev/md2`.
11. Fail one disk in the RAID 5 array and confirm the array survives in degraded mode, exactly like RAID 1 did, but now with only one drive's worth of capacity sacrificed instead of half.

**Expected Result:** A short written comparison table (RAID 0 vs. RAID 1 vs. RAID 5) populated with your **own measured** write speeds, actual usable capacities, and failure-survival outcomes — turning the textbook's RAID comparison table from memorized facts into observed, first-hand results.
