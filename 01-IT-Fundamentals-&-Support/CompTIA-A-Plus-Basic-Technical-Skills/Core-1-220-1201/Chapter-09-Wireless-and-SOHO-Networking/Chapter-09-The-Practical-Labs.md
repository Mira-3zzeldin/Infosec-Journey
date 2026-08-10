### 🛠️ Lab 1: The Control Tower Readout — Wi-Fi Network Inspection with `netsh wlan`

**Objective:** Build hands-on fluency with real Wi-Fi network metadata — SSID, channel, radio type (802.11 standard), and signal strength — by querying Windows' native wireless stack directly, and connect observed channel numbers back to this chapter's nonoverlapping-channel rules.

**Environment/Tools Needed:** A Windows 11 PC (physical or VM with a real or passed-through Wi-Fi adapter — this will not work over a virtual/emulated NIC) with an active Wi-Fi connection, and a Command Prompt window (no admin rights required).

**Step-by-Step Instructions:**

1. Open **Start**, type `cmd`, and open a normal (non-admin) Command Prompt window.
2. Run `netsh wlan show interfaces` and record the following fields from the output: **SSID**, **Radio type** (this will show something like `802.11ac` or `802.11ax` — your connected standard), **Channel**, and **Signal** (shown as a percentage).
3. Based on the radio type recorded in step 2, identify which Wi-Fi generation name it maps to (for example, `802.11ac` = Wi-Fi 5, `802.11ax` = Wi-Fi 6/6E) using this chapter's naming conventions.
4. Run `netsh wlan show networks mode=bssid` and scroll through the output. For at least three visible networks (including your own, if shown), record the **SSID**, **Signal** strength, **Authentication** type (e.g., `WPA2-Personal`, `WPA3-Personal`), and **Channel**.
5. For any networks you recorded operating in the `2.4 GHz` range (channel numbers roughly 1–11), check whether their channel numbers are 1, 6, or 11, or something else.
6. Run `netsh wlan show networks mode=bssid` again if needed and specifically look for two or more networks sharing the same or adjacent (non-1/6/11) channel numbers in the `2.4 GHz` range.
7. Write two to three sentences explaining, based on this chapter's channel-overlap rules, what problem could occur if two nearby access points were both configured on channel 4 instead of channels 1 and 6, and why the ISP/router default of "auto-channel" usually helps avoid this in the real world.

**Expected Result:** A recorded SSID, radio type/Wi-Fi generation, channel, and signal strength for your own connection, plus the same details for at least three neighboring networks, along with a short written explanation connecting observed channel numbers to the nonoverlapping-channel concept from this chapter.

---

### 🛠️ Lab 2: Ground Crew Diagnostics — NIC IP Configuration, DHCP, and APIPA

**Objective:** Reinforce dynamic vs. static IP configuration, the role of the default gateway and DNS server, and the purpose of APIPA by directly inspecting and cycling a live network adapter's configuration.

**Environment/Tools Needed:** A Windows 11 PC connected to a network via DHCP (Wi-Fi or Ethernet), and a Command Prompt window (no admin rights required for `ipconfig`; administrator rights needed only for the optional adapter-properties step).

**Step-by-Step Instructions:**

1. Open Command Prompt and run `ipconfig /all`. Record the following for your active adapter: **IPv4 Address**, **Subnet Mask**, **Default Gateway**, **DHCP Enabled** (Yes/No), **DHCP Server**, and **DNS Servers**.
2. Confirm that the Default Gateway address matches your router's LAN IP address (commonly `192.168.1.1` or `192.168.0.1`, per this chapter's discussion of default router addressing).
3. Run `ipconfig /release`. This releases the adapter's current DHCP-assigned lease.
4. Immediately run `ipconfig /all` again and note that the IPv4 Address field is now blank or shows `APIPA`, confirming the lease was released.
5. Run `ipconfig /renew` to request a new lease from the DHCP server, and confirm the IPv4 Address, Subnet Mask, and Default Gateway have been restored (the address may match the original lease or be a newly assigned one).
6. (Optional, requires administrator rights) Open **Settings > Network & Internet > Advanced Network Settings**, click **More Adapter Options**, right-click your active adapter, select **Properties**, select **Internet Protocol Version 4 (TCP/IPv4)**, and click **Properties**. With **Obtain an IP address automatically** selected, click the **Alternate Configuration** tab and note that this is where a manual fallback address could be defined — if left unconfigured, Windows instead falls back automatically to an APIPA address in the `169.254.x.x` range whenever no DHCP server responds. Close without making changes.
7. Write two to three sentences explaining, based on this chapter, why a computer that has self-assigned an APIPA address can still communicate with other APIPA-addressed devices on the same local network but cannot reach the Internet, referencing the role of the default gateway.

**Expected Result:** A recorded full IP configuration (address, subnet mask, gateway, DHCP status, DNS servers), confirmation that `ipconfig /release` clears the address and `ipconfig /renew` restores it, and a short written explanation connecting APIPA's local-only reachability to the missing default gateway.

---


### 🛠️ Lab 3: The Customs Checkpoint — Windows Defender Firewall ACL Behavior

**Objective:** Reinforce how a host-based firewall's access control list (ACL) governs inbound traffic by enabling and disabling a real inbound rule and observing the resulting change in reachability, tying the exercise back to this chapter's default deny/default allow and ACL concepts.

**Environment/Tools Needed:** A Windows 11 PC with local administrator rights, a second device on the same local network capable of running `ping` (another PC, or a phone with a terminal/network-tools app), and Windows Defender Firewall with Advanced Security (`wf.msc`).

**Step-by-Step Instructions:**

1. On the Windows 11 PC, open Command Prompt and run `ipconfig` to find and record its IPv4 address on the local network.
2. From the second device, attempt to `ping` that IPv4 address. In most default Windows 11 configurations, this will fail or time out — Windows Firewall blocks unsolicited inbound ICMP echo requests by default. Record the result.
3. On the Windows 11 PC, press **Start**, type `wf.msc`, and open **Windows Defender Firewall with Advanced Security** (this requires administrator rights).
4. In the left pane, click **Inbound Rules**. In the rule list, locate the two rules named **File and Printer Sharing (Echo Request - ICMPv4-In)** — there are typically both a Domain/Private and a Public profile version.
5. Right-click each of these rules and select **Enable Rule** (or check the box in the Actions pane). Confirm the rule status column now shows the rule as enabled.
6. From the second device, `ping` the Windows 11 PC's IPv4 address again. Record whether you now receive replies.
7. Return to Windows Defender Firewall with Advanced Security, right-click the same two rules, and select **Disable Rule** to restore the default configuration.
8. From the second device, `ping` the address one final time and confirm it fails again, matching the original default state.
9. Write two to three sentences explaining, based on this chapter, how this exercise demonstrates an ACL rule controlling default-deny behavior, and why a business would want intentional control over which inbound traffic (like ICMP, or a specific application port) is allowed through a firewall rather than leaving everything open.

**Expected Result:** A confirmed baseline of blocked inbound ICMP traffic, successful ping replies after enabling the Echo Request rule, and a return to blocked traffic after disabling it again — plus a short written explanation tying the behavior to ACL and default-deny concepts.