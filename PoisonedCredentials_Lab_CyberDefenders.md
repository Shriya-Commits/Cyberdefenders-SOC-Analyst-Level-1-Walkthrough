**#CyberDefenders - SOC Analyst - Level 1**

**#Poisoned Credentials**

**#SCENARIO**<br>
**Your organization's security team has detected a surge in suspicious network activity.There are concerns that LLMNR (Link-Local Multicast Name Resolution) and NBT-NS (NetBIOS Name Service) poisoning attacks may be occurring within your network. These attacks are known for exploiting these protocols to intercept network traffic and potentially compromise user credentials. Your task is to investigate the network logs and examine captured network traffic.**

**#LINK LOCAL MULTICAST NAME RESOLUTION (LLMNR)**<br>
**LLMNR is a network protocol that allows devices on a loacl network to resolve hostnames to IP addresses without a DNS server when a DNS fails. It is designed for small, local networks where a DNS server is not functioning or unavailable.**

**#NetBIOS Name Service (NBT-NS)**<br>
**NetBIOS Name is a human-readable name used to identfy devices on the network. NBT-NS is the service that works like DNS but for a limited scope in older Microsoft based networks.**

**Q1. In the context of the incident described in the scenario, the attacker initiated their actions by taking advantage of benign network traffic from legitimate machines. Can you identify the specific mistyped query made by the machine with the IP address 192.168.232.162?**

**Step 1:** Open PCAP in Wireshark

**Step 2:** Write the query filtering for LLMNR and the source ip 192.168.232.162 - llmnr and ip.src == 192.168.232.162

**Step 3:** When a packet stream is opened, check for more information under the LLMNR tab which displays the mistyped query

**Result:** The mistyped query is "fileshaare"

**Q2. We are investigating a network security incident. To conduct a thorough investigation, We need to determine the IP address of the rogue machine. What is the IP address of the machine acting as the rogue entity?**

**Step 1:** Write the query filtering for LLMNR as llmnr

**Step 2**: The machine that initiated the attack sends an NBNS response in the previous query.

**Result**: The rogue machine IP address is 192.168.232.215

**#There are 2 machines that received the responses.** 

**Q3. As part of our investigation, identifying all affected machines is essential. What is the IP address of the second machine that received poisoned responses from the rogue machine?**

**Result:** The second machine has the iP address 192.168.232.176

**Q4. We suspect that user accounts may have been compromised. To assess this, we must determine the username associated with the compromised account. What is the username of the account that the attacker compromised?**

**Step 1:** The query filter to look up the account is ntlmssp.auth.username

**Step 2:** Double click the result and the username is displayed

**Result:** The username is janesmith

**Q5. As part of our investigation, we aim to understand the extent of the attacker's activities. What is the hostname of the machine that the attacker accessed via SMB?**

**Step 1:** The query filter to look up the account is ntlmssp.auth.hostname

**Step 2:** Double click the result and the host is displayed

**Result:** The host name is AccountingPC

 
