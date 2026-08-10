## Chapter 10: Mobile Connectivity and Application Support | 60 Questions

> **Instructions:** Answer all questions before checking the Answer Key at the bottom of this file.

---

## Section 1: Direct/Basic Recall (Q1–20)

**1.** In what year did 1G, the original analog cellular standard, launch?

- A. 1979
- B. 1991
- C. 1998
- D. 2008

---

**2.** What was the maximum data rate of 2G once it became commercially available?

- A. 14.4 Kbps
- B. 64 Kbps
- C. 200 Kbps
- D. 2 Mbps

---

**3.** Which company developed CDMA, the cellular standard used only in the United States?

- A. AT&T
- B. Verizon
- C. Qualcomm
- D. Nokia

---

**4.** What was the minimum specified download rate when 3G was introduced in 1998?

- A. 64 Kbps
- B. 200 Kbps
- C. 1 Mbps
- D. 7 Mbps

---

**5.** Which two competing standards battled for dominance in the early days of 4G?

- A. GSM and CDMA
- B. WiMAX and LTE
- C. IKEv2 and L2TP
- D. eMBB and URLLC

---

**6.** What is the theoretical maximum download speed for 4G LTE?

- A. 75 Mbps
- B. 100 Mbps
- C. 300 Mbps
- D. 1 Gbps

---

**7.** What is the theoretical peak download capacity of 5G?

- A. 1 Gbps
- B. 10 Gbps
- C. 20 Gbps
- D. 100 Gbps

---

**8.** What frequency range does 5G mmWave use?

- A. 600 MHz–6 GHz
- B. 2.4 GHz–5 GHz
- C. 24 GHz–86 GHz
- D. 100 GHz–200 GHz

---

**9.** Which 5G classification is designed specifically for autonomous vehicles and industrial applications?

- A. eMBB
- B. URLLC
- C. mMTC
- D. GNSS

---

**10.** On an Android device, enabling the mobile hotspot automatically does what to the device's own Wi-Fi?

- A. Nothing changes
- B. Wi-Fi switches to 5 GHz only
- C. Wi-Fi is turned off
- D. Wi-Fi is bridged to the hotspot

---

**11.** How many digits does a standard IMEI contain?

- A. 10
- B. 14
- C. 15
- D. 20

---

**12.** What dial code displays a phone's IMEI on most devices?

- A. *#06#
- B. *228
- C. *#61#
- D. #31#

---

**13.** How many digits of the IMEI does the MEID duplicate?

- A. The first 10
- B. The first 14
- C. All 15
- D. The last 14

---

**14.** What are the three components of an IMSI?

- A. IMEI, MEID, ICCID
- B. MCC, MNC, MSIN
- C. SIM, eSIM, SEID
- D. PRI, PRL, RTOS

---

**15.** How many digits does a typical ICCID contain?

- A. 10–12
- B. 14–15
- C. 19–20
- D. 25–30

---

**16.** What port number does SMTP use by default, without encryption?

- A. 21
- B. 25
- C. 110
- D. 143

---

**17.** What port does POP use with SSL/TLS encryption?

- A. 465
- B. 587
- C. 993
- D. 995

---

**18.** What port does IMAP use with SSL/TLS encryption?

- A. 143
- B. 465
- C. 993
- D. 995

---

**19.** Approximately how many total GPS satellites does the United States currently manage?

- A. 7
- B. 24
- C. 31
- D. 45

---

**20.** What is the default free storage tier for Apple iCloud?

- A. 2 GB
- B. 5 GB
- C. 15 GB
- D. 50 GB

---

## Section 2: Intermediate/Conceptual (Q21–40)

**21.** A user's phone was originally activated on Verizon and used CDMA. Why couldn't that same phone, without modification, be used on an AT&T network?

- A. AT&T only supports 5G devices
- B. GSM and CDMA are incompatible cellular standards
- C. Verizon phones do not have a SIM slot
- D. AT&T requires an eSIM only

---

**22.** Why do many IoT systems continue to rely on 4G rather than upgrading to 5G?

- A. 5G modems are not yet manufactured
- B. 4G throughput and latency are sufficient, and the hardware is cheaper
- C. 4G has stronger encryption than 5G
- D. IoT devices cannot process IP-based traffic

---

**23.** A technician needs to explain why mmWave 5G, despite its speed, is not practical for wide-area rural coverage. What is the best explanation?

- A. mmWave requires a paid subscription unavailable in rural areas
- B. mmWave signals are limited to about half a mile and are easily blocked by obstructions
- C. mmWave only operates below 1 GHz
- D. mmWave is incompatible with eMBB service

---

**24.** A user wants to share their smartphone's cellular connection with a laptop, but the smartphone doesn't support acting as a full hotspot. What term describes connecting the laptop to that phone anyway?

- A. Tethering
- B. Sideloading
- C. Provisioning
- D. Roaming

---

**25.** A network administrator wants a phone's airplane mode to disable cellular and Wi-Fi but leave Bluetooth active every time it's triggered. What is the correct approach on newer iOS versions?

- A. This configuration is not possible on iOS
- B. Configure airplane mode that way once, then toggle it off; it will restore that configuration the next time it's enabled
- C. Disable Bluetooth permanently in Settings instead
- D. Use a third-party app, since iOS airplane mode always disables all radios equally

---

**26.** Why does a smartphone need a separate baseband OS rather than having the primary OS (iOS/Android) talk directly to the radio hardware?

- A. The primary OS lacks the processing power to manage radio signals
- B. It reduces flexibility and increases development costs
- C. It isolates radio hardware differences so the primary OS doesn't need to know how to talk to every possible chipset
- D. Carriers require it for billing purposes

---

**27.** Why is manually updating an Android device's baseband firmware considered risky?

- A. It requires a factory reset every time
- B. Interrupting the update process can brick the phone, and it typically voids the warranty
- C. It disables the SIM OS permanently
- D. It is illegal in most jurisdictions

---

**28.** A user reports their Android phone experiences intermittent dropped calls and poor signal after installing a third-party firmware update. Which subsystem was most likely affected?

- A. The primary OS (Android)
- B. The baseband OS
- C. The SIM OS
- D. The location services daemon

---

**29.** A user has a MEID displayed in their phone's settings. Based on this chapter, what can be inferred about the first 14 digits of that value?

- A. They are identical to the first 14 digits of the device's IMEI
- B. They represent the carrier's MNC
- C. They change every time the SIM is swapped
- D. They are unrelated to any other identifier

---

**30.** A user wants faster, free Internet on their phone instead of using their data plan, and they're within range of a known secured network. What should they do?

- A. Enable Bluetooth tethering
- B. Connect to the Wi-Fi network and satisfy its security requirements
- C. Switch to airplane mode
- D. Enable a mobile hotspot on their own device

---

**31.** A technician is helping a client configure a VPN on an iPhone and wants the fastest, most secure protocol available, understanding it may have narrower OS compatibility. Which should they choose?

- A. L2TP
- B. IPsec alone
- C. IKEv2
- D. PPTP

---

**32.** On Android, a VPN profile uses IKEv2/IPsec MSCHAPv2. Which of the three terms in that string is the authentication protocol?

- A. IKEv2
- B. IPsec
- C. MSCHAPv2
- D. None of the three handles authentication

---

**33.** Why is a PSK-based L2TP/IPsec VPN generally considered less secure than an RSA-based one?

- A. PSK does not encrypt any traffic at all
- B. PSK uses a server-generated shared key vulnerable to brute-force attacks, while RSA uses stronger asymmetric keys
- C. PSK only works over Wi-Fi, never cellular
- D. PSK requires a dedicated RSA server to function

---

**34.** A corporate network exclusively uses OpenVPN for remote access. What must an iOS or Android user do to connect?

- A. Nothing — both platforms support OpenVPN natively
- B. Install a third-party app such as OpenVPN Connect
- C. Downgrade to L2TP instead
- D. Use only a desktop computer, since mobile devices cannot use OpenVPN

---

**35.** Two Bluetooth devices pair successfully, but no file transfer is possible between them afterward. What is the most likely explanation?

- A. The Bluetooth pairing itself must have actually failed
- B. The devices are using different IEEE 802.15 subversions that cannot coexist
- C. One of the devices lacks the software service needed to support file transfers, even though the base pairing succeeded
- D. File transfer always requires a third RTOS not present on either device

---

**36.** What underlying wireless technology does Apple's AirDrop rely on for discovery and transfer between iOS devices?

- A. NFC
- B. Bluetooth Low Energy (BLE)
- C. Wi-Fi Direct exclusively
- D. Classic Bluetooth EDR only

---

**37.** A user's iPad shows strong GPS accuracy outdoors but noticeably worse location accuracy indoors, even with GPS enabled. What additional signals does the chapter say a device can use indoors to improve that accuracy?

- A. Cellular location services only
- B. Wi-Fi and Bluetooth signals
- C. IMEI triangulation
- D. eSIM roaming data

---

**38.** Why does cellular location service typically provide less precise positioning than GPS?

- A. It relies on triangulation from cell towers rather than satellites, which is inherently less exact
- B. It requires a paid GPS subscription that most users decline
- C. It only functions indoors
- D. It uses the same L1/L2 frequencies as GPS, causing interference

---

**39.** A company issues corporate-owned smartphones to its sales team, restricted to business use only. If a device is lost, what is generally the most appropriate MDM action?

- A. Do nothing until the device is found
- B. Fully wipe the device remotely, since it contains no personal user data
- C. Contact the user's ISP to cancel their personal data plan
- D. Disable only the SIM OS remotely

---

**40.** An employee enrolls a personal phone in a BYOD program. If that phone is lost, why would a full MDM wipe typically be avoided in favor of a MAM-based selective wipe?

- A. MDM cannot access BYOD devices at all
- B. A full wipe would destroy the user's personal photos, apps, and data along with corporate data
- C. MAM is required by law for all BYOD devices
- D. Selective wipes are faster to execute over cellular

---

## Section 3: Advanced/Troubleshooting (Q41–60)

**41.** A user configuring a corporate email account manually enters port 587 for outgoing mail. Which protocol and security combination does that port number represent?

- A. SMTP with SSL
- B. SMTP with TLS
- C. IMAP with SSL/TLS
- D. POP with SSL/TLS

---

**42.** A user's mobile email client is set to POP3, configured to delete messages from the server after download. The same user later checks email from a second device and finds many messages missing. What's the most likely explanation, based on this chapter?

- A. The mail server is down
- B. POP3 downloaded and deleted those messages from the server on the first device, so they're no longer available to the second
- C. IMAP overwrote the POP3 configuration automatically
- D. The second device is using the wrong MCC

---

**43.** A technician troubleshooting a mobile client's failed secure IMAP connection manually opens a terminal and runs `openssl s_client -connect imap.example.com:993`. If the handshake and certificate exchange succeed, what does that tell the technician about the source of the original problem?

- A. The mail server and secure port are reachable, so the issue likely lies in the phone's mail app configuration rather than the server itself
- B. The problem must be a firewall blocking port 25
- C. IMAP is fundamentally incompatible with mobile clients
- D. The server does not actually support SSL/TLS

---

**44.** A user wants to send mail over SMTP secured with STARTTLS rather than a dedicated SSL port. Which statement correctly describes what STARTTLS does?

- A. It moves SMTP traffic to port 465 permanently
- B. It secures the existing protocol's default port without changing the port number itself
- C. It only works with IMAP, never SMTP
- D. It removes the need for any encryption at all

---

**45.** A field technician's iPhone shows the Personal Hotspot option missing from Settings entirely. Based on this chapter, what is the most likely cause and next step?

- A. The device is defective and needs replacement
- B. The wireless plan doesn't allow hotspot use; the technician should check Settings → Cellular → Set Up Personal Hotspot instead
- C. Airplane mode is silently blocking the hotspot feature
- D. iOS versions before 18 never included hotspot functionality

---

**46.** An Android user notices that after enabling Data Saver, most apps only load images and updates while connected to Wi-Fi. What does this behavior confirm about Data Saver's function?

- A. It disables Wi-Fi entirely
- B. It forces background app data to Wi-Fi-only unless an app is individually exempted
- C. It permanently disables cellular data
- D. It only affects the Settings app itself

---

**47.** A user configuring a VPN reports that IKEv2 is unavailable on their older router-based VPN server, but L2TP is supported. Based on this chapter's description, what tradeoff are they accepting by using L2TP instead of IKEv2?

- A. L2TP offers broader OS compatibility but is not the fastest or most secure of the iOS VPN options
- B. L2TP is faster than IKEv2 but far less secure
- C. L2TP cannot function over cellular connections
- D. L2TP requires a certificate while IKEv2 does not

---

**48.** A corporate security team wants to prevent brute-force key-guessing attacks against their Android VPN's authentication method. Which configuration choice should they avoid?

- A. IKEv2/IPsec MSCHAPv2
- B. L2TP/IPsec with RSA
- C. L2TP/IPsec with PSK
- D. OpenVPN via a third-party client

---

**49.** A user reports their phone shows "connected" to their home Wi-Fi network, but apps are still consuming cellular data heavily. Which setting, if accidentally left enabled, would explain apps bypassing the Wi-Fi connection for a specific app?

- A. Airplane mode
- B. A per-app cellular data toggle left on for that app
- C. STARTTLS
- D. Low Data Mode

---

**50.** A traveler crosses into a new country and their phone fails to connect to any local tower despite showing full signal bars at times. Their carrier support suggests a manual PRL update. What does updating the PRL actually correct?

- A. The device's baseband firmware version
- B. The phone's reference list for connecting to the correct cell tower while roaming
- C. The IMEI blacklist status
- D. The SIM's ICCID

---

**51.** An enterprise wants remote employees to be able to wipe corporate apps and their data from a lost BYOD phone without touching the employee's personal photos or contacts. Which technology directly provides that capability?

- A. MDM alone
- B. MAM
- C. GNSS
- D. STARTTLS

---

**52.** A user disables Location Services entirely on their iPhone. Which single app, per this chapter, continues to function despite the master toggle being off?

- A. Maps
- B. Find My iPhone
- C. Weather
- D. Camera

---

**53.** A hiker using a standalone GPS device gets a location fix using only three visible satellites. What capability do they lose compared to having a fourth satellite in view?

- A. Any location accuracy at all
- B. Elevation data
- C. Access to the P code
- D. The ability to use SPS instead of PPS

---

**54.** A government contractor requires centimeter-level GPS accuracy for a surveying project and has secured DoD authorization. Which GPS service tier and frequency are they most likely using?

- A. SPS on L1 with C/A code
- B. PPS on L2 with encrypted P (Y) code
- C. SPS on L2 with C/A code
- D. eMBB on the L1 band

---

**55.** A network admin needs to determine whether a lost corporate phone's location can still be tracked despite having no cellular signal in a remote area, assuming GPS hardware is functional. What is the most accurate assessment?

- A. GPS will still function, since it relies on satellites rather than cell towers
- B. Neither GPS nor cellular location will work without a cell signal
- C. Cellular location services will work fine without cellular signal
- D. Only Wi-Fi-based positioning will work in this scenario

---

**56.** A user wants their Windows 11 laptop and desktop to always show identical desktop backgrounds, accessibility settings, and installed apps, syncing automatically through their Microsoft account. Which feature should they enable?

- A. iCloud
- B. Windows Backup (via Microsoft 365 subscription)
- C. MAM
- D. STARTTLS

---

**57.** A user wants to completely stop Windows Backup sync across all of their computers and remove any stored settings from Microsoft's cloud. What is the correct final step in that process?

- A. Uninstall OneDrive from each computer
- B. Visit account.microsoft.com/devices and select Clear Stored Settings
- C. Disable Bluetooth on each computer
- D. Delete the Microsoft account entirely

---

**58.** A small business wants the most cost-effective plan that still includes a full 2 TB premium storage tier. Comparing this chapter's provider table, which two services tie for the lowest annual premium cost while offering 2 TB?

- A. Dropbox and Box
- B. Google Drive and Apple iCloud
- C. Microsoft OneDrive and Box
- D. Dropbox and Google Drive

---

**59.** A user is troubleshooting why their iPhone's Calendar app isn't syncing new events to their laptop, even though Mail syncs correctly for the same account. Based on this chapter, what is the most likely explanation?

- A. Calendar and Mail always share the exact same sync toggle with no way to separate them
- B. Calendar sync must be separately enabled under Settings → Apps → Calendar → Calendar Accounts, distinct from the Mail account's own toggle
- C. iOS does not support calendar syncing under any circumstances
- D. The device needs to be in airplane mode to sync calendars

---

**60.** A user wants to force an immediate sync of new email rather than waiting for the normal automatic interval. What is the correct terminology for this manual action on iOS versus Android, respectively?

- A. "Fetch New Data" on iOS; "Sync Now" on Android
- B. "Sync Now" on iOS; "Fetch New Data" on Android
- C. "Force Refresh" on both platforms
- D. "Pull to Update" on iOS; "Manual Sync" on Android

---

## Answer Key & Explanations

**1. A — 1979.** The chapter states 1G, the original analog cellular standard, launched in 1979, with 2G following commercially in 1991.

**2. B — 64 Kbps.** After several enhancements, 2G reached a maximum data rate of 64 Kbps — enough for text and basic email, but very slow by later standards.

**3. C — Qualcomm.** CDMA was developed by Qualcomm and, unlike GSM's global reach, was only available in the United States.

**4. B — 200 Kbps.** 3G specified a minimum download rate of 200 Kbps at its 1998 launch; some carriers later claimed faster speeds under 3.5G enhancements.

**5. B — WiMAX and LTE.** These two standards competed in early 4G; carriers ultimately backed LTE, and WiMAX lost out.

**6. C — 300 Mbps.** The chapter lists 4G LTE's theoretical maximum as 300 Mbps download and 75 Mbps upload, far above typical real-world speeds of 10–20 Mbps down.

**7. C — 20 Gbps.** 5G's theoretical peak download capacity is 20 Gbps, though real-world average speeds are much lower, around 490 Mbps.

**8. C — 24 GHz–86 GHz.** This is the mmWave range specifically; standard 5G LTE frequencies use the lower 600 MHz–6 GHz range shared with 4G.

**9. B — URLLC.** Ultra-Reliable Low-Latency Communications targets autonomous vehicles and industrial applications; eMBB serves phones, and mMTC serves IoT sensors.

**10. C — Wi-Fi is turned off.** On Android, enabling the mobile hotspot automatically disables the device's own Wi-Fi connection.

**11. C — 15.** The IMEI is a 15-digit serial number unique to each physical device.

**12. A — *#06#.** Dialing this code displays the device's IMEI on most phones without needing to place a call.

**13. B — The first 14.** The MEID is identical to the first 14 digits of a device's IMEI, serving as an alternate serial format.

**14. B — MCC, MNC, MSIN.** The IMSI is composed of the Mobile Country Code, Mobile Network Code, and Mobile Station Identifier Number.

**15. C — 19–20.** The ICCID, which uniquely identifies a physical SIM card globally, runs 19 to 20 digits long.

**16. B — 25.** TCP port 25 is SMTP's unencrypted default port, used for sending mail.

**17. D — 995.** POP with SSL/TLS uses port 995, distinct from its unencrypted default of port 110.

**18. C — 993.** IMAP with SSL/TLS uses port 993, distinct from its unencrypted default of port 143.

**19. C — 31.** The U.S. currently manages 31 total GPS satellites, 24 active with the remainder as backups.

**20. B — 5 GB.** Apple iCloud's default free tier is 5 GB, expandable through paid iCloud+ tiers.

**21. B — GSM and CDMA are incompatible cellular standards.** The chapter explicitly notes that a CDMA phone (Verizon) couldn't switch to a GSM carrier (AT&T) because the two standards never interoperated.

**22. B — 4G throughput and latency are sufficient, and the hardware is cheaper.** Many IoT systems stick with 4G precisely because its performance is adequate for sensor-class workloads at lower hardware cost than 5G.

**23. B — mmWave signals are limited to about half a mile and are easily blocked by obstructions.** This short range and obstruction sensitivity make mmWave impractical for broad rural coverage despite its speed.

**24. A — Tethering.** Tethering describes connecting a device to a mobile hotspot (or sharing a cellular connection) even when the sharing device doesn't support acting as a full standalone hotspot.

**25. B — Configure airplane mode that way once, then toggle it off; it will restore that configuration the next time it's enabled.** Newer iOS versions remember the last airplane-mode radio configuration and reapply it automatically.

**26. C — It isolates radio hardware differences so the primary OS doesn't need to know how to talk to every possible chipset.** The baseband OS acts as a translation layer, letting the primary OS avoid needing native support for every radio chipset on the market.

**27. B — Interrupting the update process can brick the phone, and it typically voids the warranty.** Both risks are explicitly listed among the chapter's three warnings for manual baseband updates.

**28. B — The baseband OS.** Since the baseband OS manages all wireless communication, a firmware update to it is the most likely source of new call and signal issues.

**29. A — They are identical to the first 14 digits of the device's IMEI.** This relationship is defined directly in the chapter — MEID duplicates the IMEI's first 14 digits.

**30. B — Connect to the Wi-Fi network and satisfy its security requirements.** Wi-Fi offers faster, free connectivity compared to cellular whenever a known secured network is in range.

**31. C — IKEv2.** The chapter identifies IKEv2 as the fastest and most secure of iOS's three VPN protocol options, at the cost of narrower OS support than L2TP.

**32. C — MSCHAPv2.** In that protocol stack, IKEv2 is the connection protocol, IPsec handles tunneling/encryption, and MS-CHAPv2 is specifically the authentication protocol.

**33. B — PSK uses a server-generated shared key vulnerable to brute-force attacks, while RSA uses stronger asymmetric keys.** This is exactly the distinction the chapter draws between the two L2TP/IPsec authentication options.

**34. B — Install a third-party app such as OpenVPN Connect.** Neither iOS nor Android natively supports OpenVPN; both require a dedicated third-party client from their respective app stores.

**35. C — One of the devices lacks the software service needed to support file transfers, even though the base pairing succeeded.** The chapter explicitly separates the Bluetooth handshake from the manufacturer-decided software services that determine actual transfer capability.

**36. B — Bluetooth Low Energy (BLE).** AirDrop uses BLE for its discovery and transfer process between nearby iOS devices.

**37. B — Wi-Fi and Bluetooth signals.** Indoors, where satellite visibility is weak, the chapter notes both Wi-Fi and Bluetooth can contribute highly accurate positioning data.

**38. A — It relies on triangulation from cell towers rather than satellites, which is inherently less exact.** Cellular location services' tower-based triangulation is described as roughly 100 meters accurate versus GPS's roughly 10 meters.

**39. B — Fully wipe the device remotely, since it contains no personal user data.** Corporate-owned devices restricted to business use don't carry the personal-data concern that makes full wipes risky on BYOD devices, making a full remote wipe appropriate.

**40. B — A full wipe would destroy the user's personal photos, apps, and data along with corporate data.** This is exactly why the chapter recommends MAM's selective, corporate-data-only wipe for BYOD scenarios, reserving a full wipe as a last resort.

**41. B — SMTP with TLS.** Port 587 specifically corresponds to SMTP secured with TLS, distinct from port 465's SMTP with SSL.

**42. B — POP3 downloaded and deleted those messages from the server on the first device, so they're no longer available to the second.** This is the classic POP multiple-device confusion the chapter warns about when the server-copy option isn't configured.

**43. A — The mail server and secure port are reachable, so the issue likely lies in the phone's mail app configuration rather than the server itself.** A successful manual handshake isolates the server/network as functioning, pointing troubleshooting back toward the client-side configuration.

**44. B — It secures the existing protocol's default port without changing the port number itself.** STARTTLS upgrades an existing connection to encrypted status without altering SMTP, POP, or IMAP's assigned port numbers.

**45. B — The wireless plan doesn't allow hotspot use; the technician should check Settings → Cellular → Set Up Personal Hotspot instead.** The chapter specifically notes that a missing Personal Hotspot menu item means the plan doesn't support it, and directs users to the Cellular settings path instead.

**46. B — It forces background app data to Wi-Fi-only unless an app is individually exempted.** This is precisely how Android's Data Saver setting is described in the chapter.

**47. A — L2TP offers broader OS compatibility but is not the fastest or most secure of the iOS VPN options.** The chapter frames IKEv2 as fastest/most secure with narrower support, implying L2TP trades some speed and security for wider compatibility.

**48. C — L2TP/IPsec with PSK.** PSK is specifically called out as vulnerable to brute-force attacks and unsuitable for highly secure environments, unlike the more secure RSA option.

**49. B — A per-app cellular data toggle left on for that app.** iOS and Android both allow per-app cellular data permissions independent of the overall Wi-Fi connection status, which would explain one app bypassing Wi-Fi.

**50. B — The phone's reference list for connecting to the correct cell tower while roaming.** This is the defined function of a PRL — distinct from the baseband firmware (RTOS) or the PRI's network-specific configuration settings.

**51. B — MAM.** Mobile application management specifically handles remote install/delete/wipe of corporate apps and their data without touching personal content, which is exactly this scenario's requirement.

**52. B — Find My iPhone.** The chapter specifically states that disabling the Location Services master toggle blocks every app except Find My iPhone.

**53. B — Elevation data.** Three satellites yield a location fix alone; a fourth satellite is needed to add elevation to that fix.

**54. B — PPS on L2 with encrypted P (Y) code.** Precise Positioning Service requires DoD authorization, delivers centimeter-level accuracy, and transmits its encrypted P code (called Y code) on the L2 frequency.

**55. A — GPS will still function, since it relies on satellites rather than cell towers.** GPS is independent of cellular signal, while cellular location services specifically require tower reception to function at all.

**56. B — Windows Backup (via Microsoft 365 subscription).** This Microsoft feature syncs desktop settings, apps, and preferences across PCs tied to the same Microsoft account.

**57. B — Visit account.microsoft.com/devices and select Clear Stored Settings.** This is the final documented step after disabling sync on all individual machines.

**58. B — Google Drive and Apple iCloud.** Both are listed at $120/year for their 2 TB premium tier, tied for the lowest cost among providers offering that capacity.

**59. B — Calendar sync must be separately enabled under Settings → Apps → Calendar → Calendar Accounts, distinct from the Mail account's own toggle.** The chapter treats Calendar and Contacts sync as configured independently from the Mail account's sync settings.

**60. A — "Fetch New Data" on iOS; "Sync Now" on Android.** These are the platform-specific terms the chapter gives for manually forcing a sync.
