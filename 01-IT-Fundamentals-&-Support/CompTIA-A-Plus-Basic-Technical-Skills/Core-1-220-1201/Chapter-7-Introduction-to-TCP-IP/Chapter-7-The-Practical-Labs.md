### 🛠️ Lab 1: Staffing the Counters — Port and Protocol Identification

**Objective:** Build hands-on fluency with TCP/IP ports and protocols by inspecting real network connections on your own machine and matching live traffic back to the service counters covered in this chapter.

**Environment/Tools Needed:** A Windows 11 PC (physical or VM) with internet access, PowerShell (no admin rights required), and a web browser.

**Step-by-Step Instructions:**

1. Open **Start**, type `powershell`, and open a normal (non-admin) PowerShell window.
2. Run `Get-NetTCPConnection | Where-Object State -eq "Established" | Select-Object LocalAddress, LocalPort, RemoteAddress, RemotePort, State` and record at least five active connections along with their remote ports.
3. For each remote port you recorded, look it up against this chapter's port table and identify the protocol/service it corresponds to (e.g., a remote port of 443 means an HTTPS connection). If a port isn't in the chapter's list, note that too — not every connection will map to a named A+ objective protocol.
4. Open a web browser and visit any `http://` (not `https://`) site you can find, or use `http://neverssl.com`, which is designed for exactly this purpose. Immediately after loading it, run `Get-NetTCPConnection | Where-Object RemotePort -eq 80` and confirm you can see the live plaintext HTTP connection.
5. Now visit any standard `https://` website and run `Get-NetTCPConnection | Where-Object RemotePort -eq 443` to confirm the encrypted HTTPS connection appears instead.
6. Run `nslookup www.wiley.com` (or any domain of your choice) and record the IP address returned — this is DNS (port 53) resolving a hostname to an address in real time, the exact process described in this chapter's DNS section.
7. Write two to three sentences comparing what you observed on port 80 versus port 443, tying it back to the chapter's explanation of data in transit and why HTTPS matters for sensitive information.

**Expected Result:** A recorded list of live TCP connections mapped to their corresponding chapter protocols, confirmation of both an HTTP (port 80) and HTTPS (port 443) connection captured live, a resolved DNS lookup, and a short written comparison of plaintext vs. encrypted transmission.