### 🛠️ Lab 1: Commissioning a New Press — Installing & Configuring a Local Printer

**Objective:** Practice the full seven-step printer installation and configuration procedure this chapter covers, using Windows 11's native printer tools — from picking a connection method through verifying output — so the sequence (and where each setting actually lives) is second nature before the exam.

**Environment/Tools Needed:** A Windows 11 PC (physical or VM), and either a real USB/wireless printer or the Microsoft-provided **Microsoft Print to PDF** virtual printer (already installed on every Windows 11 system, and perfectly usable for every step below except the physical connectivity step).

**Step-by-Step Instructions:**

1. Press `Win + I` to open Settings, then navigate to **Bluetooth & devices ➤ Printers & scanners**. Click **Add device**. If you have a real local printer connected via USB, let Windows attempt automatic detection and driver installation; note how long detection takes and whether a driver installs automatically or prompts you for a source.
2. If no physical printer is available (or detection fails), click **"The printer that I want isn't listed"** to launch the **Add Printer Wizard** manually. Choose **Add a local printer or network printer with manual settings**, select **Use an existing port** (`FILE:` or an available `LPT`/`USB` port), and when prompted for a manufacturer/model, select any manufacturer and any printer model from the built-in driver list — you're practicing the wizard flow, not actually printing.
3. Once the printer is installed, return to **Printers & scanners**, click your newly installed printer, and open **Printer properties**. Work through the **General**, **Sharing**, **Ports**, **Advanced**, and **Security** tabs one at a time, and for each tab write down in your lab notes: what this chapter says that tab controls, and what you actually see available on your system.
4. On the **Ports** tab, locate the **Enable printer pooling** checkbox. Without enabling it, explain in your own words (per this chapter's Guild Mailroom section) why printer pooling only makes practical sense when every pooled printer is in the same physical location.
5. Back in **Printers & scanners**, click your printer once more and open **Printing Preferences** (a separate dialog from Printer Properties). Locate and record where your specific driver places the **duplex/double-sided**, **orientation**, **quality**, and **paper tray/source** settings — note that these often live under different tab names than this chapter's example printer, which is expected and part of the "poking around" this chapter warns you about.
6. Click **Print a test page** (available either from Printer Properties' General tab, or by right-clicking the printer and selecting it directly). Confirm the result — either a physical printout or, for Microsoft Print to PDF, a save-file dialog confirming the render succeeded.
7. Open **Notepad**, type a line of text, and print it using your newly installed printer to confirm application-level compatibility (Step 6 of this chapter's seven-step procedure), separately from the OS-level test page in Step 6 above.

**Expected Result:** A fully installed and configured printer (real or virtual) in Windows 11's Printers & Scanners list, a completed tab-by-tab notes sheet for Printer Properties, a documented location for each of the four key Printing Preferences settings, and two successful test outputs — one from Windows' own test page function and one printed from an actual application.

---

### 🛠️ Lab 2: Running the Guild's Mailroom — Print Queue Management & TCP/IP Printer Setup

**Objective:** Get comfortable managing live print jobs and adding a network printer by IP address/hostname using native Windows tools — the PowerShell PrintManagement module and the Add Printer Wizard's manual TCP/IP path — mirroring real network-printer troubleshooting and setup work.

**Environment/Tools Needed:** A Windows 11 PC, PowerShell running as Administrator, at least one installed printer (the one from Lab 1 works fine), and — optionally, for Steps 5–6 — a second device on the same network with a discoverable printer or print-capable service for a genuine TCP/IP add attempt.

**Step-by-Step Instructions:**

1. Open **Start**, type `powershell`, right-click **Windows PowerShell**, and select **Run as administrator**.
2. Run `Get-Printer` to list every printer currently installed on the system, and record the **Name**, **DriverName**, and **PortName** columns for your Lab 1 printer.
3. Send a small print job to that printer (print any short document, or a Notepad test line, from Step 7 of Lab 1 again), then immediately run `Get-PrintJob -PrinterName "<your printer name>"` to view the job while it's still in the queue. Record the **JobStatus**, **SubmittedTime**, and **TotalPages** fields.
4. Practice job control directly from PowerShell: run `Suspend-PrintJob -PrinterName "<your printer name>" -ID <job ID>` to pause the job, confirm the status change with `Get-PrintJob` again, then either `Resume-PrintJob` or `Remove-PrintJob` (using the same `-PrinterName` and `-ID` parameters) to finish. This is the command-line equivalent of the Print Queue GUI's pause/restart/cancel options covered in this chapter's Guild Intake Office section.
5. Run `Get-PrinterPort` to list every configured port on the system, and identify which port type (`9100`, `LPR`, `USB`, etc.) your printer is using — cross-reference against this chapter's RAW (port 9100) vs. LPR (ports 721–731/515) distinction.
6. Launch the **Add Printer Wizard** (Settings ➤ Printers & scanners ➤ Add device ➤ "The printer that I want isn't listed"), select **Add a printer using a TCP/IP address or hostname**, and set **Device type** to **TCP/IP Device**. Enter any IP address on your local subnet (your own router's gateway address works fine for this exercise, e.g., `192.168.1.1`) purely to observe the wizard's detection behavior — you are not expected to complete a real installation unless a genuine network printer answers on that address. Record what message or behavior the wizard shows when it can't find a printer service at that address, and cancel out once you've observed it.
7. Back in PowerShell, run `Get-Printer | Select Name, Shared, Published` to check which of your printers (if any) are currently shared and/or published to the network — the command-line view of the Sharing tab you inspected in Lab 1.

**Expected Result:** A working knowledge of `Get-Printer`, `Get-PrintJob`, `Suspend-PrintJob`, `Resume-PrintJob`, and `Remove-PrintJob`, a completed notes sheet identifying your printer's port type, and firsthand observation of how the TCP/IP Add Printer flow behaves when probing an address with no listening print service — the exact troubleshooting step you'd take first against a real "printer not found on network" complaint.

---

### 🛠️ Lab 3: Manning the Gatehouse & Scribe's Post — Print Security & Audit Trail Inspection

**Objective:** Practice locating and reasoning about the four Exam Objective 3.7 security features (user authentication, badging, secured prints, audit logs) on real Windows tooling, and simulate audit-log review using Windows Event Viewer and the print spooler's own logging — since most home/lab printers won't have enterprise badge-reader hardware to test against directly.

**Environment/Tools Needed:** A Windows 11 PC with at least one installed printer (from Lab 1), Event Viewer, and Administrator access.

**Step-by-Step Instructions:**

1. Open your printer's **Printer properties ➤ Security** tab (the same tab you catalogued in Lab 1). Record which user/group entries are listed and which permissions (Print, Manage this printer, Manage documents) are granted to each — this is the closest native-Windows equivalent to the "who's allowed to print" access control this chapter describes under printer security.
2. Open **Event Viewer** (search "Event Viewer" from Start). Navigate to **Applications and Services Logs ➤ Microsoft ➤ Windows ➤ PrintService ➤ Operational**. If this log is disabled, right-click it and select **Enable Log** — this is the built-in Windows analog to the "audit log integrated into the host OS's standard logging utilities" this chapter describes for some HP printers.
3. Print a test page or short document (as in Lab 1, Step 7) to generate fresh log activity, then refresh the PrintService Operational log. Locate the entry recording your print job and record the **Event ID**, **user account** shown, and **document name** — this is your audit trail: proof of who printed what, functioning the same way this chapter's audit-log feature does on enterprise MFDs.
4. In the same Event Viewer log, use **Filter Current Log** on the right-hand pane to filter for only printing-related events from the last 24 hours, and count how many print events your session generated. Note in your lab notes how this filtered view is functionally identical to what an administrator would pull when investigating a specific user's print history.
5. Revisit your **Printer Properties ➤ Advanced** tab. Locate the **Keep printed documents** checkbox. Leave it unchecked, and write one to two sentences (in your own words, referencing this chapter's hard-drive-caching security note) explaining specifically why this option should never be enabled on a printer sitting in a public or shared space.
6. As a written exercise (no hardware required), map each of this chapter's four printer security features — **user authentication**, **badging**, **secured prints**, and **audit logs** — to the closest Windows/PowerShell equivalent you used in this lab (Security tab permissions, none/N/A, none/N/A, and Event Viewer's PrintService log, respectively), and for the two features with no native Windows equivalent, briefly note what kind of third-party or enterprise MFD hardware/software would be needed to add that capability.

**Expected Result:** A completed Security-tab permissions record, a captured and filtered PrintService audit-log entry tied to a real print job you generated, and a short written mapping exercise connecting all four Exam Objective 3.7 security features to concrete tools — real or conceptual — reinforcing exactly which of these features come "free" with Windows and which require dedicated MFD/enterprise hardware.
