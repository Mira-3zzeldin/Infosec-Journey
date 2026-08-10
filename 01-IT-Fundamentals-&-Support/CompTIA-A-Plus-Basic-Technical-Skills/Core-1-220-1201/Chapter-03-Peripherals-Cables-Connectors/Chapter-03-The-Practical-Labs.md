### 🛠️ Lab 1: Monitor & Display Attribute Audit with Windows Settings + CPU-Z

**Objective:** Master real-world identification of display panel type, native resolution, refresh rate, and color capability — the exact "will this monitor/GPU combo actually deliver what's advertised" skill tested on the A+ exam.

**Environment/Tools Needed:** A Windows physical PC or Windows VM (VMware Workstation/VirtualBox), internet access, [CPU-Z](https://www.cpuid.com/) freeware.

- Note on Virtual Machines (VMs): A VM's virtualized GPU driver will often misreport or cap refresh rate/resolution options compared to a native install with the real GPU driver installed. For full accuracy on Steps 3–5, a physical machine with the manufacturer's GPU driver is recommended.

**Step-by-Step Instructions:**

1. Right-click a blank portion of the desktop and select **Display Settings**. Record your monitor's currently selected **Display Resolution**.
2. Scroll to **Related Settings** and click **Advanced Display**. Note the **Desktop mode** (current resolution/Hz) and **Active signal mode** fields, then click the **Choose a refresh rate** dropdown and record every refresh rate option offered at your current resolution.
3. Change the resolution one step down from native (e.g., from 2560×1440 to 1920×1080) and revisit the refresh rate dropdown. Record whether _more_ refresh rate options appear at the lower resolution — this demonstrates the resolution/refresh-rate bandwidth trade-off described in this chapter. **Revert to your native resolution when finished.**
4. **Pro-Tip / Technical Note:** If no additional refresh rate options appear after lowering the resolution, this does not contradict the **Bandwidth Trade-off** principle. Instead, it indicates that your monitor features a **Firmware-Locked Panel** (common in standard office and budget displays). In these monitors, the internal controller restricts the refresh rate to a fixed maximum (e.g., 60Hz) under all circumstances to ensure display stability and longevity.
5. Open **CPU-Z**, go to the **Graphics** tab (if present in your version) to confirm your GPU model and confirm it against your monitor's maximum advertised refresh rate and resolution from its own spec sheet (search the monitor model online if unknown).
6. Back in Windows, on the **Display** page, check for an a **color format/color space** field under Advanced Display (or your GPU vendor's control panel, e.g., NVIDIA Control Panel → Display → Change Resolution, which will show Output Color Format and Output Dynamic Range). Record whether your setup is running at a full or limited color gamut.
7. Physically inspect (or research) your monitor's panel type sticker/spec sheet and classify it as TN, IPS, VA, OLED, or Mini-LED using the viewing-angle/contrast/lag characteristics from this chapter's study guide.

**Expected Result:** A completed display-attribute worksheet (native resolution, all supported refresh rates, panel type classification, and color format/gamut setting) that lets you diagnose, without guesswork, whether a "monitor looks washed out" or "can't hit advertised Hz" ticket is a cable/bandwidth issue, a settings issue, or a genuine hardware limitation.

---
### 🛠️ Lab 2: Cable & Connector Field Identification Workshop

**Objective:** Build hands-on pattern recognition for the physical connectors covered in this chapter (USB-A/B/C, Micro/Mini-USB, HDMI/mini/micro-HDMI, DisplayPort/mDP, DVI-A/D/I, VGA, SATA, eSATA, Molex, Lightning, Thunderbolt, DB-9, PS/2, TRS/TRRS) so identification becomes instant — mirroring the exact performance-based question format used on the real A+ exam.

**Environment/Tools Needed:** Access to at least one desktop PC/laptop chassis (powered off), a smartphone camera, and (optional) an assortment of spare cables/adapters from a junk drawer or electronics store.

**Step-by-Step Instructions:**

1. With the PC/laptop **powered off and unplugged**, photograph the rear I/O panel (desktop) or side ports (laptop) at high resolution.
2. Create a numbered answer sheet. For every physical port visible in your photo, identify: (a) connector family, (b) male or female, (c) analog or digital, and (d) which peripheral category it belongs to (video, storage, peripheral/multi-purpose, or audio).
3. Cross-check color-coding where present: blue = VGA or USB 3.0/SuperSpeed; black = USB 2.0; PS/2 purple (keyboard) vs. green (mouse); yellow = USB always-on charging port.
4. For any DVI port found, physically inspect the pin layout (if accessible) and classify it as DVI-A, DVI-D, or DVI-I, single-link or dual-link, referencing the six-conductor rule for dual-link.
5. Gather any spare cables you have access to (USB cables of different generations, HDMI, a phone charging cable, an old SATA cable, etc.) and sort them into two piles: "provides power" vs. "data only," then a second pass sorting by maximum theoretical throughput using the tables from this chapter.
6. Write a one-paragraph summary for each connector explaining what adapter (if any) would be required to connect it to a different, incompatible standard (e.g., "this DVI-I port would need a passive DVI-to-VGA adapter to connect to an analog monitor").

**Expected Result:** A fully annotated port-identification worksheet/photo, plus a sorted cable inventory categorized by power delivery and data throughput — directly mirroring the format of the A+ exam's Performance-Based Questions.