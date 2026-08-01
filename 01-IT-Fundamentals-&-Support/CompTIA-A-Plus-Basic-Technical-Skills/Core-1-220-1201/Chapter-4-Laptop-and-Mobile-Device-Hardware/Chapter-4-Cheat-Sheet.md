## Laptop vs. Desktop vs. Mobile Device

|Factor|Laptop vs. Desktop|
|---|---|
|Portability|Laptop wins (battery + wireless)|
|Cost|Laptop typically higher for same specs|
|Performance|Desktop typically wins|
|Expandability|Desktop far more modular; laptop CPU/mobo not upgradable|
|Build quality demands|Laptop must be more durable (portability abuse)|

Laptop motherboards/cases: proprietary, custom-fit — no cross-brand "build your own laptop" market.

---

## Manufacturer Service/Support Sites (Table 4.1)

|Company|URL|
|---|---|
|Apple|support.apple.com/mac|
|Asus|www.asus.com/support|
|Dell|www.dell.com/support|
|HP|support.hp.com|
|Lenovo|support.lenovo.com|
|Sony|www.sony.com/electronics/support|

---

## Pre-Repair Safety Checklist

1. Turn off the computer
2. Disconnect all external peripherals/cables
3. Unplug from power source
4. Clear, well-lit workspace
5. Manual/help videos handy
6. Proper tools ready (+ phone for photos)
7. ESD wrist strap / antistatic protection

---

## Laptop Case & Clamshell

|Part|Detail|
|---|---|
|Display|LCD / LED / OLED|
|Case structure|Internal metal skeleton (rigidity)|
|Case (outer)|Plastic (ABS/ABS composite) or aluminum/titanium|
|Top half (clamshell)|Webcam, mic, Wi-Fi antenna|
|Bottom half (clamshell)|Motherboard, memory, storage, keyboard, battery, fan, speakers|

---

## Display Components

|Component|Function|
|---|---|
|Backlight|Lights LCD panel (OLED needs none)|
|Inverter|DC→AC for backlight; stores charge = shock risk; rod-shaped|
|Digitizer|Converts touch → digital signal|
|Webcam|Usually above screen; illumination light = "live" indicator|
|Microphone|In display bezel or bottom clamshell|
|Wi-Fi antenna|Runs through top half + hinge; hinge damage can break Wi-Fi|

**Exam Objective 1.1 replaceable display parts:** Wi-Fi antenna connector, camera/webcam, microphone.

---

## Motherboard / Processor

|Item|Detail|
|---|---|
|Riser card / daughterboard|Offloads video/audio/network circuitry (Dell: "I/O board")|
|Laptop CPU mounting|Soldered OR Micro-FCBGA (Flip Chip Ball Grid Array) — not upgradable|
|Heat management|Lower voltage/clock speed + processor throttling (active sleep/slowdown)|
|Shared video memory|Configured in BIOS/UEFI, typically 512MB–2GB range; reconfigure after RAM upgrade|

---

## SODIMM Generations

|Type|Pins|Bit Width|Max Capacity (per module)|
|---|---|---|---|
|SDRAM|144-pin|64-bit|—|
|DDR|72-pin / 100-pin (older 32-bit) also existed|32-bit (legacy)|~1 GB|
|DDR/DDR2|200-pin|64-bit|DDR2 up to 8 GB|
|DDR3|204-pin|64-bit|Up to 8 GB|
|DDR4|260-pin|64-bit|Up to 32 GB|
|DDR5|262-pin|64-bit|Up to 64 GB|

SODIMM dimensions: `67.6mm (2.6") × 32mm (1.25")`

---

## MicroDIMM

|Attribute|Detail|
|---|---|
|Dimensions|~45.5mm (1.75") × 30mm (1.2")|
|Keying|No keying notches (more square than SODIMM)|
|Supported|64-bit, 172-pin or 214-pin (DDR2/DDR3 only)|
|Not produced|DDR4, DDR5 MicroDIMMs never made|
|Use case|Ultra-light subnotebooks|

---

## Laptop Storage

|Form Factor|Notes|
|---|---|
|2.5" / 1.8" HDD or SSD|<0.5" thick typical; smaller connectors than desktop 3.5"|
|M.2 SSD|Narrow slot-mounted; single screw; no separate cable|
|Removal (M.2)|Remove bottom cover → remove screw → slide out|
|Removal (2.5"/1.8")|Disconnect cable → remove 2–4 screws → lift drive/bracket|

**Migration options:**

|Method|Transfers Files|Transfers Settings/Apps|Requires Both Drives Accessible|
|---|---|---|---|
|Manual copy|Yes|No|Not necessarily|
|Migration software (PCmover, Macrium Reflect X, SuperDuper)|Yes|Yes|Yes|

---

## Input / Pointing Devices

|Device|Key Trait|Common Issue|
|---|---|---|
|Trackball|Inverted mouse|Clogs w/ dirt/oil from fingers|
|Trackpad / Touchpad (HP trademark)|Touch-sensitive pad, 2-button or tap-click|Palm-triggered accidental input|
|Track Point / Point Stick (IBM/Lenovo)|Rubber-tipped stick, pressure = speed|Drift (centering failure), gummy cap|
|Touchscreen|Direct-touch input|Needs periodic calibration|

**Disable trackpad (Win 11):** Search "touchpad" → toggle off **Disable track point (Win 11):** Search "mouse"/"pointstick" → PointStick Settings → Properties → Disable **Calibrate touchscreen (Windows):** Control Panel ➤ Tablet PC Settings ➤ Calibrate

2-in-1 devices: screen folds flat → tablet mode → keyboard disabled, auto screen-orientation.

---

## Internal Expansion

|Standard|Connector Width|Pins|Max Speed|Common Since|
|---|---|---|---|---|
|Mini PCIe|30mm|52-pin|PCIe x1 (+ USB)|~2005|
|M.2|22mm|66-pin|PCIe x2 (min) / PCIe x4 (M-keyed)|Newer, faster|

Mini PCIe card sizes: Full = 30mm × 51mm · Half = 30mm × 27mm Mini PCIe power: 1.5V and 3.3V

---

## Battery Chemistries

|Chemistry|Notes|
|---|---|
|NiCd|Chemical memory effect (true capacity loss)|
|Li-ion|Digital memory effect (gauge miscalibration, not real capacity loss)|
|NiMH|Common older chemistry|
|Li-poly|Newer, common in smaller devices|

Battery calibration fix: full discharge ~monthly (fixes digital memory effect) Li-ion day-to-day: prefers partial discharge/recharge cycles Energy density = how much stored · Power density = how fast it releases · Self-discharge rate = idle charge loss

---

## Power Adapters

|Rule|Detail|
|---|---|
|Wattage|Match original or higher — never lower|
|Voltage|Must match regional power grid|
|Autoswitching|Universal voltage — common but not universal to all adapters|
|International travel|Plug converter may still be needed even with autoswitching|
|Common connector (2014+)|USB-C|

---

## Other Internal Components (Non-Exam, Still Practical)

|Component|Removal Notes|
|---|---|
|Fan|Bottom cover → 2 screws → lift away|
|Heat sink|Remove fan first → loosen 4 bracket screws (don't fully remove) → lift straight up|
|Wireless NIC|Bottom cover → bracket screw → disconnect 2 antenna wires (white=main, black=aux) → pull from M.2 socket|
|CMOS battery|Bottom cover → disconnect connector → peel off (often glued)|

**Flash BIOS/UEFI (Dell example):** dell.com/support → Drivers & Downloads → select OS → BIOS section → download → run

---

## Physical Privacy & Security (Exam Objective 1.1)

|Item|Detail|
|---|---|
|Biometrics|Fingerprint, facial recognition, voice, retinal|
|Near-field scanner (NFC)|~10cm (4") range; risks: confidentiality, DoS, on-path attacks|
|Cable lock|a.k.a. Kensington lock / K-lock; anchors to fixed structure|
|Privacy screen|Narrows viewing angle; some laptops built-in via Fn key (e.g., Fn+F2)|

---

## Connection Methods (Exam Objective 1.2)

| Method                         | Key Fact                                                                                          |
| ------------------------------ | ------------------------------------------------------------------------------------------------- |
| USB (+ microUSB/miniUSB/USB-C) | Most universal                                                                                    |
| Lightning                      | Apple proprietary, 8-pin; Apple shifting to USB-C since 2022                                      |
| NFC                            | ~10cm range; more often built into an accessory than used to connect one                          |
| Bluetooth                      | Popular for headsets/speakers/keyboards/mice; drains battery faster                               |
| Tethering / Hotspot            | Hotspot = shares cellular via Wi-Fi; Tethering = historically wired USB connection, now broadened |

---

## Mobile Accessories (Exam Objective 1.2)

|Accessory|Notes|
|---|---|
|Stylus / Touch pen|Narrow tip or soft rubber-ball tip|
|Headset|Speakers (in/over-ear) + mic; wired or Bluetooth|
|Speakers|USB or Bluetooth common|
|Webcam|Built-in on most mobile devices; USB/Bluetooth standalone available|
|Trackpad/Drawing pad/Track point|Drawing pads ~sheet-of-paper size, USB-attached|

---

## Docking Stations & Port Replicators

|Item|Detail|
|---|---|
|Docking station|Extension of motherboard; can host full-size bays/expansion slots|
|Port replicator|Reproduces laptop's rear ports for permanently-connected peripherals|
|Modern connection|USB-C (non-proprietary) — technically a port replicator even if called "docking station"|
|Legacy connection|Proprietary bottom-of-case connector, manufacturer-specific|
|Example dock ports|4× USB (2 side), 2× DisplayPort, 1× HDMI, 1× RJ45, cable lock slot; ~5" square × 2" high|