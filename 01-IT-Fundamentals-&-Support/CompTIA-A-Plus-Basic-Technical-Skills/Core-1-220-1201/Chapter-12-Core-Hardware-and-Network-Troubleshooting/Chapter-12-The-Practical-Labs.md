### 🛠️ Lab 1: Reading the Newborn's Chart — Safe BIOS/UEFI and Visual Hardware Inspection

**Objective:** Perform a non-destructive physical and firmware-level inspection of a desktop PC — checking BIOS/UEFI date/time accuracy, boot priority, and a visual scan for capacitor swelling or dust buildup — reinforcing this chapter's coverage of CMOS battery symptoms, boot sequence troubleshooting, and general hardware symptom identification, without requiring any component removal.

**Environment/Tools Needed:** A desktop PC you're permitted to power down and open (a laptop can be substituted for the firmware steps only, skipping the physical inspection), a Phillips screwdriver if the case requires one to open, and a flashlight. No components will be removed or disconnected in this lab.

**Step-by-Step Instructions:**

1. With the system currently running, note the actual current date and time from your phone or another reliable source.
2. Restart the system and watch for the on-screen prompt telling you which key opens BIOS/UEFI Setup (commonly F2, F10, or Del — check your manufacturer's documentation if it flashes by too quickly to read).
3. Enter BIOS/UEFI Setup. Locate the date/time display (usually on a Main or System Information screen) and compare it to the actual time you noted in step 1. Record whether it matches or has drifted — a significant drift is a classic symptom of a dying CMOS battery, even though replacing the battery itself is out of scope for this lab.
4. Locate the Boot Priority (or Boot Order/Boot Sequence) menu. Record the current order of boot devices without changing it.
5. If your system supports it, locate the Virtualization Technology setting (Intel VT-x/VT-c or AMD-V/SVM Mode) referenced in earlier chapters, and record whether it's currently enabled or disabled — do not change it unless you specifically intend to.
6. Exit BIOS/UEFI Setup without saving any changes (usually Esc, then a "Discard changes" confirmation) so the system boots normally afterward.
7. Once the system is back at the desktop, shut it down completely and unplug the power cable from the wall or power supply.
8. Open the case following your case manufacturer's access panel instructions (typically one or two thumbscrews or Phillips screws on the back edge).
9. Using the flashlight, visually inspect the motherboard's capacitors — the small cylindrical components clustered near the CPU socket and expansion slots — for any swelling, bulging tops, or brownish-red residue, as described in this chapter. Do not touch any residue if present.
10. Continue the visual inspection by checking for dust buildup on the CPU heat sink fins, case fans, and power supply intake, and confirm that no expansion slot is missing its blank/slot cover.
11. Close the case, reconnect the power cable, and power the system back on to confirm it boots normally.
12. Write two to three sentences explaining, based on this chapter, what your next troubleshooting step would be if you had found a distended capacitor during step 9, and why that step is the recommended one over attempting a repair yourself.

**Expected Result:** A recorded comparison of BIOS/UEFI time against real-world time, a documented boot priority order, a documented virtualization setting, a completed visual inspection with no components removed, a system that powers back on normally, and a short written explanation connecting a found capacitor problem to the correct next action from this chapter.

---

### 🛠️ Lab 2: Records Room Triage — Diagnosing Storage and Performance Symptoms

**Objective:** Use Windows' built-in storage and performance utilities to investigate a sluggish or space-constrained system, directly reinforcing this chapter's guidance on Task Manager thresholds, free-space rules of thumb, and drive optimization tools.

**Environment/Tools Needed:** A Windows 11 PC (any drive type), no additional software required — this lab uses only Task Manager, the Storage app, and the built-in Optimize Drives utility.

**Step-by-Step Instructions:**

1. Open Task Manager using any of the three methods from this chapter: press Ctrl+Alt+Delete and choose Task Manager, right-click the Taskbar and select Task Manager, or press Ctrl+Shift+Esc.
2. Click the Processes tab (or the "More details" arrow first, if Task Manager opened in compact view). Click the column header for CPU to sort processes by CPU usage, and record the top three processes and their percentages.
3. Click the column header for Memory and record the top three memory-consuming processes. Note whether any single process is using a disproportionate share.
4. Click the column header for Disk and note whether any process shows sustained, heavy disk activity.
5. Compare your CPU, Memory, and Disk totals (shown at the top of each respective column, or in the Performance tab) against the "over 80 percent sustained usage" threshold discussed in this chapter. Note whether your system is currently near that threshold on any resource.
6. Close Task Manager. Open the Storage app: Start > Settings > System > Storage.
7. Note the total capacity and used space shown for your primary drive. Calculate what percentage is free, and compare it against the "at least 10 percent free" rule of thumb from this chapter.
8. In the Storage Management section, click Cleanup Recommendations and review (without necessarily deleting) what categories of reclaimable space it identifies — temporary files, large or unused files, cloud-synced files, and unused apps.
9. Navigate back and click Advanced Storage Settings, then click Drive Optimization to open the Optimize Drives utility.
10. Highlight your primary drive and click Analyze. Read the "Current status" column once analysis completes — for an SSD it should indicate optimization isn't typically needed as often as for an HDD; for a mechanical HDD, note the reported fragmentation percentage.
11. Write two to three sentences explaining, based on this chapter, why running Disk Cleanup or Optimize Drives would (or wouldn't) be an appropriate next step if your drive's free space was already comfortably above 10 percent but the system still felt sluggish.

**Expected Result:** A recorded snapshot of Task Manager's CPU/Memory/Disk usage by process, a calculated free-space percentage for the primary drive compared against the 10-percent guideline, a reviewed set of Cleanup Recommendations, a completed drive analysis in Optimize Drives, and a short written explanation distinguishing a disk-space-driven slowdown from a different root cause.

---

### 🛠️ Lab 3: The Full Workup — Command-Line Network Diagnostics

**Objective:** Run through the complete chain of network troubleshooting commands (`ipconfig`, `ping`, `hostname`, `nslookup`, `netstat`, and `tracert`/`pathping`) in the correct diagnostic order, reinforcing this chapter's structured approach to isolating a connectivity problem from the client outward.

**Environment/Tools Needed:** Any Windows 10/11 PC connected to a working network with internet access, and access to the built-in Command Prompt (no administrator rights required for most steps). macOS/Linux users can substitute `ip`, `ping`, `hostname`, `nslookup`, `netstat`, and `traceroute`/`mtr` at the equivalent steps.

**Step-by-Step Instructions:**

1. Open a command prompt (type `cmd` into the Windows search box and press Enter).
2. Type `hostname` and press Enter. Record the name it returns — this is your machine's identity on the network.
3. Type `ipconfig /all` and press Enter. Scroll up to find your active adapter's IPv4 address, subnet mask, default gateway, and DHCP lease information. Confirm the address is NOT in the `169.254.x.x` range (if it is, stop here — that's an APIPA address and means your machine isn't reaching a DHCP server).
4. Test the loopback first: type `ping 127.0.0.1` and press Enter. You should see four successful replies — this confirms your TCP/IP stack itself is functioning before you test anything external.
5. Ping your default gateway (the router) using the address you recorded in step 3: type `ping <gateway address>` and press Enter. Confirm you get replies with a low round-trip time.
6. Ping a known external IP address directly (Google's public DNS server works well): type `ping 8.8.8.8` and press Enter. If this succeeds but ping-by-hostname fails in the next step, you're looking at a DNS problem, not a connectivity problem.
7. Ping the same destination by hostname: type `ping google.com` and press Enter. Compare the resolved IP address shown in the output to the one you pinged directly in step 6.
8. Run a DNS-specific check: type `nslookup google.com` and press Enter. Record the IP address(es) returned and confirm they match what you saw in step 7.
9. Trace the full path to the destination: type `tracert google.com` and press Enter. Watch for any hop that shows a request timeout (`*`) or a dramatic jump in response time — either is worth noting as a possible trouble spot.
10. If your system supports it, run `pathping google.com` and let it complete (this can take a minute or two). Compare the packet-loss percentage shown for each hop against the "anything over 5 percent is high" guideline from this chapter.
11. Finally, type `netstat -n` and press Enter. Record how many established connections are currently open on your machine.
12. Write two to three sentences explaining, based on this chapter, what the difference in results between step 6 (ping by IP) and step 7 (ping by hostname) would tell you if step 7 had failed while step 6 succeeded.

**Expected Result:** A complete, ordered diagnostic trail — hostname, full IP configuration, a successful loopback test, a successful gateway ping, a successful external IP ping, a successful hostname ping with matching DNS resolution, a full trace route with hop-by-hop timing, a pathping packet-loss breakdown, and a snapshot of active connections — plus a short written explanation connecting a hostname-vs-IP ping mismatch to a DNS-specific failure.