- Understanding the methods by which threat actors infiltrate networks and systems is essential for us to assess the attack surface of your network and deploy controls to block attack vectors
- ==Attack Surface and Threat Vectors==
	- The attack surface is all the points at which a malicious threat actor could try to exploit a vulnerability
	- Any location or method where a threat actor can interact with a network port, app, computer, or user is part of a potential attack surface.
	- Minimizing the attack surface means restricting access so only that a few known endpoints, protocols/ports, and services/methods are permitted.
	- To evaluate the attacker surface, consider the attributes of threat actors that pose the most risk to your organization
		- Attack surface of an external threat actor should be far smaller than that for an insider threat
			- Block off as much outside access as possible. Board up the ENTIRE house, not just the windows
	- Each part of the attack surface represents a potential vector for intrusion
	- A *threat vector* is the path that a threat actor uses to execute a data exfiltration, service disruption or disinformation attack.
		- Sophisticated threat actors will make use of multiple vectors
		- Likely to plan a multistage campaign, rather than single smash and grab
		- Highly capable threat actors will be able to develop novel vectors, meaning that the treat actors knowledge of your organization's attack surface may be better than your own.
- ==Vulnerable Software Vectors==
	- *Vulnerable Software* contains a flaw in its code or design that can be exploited to circumvent access control or the crash the process.
	- Typically vulnerabilities can only be exploited in specific circumstances
	- Due to complexity of modern software and the speed with which new versions must be released, almost no software is free from vulnerabilities.
	- An organization might not have an effective patch management system.
	- Large number of operating systems and applications run on a company's appliances, servers, clients and cloud networks directly increases the potential attack surface.
		- Can be consolidated by reducing to fewer products
	- Impact and consequences of a software vulnerability are varied.
	- **Unsupported Systems Applications**
		- *Unsupported systems* and applications are particular reason that vulnerably software will be exposed as a threat vector.
		- Unsupported system is one where its vendor no longer develops updates and patches
	- **Client-Based vs Agentless**
		- Scanning software helps organizations to automate the discovery and classification of software vulnerabilities
		- Tools can also be used by threat actors as a part of recon against a target
		- Agentless scanning is most likely to be used in threat actor recon.
- ==Network Vectors==
	- Vulnerable software give a threat actor the opportunity to execute malicious code onto a system.
	- The threat actor must be able to run exploit code on the system or over a network to trigger the vulnerability.
	- Exploit technique can be considered as:
		- Remote
			- Means that the vulnerability can be exploited by sending code to the target over a network and does not depend on an authenticated session with the system to execute.
		- Local
			- Means that the exploit code must be executed from an authenticated session
			- Could still occur over a network, but the threat actor needs to use some valid credentials or hijack an existing session to execute it
	- To minimize risks from software vulnerabilities, administrators must reduce attack surface by eliminating unsecure networks.
	- An *unsecure network* is one that LACKS the attributes of confidentiality, integrity, and availability.
		- Lack of Confidentiality
			- Threat actors are able to snoop on network traffic and recover passwords or other sensitive information
				- Also described as eavesdropping attacks
		- Lack of Integrity
			- threat actors are able to attach unauthorized devices
			- Devices can be used to:
				- Snoop traffic
				- Intercept and modify traffic
				- Run spoofed services
				- Run exploit code against other network hosts
			- Often described as on-path attacks
		- Lack of Availability
			- threat actors are able to perform service disruption attacks
			- Also called DoS attack
				- Denial of Service
	- A *secure* network uses an access control framework and cryptographic solutions to identify, authenticate, authorize, and audit network users, hosts and traffic
	- Special threat actors associated with unsecure networks are as follows:
		- Direct access
			- Threat actor uses physical access to the site to perpetrate an attack
		- Wired Network
			- A threat actor with access to the site attaches an unauthorized devices to a physical network port, and the device is permitted to communicate with other hosts
		- Remote and Wireless network
			- Attacker either obtains credentials for a remote access or wireless connection to the network or cracks the security protocols used for authentication.
			- Attacker spoofs a trusted recourse
		- Cloud Access
			- Many companies run part or all of the network services via Internet-accessible clouds.
			- Attacker only needs to find one account, service or host with weak credentials
		- Bluetooth network
			- Threat actor exploits a vulnerability or misconfiguration to transmit a malicious file to a users device over bluetooth
		- Default Credentials
			- Attacker gains control of a network device or app because it has been left configured with a default password
		- Open Service port
			- Threat actor is able to establish an unauthenticated connection to a logical TCP or UDP network
- ==Lure-Based Vectors==
	- A *lure* is something superficially attractive or interesting that causes its target to want it, even though it may be concealing something dangerous.
	- When the target opens the file bait, it delivers a malicious payload hook that will give the threat actor control over the system or perform service disruption.
	- A lure might trick a user into facilitating the attack.
	- The following are used as lures:
		- **Removable Devices**
			- Attacker conceals malware on a USB drive or memory card.
			- Tries to trick employees into connecting the media to their computer.
				- For some exploits, connecting the media will be enough to run the malware.
		- **Executable File**
			- Attacker conceals exploit code in a program file.
				- Ex. Trojan Horse
			- Trojan is a program that seems to be something free and useful or fun but contains a process that will create a backdoor
		- **Document Files**
			- Attacker conceals malicious code by embedding it in word processing and pdf format files.
		- **Image Files**
			- Attacker conceals exploit code within an image file that targets a vulnerability in browser or document editing software
	- These Vectors expose a large and diverse attack surface for the attacker.
	- Reducing this attack surface requires effective endpoint security management, using controls such as:
		- Vulnerability Management
		- Antivirus
		- Program Execution Control
		- Intrusion Detection
- ==Message-Based Vectors==
	- For a file-based lure. the threat actor needs a mechanism to deliver the file and a message that will trick a user into opening the file.
	- Any features that allow direct messaging to network users must be considered as part of the potential attack surface:
		- **Email**
			- Attacker sends a malicious file attachment via email or any other communications service that allows attachments.
			- Attacker needs to use social engineering techniques to trick the user into opening the attachment
		- **Short Message Service**
			- File or link to file is sent to mobile device using the text messaging handler built into smartphone firmware and protocol called *Signaling System*
			- SMS and the SS7 protocol are associated with numerous vulnerabilities.
			- Organizations are unlikely to monitor SMS
		- **Instant Messaging**
			- These can support voice and video messaging as well as file attachments.
			- Most are secured using encryption and offer more security than SMS.
			- Can still contain software vulnerabilities.
		- **Web and Social Media**
			- Malware may be concealed in files attached to posts or presented as downloads.
			- Attacker may compromise a site so that it automatically infects vulnerable browser software
				- Drive by Download
			- May also be used more subtly, such as disinformation campaign that persuades users to install *must have* app that is actually a Trojan
	- *Most powerful exploits are zero click*
	- Can also be exploited by a threat actor to persuade a user to reveal password or weaken the security configuration using some type of pretext.
- ==Supply Chain Attack Surface==
	- A *supply chain* is the end-to-end process of designing, manufacturing, and distributing goods and services to a consumer.
	- Rather than attacking the target directly, a threat actor will seek ways to infiltrate it via companies in its supply chain.
	- The process of ensuring reliable sources of equipment and software is called procurement management.
	- It is helpful to distinguish several types of relationships
		- **Supplier**
			- Obtains products directly from a manufacturer to sell in bulk to other businesses
		- **Vendor**
			- Obtains products from suppliers to sell to retail business or directly to customers
			- Might add some level of customization and direct support
		- **Business Partner**
			- Implies a closer relationship where two companies share quiet closely aligned goals and marketing opportunities.
	- Since Microsoft cannot establish direct relationships with all of their customers, to expand to markets the develop *partner relationships* with Original Equipment Manufacturers (OEM) and solution partners.
	- Each supplier and vendor has its own supply chain.
	- This supply chain breadth and complexity expose organizations to a huge attack surface.
		- Everyone involved must be trustworthy for the product to be trustworthy.
	- Anyone with the time and recourses to modify the computers firmware could create backdoor access.
	- Establishing a trusted supply chain for computer equipment and services essentially means denying malicious actors the time or recourses to modify the assets supplied.
	- It also depends on trade in services as well as physical assets
		- A Managed Services Provider (MSP) provisions and supports IT resources such as networks, security, or web infrastructure.
		- MSPs are useful when an organization finds it cheaper or more reliable to outsource all or part of IT provision rather than try to manage it directly.
			- **Security POV**: This type of outsourcing is complex as it can be difficult to monitor the MSP.
				- MSP's employees are all potential sources of insider threats
- ==Review==
	- A company uses stock photos from a site distributing copyright-free media to illustrate its websites and internal presentations. Subsequently, one of the company's computers is found infected with malware that was downloaded by code embedded in the headers of a photo file obtained from the site. What threat vector(s) does this attack use?
		- ==Image, which makes this a supply chain vulnerability==
	- A company's systems are disrupted by a ransomware attack launched via a vulnerability in a network monitoring tool used by the company's outsourced IT management. Aside from a software vulnerability, what part of the company's attack surface has been used as a threat vector?
		- ==MSP and Supply Chain==
	- A company uses cell phones to provide IT support to its remote employees, but it does not maintain an authoritative directory of contact numbers for support staff. Risks from which specific threat vector are substantially increased by this oversite?
		- ==Voice calls: the risk that threat actors could impersonate IT support personnel to trick employees into revealing confidential information or installing malware==
- 
