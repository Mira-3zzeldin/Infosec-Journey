## Printer Technology Comparison

|Type|Mechanism|Key Consumable(s)|Typical Use|
|---|---|---|---|
|Impact — Daisy-wheel|Solenoid strikes raised character petal into ribbon|Ribbon, printhead, paper|Multipart forms (legacy)|
|Impact — Dot-matrix|Solenoid-fired pins strike ribbon in dot patterns|Ribbon, printhead, tractor-feed paper|Multipart forms|
|Inkjet|Thermal-bubble or piezoelectric nozzles spray ink|Ink cartridge, printhead|General/photo printing|
|Laser (EP process)|Laser/LED + electrostatic charge + toner + heat|Toner cartridge, fuser|Office/high-volume|
|Thermal Direct|Heated printhead darkens heat-sensitive paper|Thermal paper roll|POS receipts|
|Thermal Transfer|Heated printhead melts wax ribbon onto paper|Wax ribbon, paper|Labels, POS|

---

## Impact Printer Specs

|Spec|Daisy-Wheel|Dot-Matrix|
|---|---|---|
|Speed unit|cps (characters/sec)|cps|
|Early speed|2–4 cps|~72 cps typical (up to ~1550 cps top-end)|
|Quality tier name|Letter Quality (LQ)|Draft (9-pin) → Near Letter Quality/NLQ (17/24-pin)|
|Pin counts (dot-matrix)|—|9-pin, 17-pin, 24-pin|
|Paper|Multipart/impact paper, tractor feed|Multipart/impact paper, tractor feed|
|Main weakness|Noise, no font flexibility|Lower image quality vs. daisy-wheel|

---

## Inkjet Printer Parts

|Component|Function|
|---|---|
|Printhead|Contains 100–200 nozzles that spray ink droplets|
|Ink cartridge|Ink reservoir; often bundled with printhead|
|CMYK|Cyan, Magenta, Yellow, Black — color ink set|
|Maintenance station|Suction pump + absorbent pad; parks/primes printhead|
|Printhead carriage|Holds cartridge(s); moves via belt|
|Carriage/stepper motor|Drives carriage belt in precise increments|
|Carriage belt|Loops around pulleys; moves carriage across page|
|Stabilizer bar|Keeps carriage aligned while traversing|
|Pickup rollers|Feed paper from tray/feeder|
|Separation pads|Prevent multiple sheets feeding at once|
|Paper feed sensors|Detect out-of-paper / jam conditions|
|Duplexing assembly|Flips paper for double-sided printing|
|Print buffer|512 KB – 16 MB onboard memory for queued jobs|

Ink ejection methods: **Thermal/bubble** (HP-style, heats ink to vaporize/expand) vs. **Piezoelectric** (Epson-style, flexing element pushes/pulls ink).

---

## Laser Printer (EP Process) — 9 Standard Assemblies

|Assembly|Function|
|---|---|
|Toner cartridge|Holds toner + developer/carrier + photosensitive drum + cleaning blade|
|Laser scanning assembly|Scans laser across drum to discharge exposed areas|
|High-Voltage Power Supply (HVPS)|Powers charging + transfer coronas|
|DC Power Supply (DCPS)|+5VDC/−5VDC logic, +24VDC paper transport motors|
|Paper transport assembly|Feed roller + registration rollers, driven by electronic stepper motor|
|Transfer corona assembly|Charges paper to pull toner off drum; includes static-eliminator strip|
|Fusing assembly|Halogen lamp + Teflon fusing roller + rubber pressure roller|
|Printer controller circuitry|Rasterizes data; commands each assembly|
|Ozone filter|Removes ozone from corona-wire designs (largely absent on roller-based printers)|

**Fuser temperature:** 329°F–392°F (165°C–200°C)

**Transfer corona types:** Corona wire (legacy, lower speed) vs. Corona roller (direct contact, higher speed, standard today)

---

## EP Imaging Process — 7 Steps (in order)

|#|Step|What Happens|Voltage|
|---|---|---|---|
|1|Processing|Job received via interface; RIP builds raster image in memory|—|
|2|Charging|Charging corona applies uniform charge to drum|−600VDC|
|3|Exposing|Laser discharges drum where image should appear|Drops to −100VDC|
|4|Developing|Developing roller (bias voltage) sticks toner to discharged areas|Roller at −600VDC|
|5|Transferring|Transfer corona charges paper; paper pulls toner off drum|+600VDC to paper|
|6|Fusing|Heat + pressure rollers permanently bond toner to paper|329–392°F / 165–200°C|
|7|Cleaning|Rubber blade scrapes drum; lamp discharges remaining voltage|—|

Mnemonic order: **P**rocessing, **C**harging, **E**xposing, **D**eveloping, **T**ransferring, **F**using, **C**leaning.

---

## Thermal Printers

|Type|Mechanism|Notes|
|---|---|---|
|Thermal Direct|Heated printhead darkens heat-sensitive paper directly|Waxy roll paper; degrades in heat/sun|
|Thermal Transfer / Wax-Transfer|Heated printhead melts wax ribbon onto plain paper|Used for labels|

Key part: **Feed assembly** (accommodates roll paper). Few moving parts = long service life. Poorer image quality than impact/inkjet/laser.

---

## Printer Connectivity (Exam Objective 3.7)

|Method|Notes|
|---|---|
|USB|Most common wired interface; square Type-B on printer side; higher transfer rate than serial/parallel; auto-recognizes|
|Ethernet (RJ45)|Built-in NIC + ROM software; direct network attachment|
|Wireless (Wi-Fi)|Supports 802.11 a/b/g/n/ac/ax/be|
|Bluetooth|~10 meters (33 feet) range; common on compact/mobile printers|
|Legacy|DB-9 serial, DB-25 parallel (largely retired)|

**Infrastructure mode** = permanent Wi-Fi network attachment. **Ad hoc** = temporary single-device Wi-Fi/Bluetooth link.

---

## Installation Procedure (7 Steps)

|#|Step|
|---|---|
|1|Choose setup location + properly unbox|
|2|Attach device (USB/Ethernet/wireless) + connect power|
|3|Install/update driver, update firmware, calibrate|
|4|Configure options and settings|
|5|Print a test page|
|6|Verify OS/application compatibility|
|7|Educate users about functionality|

---

## Page-Description Languages

|Language|Notes|
|---|---|
|PostScript (PS)|Higher-level draw/position commands; fast for graphics|
|PCL (Printer Control Language)|More common; became near-universal across printer types|
|Wrong driver symptom|Pages of garbled text = literal PDL commands printed instead of interpreted|

---

## Printer Properties Tabs

|Tab|Controls|
|---|---|
|General|Basic info, test page|
|Sharing|Network availability|
|Ports|Port assignment, printer pooling (same location only)|
|Advanced|Available hours, spooling on/off, keep printed documents|
|Security|Who can print/manage|

## Printing Preferences (per-job settings)

|Setting|Options|
|---|---|
|Orientation|Portrait / Landscape|
|Duplex|Single-sided / Double-sided|
|Quality|Draft / Normal / Best|
|Paper tray/size|Letter (8.5"×11"), Legal (8.5"×14"), A4 (210mm×297mm ≈ 8.3"×11.7")|

---

## Sharing & Networked Printing

|Term|Definition|
|---|---|
|Printer share|A printer made available to other network users|
|Print server|Device/system hosting the printer and processing print commands|
|Integrated print server|Print-server role built into the printer itself (most common today)|
|RAW / Standard TCP/IP Port Monitor|Default; TCP port **9100**; uses SNMP for bidirectional status|
|LPR|Legacy protocol; source ports **721–731**, destination port **515**|
|Bonjour|Zero-config discovery over TCP/IP; single broadcast domain only; default on macOS/iOS|
|AirPrint|Driverless mobile printing; client needs no driver; same local network required|

---

## Printer Security (Exam Objective 3.7 — 4 Features)

|Feature|Description|
|---|---|
|User authentication|Login required at device (credentials)|
|Badging|Physical work-ID badge scan to authenticate|
|Secured prints|Job held until user authenticates + releases at printer|
|Audit logs|Record of who printed what (native, OS-integrated, or 3rd-party)|

**Hard drive caching risk:** "Keep printed documents" persists jobs on print-server storage indefinitely — never enable on public/shared printers.

---

## Network Scan Services (Exam Objective 3.7)

|Method|Capture Device|Notes|
|---|---|---|
|Flatbed scanner|Glass bed, lid|One document at a time|
|ADF (Automatic Document Feeder)|Feeder tray|Up to ~50 pages in one job|
|Scan to Email|—|Most common; typically PDF output|
|Scan to Folder|—|Uses SMB (Server Message Block) protocol|
|Scan to Cloud|—|Google Drive, OneDrive, Box, Dropbox, manufacturer services|

---

## Maintenance by Printer Type (Exam Objective 3.8)

|Type|Maintenance Tasks|
|---|---|
|Impact|Replace ribbon, printhead, paper|
|Inkjet|Clean printheads, replace cartridges, calibrate, clear jams|
|Laser|Replace toner, apply maintenance kit, calibrate, clean|
|Thermal|Replace paper, clean heating element, remove debris|

---

## Paper Properties

|Property|Definition|
|---|---|
|Composition|Cotton (rag stock) vs. wood pulp vs. blend|
|Basis weight|Weight (lbs) of a 500-sheet ream at standard size (17"×22" for bond)|
|Caliper|Thickness — too thick jams curved paths, too thin may not feed|

|Size|Dimensions|
|---|---|
|US Letter|8.5" × 11"|
|US Legal|8.5" × 14"|
|A4 (international)|210mm × 297mm (≈ 8.3" × 11.7")|

---

## Ink/Toner Rules

|Rule|Detail|
|---|---|
|Source|Always buy from manufacturer or authorized reseller|
|Never refill toner|Skips drum replacement often bundled in cartridge; degrades quality|
|Never use refill kits (inkjet)|Wrong ink viscosity; doesn't replace worn printhead; reseal leaks|
|Ribbon source (dot-matrix)|Buy from printer's own manufacturer to avoid jams/quality issues|

---

## Environmental Hazards

|Hazard|Effect|Mitigation|
|---|---|---|
|Heat|Shortens printer life (laser/thermal generate heat)|Well-ventilated placement|
|Humidity|>80–90% causes paper sticking → jams|Dry storage area|
|Light|Can ruin photosensitive drum|Never open toner cartridge unnecessarily|
|Ozone|Respiratory irritant; damages components|Ventilation, periodic filter replacement|
|Ammonia|Neutralizes ozone-fighting ability; damages toner cartridges|Avoid ammonia-based cleaners near laser printers|

---

## PowerShell Print Management Cmdlets

|Cmdlet|Purpose|
|---|---|
|`Get-Printer`|List installed printers|
|`Get-PrinterPort`|List configured printer ports|
|`Get-PrintJob -PrinterName "X"`|View jobs in a printer's queue|
|`Suspend-PrintJob`|Pause a print job|
|`Resume-PrintJob`|Resume a paused job|
|`Remove-PrintJob`|Cancel/delete a print job|
