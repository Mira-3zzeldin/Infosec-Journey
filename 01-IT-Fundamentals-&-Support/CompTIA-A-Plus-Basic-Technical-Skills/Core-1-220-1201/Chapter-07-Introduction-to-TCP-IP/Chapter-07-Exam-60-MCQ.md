## Chapter 7: Introduction to TCP/IP | 60 Questions

> **Instructions:** Answer all questions before checking the Answer Key at the bottom of this file.

---

## SECTION 1: Questions 1–20 — Direct / Basic

**1.** Which two protocols is the TCP/IP suite specifically named after?

- A. TCP and UDP
- B. IP and ICMP
- C. TCP and IP
- D. HTTP and IP

---

**2.** How many layers does the DoD model have?

- A. Three
- B. Four
- C. Five
- D. Seven

---

**3.** Which DoD model layer combines the OSI Application, Presentation, and Session layers?

- A. Network Access
- B. Internet
- C. Host-to-Host
- D. Process/Application

---

**4.** Which protocol is responsible for delivering error messages and is used by the `ping` utility?

- A. ARP
- B. ICMP
- C. RARP
- D. IP

---

**5.** Which protocol resolves logical IP addresses into physical MAC addresses?

- A. RARP
- B. DNS
- C. ARP
- D. DHCP

---

**6.** Which of the following best describes UDP?

- A. Connection-oriented, uses a virtual circuit
- B. Connectionless, no delivery guarantee
- C. Connection-oriented, no delivery guarantee
- D. Connectionless, guarantees delivery

---

**7.** What is the combination of an IP address and a port number called?

- A. A handle
- B. A tunnel
- C. A socket
- D. A gateway

---

**8.** Which port range is designated as the "well-known ports"?

- A. 0–1023
- B. 1024–49151
- C. 49152–65535
- D. 0–65535

---

**9.** What port does FTP use for control and data connections?

- A. 20 and 21
- B. 22 and 23
- C. 80 and 443
- D. 67 and 68

---

**10.** Which port does SSH use?

- A. 21
- B. 22
- C. 23
- D. 25

---

**11.** What port does SMTP use?

- A. 25
- B. 53
- C. 110
- D. 143

---

**12.** What port(s) does DHCP use?

- A. 53
- B. 67, 68
- C. 80
- D. 389

---

**13.** How many bits make up an IPv4 address?

- A. 16
- B. 24
- C. 32
- D. 128

---

**14.** What term describes one of the four numbers in a dotted-decimal IPv4 address?

- A. Nibble
- B. Field
- C. Octet
- D. Segment

---

**15.** A Class A network's default subnet mask is which of the following?

- A. 255.0.0.0
- B. 255.255.0.0
- C. 255.255.255.0
- D. 255.255.255.128

---

**16.** Which first-octet range identifies a Class C address?

- A. 1–127
- B. 128–191
- C. 192–223
- D. 224–239

---

**17.** What is the private IP address range reserved for Class C-equivalent use?

- A. 10.0.0.0–10.255.255.255
- B. 172.16.0.0–172.31.255.255
- C. 192.168.0.0–192.168.255.255
- D. 169.254.0.0–169.254.255.255

---

**18.** What is the APIPA address range?

- A. 10.0.0.0/8
- B. 169.254.0.0/16
- C. 172.16.0.0/12
- D. 192.168.0.0/16

---

**19.** How many bits make up an IPv6 address?

- A. 32
- B. 64
- C. 96
- D. 128

---

**20.** What is the IPv6 equivalent of the IPv4 loopback address 127.0.0.1?

- A. FE80::
- B. FF00::
- C. ::1
- D. 2000::/3

---

## SECTION 2: Questions 21–40 — Intermediate / Conceptual

**21.** Why is TCP generally considered slower than UDP, even though the real-world difference is small?

- A. TCP uses a smaller port range
- B. TCP requires a virtual circuit and delivery acknowledgments
- C. TCP only works with IPv6
- D. TCP encrypts all traffic by default

---

**22.** A client needs to browse a secure website. On which port should the client's request be sent?

- A. 80
- B. 143
- C. 443
- D. 3389

---

**23.** Why is NetBIOS unable to function on its own across a routed network like the Internet?

- A. It operates at OSI Layer 5 and needs another protocol to handle Layer 4 and below
- B. It only works with IPv6
- C. It requires a public IP address
- D. It is a connectionless protocol

---

**24.** Which of the following correctly distinguishes IMAP4 from POP3?

- A. IMAP4 requires the client to download and then disconnect; POP3 stays connected
- B. IMAP4 allows multiple clients to stay synchronized with the same server-stored inbox; POP3 requires local download
- C. POP3 is more secure and has replaced IMAP4 in most installations
- D. IMAP4 cannot be used by smartphone email clients

---

**25.** A network administrator wants to reduce broadcast traffic and isolate an R&D team's computers from the rest of the office, using the same physical switches already in place. Which technology best fits this need?

- A. NAT
- B. VLAN
- C. APIPA
- D. RARP

---

**26.** What is the essential functional difference between a VLAN and a subnet?

- A. A VLAN works at Layer 3 with IP addresses; a subnet works at Layer 2 with MAC addresses
- B. A VLAN works at Layer 2 with MAC addresses via a switch; a subnet works at Layer 3 with IP addresses via a router
- C. They are functionally identical
- D. A subnet requires a switch; a VLAN requires a router

---

**27.** A host is configured to receive its address from a DHCP server, but no DHCP server is currently reachable. What address range will the host most likely self-assign?

- A. 10.0.0.0/8
- B. 127.0.0.0/8
- C. 169.254.0.0/16
- D. 192.168.0.0/16

---

**28.** Which of the following is a valid reason a network administrator would choose CIDR over default class-based subnet masks?

- A. CIDR requires no subnet mask at all
- B. CIDR allows subnet mask flexibility beyond the rigid class-based defaults
- C. CIDR is required for any network using private addresses
- D. CIDR only applies to IPv6

---

**29.** An administrator configures a NAT router so that dozens of internal private addresses all share one single public IP address. What is this specific variant of NAT called?

- A. Static NAT
- B. Dynamic NAT
- C. NAT Overload (PAT)
- D. Reverse NAT

---

**30.** Why can HTTPS no longer protect data once it is stored on a web server's disk?

- A. HTTPS only protects data in transit, not data at rest
- B. HTTPS certificates expire after storage
- C. HTTPS only works with FTP
- D. Servers automatically decrypt all stored data

---

**31.** An IPv6 address is written with two consecutive double colons, such as `2001::1ab4::5468`. Why is this address invalid?

- A. IPv6 addresses cannot contain hexadecimal digits
- B. The double colon can only be used once per address, or the number of zero-fields becomes ambiguous
- C. IPv6 addresses cannot exceed six fields
- D. IPv6 does not support shorthand notation

---

**32.** Which IPv6 address type delivers a message to the single nearest node among a group sharing the same address?

- A. Unicast
- B. Multicast
- C. Anycast
- D. Broadcast

---

**33.** A technician sees a packet capture showing an unencrypted IP header, source and destination addresses, and readable payload data. Which type of connection is most likely being observed?

- A. An HTTPS session
- B. An SSH session
- C. A plain HTTP session
- D. An IPSec tunnel-mode VPN

---

**34.** Which of the following correctly pairs an IPSec component protocol with its function?

- A. AH — encryption; ESP — data integrity
- B. AH — data integrity and origin verification; ESP — encryption
- C. AH — tunneling; ESP — authentication
- D. AH and ESP both perform identical functions

---

**35.** A remote employee connects to the corporate network using a VPN client, and their traffic is encrypted while the original IP header remains readable to routing infrastructure along the way. Which IPSec mode is in use?

- A. Transport mode
- B. Tunnel mode
- C. Bridge mode
- D. Relay mode

---

**36.** Why does an SSL/TLS VPN typically secure only a specific application rather than an entire network data stream?

- A. It operates at the Application layer (Layer 7), the same layer HTTPS uses
- B. It operates at the Network layer and only supports UDP
- C. SSL/TLS VPNs cannot encrypt any traffic
- D. SSL/TLS VPNs only work with IPv6

---

**37.** A company's Class A private network of 10.0.0.0/8 is far larger than needed. To subnet the network to support 15 divisions of about 3,000 hosts each, what is the minimum number of host bits required per division?

- A. 8 bits
- B. 10 bits
- C. 12 bits
- D. 16 bits

---

**38.** Which statement correctly describes the relationship between a hostname and a NetBIOS name?

- A. They are always identical strings
- B. A hostname is resolved via DNS and can work across the Internet; a NetBIOS name historically required WINS/LMHOSTS and could not
- C. NetBIOS names replaced hostnames entirely in modern Windows
- D. Hostnames only exist in IPv6 environments

---

**39.** An administrator wants a single VLAN to span two switches in two different physical office buildings, with all associated computers treated as one logical group regardless of location. Is this possible with VLANs?

- A. No, VLANs are strictly limited to a single physical switch
- B. Yes, VLANs can span multiple switches in different physical locations
- C. No, this requires subnetting instead
- D. Yes, but only using IPv6

---

**40.** A network engineer configures a subnet mask of 255.255.240.0. What is the correct CIDR slash notation for this mask?

- A. /16
- B. /20
- C. /24
- D. /28

---

## SECTION 3: Questions 41–60 — Advanced / Troubleshooting

**41.** A user reports they cannot reach any websites or internal file shares. Running `ipconfig` shows an IP address of 169.254.5.12. What is the most likely root cause?

- A. The user's DNS server is misconfigured
- B. The user's computer could not reach a DHCP server and self-assigned an APIPA address
- C. The user's subnet mask is set incorrectly
- D. The user's default gateway is unreachable but the IP address is valid

---

**42.** A technician troubleshooting the issue in the previous question checks the physical connection first. What two quick checks should be performed before moving to advanced troubleshooting?

- A. Reinstall the operating system and reset the router
- B. Verify the cable is properly connected and check for link lights on the NIC
- C. Change the computer's IP address class
- D. Disable IPv6 entirely

---

**43.** A user enters a website address beginning with `http://` and is prompted to submit a credit card number. What should the user be advised to do?

- A. Proceed normally, since HTTP is equivalent to HTTPS
- B. Avoid entering sensitive information, since HTTP transmits data in plain text
- C. Only avoid it if using a public Wi-Fi network
- D. HTTP is secure as long as the site has a valid domain name

---

**44.** A packet sniffer captures traffic on a network segment and is able to read full plaintext usernames and passwords from a remote login session. Which protocol is most likely in use?

- A. SSH
- B. Telnet
- C. HTTPS
- D. IPSec (tunnel mode)

---

**45.** An administrator needs to give a third-party application vendor a port number to build custom software around, one that is guaranteed not to conflict with well-known or registered protocol assignments. Which range should the vendor use?

- A. 0–1023
- B. 1024–49151
- C. 49152–65535
- D. Any port is equally appropriate

---

**46.** A network file share stops appearing in Windows File Explorer's Network browsing pane, though the file server itself is reachable by IP address. Which protocol's malfunction is most likely responsible?

- A. RDP
- B. SMB/CIFS
- C. LDAP
- D. SNMP

---

**47.** A company's help desk technician needs to remotely view and control a user's desktop exactly as if seated at the machine, including sound and printer redirection. Which protocol and port should be used?

- A. SSH, port 22
- B. Telnet, port 23
- C. RDP, port 3389
- D. VNC, port 5900

---

**48.** An administrator is troubleshooting a scenario where an internal LDAP directory lookup for an employee's phone number is failing, though general network connectivity is fine. Which port should the administrator verify is open?

- A. 143
- B. 389
- C. 443
- D. 445

---

**49.** A company migrating its corporate mail server wants clients to be able to see real-time updates to a shared support inbox from multiple simultaneously connected staff members. Which protocol satisfies this requirement, and why?

- A. POP3, because it downloads mail directly to each client
- B. IMAP4, because it supports multiple simultaneous connected clients viewing the same server-stored inbox
- C. SMTP, because it is the protocol used for receiving mail
- D. SNMP, because it monitors mailbox status

---

**50.** A network technician calculates that a subnetted network needs to support up to 4,094 hosts per subnet. Which CIDR notation correctly provides this capacity?

- A. /16
- B. /18
- C. /20
- D. /22

---

**51.** An administrator configures a router's external interface with a single ISP-assigned public address while dozens of internal hosts use private 192.168.1.0/24 addresses. Outbound web requests from all internal hosts appear, from the Internet's perspective, to originate from the single public address. What is functioning here?

- A. APIPA
- B. VLAN
- C. NAT (specifically NAT Overload/PAT)
- D. DHCP relay

---

**52.** A remote worker's VPN client is configured to encrypt an entire data stream to the corporate network, not just a single browser session, and it operates at OSI Layer 3. Which VPN type is this?

- A. SSL/TLS VPN
- B. IPSec VPN
- C. RDP-based VPN
- D. NetBIOS VPN

---

**53.** During VPN configuration troubleshooting, a technician notes that the original IP header of each packet is fully encrypted along with the payload, and the entire network sits behind a NAT device. Which IPSec mode is being used?

- A. Transport mode
- B. Tunnel mode
- C. Bridge mode
- D. Direct mode

---

**54.** An organization's engineers are debating whether to use a VLAN or a full physical network segmentation to isolate a sensitive finance department's traffic from the rest of the company, while keeping costs low and using existing switch hardware. What is the most appropriate recommendation, and why?

- A. Physical segmentation, because VLANs cannot provide any security isolation
- B. A VLAN, because it isolates broadcast domains and traffic logically without requiring new physical hardware
- C. NAT, because it is designed specifically for department-level isolation
- D. APIPA, because it automatically segments unreachable hosts

---

**55.** A technician reviews IPv6 traffic and finds an address beginning with `FE80::`. What does this indicate about the address's scope?

- A. It is a globally routable Internet address
- B. It is a link local address, nonroutable outside the local segment
- C. It is a multicast address reaching all hosts in a group
- D. It is the IPv6 loopback address

---

**56.** A company wants new IP addressing to support significantly more devices than their current Class C-equivalent private range allows, without redesigning their entire addressing scheme immediately. Which two facts about IPv6 make it a long-term solution to this problem?

- A. IPv6 uses a 128-bit address space and can run alongside IPv4 during a gradual migration
- B. IPv6 replaces subnet masks entirely and requires NAT
- C. IPv6 eliminates the need for DNS
- D. IPv6 only supports private addressing

---

**57.** A user calls the help desk saying their web browser won't load a specific internal application, but pinging the application's IP address directly succeeds. Which protocol should be investigated first?

- A. DNS, since hostname resolution may be failing while the IP-level connection works fine
- B. ARP, since MAC resolution would prevent all connectivity, including ping
- C. RARP, since ping relies on RARP
- D. SNMP, since it manages all name resolution

---

**58.** A technician needs to confirm whether a given TCP/IP address a coworker mentions, `172.20.5.10`, falls within a reserved private range. Based on this chapter's private address table, is it private, and why?

- A. No, because 172.20.0.0 falls outside the 172.16.0.0–172.31.255.255 private Class B range
- B. Yes, because it falls within the 172.16.0.0–172.31.255.255 private Class B range
- C. No, private addresses only start with 10 or 192
- D. Yes, because all 172.x.x.x addresses are private

---

**59.** An administrator is asked to explain to a junior technician why a device on the network with an APIPA address can still discover a DHCP server that comes back online later, despite already having self-assigned an address. What is the correct explanation?

- A. APIPA-configured clients continuously broadcast for a DHCP server in the background even after self-assignment
- B. APIPA addresses automatically renew as static addresses and never change
- C. The device must be manually restarted to search for a DHCP server again
- D. APIPA disables all further DHCP discovery permanently

---

**60.** A security-conscious administrator wants to encrypt all traffic between two branch office networks connected across the public Internet, without limiting the encryption to a single application, and wants the internal IP addressing scheme fully hidden from anyone intercepting traffic between the sites. Which VPN configuration best satisfies both requirements?

- A. An SSL/TLS VPN in transport mode
- B. An IPSec VPN in transport mode
- C. An IPSec VPN in tunnel mode
- D. A VLAN trunked across both sites

---

## Answer Key & Explanations

**1. C — TCP and IP.** The suite is named for Transmission Control Protocol and Internet Protocol, even though it actually bundles dozens of cooperating protocols beyond just those two.

**2. B — Four.** The DoD model has four layers — Process/Application, Host-to-Host, Internet, and Network Access — mapping onto the seven-layer OSI model.

**3. D — Process/Application.** This layer absorbs the functionality of OSI's Application, Presentation, and Session layers, and hosts the majority of TCP/IP's protocols.

**4. B — ICMP.** Internet Control Message Protocol delivers error messages and is the protocol the `ping` utility relies on.

**5. C — ARP.** Address Resolution Protocol resolves a known logical IP address into the physical MAC address needed for actual delivery on the local segment.

**6. B — Connectionless, no delivery guarantee.** UDP skips the virtual circuit and acknowledgment overhead that makes TCP connection-oriented, trading guaranteed delivery for slightly faster transmission.

**7. C — A socket.** A socket combines a host's IP address with a port number, such as `192.168.2.115:443`.

**8. A — 0–1023.** These are the well-known ports, reserved for commonly used services; 1024–49151 are registered ports, and 49152–65535 are free for vendor use.

**9. A — 20 and 21.** FTP uses port 20 for data and port 21 for control.

**10. B — 22.** SSH operates on port 22, originally designed to replace the unsecure Telnet.

**11. A — 25.** SMTP, a push protocol used to send email, operates on port 25.

**12. B — 67, 68.** DHCP uses ports 67 and 68 to dynamically assign IP configuration information to clients.

**13. C — 32.** An IPv4 address is a 32-bit address, typically written as four 8-bit octets in dotted-decimal notation.

**14. C — Octet.** Each of the four numbers in a dotted-decimal IPv4 address represents 8 bits, called an octet.

**15. A — 255.0.0.0.** This is the default Class A subnet mask, using the first 8 bits for the network portion.

**16. C — 192–223.** Class C addresses have their first octet in the 192–223 range and use a default /24 mask.

**17. C — 192.168.0.0–192.168.255.255.** This is the private range associated with the Class C default mask (255.255.0.0, a /16 in this private context), supporting up to 65,534 hosts.

**18. B — 169.254.0.0/16.** APIPA addresses fall in the 169.254.0.0–169.254.255.255 range with a 255.255.0.0 subnet mask.

**19. D — 128.** IPv6 addresses are 128 bits, written as eight 16-bit hexadecimal fields, versus IPv4's 32 bits.

**20. C — ::1.** The IPv6 loopback address ::1 (or 0:0:0:0:0:0:0:1 in full) replaces IPv4's 127.0.0.1.

**21. B — TCP requires a virtual circuit and delivery acknowledgments.** This overhead is what makes TCP connection-oriented and marginally slower than UDP's connectionless approach, though the real-world difference is measured in milliseconds.

**22. C — 443.** HTTPS-secured web traffic is requested on port 443, distinct from HTTP's plaintext port 80.

**23. A — It operates at OSI Layer 5 and needs another protocol to handle Layer 4 and below.** This is why NetBIOS is paired with TCP/IP as NetBT, and why routed networks like the Internet historically couldn't resolve NetBIOS names without help.

**24. B — IMAP4 allows multiple clients to stay synchronized with the same server-stored inbox; POP3 requires local download.** IMAP4's connected-mode and server-side storage are its two major advantages over POP3.

**25. B — VLAN.** VLANs are purpose-built to logically isolate traffic and reduce broadcast domains using existing switch infrastructure, without new physical wiring.

**26. B — A VLAN works at Layer 2 with MAC addresses via a switch; a subnet works at Layer 3 with IP addresses via a router.** This is the fundamental technical distinction between the two, despite both breaking up broadcast domains.

**27. C — 169.254.0.0/16.** This is the APIPA self-assignment range triggered when a DHCP client cannot reach a DHCP server.

**28. B — CIDR allows subnet mask flexibility beyond the rigid class-based defaults.** CIDR lets administrators use any valid subnet mask rather than being locked into class-based defaults, enabling more efficient address allocation.

**29. C — NAT Overload (PAT).** This variant, also called Port Address Translation, allows many private addresses to share a single public IP address, unlike standard one-to-one NAT.

**30. A — HTTPS only protects data in transit, not data at rest.** Once data reaches the server and is stored, HTTPS's encryption no longer applies; other protections are needed to secure data at rest.

**31. B — The double colon can only be used once per address, or the number of zero-fields becomes ambiguous.** With two double colons, there's no way to determine how many zero fields belong to each gap.

**32. C — Anycast.** An anycast address is shared by multiple nodes, and traffic addressed to it is delivered to whichever node is closest — "one-to-nearest" addressing.

**33. C — A plain HTTP session.** Unencrypted, readable IP headers and payload are the signature of plaintext HTTP traffic, unlike HTTPS or an IPSec-secured connection.

**34. B — AH — data integrity and origin verification; ESP — encryption.** These are IPSec's two component protocols, working together to secure a VPN connection.

**35. A — Transport mode.** Transport mode encrypts the payload but leaves the original IP header readable, typical of client-to-office VPN connections used by remote workers.

**36. A — It operates at the Application layer (Layer 7), the same layer HTTPS uses.** Because SSL/TLS VPNs work at Layer 7, they're scoped to individual applications rather than encrypting an entire network data stream, unlike Layer 3 IPSec VPNs.

**37. C — 12 bits.** Supporting roughly 3,000 hosts with room to grow requires 12 host bits (2¹²−2 = 4,094 hosts), leaving 20 bits for the network portion.

**38. B — A hostname is resolved via DNS and can work across the Internet; a NetBIOS name historically required WINS/LMHOSTS and could not.** This distinction is exactly why Microsoft eventually adopted DNS-based hostnames industry-wide instead of relying on NetBIOS naming.

**39. B — Yes, VLANs can span multiple switches in different physical locations.** This is one of VLANs' defining advantages over subnetting, which cannot achieve the same cross-location grouping.

**40. B — /20.** A mask of 255.255.240.0 sets 20 bits to 1 (the full first two octets plus 4 bits of the third), corresponding to /20.

**41. B — The user's computer could not reach a DHCP server and self-assigned an APIPA address.** An address beginning with 169.254 is the clearest sign of APIPA self-assignment following a failed DHCP request.

**42. B — Verify the cable is properly connected and check for link lights on the NIC.** These are the standard first checks before escalating to more advanced troubleshooting steps.

**43. B — Avoid entering sensitive information, since HTTP transmits data in plain text.** Without HTTPS's encryption, HTTP traffic — including credit card numbers — is transmitted in cleartext and vulnerable to interception.

**44. B — Telnet.** Telnet transmits all data, including login credentials, in plain text, making a sniffed session fully readable — exactly the vulnerability SSH was designed to eliminate.

**45. C — 49152–65535.** This range is free for application vendors to use, without conflicting with the well-known (0–1023) or registered (1024–49151) ranges.

**46. B — SMB/CIFS.** SMB/CIFS on port 445 is responsible for shared file/printer visibility in Windows network browsing, distinct from basic IP reachability.

**47. C — RDP, port 3389.** RDP is specifically designed for full remote desktop control, including sound, drive, and printer redirection, over port 3389.

**48. B — 389.** LDAP directory service lookups, including employee information queries, use port 389.

**49. B — IMAP4, because it supports multiple simultaneous connected clients viewing the same server-stored inbox.** This real-time, multi-client synchronization is one of IMAP4's defining advantages over POP3.

**50. C — /20.** Supporting 4,094 hosts (2¹²−2) requires 12 host bits; on a 32-bit address that leaves 20 network bits, giving /20 — the same math this chapter uses for its 3,000-host division-sizing example.

**51. C — NAT (specifically NAT Overload/PAT).** This is the classic Port Address Translation setup, letting many internal private addresses share a single public-facing address.

**52. B — IPSec VPN.** IPSec operates at OSI Layer 3 and can encrypt an entire packet stream, unlike an SSL/TLS VPN which is limited to Application-layer, per-application encryption.

**53. B — Tunnel mode.** Tunnel mode encrypts the original IP header along with the payload, which is standard when an entire network sits behind a NAT device.

**54. B — A VLAN, because it isolates broadcast domains and traffic logically without requiring new physical hardware.** This directly matches the cost and hardware-reuse goals described in the scenario.

**55. B — It is a link local address, nonroutable outside the local segment.** FE80::/10 is IPv6's link local range, required on every IPv6-enabled interface and functionally similar to IPv4's APIPA range.

**56. A — IPv6 uses a 128-bit address space and can run alongside IPv4 during a gradual migration.** These two facts — a vastly larger address pool and backward compatibility — are exactly what make IPv6 a practical long-term solution.

**57. A — DNS, since hostname resolution may be failing while the IP-level connection works fine.** A successful ping to the IP address confirms Layer 3 connectivity, isolating the problem to hostname-to-address resolution.

**58. B — Yes, because it falls within the 172.16.0.0–172.31.255.255 private Class B range.** 172.20.x.x sits inside that range, making it a private address.

**59. A — APIPA-configured clients continuously broadcast for a DHCP server in the background even after self-assignment.** This background broadcasting is exactly what allows the client to obtain a real address the moment a DHCP server becomes reachable.

**60. C — An IPSec VPN in tunnel mode.** Tunnel mode both encrypts the full data stream (not just one application) and hides the original IP header, satisfying both the broad-encryption and address-concealment requirements in the scenario.