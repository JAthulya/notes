ports
malwaretypes
bassic networking 
osi
cia
siem
edr
ad
ssl/tls
telnet
tcp -segments udp-datagram
__what is a hub__
hub is a layer 1 device that connects multiple computers. hub is a dumb device because it broadcast all the data to everyport

what is mitre attack
framework which we can use to identify uncovered vulnerabilities, security risks. it has advasarial tactics, technics and common knowledge. 

endpoints
windows event logs
sysmon - tool used to monitor log events in windows
os query - can query endpoint using SQL syntax
wazuh - open source extensive EDR solution.
In the simulated threat investigation activity, we have learned the following:

-   Having a baseline document aids you in differentiating malicious events from benign ones.
-   Event correlation provides a deeper understanding of the concurrent events triggered by the malicious activity.
-   Taking note of each significant artefact is crucial in the investigation.
-   Other potentially affected assets should be inspected and remediated using the collected malicious artefacts. 

In conclusion, we covered the basic concepts of Endpoint Security Monitoring:

-   **Endpoint Security Fundamentals** tackled Core Windows Processes and Sysinternals.
-   **Endpoint Logging and Monitoring** introduced logging functionalities such as Windows Event Logging and Sysmon and monitoring/investigation tools such as OSQuery and Wazuh.
-   **Endpoint Log Analysis** highlighted the importance of having a methodology such as baselining and event correlation.

what is EDR 
Endpoint detection and response (EDR) are tools and applications that monitor devices for an activity that could indicate a threat or security breach. These tools and applications have features that include:  

-   Auditing a device for common vulnerabilities
-   Proactively monitoring a device for suspicious activity such as unauthorized logins, brute-force attacks, or privilege escalations.
-   Visualizing complex data and events into neat and trendy graphs
-   Recording a device's normal operating behaviour to help with detecting anomalies

__what is active directory__
AD serves as a centralized security management solution that houses all network resources. The purpose of Active Directory is **to enable organizations to keep their network secure and organized without having to use up excessive IT resources

__what is rfi__
Remote file inclusion (RFI) is an attack targeting [vulnerabilities](https://www.imperva.com/learn/application-security/vulnerability-management/) in web applications that dynamically reference external scripts. The perpetrator’s goal is to exploit the referencing function in an application to upload malware (e.g., [backdoor shells](https://www.imperva.com/learn/application-security/backdoor-shell-attack/)) from a remote URL located within a different domain.

__what is lfi__
An attacker can use Local File Inclusion (LFI) to trick the web application into exposing or running files on the web server. An LFI attack may lead to information disclosure, remote code execution, or even [Cross-site Scripting (XSS)](https://www.acunetix.com/websitesecurity/cross-site-scripting/). Typically, LFI occurs when an application uses the path to a file as input. If the application treats this input as trusted, a local file may be used in the include statement.

__what is xss__
Cross site scripting (XSS) is an attack in which an attacker injects malicious executable scripts into the code of a trusted application or website. Attackers often initiate an XSS attack by sending a malicious link to a user and enticing the user to click it. If the app or website lacks proper data sanitization, the malicious link executes the attacker’s chosen code on the user’s system. As a result, the attacker can steal the user’s active session cookie.
-   Never trust user input.
-   Implement output encoding.
-   Perform user input validation.
-   Follow the [defense in depth](https://www.synopsys.com/blogs/software-security/the-secret-to-red-teaming/) principle.
-   Ensure that web application development aligns with [OWASP’s XSS Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html).
-   After remediation, perform [penetration testing](https://www.synopsys.com/software-integrity/application-security-testing-services/penetration-testing.html) to confirm it was successful.

what is csrf
Cross-Site Request Forgery (CSRF) is an attack that forces an end user to execute unwanted actions on a web application in which they’re currently authenticated. With a little help of social engineering (such as sending a link via email or chat), an attacker may trick the users of a web application into executing actions of the attacker’s choosing. If the victim is a normal user, a successful CSRF attack can force the user to perform state changing requests like transferring funds, changing their email address, and so forth. If the victim is an administrative account, CSRF can compromise the entire web application.

__what is hashing__
Hashing is **the process of transforming any given key or a string of characters into another value**. This is usually represented by a shorter, fixed-length value or key that represents and makes it easier to find or employ the original string.

__what is encryption__
Encryption is **the method by which information is converted into secret code that hides the information's true meaning**.

ssl vs tls
ssl use message authentication code/port to set up explicit connection
tls use hash based message authentication code/ protocol to set up implicit connection

what is threat
**What are threats?**

Threats have the potential to steal or damage data, disrupt business, or create harm in general. To keep that from happening, you need to know what [cyber threats](https://www.travasecurity.com/blog/top-5-cyber-threats-2021) exist. In general terms, there are three categories.   

-   **Intentional threats:** Things like malware, ransomware, phishing, malicious code, and wrongfully accessing user login credentials are all examples of intentional threats. They are activities or methods bad actors use to compromise a security or software system. 
-   **Unintentional threats:** Unintentional threats are often attributed to human error. For example, let’s say you forgot to lock the back door before leaving for work. While you’re at the office, a thief seizes the opportunity to sneak into your home and steal your valuables. Even though you didn’t mean to leave the door unlocked, the thief took advantage of your home’s vulnerability. In the cybersecurity industry, someone might leave the door to the IT servers unlocked or leave sensitive information unmonitored. An employee could forget to update their firewall or anti-virus software. Current and even former employees may also have unnecessary access to sensitive data, or simply be unaware of the threats. (Which is why [employee training](https://www.travasecurity.com/blog/how-to-protect-yourself-from-phishing-attacks) is so important.)
-   **Natural threats:** While acts of nature (floods, hurricanes, tornadoes, earthquakes, etc.) aren’t typically associated with cybersecurity, they are unpredictable and have the potential to damage your assets.

**What does risk mean?**

Cyber risk is the intersection of assets, threats, and vulnerabilities. It’s the _potential_ for loss, damage, or destruction of an asset when a threat takes advantage of a vulnerability. Put another way:   

Threats + Vulnerability = Risk

what is a DLP
Data loss prevention (DLP) **makes sure that users do not send sensitive or critical information outside the corporate network**. The term describes software products that help a network administrator control the data that users can transfer.

encryption
symmentric - DES(data encryption standard) / AES(advances encryption standard)
asymmetric - rsa, diffie-helmen