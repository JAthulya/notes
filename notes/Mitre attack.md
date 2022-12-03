__threat informed defence__ 
	threat intelligence analysis
		threat intelligence analysis is taking existing intelligence data like TTPs, malware hashes, or domain names and applying human intelligence to harden cyber defenses. this improves ways to anticipate, prevent, detect and respond to cyber attacks. 

	defensive engagement of the threat
		takes what you'v learned from intelligence analysis and allows you to look for indicators of a pending, active or successful cyber attack. breach and attack simulation (BAS) tools fit in well here. they take the behavioral models uncovered during intel analysis and use BAS to automate testing and reporting on what those behavior patterns look like in our enterprise.
	focused sharing and collaboration
		By sharing threat actor TTPs through standards such as STIX and TAXII, the security community benefits together. If you are part of a large organization with different security groups, information shared between groups in a standard format can help your enterprise build a threat informed defense.  

Groups like MITRE’s [Center for Threat Informed Defense (CTID)](https://mitre-engenuity.org/center-for-threat-informed-defense/) bring together sophisticated security teams from leading organizations around the world to expand the global understanding of adversary behaviors. They accomplish this by creating focus, collaboration, and coordination to accelerate innovation in threat-informed defense, building on the MITRE ATT&CK framework

_crist_
CRIST does handful of things that assist with intelligence analysis.
-   Collecting and archiving attack artifacts
-   Associating artifacts with stages of the cyber attack lifecycle
-   Conducting malware reverse engineering
-   Tracking environmental influences
-   Connecting all of this together to shape and prioritize defenses and react to incidents

Center for threat informed defense(CTID)
	Research areas of the CTID include:  

-   Advance global understanding of adversary tradecraft, e.g. expand ATT&CK into new technology domains like cloud
-   Measure evolving adversary behavior, e.g. establish a “most wanted” list of adversary techniques
-   Enable continuous assessment of our defenses, e.g. develop, share and automate adversary emulation playbooks
-   Continuously identify, catalyze the development of, and/or research new ways to thwart ATT&CK techniques across Protect, Detect & Respond All R&D outputs will be made globally available to maximize impact.

__what is metre__
	


Tactics, techniques, procedures
-   Tactics are the adversary’s technical goals.
-   Techniques are how those goals are achieved.
-   Procedures are specific implementations of techniques.

MITRE attack framework is a collection of techniques used by attackers.
	The MITRE ATT&CK Framework is a collection of techniques used by attackers during a breach. The ATT&CK Matrix breaks the techniques down into the following tactics:  
	
	-   **Initial Access** - Techniques that use various entry vectors to gain a foothold. Footholds gained through initial access may allow for continued access, like valid accounts and use of external remote services, or may be limited-use due to changing passwords.
	-   **Execution** - Techniques that result in adversary-controlled code running on a local or remote system. Techniques that run malicious code are often paired with techniques from all other tactics to achieve broader goals.
	-   **Persistence** - Techniques that adversaries use to keep access to systems across restarts, changed credentials and other interruptions that could cut off their access.  
	-   **Privilege Escalation** - Techniques that adversaries use to gain higher-level permissions on a system or network. The techniques often overlap with Persistence techniques.
	-   **Defense Evasion** - Techniques that adversaries use to avoid detection throughout their compromise.
	-   **Credential Access** - Techniques for stealing credentials, like account names and passwords.
	-   **Discovery** - Techniques an adversary use to gain knowledge about the system and internal network. Native operating system tools are often used toward this post-compromise information-gathering objective.  
	-   **Lateral Movement** - Techniques that adversaries use to enter and control remote systems on a network.
	-   **Collection** - Techniques adversaries use to gather information and the sources information is collected from that are relevant to following through on the adversary’s objectives.
	-   **Command and Control** - Techniques that adversaries use to communicate with systems under their control within a victim network.
	-   **Exfiltration** - Techniques that adversaries use to steal data from your network.
	-   **Impact** - Techniques that adversaries use to disrupt availability or compromise integrity by manipulating business and operations processes.


Mapping Organizational intel to attack
	If you have a more mature organization, there may be threat analysts in place who regularly review information about your adversaries. If you have access to previous incident reports, start mapping the tactics identified in the report to the MITRE ATT&CK matrix. Paragraph blocks may seem impossible to map back to ATT&CK, so MITRE has offered some suggestions for doing this.  
	
	1.  Understand ATT&CK—Familiarize yourself with the overall structure of ATT&CK:  
	    1.  Tactics - The adversary’s technical goals
	    2.  Techniques - How those goals are achieved
	    3.  Procedures - Specific implementations of techniques
	2.  Find the behavior—Think about the adversary’s action in a broader way than just the atomic indicator (like an IP address) used. For example, the malware in the above report “establishes a SOCKS5 connection.” The act of establishing a connection is a behavior the adversary took.
	3.  Research the behavior—If you’re not familiar with the behavior, you may need to do more research. In our example, a little research would show that SOCKS5 is a Layer 5 (session layer) protocol.
	4.  Translate the behavior into a tactic—Consider the adversary’s technical goal for that behavior and choose a tactic that fits. The good news: there are only 12 tactics to choose from in Enterprise ATT&CK. For the SOCKS5 connection example, establishing a connection to later communicate would fall under the Command and Control tactic.
	5.  Figure out what technique applies to the behavior—This can be a little tricky, but with your analysis skills and the ATT&CK website examples, it’s doable. If you search our website for SOCKS, the technique Standard Non-Application Layer Protocol (T1095) pops up. Looking at the technique description, you’ll find this could be where our behavior fits.
	6.  Compare your results to other analysts—Of course, you might have a different interpretation of a behavior than another analyst. This is normal, and it happens all the time on the ATT&CK team! We recommend comparing your ATT&CK mapping of information to another analyst’s and discussing any differences.

__Detection and analytics process__
1. collect data
2. analyze data
3. expand and customize

__Collect data__
	-   Process and process command line monitoring can be collected via Sysmon, Windows Event Logs, and many EDR platforms.
	-   File and registry monitoring is also often collected by Sysmon, Windows Event Logs, and many EDR platforms.
	-   Authentication logs collected from the domain controller.
	-   Packet capture, especially east/west capture, such as those collected between hosts and enclaves in your network.

Analyzing data
	Once you’ve identified the data that you need, collect it into some kind of search platform so that it can be analyzed. For most of you, this platform will be a SIEM. MITRE has provided additional guidance on what to look for in this analysis as well.
	
	**MITRE Cyber Analytics Repository (CAR)**  
	
	CAR ([https://car.mitre.org/](https://car.mitre.org/)) is a knowledge base of analytics developed by MITRE and is based on the MITRE ATT&CK adversary model. Analytics stored in CAR contain the following information for each analytic:  
	
	-   A hypothesis which explains the idea behind an analytic
	-   The information or primary domain the analytic is designed to operate within (this could be host, network, process, external, etc.)
	-   References to ATT&CK Techniques and Tactics that the analytic detects
	-   The Glossary
	-   A pseudocode description of how the analytic might be implemented
	-   A unit test which can be run to trigger the analytic
	
	By reviewing the data presented in MITRE CAR, you can begin to not only analyze the behaviors occurring in your enterprise but also begin to expand on your threat intelligence data by mapping these behaviors back to MITRE ATT&CK.
	
	In our Foundations of Breach & Attack Simulation course, we discuss creating test plans based on your defenses. CAR can assist in creating test plans by providing unit tests that trigger alerts or analytics.

mitre car analytics 


