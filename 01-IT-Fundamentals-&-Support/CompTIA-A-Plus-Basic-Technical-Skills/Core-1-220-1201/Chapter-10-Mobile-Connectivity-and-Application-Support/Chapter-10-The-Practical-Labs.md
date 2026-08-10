### 🛠️ Lab 1: The Cover Identity Check — Reading Your Device's Cellular Identifiers

**Objective:** Build hands-on fluency with the identifiers a mobile device uses to prove its identity to a cellular network — IMEI/MEID, SIM presence, and carrier-reported network details — by pulling them directly from a real phone, and connect each one back to this chapter's identifier definitions.

**Environment/Tools Needed:** Your own iPhone or Android smartphone with an active or previously active SIM/eSIM (no computer or admin rights required — this lab runs entirely on the phone itself).

**Step-by-Step Instructions:**

1. Open the Phone app's dialer and enter `*#06#`. Do not press call — on most devices this code triggers automatically and displays the device's IMEI (and, on dual-SIM phones, a second IMEI for the second SIM slot). Record the IMEI(s) shown.
2. On iOS, navigate to Settings → General → About. On Android, navigate to Settings → About Phone. Scroll through this screen and record any of the following fields you can find: IMEI, MEID, ICCID, serial number, and model number.
3. Compare the IMEI recorded in step 1 against the IMEI shown in step 2. They should match exactly — this confirms the dial-code shortcut and the Settings menu are reading from the same underlying identifier.
4. If your device shows an ICCID, count its digits and confirm it falls within this chapter's expected range of 19–20 digits. If your device shows a MEID, confirm it is 14 digits — the length you'd expect from "the first 14 digits of the IMEI."
5. Still in Settings, locate your carrier name (iOS: Settings → Cellular; Android: Settings → About Phone → SIM Status or Settings → Connections → SIM Manager). Based on this chapter's discussion of GSM versus CDMA carrier history in the United States, write down whether your current carrier's network lineage traces back to the GSM camp (AT&T, T-Mobile) or the CDMA camp (Verizon, and the former Sprint, now part of T-Mobile).
6. Write two to three sentences explaining, in your own words, why a phone's IMEI stays fixed to the physical hardware while the SIM (or eSIM profile) can be swapped to change carriers — and what that implies about which identifier a carrier blacklists when a phone is reported stolen.

**Expected Result:** A recorded IMEI (confirmed identical from both the dial code and the Settings menu), any additional identifiers your specific device exposes (ICCID, MEID, serial number), a determination of your carrier's GSM/CDMA lineage, and a short written explanation connecting the IMEI to the physical device versus the SIM to the carrier account.

---

### 🛠️ Lab 2: Tapping the Cable Lines — Verifying Secure Mail Ports with OpenSSL

**Objective:** Reinforce the mail protocol port table from this chapter — including which ports are secured with SSL/TLS and which are not — by manually opening a TLS connection to a real commercial mail server's secure port from the command line, and observing the TLS handshake succeed.

**Environment/Tools Needed:** A Windows 11, macOS, or Linux computer with a terminal (Command Prompt, PowerShell, Terminal.app, or a Linux shell) and OpenSSL installed. macOS and most Linux distributions include OpenSSL by default; on Windows 11, OpenSSL ships alongside Git for Windows, or can be installed standalone.

**Step-by-Step Instructions:**

1. Open a terminal window. Confirm OpenSSL is available by running `openssl version`. You should see a version string printed back (for example, `OpenSSL 3.x.x`).
2. Using this chapter's mail server table, run the following command to open a secure IMAP connection to Gmail's server on its secure port:
   ```
   openssl s_client -connect imap.gmail.com:993
   ```
3. Watch the output. You should see a TLS handshake take place, followed by certificate details (issuer, subject, validity dates) and, near the very end, a line beginning with `* OK` — this is the IMAP server's own greeting banner, confirming the encrypted session is live even though you haven't logged in.
4. Type `a1 LOGOUT` and press Enter to close the session cleanly, or press `Ctrl+C` to terminate the connection.
5. Repeat step 2, but this time connect to the SMTP-with-TLS port instead: `openssl s_client -connect smtp.gmail.com:587 -starttls smtp`. Note the `-starttls smtp` flag — port 587 does not begin encrypted; the client has to explicitly request an upgrade to TLS mid-connection, which is exactly the STARTTLS behavior this chapter describes.
6. Compare the two commands from steps 2 and 5. Write one to two sentences explaining why port 993 could be reached directly with `s_client -connect`, while port 587 needed the extra `-starttls smtp` flag to succeed.
7. (Optional) Repeat step 2 against one additional provider from this chapter's server table, such as `imap.mail.yahoo.com:993` or `outlook.office365.com:993`, and confirm you get a similar successful handshake and greeting banner.
8. Write two to three sentences explaining, based on this chapter, why an administrator troubleshooting a mobile client's failed email setup might use a command like this on a laptop to isolate whether the problem is the mail server/port itself versus something specific to the phone's mail app configuration.

**Expected Result:** A successful TLS handshake and certificate dump against at least one provider's secure IMAP port (993), a successful STARTTLS upgrade against a provider's secure SMTP port (587), and a short written explanation of the difference between an implicitly encrypted port and a STARTTLS-upgraded one, tied back to this chapter's port tables.

---

### 🛠️ Lab 3: The Dead Drop Handshake — Bluetooth Pairing and File Transfer

**Objective:** Walk through the full five-step Bluetooth connectivity sequence from this chapter — enable Bluetooth, enable pairing, find a device, enter the PIN, test connectivity — by pairing a real smartphone with a Windows 11 laptop and transferring a file in both directions.

**Environment/Tools Needed:** A Windows 11 PC with Bluetooth hardware and administrator rights, and an Android or iOS smartphone with Bluetooth capability. Both devices should be within a few feet of each other.

**Step-by-Step Instructions:**

1. On the Windows 11 laptop, open Settings → Bluetooth & Devices and toggle Bluetooth on. This satisfies step one of the chapter's sequence — enable Bluetooth — on the non-mobile side of the pairing.
2. On the smartphone, enable Bluetooth (Android: Settings → Connections → Bluetooth; iOS: Settings → Bluetooth) and confirm the device is scanning for nearby devices — on most phones, having the Bluetooth settings screen open already satisfies "enable pairing" and "find a device for pairing" simultaneously, since the phone actively searches while the screen is open.
3. On the laptop, click **Add Device** in the Bluetooth & Devices settings, and select Bluetooth as the device type, putting the laptop into discoverable mode.
4. On the smartphone's list of available devices, locate and tap the laptop's device name to begin pairing.
5. A passkey will appear on both the phone and the laptop. Confirm the two codes match exactly — this is the PIN-entry step from this chapter's sequence — and accept the pairing on both devices.
6. Once paired, confirm connectivity (the chapter's final step, "test connectivity") by sending a small file. On the laptop, go to Settings → Bluetooth & Devices, scroll to **Send Or Receive Files Via Bluetooth**, click it, choose **Send Files**, select your paired phone as the target, and browse to a small test file (a short text file works well). On the phone, accept the incoming transfer when prompted.
7. Confirm the laptop reports the transfer as complete, and locate the received file on the phone (Android: My Files → Documents → Download folder by default; iOS: the file will typically arrive via the app you accepted it into, such as Files).
8. Now reverse the transfer: on the laptop, return to **Send Or Receive Files Via Bluetooth** and choose **Receive Files** this time. On the phone, locate the same test file, use its native Share option, choose Bluetooth as the sharing method, and select the laptop as the destination. Confirm the laptop receives the file and prompts you for a save location.
9. Write two to three sentences explaining, based on this chapter, why a successful pairing (step 5) does not automatically guarantee that file transfer (step 6 onward) will work, and what factor — beyond the Bluetooth handshake itself — actually determines whether two paired devices can exchange files.

**Expected Result:** A completed pairing between the smartphone and the Windows 11 laptop with matching confirmed passkeys, a successfully transferred file from laptop to phone, a successfully transferred file from phone to laptop, and a short written explanation distinguishing the pairing handshake from the software-service negotiation that determines file-transfer capability.
