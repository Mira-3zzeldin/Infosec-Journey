### 🛠️ Lab 1: Reactor & Chart Room Recon — Hardware Inventory Without Opening a Hatch

**Objective:** Practice the "gather documentation before you touch a screw" discipline this chapter emphasizes, by using native Windows tools to positively identify your own laptop's processor mounting style, installed memory type/generation, storage interface (SATA vs. M.2/NVMe), and wireless card — exactly the information you'd need in hand before ever researching a compatible replacement part or locating a service manual.

**Environment/Tools Needed:** A Windows physical PC or Windows VM (VMware Workstation/VirtualBox — note that a VM will report virtualized/generic hardware for some fields, so a physical laptop gives more realistic results for Steps 3–5), internet access, [CPU-Z](https://www.cpuid.com/) freeware.

**Step-by-Step Instructions:**

1. Press `Win + R`, type `msinfo32`, and press Enter to open **System Information**. Record the **BaseBoard Manufacturer/Product** field (your motherboard's proprietary model identifier — exactly what you'd search a manufacturer's support site with, per this chapter's documentation-first principle) and the **Processor** field.
2. Open **Device Manager** (`Win + X` ➤ Device Manager). Expand **Memory technology devices** and **Disk drives** to see how Windows enumerates your onboard storage; right-click your primary drive, select **Properties** ➤ the **Details** tab, and change the property dropdown to **Bus type reported** to confirm whether your drive is connecting as SATA or NVMe (a strong indicator of 2.5"/SATA vs. M.2 storage as discussed in the Torpedo Room section).
3. Open **CPU-Z**, go to the **Memory** tab. Record the memory **Type** (DDR4, DDR5, etc.), **Channel** configuration, and total size. Switch to the **SPD** tab and check each populated memory slot — record the **Module Size**, **Max Bandwidth**, and, if listed, the **Part Number**. Cross-reference the part number against the manufacturer's site (or `www.crucial.com`) to identify the exact SODIMM generation and pin count installed, using this chapter's SODIMM table as your reference.
4. Still in CPU-Z, check the **Mainboard** tab for your BIOS/UEFI version — this is the exact information Exercise "Flashing the System BIOS" in this chapter says you'd need before downloading a matching firmware update from your manufacturer's support site.
5. In Device Manager, expand **Network adapters** and record your wireless card's exact model name. Search that model name online to determine whether it's a Mini PCIe or M.2 card, and cross-reference its supported PCIe lanes/speed against this chapter's Auxiliary Bays table.
6. Using the manufacturer/model information gathered above, visit that manufacturer's support site from **Table 4.1** in the study guide (Apple, Asus, Dell, HP, Lenovo, or Sony) and locate — but do not download unless you plan to actually service the device — the official service manual for your exact model, confirming it lists the same components you just identified in software.

**Expected Result:** A completed hardware dossier (motherboard identity, CPU, RAM type/generation/slot layout, storage bus type, wireless card model) plus a confirmed link to that exact model's official service manual — the complete "documentation gathered before touching a single screw" packet this chapter insists on before any real laptop teardown begins.

---

### 🛠️ Lab 2: Battery Compartment Diagnostics with `powercfg`

**Objective:** Learn to generate and interpret a real battery health report — reading design capacity vs. current full-charge capacity, cycle behavior, and charge history — the exact kind of diagnostic data you'd use to decide whether a "won't hold a charge" complaint is a battery problem or something else, without ever opening the case.

**Environment/Tools Needed:** A Windows physical laptop (a desktop with no battery will generate an empty/error report, so this lab requires an actual portable device), Command Prompt or PowerShell running as Administrator.

**Step-by-Step Instructions:**

1. Open the **Start Menu**, type `cmd`, right-click **Command Prompt**, and select **Run as administrator**.
2. Generate a battery report by running: `powercfg /batteryreport /output "C:\Users\%USERNAME%\Desktop\battery-report.html"`
3. Navigate to your Desktop and open `battery-report.html` in a web browser.
4. Locate the **Installed batteries** section near the top. Record the battery's **Design Capacity** (the capacity it shipped with) and its current **Full Charge Capacity**. Calculate the percentage of original capacity remaining: `(Full Charge Capacity ÷ Design Capacity) × 100`. A laptop battery that's dropped meaningfully below 80% of design capacity is a strong candidate for the digital/chemical memory-loss behavior and calibration discussion covered in this chapter's Battery Compartment section.
5. Scroll to the **Battery usage** and **Usage history** graphs. Note any sudden vertical drops in the runtime estimate — a sharp cliff rather than a smooth decline is the signature of the digital memory effect described in this chapter (the gauge itself losing calibration, not the chemistry actually failing).
6. Scroll to **Battery capacity history**. Record how Full Charge Capacity has trended over the report's recorded history. A steady downward trend across many recorded days points to genuine chemical wear; a battery that appears to have never been recalibrated (no visible full-discharge cycles in a long time) is a candidate for the once-a-month calibration discharge this chapter recommends.
7. Run `powercfg /energy /output "C:\Users\%USERNAME%\Desktop\energy-report.html"` and let it collect data for 60 seconds. Open the resulting report and review any listed **Battery** or **USB Selective Suspend** errors/warnings, which flag devices or settings preventing the system from power-saving effectively.

**Expected Result:** A completed two-report diagnostic packet (battery health report + energy efficiency report) that lets you state, with actual numbers instead of guesswork, whether a laptop's battery complaint is normal age-related chemical wear, a gauge-calibration issue fixable with a full discharge cycle, or a power-configuration problem unrelated to the battery hardware itself.

---

### 🛠️ Lab 3: Signal Flags & Sub Pen Workshop — Connection Method & Docking Inventory

**Objective:** Build fluency identifying and testing every connection method covered in this chapter (USB variants, Bluetooth, NFC/near-field payment, tethering/hotspot, and USB-C docking/DisplayPort Alt Mode) on real hardware you already own, mirroring the kind of accessory-compatibility troubleshooting the A+ exam tests.

**Environment/Tools Needed:** A laptop and a smartphone (any modern Android or iOS device works), a USB-C cable, a Bluetooth accessory if available (headset, mouse, or keyboard), and — optionally — a USB-C dock or hub.

**Step-by-Step Instructions:**

1. On your laptop, open **Settings ➤ Bluetooth & devices** (Windows) and put a Bluetooth accessory into pairing mode. Pair it, then note the connection in Device Manager under **Bluetooth**. Time roughly how long pairing takes, and check your phone's battery percentage before and after 15 minutes of active Bluetooth use to observe the battery-drain tradeoff this chapter describes.
2. On your smartphone, open its wireless hotspot settings (usually **Settings ➤ Network & Internet ➤ Hotspot & Tethering** on Android, or **Settings ➤ Personal Hotspot** on iOS) and enable the hotspot. From your laptop, connect to that hotspot over Wi-Fi and run a quick speed test, comparing it against your normal home/office Wi-Fi speed to observe the "better than nothing, but slower" cellular-tethering tradeoff described in this chapter.
3. Repeat step 2, but this time connect your phone to the laptop via USB cable and enable **USB tethering** specifically (rather than the wireless hotspot) if your phone supports it. Note in your worksheet which of the two methods historically earned the name "tethering" per this chapter's distinction between tethering and hotspot.
4. If your phone supports mobile payments (Apple Pay, Google Wallet, etc.) and you have access to an NFC reader (a contactless payment terminal, transit card reader, or a second NFC-capable phone with an NFC-reading app), test tapping your phone against the reader from roughly 10cm away, then again from about 30cm away. Confirm that the connection only succeeds at short range, consistent with NFC's roughly 4-inch effective range described in this chapter.
5. Plug a USB-C cable or dock into your laptop's USB-C port and, if available, connect an external monitor through the dock's DisplayPort or HDMI output. If the display activates, you've confirmed your laptop's USB-C port supports DisplayPort Alt Mode video output — the same USB-C-as-video-connector concept referenced in the peripherals chapter and reused here for modern USB-C docking stations.
6. On your laptop, open **Settings ➤ Bluetooth & devices ➤ USB** (Windows 11) or check your dock/hub's included ports, and build a table listing every physical/wireless connection method your laptop supports, categorized as this chapter categorizes them: USB and variants, Lightning (N/A on non-Apple hardware), NFC, Bluetooth, and tethering/hotspot.

**Expected Result:** A completed connection-method worksheet confirming, with real pairing/timing/range data rather than spec-sheet assumptions, which of the five Exam Objective 1.2 connection methods your own hardware actually supports and how each behaves in practice — plus confirmation of whether your laptop's USB-C port functions as a full docking connection (power + video + data) or data-only.