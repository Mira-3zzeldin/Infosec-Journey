## Motherboard Form Factors

|Form Factor|Dimensions|Developer|Notes|
|---|---|---|---|
|ATX|12" × 9.6" (305mm × 244mm)|Intel (mid-1990s)|Dominant PC form factor; CPU/RAM at right angle to expansion cards|
|microATX|9.6" square (244mm)|Intel derivative|Shares ATX mounting points; fewer connectors|
|Mini-ITX|6.7" × 6.7" (170mm × 170mm)|VIA Technologies|ATX-case compatible mounting/rear I/O|
|Nano-ITX|4.7" × 4.7" (120mm × 120mm)|VIA Technologies|Embedded use; not ATX-mount compatible|
|Pico-ITX|3.9" × 2.8" (100mm × 72mm)|VIA Technologies|Embedded use|
|Mobile-ITX|2.4" × 2.4" (60mm × 60mm)|VIA Technologies|Embedded use|

## Expansion Slots / Buses

| Interface             | Width/Config | Speed / Throughput                    | Notes                            |
| --------------------- | ------------ | ------------------------------------- | -------------------------------- |
| PCI                   | 32-bit       | 133 MBps @ 33 MHz / 266 MBps @ 66 MHz | Shared bus; 3.3V or 5V keyed     |
| PCI (64-bit, servers) | 64-bit       | 2× the 32-bit rates                   | Version 1.0+                     |
| AGP                   | Video-only   | Obsolete (1997–late 2000s)            | Superseded by PCIe               |
| PCIe 1.x              | x1 lane      | 250 MBps/dir (500 Mbps bidirectional) | Ratified 2003                    |
| PCIe 4.0              | —            | 2× PCIe 3.0                           | Ratified Oct. 2017               |
| PCIe 5.0              | —            | 2× PCIe 4.0                           | Released May 2019                |
| PCIe 6.0              | x16          | 256 GBps bidirectional                | Released Jan. 2022, devices 2024 |
| PCIe 7.0              | —            | 2× PCIe 6.0                           | Spec 2025, devices ~2027         |
| PCIe 1.1 x16          | 16 lanes     | 4 GBps/dir, 8 GBps bidirectional      | Common gaming-era slot           |

## Storage & I/O Connectors

|Connector|Speed|Notes|
|---|---|---|
|PATA/IDE|Legacy|Obsolete; missing center pin keys cable|
|SATA 1.5 Gbps (SATA I/150)|150 MBps effective|8b/10b encoding, 20% overhead|
|SATA 3 Gbps (SATA II/300)|300 MBps effective|2× SATA I|
|SATA 6 Gbps (SATA III/600)|600 MBps effective|2× SATA II|
|eSATA|= matching SATA speed|No power delivery; losing ground to USB-C/Thunderbolt|
|M.2|Varies (SATA/USB/PCIe)|Form factor only, NOT a bus standard|

## CPU Sockets (Selected)

|Socket|Released|Type|Pins|Processors|
|---|---|---|---|---|
|Socket sTR5|2023|LGA|4844|AMD Threadripper|
|LGA 1700|2021|LGA|1700|Intel Alder/Raptor Lake|
|LGA 1200|2020|LGA|1200|Intel Comet/Rocket Lake|
|Socket AM4|2017|PGA|1331|AMD Ryzen 3/5/7/9, Athlon 200GE|
|LGA 2066|2017|LGA|2066|Intel Skylake-X, Kaby Lake-X|
|LGA 1151|2015|LGA|1151|Intel Skylake/Kaby Lake/Coffee Lake|
|Socket FM2+|2014|PGA|906|AMD Kaveri/Godavari|
|Socket AM1|2014|PGA|721|AMD Athlon/Sempron|

## DDR Memory Generations

| Gen  | Pins (DIMM) | Pins (SODIMM) | Max Memory                                      | Channels | Voltage | Released  |
| ---- | ----------- | ------------- | ----------------------------------------------- | -------- | ------- | --------- |
| SDR  | 168         | 144           | —                                               | 1        | —       | Legacy    |
| DDR  | 184         | 200           | 1 GB                                            | 1        | 2.5V    | Legacy    |
| DDR2 | 240         | 200           | 8 GB                                            | 1        | 1.8V    | Legacy    |
| DDR3 | 240         | 204           | 32 GB                                           | 1        | 1.5V    | Legacy    |
| DDR4 | 288         | 260           | 64 GB (realistic max) / 512 GB theoretical/chip | 1        | 1.2V    | ~2014     |
| DDR5 | 288         | 262           | 128 GB/module                                   | 2        | 1.1V    | Late 2021 |

**DIMM length (all DDR generations): 5.25" (133.35mm) — SODIMM width: 2.75" (69.6mm)**

## Cache Hierarchy (representative, 10th-gen i7 per-core)

|Level|Size|Location|Speed|
|---|---|---|---|
|L1|80 KB (32 KB inst + 48 KB data)|On-die|Fastest|
|L2|512 KB|On-die (per-core typical)|Fast|
|L3|8–16 MB|On-die (shared)|Slower|
|RAM|16–256 GB|Off-die|Slower still|
|HDD/SSD|100s GB–TBs|Off-die|Slowest|

## BIOS/UEFI & Security

|Item|Key Fact|
|---|---|
|UEFI release|2002|
|BIOS HDD limit|2.2 TB|
|TPM|Onboard security coprocessor; seals boot device to system|
|HSM|External key management device; used if no TPM present|
|Secure Boot|Validates digital signatures of boot files|
|BitLocker|Uses TPM to encrypt entire drive (OS, Registry, hibernation file, data)|
|CMOS battery|Non-rechargeable lithium; powers CMOS memory when unplugged|
|ATX power connector|24-pin|
|POST|Power-On Self-Test; verifies BIOS integrity, memory size, catalogs hardware|

## Cooling

|Type|Notes|
|---|---|
|Heat sink|Passive metal mass; larger surface area = better dissipation|
|Thermal paste/pad|Fills microscopic gaps; apply to heat sink center, thin layer|
|CFM|Cubic feet per minute — airflow volume measurement|
|AIO liquid — 120mm|1 fan; most common; light-duty|
|AIO liquid — 240mm|2 fans; for overclocked components|
|AIO liquid — 360mm|3 fans; high-end multicore overclocking|
|CPU fan headers|3-pin (basic) or 4-pin (adds PWM speed control)|

## CPU Architecture Quick Reference

|Term|Meaning|
|---|---|
|CISC|Complex Instruction Set Computing — x86/x64 (Intel, AMD)|
|RISC|Reduced Instruction Set Computer — ARM family|
|x86|32-bit processors (legacy naming from 80386/80486)|
|x64|True 64-bit processors, 64-bit registers|
|ARM64|64-bit ARM implementation|
|PGA|Pin Grid Array — pins on CPU (e.g., Socket AM4)|
|LGA|Land Grid Array — pins on socket, lands on CPU (e.g., LGA 1700)|
|ZIF|Zero Insertion Force — PGA locking mechanism|
|HTT/SMT|Intel Hyper-Threading Technology / Simultaneous Multithreading|
|P-core / E-core|Performance core (hyperthreads) / Efficient core (no hyperthreading)|
