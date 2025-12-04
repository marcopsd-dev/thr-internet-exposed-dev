<h1 align="center">Timeline Summary and Findings:</h1>

<h3>Data Collection:</h3>

<a>Virtual client "mps-mde-w11" was exposed to the internet for 3 days as of NOV-25-2025.</a><br><br>

<b>KQL Query used on Microsoft Defender for findings on 11-26-2025:</b><br>


<img width="303" height="92" alt="Screenshot 2025-11-26 at 4 26 57 PM" src="https://github.com/user-attachments/assets/8021d349-c5c5-45e1-a9a9-2570efac6e96" />


<a>Last internet facing time on:</a><br>
<a> 2025-11-26T15:37:23.2046413Z </a>
_________
A couple bad actors were discovered trying to breakin to the target machine. <br><br>

<b>KQL Query used on Microsoft Defender for findings on 11-26-2025:</b><br>

<img width="459" height="123" alt="Screenshot 2025-11-26 at 4 32 08 PM" src="https://github.com/user-attachments/assets/726e5989-a36c-42f8-92c5-e268be6395f0" /> <br>

<b>Query Results:</b><br><br>
<img width="485" height="224" alt="Screenshot 2025-12-04 at 2 37 38 PM" src="https://github.com/user-attachments/assets/2094e6d4-a5ff-4051-8f2f-7db07ea8919d" />


_________
The most failed login attempts IP address was not able to login successfully into the target machine. <br>

<b>KQL Query used on Microsoft Defender for findings on 11-26-2025:</b><br>

<img width="615" height="109" alt="Screenshot 2025-11-26 at 4 36 50 PM" src="https://github.com/user-attachments/assets/2f37707f-514b-4020-8b51-ccac8204715e" />

`<Query NO RESULTS>`


_________
The only successful logins made into the target machine were made by the “mpsadmin” account (a total of 6 times) in the last 30 days. <br>

<b>KQL Query used on Microsoft Defender for findings on 11-26-2025:</b><br>

<img width="287" height="120" alt="Screenshot 2025-12-04 at 11 45 31 AM" src="https://github.com/user-attachments/assets/a754a75f-9ec3-4b9f-9461-889ac05dbd54" />


_________
There were zero (0) failed logons by the “mpsadmin” user account, thus indicating a lack of brute force attack attempts for this account, and a one-time password guess is highly unlikely. 

<b>KQL Query used on Microsoft Defender for findings on 11-26-2025:</b><br>

<img width="273" height="119" alt="Screenshot 2025-12-04 at 11 49 42 AM" src="https://github.com/user-attachments/assets/57cd131e-e6c1-422a-b8ad-4691c9f882fc" />


_________
Revised the IP addresses used to login to “mpsadmin” account, query shows only one IP address associated with the account located in the U.S.

<b>KQL Query used on Microsoft Defender for findings on 11-26-2025:</b><br>

<img width="592" height="113" alt="Screenshot 2025-12-04 at 11 51 09 AM" src="https://github.com/user-attachments/assets/52fcc57a-0326-4337-aa1c-e089f00b40b9" /> <br>

___

<h3> Data Analysis:</h3><br>
Though the device was exposed to the internet and clear brute force attempts have taken place, there is no evidence of any brute force success or unauthorized access from the legitimate account “mpsadmin”. <br><br>


___

<h3> Investigation: </h3><br>

Relevant MITRE ATT&CK TTPs:

- T1190: Exploit Public-Facing Application (due to the internet-facing nature of the machine).
- T1078: Valid Accounts (successful logons by legitimate account “mpsadmin”).
- T1110: Brute Force (failed logon attempts from multiple IP addresses).
- T1587: Develop Capabilities: Exploit Code (indirect inference from multiple bad actors attempting to log in). <br><br>


___

<h3> Response: </h3><br>

- Hardened the NSG attached to “mps-mde-w11” to allow only RDP traffic from specific endpoints (no public internet access). 
- Implemented Account lockout policy. 
- Implemented MFA.
