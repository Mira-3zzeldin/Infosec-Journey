## Chapter 8: Network Services | 60 Questions

> **Instructions:** Answer all questions before checking the Answer Key at the bottom of this file.

---

## Section 1: Direct/Basic Recall (Q1–20)

**1.** What is the primary function of a DNS server?

- A. Assigning IP addresses to clients dynamically
- B. Resolving hostnames to IP addresses
- C. Distributing print jobs to networked printers
- D. Synchronizing device clocks across a network

---

**2.** Which port(s) does DNS use?

- A. TCP/UDP port 53
- B. UDP port 67 and 68
- C. TCP port 443
- D. TCP port 389

---

**3.** Which port(s) does DHCP use?

- A. TCP port 25
- B. UDP ports 67 and 68
- C. TCP/UDP port 53
- D. UDP port 514

---

**4.** In a DNS zone file, which record type stores an IPv4 host address?

- A. AAAA
- B. CNAME
- C. A
- D. MX

---

**5.** In a DNS zone file, which record type stores an IPv6 host address?

- A. A
- B. AAAA
- C. TXT
- D. NS

---

**6.** Which DNS record type identifies the mail server responsible for a domain?

- A. CNAME
- B. SOA
- C. MX
- D. TXT

---

**7.** Which DNS record type functions as an alias, allowing multiple names to point at the same host?

- A. CNAME
- B. NS
- C. A
- D. MX

---

**8.** What is the primary modern use of a DNS TXT record?

- A. Storing the IPv6 address of a host
- B. Spam prevention and domain ownership verification
- C. Identifying the authoritative server for a zone
- D. Assigning a static IP lease to a device

---

**9.** What does SPF authenticate?

- A. The digital signature attached to an email's headers
- B. The IP address of an email server against a list of legitimate senders
- C. The recipient's spam-handling policy
- D. The physical location of the sending device

---

**10.** How does DKIM verify that an email is legitimate?

- A. It checks the sender's IP address against a published list
- B. It checks a public/private key digital signature attached to the message
- C. It queries a syslog server for prior message history
- D. It cross-references the sender against Active Directory

---

**11.** What is the primary function of DMARC?

- A. It encrypts email traffic in transit
- B. It defines policy for handling mail that fails SPF or DKIM checks
- C. It assigns IP addresses to mail servers
- D. It stores mail server IP addresses in a CNAME record

---

**12.** How many global root DNS server IP addresses exist?

- A. 4
- B. 8
- C. 13
- D. 24

---

**13.** Which port does SMTP use?

- A. 25
- B. 110
- C. 143
- D. 443

---

**14.** Which port does POP3 use?

- A. 25
- B. 110
- C. 143
- D. 3389

---

**15.** Which port does IMAP4 use?

- A. 110
- B. 143
- C. 389
- D. 445

---

**16.** What is the default port for an unsecured syslog implementation?

- A. TCP 514
- B. UDP 514
- C. TCP 6514
- D. UDP 6514

---

**17.** When syslog is secured using TLS, which port does it use?

- A. UDP 514
- B. TCP 514
- C. TCP 6514
- D. UDP 6514

---

**18.** What is the numeric range of a syslog facility code?

- A. 0–7
- B. 0–23
- C. 1–100
- D. 0–65535

---

**19.** Which port does a standard web server listen on for HTTPS traffic?

- A. 80
- B. 443
- C. 8080
- D. 3389

---

**20.** Which port does NTP use?

- A. UDP 123
- B. TCP 123
- C. UDP 161
- D. TCP 389

---

## Section 2: Intermediate/Conceptual (Q21–40)

**21.** What is the primary purpose of placing a server in a screened subnet rather than the internal network?

- A. It allows the server to bypass firewall rules entirely
- B. It permits controlled external access while still shielding the internal network
- C. It automatically encrypts all traffic to and from that server
- D. It eliminates the need for a default gateway

---

**22.** What distinguishes a two-pronged firewall configuration from a three-pronged one?

- A. A two-pronged setup uses one device with two interfaces; a three-pronged setup requires no firewall at all
- B. A two-pronged setup uses two separate firewalls with the screened subnet between them; a three-pronged setup uses one device with three interfaces
- C. A three-pronged setup only works with IPv6 networks
- D. A two-pronged setup is used exclusively for internal-only servers

---

**23.** A company places its mail server in the screened subnet but keeps its file server on the internal network. What best explains this difference?

- A. File servers require more bandwidth than mail servers
- B. Mail servers need to be reachable from outside the network, while file servers typically don't
- C. File servers cannot function behind a firewall
- D. Mail servers require a different subnet mask than file servers

---

**24.** Why is a DHCP relay agent needed when a client and DHCP server sit on opposite sides of a router?

- A. Routers cannot process UDP traffic
- B. DHCP requires a static IP address to function
- C. DHCP DISCOVER and REQUEST messages are broadcasts, and routers block broadcast traffic
- D. Relay agents are required to encrypt DHCP leases

---

**25.** Why don't DHCP DISCOVER broadcasts reach a DHCP server located on a different subnet without additional configuration?

- A. DHCP broadcasts are limited to the local network segment and don't cross routers
- B. DHCP servers only listen on TCP, not UDP
- C. Broadcasts require a VPN tunnel to cross subnet boundaries
- D. DHCP DISCOVER messages expire after five seconds

---

**26.** What is the key difference between a DHCP reservation and a DHCP exclusion?

- A. A reservation permanently ties an address to a MAC address; an exclusion removes a range from the pool entirely for manual assignment
- B. An exclusion is temporary while a reservation is permanent
- C. A reservation only applies to IPv6 addresses
- D. There is no functional difference between the two

---

**27.** How does a NAS differ from a SAN?

- A. A NAS is a dedicated network segment of servers; a SAN is a single stand-alone unit
- B. A NAS is a stand-alone unit with its own file-management software; a SAN is a dedicated network segment or server collection for large-scale storage
- C. A NAS only supports IPv4; a SAN only supports IPv6
- D. A NAS requires a DBMS; a SAN does not

---

**28.** Under what circumstance should a fileshare be moved from the internal network to the screened subnet?

- A. When it stores more than 1 TB of data
- B. When it also functions as an FTP server
- C. When it hosts a company database
- D. When it uses NAS instead of SAN

---

**29.** Which statement correctly distinguishes SMTP from POP3 and IMAP4?

- A. SMTP is a pull protocol; POP3 and IMAP4 are push protocols
- B. SMTP is a push protocol used for sending mail; POP3 and IMAP4 are pull protocols used for receiving mail
- C. SMTP, POP3, and IMAP4 are all push protocols
- D. SMTP is only used internally; POP3 and IMAP4 are only used externally

---

**30.** What is the purpose of a syslog facility code?

- A. It encrypts the message payload
- B. It identifies the type of device that generated the message
- C. It sets the severity level of the event
- D. It determines which port the message is sent on

---

**31.** In the syslog severity scale, what does a lower numeric level indicate?

- A. A less urgent message
- B. A more urgent message
- C. A message generated by a printer specifically
- D. A message that has already been resolved

---

**32.** In the AAA framework, what is the correct logical order of operations for a user accessing a resource?

- A. Accounting, then authentication, then authorization
- B. Authorization, then authentication, then accounting
- C. Authentication, then authorization, then accounting
- D. Authentication and accounting occur simultaneously before authorization

---

**33.** What distinguishes multifactor authentication (MFA) from single-factor authentication (SFA)?

- A. MFA requires two or more authentication factors beyond the username; SFA requires only one
- B. MFA is only used for wireless networks
- C. SFA requires biometric verification; MFA does not
- D. MFA and SFA are functionally identical but named differently by vendor

---

**34.** Which of the following are the four recognized authentication factor categories?

- A. Something you know, something you have, something you are, somewhere you are
- B. Something you type, something you scan, something you own, something you say
- C. Password, PIN, biometric, and token — with no other categories
- D. Local, remote, cloud, and hybrid

---

**35.** What does the principle of least privilege state?

- A. Users should be granted the maximum access available to reduce support tickets
- B. Users should be granted only the access required to perform their job, and no more
- C. Only administrators should have any account privileges
- D. Privileges should rotate randomly among users each month

---

**36.** A company needs to store large volumes of unstructured data such as images, videos, and social media posts. Which database type is best suited to this need?

- A. A relational database, because of its rigid schema
- B. A non-relational database, such as a key/value or document database
- C. A flat-file spreadsheet, because of its simplicity
- D. A syslog server, because it already stores unstructured text

---

**37.** Why does accurate NTP synchronization matter specifically for AAA's accounting function?

- A. NTP encrypts accounting logs before they're stored
- B. Without synchronized clocks, timestamps across devices won't align, making log correlation unreliable
- C. NTP determines which users are authorized to access which resources
- D. AAA accounting cannot function at all without an internal NTP server

---

**38.** What is the key operational difference between an IDS and an IPS?

- A. An IDS is passive and only logs/alerts; an IPS is active and can block or reset connections
- B. An IDS actively blocks traffic; an IPS only logs traffic
- C. An IDS only works on host machines; an IPS only works on networks
- D. There is no operational difference — the terms are interchangeable

---

**39.** How does content-based load balancing differ from cross-region load balancing?

- A. Content-based load balancing routes by requester proximity; cross-region routes by request type
- B. Content-based load balancing splits servers by request type (web, streaming, downloads); cross-region routes requests to the nearest server region
- C. Content-based load balancing only applies to cloud deployments
- D. Cross-region load balancing cannot be used with virtual servers

---

**40.** Which three benefits does a proxy server provide to a network?

- A. Encryption, redundancy, and load balancing
- B. Caching, content filtering, and anonymization
- C. Authentication, authorization, and accounting
- D. DNS resolution, DHCP leasing, and NTP synchronization

---

## Section 3: Advanced/Troubleshooting (Q41–60)

**41.** Your company hosts its own web server allowing customer purchases. The help desk reports that external users can't reach the site, but an internal workstation loads it fine. What is the most likely cause?

- A. The DNS server has failed
- B. The firewall is blocking inbound TCP port 443
- C. The web server's HDD has failed
- D. The DHCP scope has been exhausted

---

**42.** Employees report a sharp increase in spam email, and some appears to be spoofed from the company's own domain. Which combination of technologies would best address this?

- A. NTP and syslog
- B. SPF, DKIM, and DMARC, potentially paired with a spam gateway
- C. A load balancer and a proxy server
- D. RADIUS and TACACS+

---

**43.** A company has five identical web servers handling online orders. One server is constantly overloaded while another sits idle, and customers are complaining about slow load times. Which solution addresses this?

- A. DNS server
- B. DHCP server
- C. Proxy server
- D. Load balancer

---

**44.** An administrator is configuring a DHCP scope for a 192.168.1.0/24 network and needs 20 addresses permanently set aside for servers, printers, and router interfaces that will be assigned manually. What is the best approach?

- A. Create a scope of 192.168.1.1–192.168.1.200 and create an exclusion for 192.168.1.1–192.168.1.20
- B. Create a scope of 192.168.1.1–192.168.1.200 and create a lease for 192.168.1.1–192.168.1.20
- C. Create a scope of 192.168.1.21–192.168.1.200 and create an inclusion for 192.168.1.1–192.168.1.20
- D. Create a scope of 192.168.1.1–192.168.1.200 and create reservations for 192.168.1.1–192.168.1.20

---

**45.** A network printer needs to always receive the same IP address every time it powers on, without the administrator manually configuring the printer itself. What DHCP feature accomplishes this?

- A. A scope
- B. An exclusion
- C. A reservation
- D. A lease renewal

---

**46.** Multiple employees are attempting to access websites with objectionable content, and the administrator wants those requests blocked before they leave the network. Which service should handle this?

- A. DNS server
- B. Proxy server
- C. DHCP server
- D. NTP server

---

**47.** An administrator investigating a security incident finds that timestamps in the logs from three different devices don't line up, making it difficult to reconstruct the sequence of events. What is the most likely underlying issue?

- A. The devices are using different subnet masks
- B. The devices are not synchronized to a common, accurate time source
- C. The devices are using different DNS servers
- D. The devices have mismatched MAC addresses

---

**48.** Two email servers at different companies need to transfer a message between each other. Which protocol handles this transfer?

- A. POP3
- B. IMAP4
- C. SNMP
- D. SMTP

---

**49.** A manager wants a single device that centralizes packet filtering, intrusion prevention, antimalware, and spam blocking, replacing several separate security tools. What should be installed?

- A. Spam gateway
- B. Load balancer
- C. UTM
- D. Proxy server

---

**50.** An email receiving server wants to confirm that an inbound message actually originated from an IP address the sending domain has designated as legitimate. Which DNS-based mechanism performs this exact check?

- A. DKIM
- B. SPF
- C. DMARC
- D. CNAME

---

**51.** An administrator is entering new server records into the corporate DNS zone file and has only IPv6 addresses for those servers. Which record type should be used?

- A. A
- B. CNAME
- C. AAAA
- D. TXT

---

**52.** A manufacturing plant relies on a decades-old industrial control system to manage its production line, and the system was designed without modern security in mind. What is the standard recommended mitigation when full replacement isn't feasible?

- A. Disable the system entirely
- B. Isolate/segment the system onto its own network segment
- C. Expose it directly to the Internet for easier remote troubleshooting
- D. Replace it immediately regardless of cost

---

**53.** A company wants to allow certain employees to log in only when connected from within the corporate office's IP range. Which authentication factor category does this represent?

- A. Something you know
- B. Something you have
- C. Something you are
- D. Somewhere you are

---

**54.** Which AAA component is responsible for tracking which specific resources a user accessed and when?

- A. Authentication
- B. Authorization
- C. Accounting
- D. All three equally

---

**55.** You are setting up a file server that will store sensitive accounting department files and will not be accessed from outside the corporate network. Where should this server be placed?

- A. In the screened subnet
- B. Directly on the firewall
- C. On the internal network
- D. Outside all firewalls for easier access

---

**56.** An administrator notices a security appliance that automatically terminates a suspicious connection the moment it detects an attack signature, without waiting for a human to respond. What kind of device is this?

- A. IDS
- B. IPS
- C. Spam gateway
- D. NTP server

---

**57.** A DNS server receives a query for a hostname it has no record of in its own zone file or cache. What is its next step in the resolution process?

- A. It immediately returns an error to the client with no further action
- B. It queries a root server to begin locating an authoritative source
- C. It broadcasts a DHCP DISCOVER message
- D. It defers to the local syslog server for the answer

---

**58.** An employee just connected a voice-activated smart speaker to the office guest network to answer questions during breaks. What category of device is this?

- A. UTM
- B. SCADA
- C. IoT
- D. AAA

---

**59.** A company is setting up its own public-facing DNS infrastructure for a new website. How many DNS servers should it maintain at minimum, and why?

- A. One, because DNS servers are inherently redundant internally
- B. Two, for redundancy
- C. Four, one per root server region
- D. As many as there are employees

---

**60.** Which two of the following are core functions a print server should provide? (Choose two.)

- A. Accepting print jobs from clients
- B. Automatically formatting documents for a specific font
- C. Managing the print queue
- D. Assigning static IP addresses to printers

---

## Answer Key & Explanations

**1. B — Resolving hostnames to IP addresses.** DNS's sole job is turning human-readable hostnames into the IP addresses computers actually need to communicate. It does not assign addresses (that's DHCP), manage printers, or handle time sync.

**2. A — TCP/UDP port 53.** DNS can operate over either UDP (for standard queries) or TCP (typically for larger transfers like zone transfers), both on port 53.

**3. B — UDP ports 67 and 68.** DHCP uses UDP port 67 on the server side and UDP port 68 on the client side to exchange lease information.

**4. C — A.** The A record is specifically the IPv4 host record. AAAA is reserved for IPv6, CNAME is an alias, and MX identifies a mail server.

**5. B — AAAA.** Nicknamed "quad A," this record type exists specifically because a standard A record can't represent IPv6's longer address format.

**6. C — MX.** The Mail Exchange record tells other mail servers where to deliver email for a domain; SOA identifies the zone's authority and TXT is for text-based data like spam controls.

**7. A — CNAME.** Canonical Name records let multiple hostnames (like `www` and `www2`) point at the same underlying host without duplicating an A record.

**8. B — Spam prevention and domain ownership verification.** While TXT records can technically hold any text data, their dominant modern use is carrying SPF, DKIM, and DMARC entries and verifying domain ownership for various services.

**9. B — The IP address of an email server against a list of legitimate senders.** SPF is IP-based authentication; it does not involve digital signatures (that's DKIM) or physical location.

**10. B — It checks a public/private key digital signature attached to the message.** DKIM encrypts a signature with the sender's private key, which the receiving server decrypts using the sender's published public key to confirm authenticity.

**11. B — It defines policy for handling mail that fails SPF or DKIM checks.** DMARC isn't an authentication method itself — it's a policy layer sitting on top of SPF and DKIM results, plus a reporting mechanism.

**12. C — 13.** There are 13 global root server IP addresses, though each represents multiple redundant physical servers distributed worldwide.

**13. A — 25.** SMTP, the push protocol for sending and relaying email, uses TCP port 25.

**14. B — 110.** POP3 downloads mail and disconnects, operating on TCP port 110.

**15. B — 143.** IMAP4 uses TCP port 143 and, unlike POP3, keeps mail synchronized on the server across multiple clients.

**16. B — UDP 514.** Syslog's default, unsecured implementation runs over connectionless UDP on port 514, meaning delivery isn't guaranteed.

**17. C — TCP 6514.** Securing syslog with TLS shifts it to the connection-oriented TCP protocol on port 6514.

**18. B — 0–23.** Facility codes span 0 through 23, each identifying a different class of originating device (kernel, mail, security, printers, and so on).

**19. B — 443.** Standard HTTPS traffic to a web server uses TCP port 443; port 80 is for unencrypted HTTP.

**20. A — UDP 123.** NTP operates on UDP port 123 to synchronize device clocks across a network.

**21. B — It permits controlled external access while still shielding the internal network.** The screened subnet exists precisely to let outside traffic reach specific servers without directly exposing the internal network to that same traffic.

**22. B — A two-pronged setup uses two separate firewalls with the screened subnet between them; a three-pronged setup uses one device with three interfaces.** Both accomplish the same segmentation goal through different hardware arrangements; the two-pronged approach forces an attacker through two independent firewalls.

**23. B — Mail servers need to be reachable from outside the network, while file servers typically don't.** Placement is driven by whether outside clients need direct access, not by bandwidth or subnet mask requirements.

**24. C — DHCP DISCOVER and REQUEST messages are broadcasts, and routers block broadcast traffic.** A relay agent exists specifically to forward those broadcast-only messages across a router boundary to reach a remote DHCP server.

**25. A — DHCP broadcasts are limited to the local network segment and don't cross routers.** This is the fundamental reason relay agents or router-based DHCP service exist at all.

**26. A — A reservation permanently ties an address to a MAC address; an exclusion removes a range from the pool entirely for manual assignment.** Reservations still come from DHCP automatically (tied to a device); exclusions are addresses DHCP won't touch at all, freeing them for manual static configuration.

**27. B — A NAS is a stand-alone unit with its own file-management software; a SAN is a dedicated network segment or server collection for large-scale storage.** SAN is the larger-scale, more expansive solution; NAS is typically a simpler, self-contained device.

**28. B — When it also functions as an FTP server.** Any fileshare that also accepts FTP connections needs to be reachable from outside, which pushes it into the screened subnet — and away from highly sensitive data.

**29. B — SMTP is a push protocol used for sending mail; POP3 and IMAP4 are pull protocols used for receiving mail.** This push/pull distinction is one of the most frequently tested facts about mail protocols.

**30. B — It identifies the type of device that generated the message.** The facility code (0–23) tells the syslog server what kind of device sent the message; it has nothing to do with encryption, port assignment, or urgency (that's the severity level).

**31. B — A more urgent message.** Severity level 0 (Emergency) is the most urgent; level 7 (Debug) is the least, making the scale inverse to what many people initially expect.

**32. C — Authentication, then authorization, then accounting.** A user must first prove who they are, then be granted (or denied) specific access, and only then does the system track what they did with that access.

**33. A — MFA requires two or more authentication factors beyond the username; SFA requires only one.** SFA is most commonly just a password; MFA layers in at least one more factor from a different category.

**34. A — Something you know, something you have, something you are, somewhere you are.** These are the four recognized categories underpinning multifactor authentication design.

**35. B — Users should be granted only the access required to perform their job, and no more.** Least privilege minimizes the damage any single compromised account can cause.

**36. B — A non-relational database, such as a key/value or document database.** Relational databases excel at rigid, structured data; unstructured content like images and video is better suited to non-relational storage models.

**37. B — Without synchronized clocks, timestamps across devices won't align, making log correlation unreliable.** Accounting relies on being able to reconstruct an accurate timeline of events across potentially many devices, which requires a shared, accurate time source.

**38. A — An IDS is passive and only logs/alerts; an IPS is active and can block or reset connections.** This is the single most important distinction between the two device types, despite both watching for the same kinds of traffic anomalies.

**39. B — Content-based load balancing splits servers by request type (web, streaming, downloads); cross-region routes requests to the nearest server region.** Both are legitimate load-balancing strategies, but they solve different problems — content specialization versus geographic proximity.

**40. B — Caching, content filtering, and anonymization.** These are the three concrete benefits a proxy server provides in exchange for the added latency of routing traffic through it.

**41. B — The firewall is blocking inbound TCP port 443.** Internal access working while external access fails points strongly to a firewall rule blocking inbound HTTPS traffic before it can reach the server, rather than a server-side failure (which would also affect internal users).

**42. B — SPF, DKIM, and DMARC, potentially paired with a spam gateway.** These DNS-based standards directly address domain spoofing, while a spam gateway adds another layer of inbound/outbound filtering — together they form the complete anti-spam toolkit covered in this chapter.

**43. D — Load balancer.** Uneven load across identical servers, with resulting performance complaints, is the textbook scenario a load balancer is designed to solve by redistributing requests.

**44. D — Create a scope of 192.168.1.1–192.168.1.200 and create reservations for 192.168.1.1–192.168.1.20.** Reservations keep those 20 addresses permanently tied to specific devices while still letting DHCP manage the entire range automatically — the best-practice approach described in this chapter, avoiding the conflict risks of a manual/hybrid split.

**45. C — A reservation.** A reservation ties an IP permanently to the printer's MAC address, ensuring it always receives the same address without needing manual static configuration on the device itself.

**46. B — Proxy server.** Content filtering — blocking access to prohibited sites — is one of the three defining benefits of a proxy server.

**47. B — The devices are not synchronized to a common, accurate time source.** Misaligned timestamps across devices is the classic symptom of missing or failed NTP synchronization, directly undermining AAA's accounting function.

**48. D — SMTP.** SMTP handles both client-to-server sending and server-to-server transfer of mail; POP3 and IMAP4 are receive-only protocols.

**49. C — UTM.** Centralizing multiple security functions — filtering, IPS, antimalware, spam blocking — into one device or interface is the defining feature of unified threat management.

**50. B — SPF.** SPF specifically checks the sending server's IP address against a domain's published list of legitimate senders — exactly the mechanism described in the question.

**51. C — AAAA.** Any time IPv6 addresses need a DNS host record, AAAA (not A) is the correct record type.

**52. B — Isolate/segment the system onto its own network segment.** When replacing a legacy/embedded system like an ICS isn't feasible, isolating it limits its exposure and keeps its vulnerabilities from threatening the rest of the network — the opposite of exposing it further.

**53. D — Somewhere you are.** Restricting login based on a recognized IP range or network location is the textbook definition of this fourth authentication factor category.

**54. C — Accounting.** Accounting is specifically the AAA component responsible for logging what a user accessed and when, distinct from authentication (identity) and authorization (permissions).

**55. C — On the internal network.** A file server holding sensitive data with no external access requirement belongs on the more secure internal network, not in the screened subnet or on the firewall itself.

**56. B — IPS.** Automatically terminating a connection without human intervention is the defining active behavior of an intrusion prevention system, as opposed to an IDS, which only logs and alerts.

**57. B — It queries a root server to begin locating an authoritative source.** Once a DNS server exhausts its own zone file and cache, the standard next step is querying one of the 13 root servers to begin the hierarchical resolution process.

**58. C — IoT.** A voice-activated smart speaker is a textbook Internet of Things device, distinct from security appliances (UTM), industrial control systems (SCADA), or access-control frameworks (AAA).

**59. B — Two, for redundancy.** This chapter specifically notes that a company hosting its own website should maintain at least two public DNS servers for redundancy, rather than relying on a single point of failure.

**60. A, C — Accepting print jobs from clients; Managing the print queue.** These are the print server's two core, defining functions described in this chapter; formatting documents for specific fonts and assigning static IPs to printers are not functions a print server itself performs.
