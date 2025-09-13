**#Cyberdefenders - SOC Analyst - Level 1**

**#WebStrike**

**#SCENARIO**

**A suspicious file was identified on a company web server, raising alarms within the intranet. The Development team flagged the anomaly, suspecting potential malicious activity. To address the issue, the network team captured critical network traffic and prepared a PCAP file for review.
Your task is to analyze the provided PCAP file to uncover how the file appeared and determine the extent of any unauthorized activity.**

**Q1. Identifying the geographical origin of the attack facilitates the implementation of geo-blocking measures and the analysis of threat intelligence. From which city did the attack originate?**

**Step 1:** Opened PCAP in Wireshark.

**Step 2:** Filtered for HTTP traffic → found suspicious requests.

**Step 3:** Source IP observed: 117.11.88.124.

**Step 4:** Destination IP (victim server): 24.49.63.79.

**Step 5:** Verified source IP is public (not in private IP ranges).

**Step 6:** Used ipinfo.io on local machine for geolocation.

**Result:** The <city_name> from where the attack originated was successfully retrieved.


**Q2. Knowing the attacker's User-Agent assists in creating robust filtering rules. What's the attacker's Full User-Agent?**

**Step 1:** Opened PCAP in Wireshark

**Step 2:** Filtered for HTTP traffic

**Step 3:** Searched for more information regarding the User-Agent header in the HTTP request

**Result:** The Full User-Agent string <Mozilla/5.0 (X11; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/115.0> was successfully retrieved.


**Q3. We need to determine if any vulnerabilities were exploited. What is the name of the malicious web shell that was successfully uploaded?**

**Step 1:** Open PCAP in Wireshark

**Step 2:** Search for the HTTP traffic with POST method

**Step 3:** Use filter http.request.method == POST to follow the HTTP streams

**Step 4:** Go to the Analyze tab in Wireshark and click follow the HTTP stream.

There are 3 HTTP streams which you would follow and would see two attempts of uploading a file of which one is successful other is not.

**Result:** The malicious web shell is <image.jpg.php>


**Q4. Identifying the directory where uploaded files are stored is crucial for locating the vulnerable page and removing any malicious files. Which directory is used by the website to store the uploaded files?**

**Step 1:** Use the filter http.request.method == POST and right-click to follow the HTTP stream

**Step 2:** The directory for the malicious web shell is display with the name of the web shell

**Result:** The directory where all the uploaded files are: </reviews/uploads/>  


**Q5. Which port, opened on the attacker's machine, was targeted by the malicious web shell for establishing unauthorized outbound communication?**

**Step 1:** Use the filter http.request.method == POST and right-click to follow the HTTP stream

**Step 2:** The port is displayed with the web shell that was targeted for establishing unauthorized connection with the attacker's machine.

**Result:** The port is 8080







