**#Cyberdefenders - SOC Analyst - Level 1**

**#WebStrike**

**#Scenario
A suspicious file was identified on a company web server, raising alarms within the intranet. The Development team flagged the anomaly, suspecting potential malicious activity. To address the issue, the network team captured critical network traffic and prepared a PCAP file for review.
Your task is to analyze the provided PCAP file to uncover how the file appeared and determine the extent of any unauthorized activity.**

**Q1. Identifying the geographical origin of the attack facilitates the implementation of geo-blocking measures and the analysis of threat intelligence. From which city did the attack originate?**

My Process:
Step 1: Opened PCAP in Wireshark.

Step 2: Filtered for HTTP traffic → found suspicious requests.

Step 3: Source IP observed: 117.11.88.124.

Step 4: Destination IP (victim server): 24.49.63.79.

Step 5: Verified source IP is public (not in private IP ranges).

Step 6: Used ipinfo.io on local machine for geolocation.

**Result: The <city_name> from where the attack originated was successfully retrieved.**


**Q2. Knowing the attacker's User-Agent assists in creating robust filtering rules. What's the attacker's Full User-Agent?**

My Process:
Step 1: Opened PCAP in Wireshark

Step 2: Filtered for HTTP traffic

Step 3: Searched for more information regarding the User-Agent header in the HTTP request

**Result: The Full User-Agent string <Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0> was successfully retrieved.**

**Q3.**  




