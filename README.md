# DNS Tunneling Lab Demo (Draft)

## General infomation
- **Project Author:**  Kevin Wafula
- **Course Title:** Cyber Operations I
- **Course Number:** CSC-840-DT1
- **Course Professor:** Dr. Michael Ham
- **Degree Program:** PhD in Cyber Operations
- **Degree Institution:** Dakota State University  
- **Project Description:** In part for fulfillment of the final exam project of CSC-840: Cyber Operations I
- **Version Control:** Draft revision 0.2.0
- **Semester:**
## Why Should You Care
DNS is a backone protocol of the internt infrastructure, it facilitates resolution of human readable domain names to IP Addresses that computing nodes require for network identification, connnectivity, and communicaiton. Without DNS, domain name resolution would be an impractical task. Each endpoint would have to establish and maintain a database all other endpoint on the internet in order to resolve domain names to IP Addresses. 

Because DNS is a requirement for internet connectivity, organizations configure their firewalls to allow endpoints behind firewalls to perform DNS queries. It this capability that DNS Tunneling attacks leverage to install tunnling client agents on a corporate endpoints behild firewall and establish private communications to tunneling server agents on a Command Control (C2) servers outside the corporate boundary. All communications between tunneling client and the server agents conform to the specifications of DNS protocol quries, however encapsulating other protocols such as SSH, HTTP, ICMP, etc. Crude DNS Tunneling attacks are difficult to identify to an untrained eye, but sophisticated attackers can craft their tools generate quries and responses that mimic DNS naming parterns of legitimate hosts and domains on the internet, making it difficult to detect by even a train eyes. Organizations need to be aware of DNS Tunneling attacks and implement DNS security bestpratices. But that is not enough, organizations should include DNS traffic as core activity in their cyber threat monitoring, analysis, validation schemes.

## Three Main Ideas
1. DNS protocol lacks inherent capabilities to authenticate the orign of DNS queries and query responses, attackers leverage this weakness to establish communication channels with systems behind firewalls.
2. Attackers deliver and install a preconfigured DNS Tunneling tools such as DNSCAT2 to corporate sytems behind firewalls via malware, malicious document attachments in emails, or drive-by internet browsing auto-download and execute scripts. Once installed, the tools initiate connectivity to attackers C2 servers via DNS queries that are typically not filtered/inspected by firewalls. With a tunnel established, attackers have command control of infected corporate end-points behind firewalls and can move laterally to find sensitive data for exfiltration via the same tunnel.
3. Virtually, any protocol can be encapsulated in established DNS Tunneling attack tunnels and all communication exchanged will appear as standard DNS qeuries and responses. The DNS Tunneling client and Server will encode and decode the communication as DNS queries and responses.

## Future Direction
Further research should be done to extend the DNS protocol with seamless, low effort capabilities for orgin authentication of DNS queries and responses. Authentication of DNS queries and responses coupled with query filtering can have a huge impact in mitigating DNS Tunneling attacks. While efforts like DNSSEC promise these features, the rate of adoption has been low largely becuase of the level of effort required to establish and maintain DNSSEC security features. More work needs to be done to ease deployment and maintainance of DNSSEC.

## Additional Resources
1. Class Demo Video: Updated video pending upload to youtube, link to be provided upon upload
2. What is DNS Tunneling? - https://www.infoblox.com/glossary/dns-tunneling/
3. Detecting DNS Tunneling - https://www.giac.org/paper/gcia/1116/detecting-dns-tunneling/108367
4. Detecting DNS tunneling in RSA NetWitness: DNS2TCP - https://community.rsa.com/t5/netwitness-blog/detecting-dns-tunneling-in-rsa-netwitness-dns2tcp/ba-p/521147
5. DNSCAT2 Tool - https://github.com/iagox86/dnscat2
6. DNSCAT Overview - https://www.youtube.com/watch?v=49F0co_VrTY
7. DNSSEC - https://www.youtube.com/watch?v=_8M_vuFcdZU
8. DNSSEC - https://www.dnssec.net/
9. DNSEC Adoption - https://blog.cloudflare.com/automatically-provision-and-maintain-dnssec/
10. DNS Protocol Abuse/ Blackhat - https://www.youtube.com/watch?v=K0zH8lHNnAI
