### 🛠️ Lab 1: The Concierge's Directory Check — DNS Record Lookup & Resolution

**Objective:** Build hands-on fluency with DNS record types and the resolution/caching process by directly querying DNS for different record types and observing how caching changes subsequent lookups.

**Environment/Tools Needed:** A Windows 11 PC (physical or VM) with internet access, and a Command Prompt or PowerShell window (no admin rights required).

**Step-by-Step Instructions:**

1. Open **Start**, type `cmd` or `powershell`, and open a normal (non-admin) window.
2. Run `nslookup wiley.com` and record the A record (IPv4 address) returned.
3. Run `nslookup -type=MX wiley.com` (or any domain of your choice) and record the mail exchange server(s) listed, along with their priority values if shown.
4. Run `nslookup -type=TXT google.com` and record at least one TXT record returned. If you can identify anything that looks like an SPF entry (it will typically start with `v=spf1`), note it — this is the exact spam-management mechanism covered in this chapter.
5. Run `nslookup -type=AAAA google.com` and record the IPv6 (quad-A) address returned, comparing its format to the A record's IPv4 format.
6. Run `ipconfig /displaydns` and scroll through the output looking for the domains you just queried. Record whether they appear in your local resolver cache and note any TTL (time-to-live) values shown.
7. Run `ipconfig /flushdns` to clear your local cache, then immediately re-run your `nslookup wiley.com` query from step 2. Note whether the response feels different, and write one to two sentences explaining — based on this chapter's DNS caching explanation — why a freshly flushed cache can mean a slightly slower first lookup.

**Expected Result:** Recorded A, MX, TXT, and AAAA records for real domains, confirmation that resolved names appear in the local DNS cache via `ipconfig /displaydns`, and a short written explanation connecting cache flushing to resolution speed.

---

### 🛠️ Lab 2: The Front Desk's Access Log — AAA Accounting via Event Viewer

**Objective:** Reinforce the "accounting" leg of the AAA framework by inspecting real Windows authentication logs and distinguishing successful logons from failed ones.

**Environment/Tools Needed:** A Windows 11 PC with local administrator rights and access to Event Viewer.

**Step-by-Step Instructions:**

1. Open **Start**, type `Event Viewer`, and launch it.
2. In the left pane, navigate to **Windows Logs > Security**.
3. In the right-hand **Actions** pane, click **Filter Current Log**, enter `4624` in the **Event IDs** field, and click **OK**. Event ID 4624 represents a successful logon.
4. Record the timestamp, account name, and logon type of at least three recent `4624` entries.
5. Repeat the filter process, this time entering `4625` (a failed logon attempt). If no results appear, lock your screen (Windows key + L) and deliberately enter an incorrect password once before logging back in correctly, then re-run the filter.
6. Record the timestamp and account name of the failed logon entry, and compare its details to the successful entries from step 4.
7. Open your web browser, press **Ctrl+H** (works in both Edge and Chrome) to view your browsing history, and note that this is a completely separate accounting trail from the Windows Security log — one tracks system logons, the other tracks web activity.
8. Write two to three sentences explaining, based on this chapter, how the Security log and browser history both serve AAA's "accounting" function, and why a proxy server (also covered in this chapter) might retain a browsing record even after a user clears their local history.

**Expected Result:** A recorded set of successful logon events (Event ID 4624) with timestamps and account names, at least one recorded failed logon event (Event ID 4625), browser history reviewed, and a short written comparison tying both logs back to AAA's accounting principle.

---

### 🛠️ Lab 3: Configuring the Concierge's Assistant — Windows 11 Proxy Server Setup

**Objective:** Get hands-on with Windows 11's native proxy client to reinforce how proxy servers are configured, verified, and removed, connecting this chapter's proxy-server concepts to a real Windows setting.

**Environment/Tools Needed:** A Windows 11 PC (physical or VM), and PowerShell (no admin rights required for the registry read in step 5).

**Step-by-Step Instructions:**

1. Open **Settings** by clicking **Start**, then **Settings**.
2. From the left-side navigation menu, choose **Network & Internet**.
3. Click **Proxy** in the list of options.
4. Under **Manual proxy setup**, click **Set up** next to **Use a proxy server**. Enter a placeholder address and port (for example, `127.0.0.1` and port `8080`, since no real proxy needs to be listening for this exercise), leave **Don't use the proxy server for local (intranet) addresses** checked, and click **Save**.
5. Open PowerShell and run `Get-ItemProperty "HKCU:\Software\Microsoft\Windows\CurrentVersion\Internet Settings"` and record the values of `ProxyEnable` and `ProxyServer`. Confirm that `ProxyEnable` now reads `1` and that `ProxyServer` matches what you entered in step 4.
6. Open a web browser and attempt to load any website. Since no real proxy is listening at the placeholder address, confirm that the page fails to load or the browser reports a connection/proxy error — this is expected and still confirms the client is correctly attempting to route traffic through the configured proxy.
7. Return to the Proxy settings screen, toggle **Use a proxy server** back to **Off**, and click **Save**.
8. Re-run the PowerShell command from step 5 and confirm `ProxyEnable` now reads `0`, then reload the website from step 6 and confirm it now loads normally.
9. Write two to three sentences explaining, based on this chapter, which of the three proxy-server benefits (caching, content filtering, or anonymization) this configuration would provide if it were pointed at a real, functioning proxy server instead of a placeholder address.

**Expected Result:** A proxy server address configured through the Windows 11 Settings app, confirmation via PowerShell registry query that `ProxyEnable`/`ProxyServer` reflect the change, an observed connection failure while the placeholder proxy is active, successful removal of the configuration, and a short written explanation of the proxy benefit that configuration would provide.
