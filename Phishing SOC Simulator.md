TryHackMe SOC Phishing simulator :






**Time of Activity:**
09/28/2025 15:35:14 (email received)
**List of Related Entities:**
User/Recipient: j.garcia@thetrydaily.thm
**Sender:** onboarding@hrconnex.thm
**Suspicious URL:** https://hrconnex.thm/onboarding/15400654060/j.garcia
**Subject:** Action Required: Finalize Your Onboarding Profile
**Reason for Classifying as False Positive:**
Although the email contained a suspicious external link, firewall/proxy log review in Splunk showed no outbound traffic from the user’s endpoint to the domain hrconnex.thm.
No evidence of user interaction or attempted connection was found.
No additional related alerts or indicators were detected.

<img width="2179" height="537" alt="image" src="https://github.com/user-attachments/assets/f993c00c-3c09-48c6-b0fc-b8f684599993" />

<img width="2543" height="673" alt="image" src="https://github.com/user-attachments/assets/5f6feec1-b4df-468f-832a-4c91b9b9ba4e" />
<img width="1277" height="1067" alt="image" src="https://github.com/user-attachments/assets/2ca9f424-7cbc-4b50-8896-7c2e5b9237a3" />
<img width="2533" height="1225" alt="image" src="https://github.com/user-attachments/assets/a556705e-a791-4b51-94a2-fd265256a554" />
<img width="1952" height="1180" alt="image" src="https://github.com/user-attachments/assets/70d53078-09c2-4ac7-a797-2c9b6bcaa760" />

TRUE POSITIVE



<img width="2191" height="597" alt="image" src="https://github.com/user-attachments/assets/1b2fe39c-21f9-4bc4-ac7f-c199eb31c833" />

<img width="1484" height="1181" alt="image" src="https://github.com/user-attachments/assets/112bda78-318a-429d-ac72-f77c8706c756" />

📝 Investigation Report

Description:
This alert was triggered by an inbound phishing-style email containing an external link. Investigation in firewall logs confirmed that the recipient attempted to access the URL, but the outbound request was successfully blocked by the firewall, preventing a connection.

**Time of Activity:**

09/28/2025 15:36:23 (email delivery to user)

09/28/2025 15:37:37 (user clicked link, firewall blocked outbound request)

**List of Related Entities:**

User/Recipient: h.harris@thetrydaily.thm

**Sender:** urgents@amazon.biz

**Suspicious URL:** http://bit.ly/3sHkX3da12340

**Source IP (user endpoint):** 10.20.2.17

**Destination IP:** 67.199.248.11

**Firewall Rule Triggered:** Blocked Websites

**Reason for Classifying as True Positive:**

Email exhibits phishing characteristics (spoofed Amazon delivery message, urgency, shortened link).

Logs confirm user engagement (attempted click on malicious URL).

Firewall successfully blocked the connection, preventing compromise.

**Reason for Escalating the Alert:**

Indicates risky user behavior (clicking phishing link).

User’s account and endpoint need review for any additional suspicious activity.

Other users may have received similar phishing emails — campaign risk.

**Recommended Remediation Actions:**

Quarantine/remove the phishing email from h.harris’s mailbox and across the environment.

Notify and educate h.harris about phishing risks.

Block/blacklist the bit.ly link and resolve for possible redirects.

Search for other recipients of emails from urgents@amazon.biz.

Monitor for further outbound attempts to the same or related domains.

Escalate to Tier 2/IR to verify no further compromise indicators.

**List of Attack Indicators (IOCs):**

Sender Address: urgents@amazon.biz
**
Suspicious Domain:** amazon.biz

**Phishing URL:** http://bit.ly/3sHkX3da12340

**Destination IP:** 67.199.248.11

**Subject Line:** Your Amazon Package Couldn’t Be Delivered – Action Required
