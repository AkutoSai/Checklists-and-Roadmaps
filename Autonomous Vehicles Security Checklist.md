# Comprehensive Checklist for  Autonomous Vehicle Security

## Firmware and Software:
   - [ ] Firmware and software updates are essential to address security vulnerabilities and improve the performance of smart cars. Keeping the firmware and software up to date ensures that the latest security patches and bug fixes are applied.
   - [ ] Manufacturers regularly release updates, so it's crucial to check for new updates and apply them promptly. These updates may address vulnerabilities, enhance system stability, or introduce new features.
   - [ ] Compatibility between software versions and hardware components is important to ensure smooth functioning. Verify that the software version you're using is suitable for the specific smart car model and its components.

## Authentication and Access Control:
   - [ ] Strong authentication mechanisms are crucial to prevent unauthorized access to the smart car's systems. This can include passwords, biometrics (such as fingerprint or facial recognition), or multifactor authentication.
   - [ ] Assess the strength of the authentication methods in place. Passwords should be complex, unique, and regularly changed. Biometric systems should use reliable and accurate sensors.
   - [ ] Access control mechanisms should limit access to critical systems and data. Ensure that appropriate access controls are implemented, granting privileges only to authorized individuals or entities.
   - [ ] Test the strength of authentication mechanisms such as passwords, biometrics, or multifactor authentication. Verify if weak passwords can be easily bypassed or if biometric systems can be fooled.
   - [ ] Attempt to bypass the authentication process through various techniques like brute-forcing, credential stuffing, or exploiting weak authentication protocols.
   - [ ] Test for any default or hardcoded credentials that could provide unauthorized access to the smart car's systems.

## Network Connectivity:
   - [ ] Smart cars often have various connectivity options like Wi-Fi, Bluetooth, cellular networks, or external ports. Each of these connections can introduce potential security risks.
   - [ ] Disable any network connections that are not required or likely to be vulnerable. For example, if the smart car doesn't utilize Wi-Fi or Bluetooth features, it's best to turn them off.
   - [ ] Securely configure active network connections. Use encryption (e.g., WPA2 for Wi-Fi) and strong authentication protocols to safeguard data transmitted over the network.
   - [ ] Conduct penetration testing to identify vulnerabilities in network connections like Wi-Fi, Bluetooth, or cellular networks.
   - [ ] Test the effectiveness of encryption protocols used in the network connections. Try to intercept and analyze network traffic to identify any potential weaknesses.
   - [ ] Perform a vulnerability scan to check for open ports, misconfigurations, or potential entry points for attackers.

## Data Protection:
   - [ ] Smart cars handle and store sensitive data, including personal information about users, their driving habits, and potentially geolocation data. It's essential to protect this data from unauthorized access.
   - [ ] Encryption is a critical aspect of data protection. Ensure that data is encrypted both during transmission (e.g., over networks) and at rest (e.g., stored on internal memory or external devices).
   - [ ] Assess mechanisms for securely wiping data from storage, such as when selling or decommissioning the smart car. Secure data deletion helps prevent data leakage and potential misuse.
   - [ ] Test the encryption mechanisms used for sensitive data transmission and storage. Verify if encryption is implemented correctly and data remains protected during transit and at rest.
   - [ ] Attempt to access and extract sensitive data from storage, such as personally identifiable information (PII), geolocation data, or driving behavior data.
   - [ ] Test the effectiveness of data wiping or deletion mechanisms to ensure that data is completely removed when required, such as when selling or decommissioning the smart car.

## Over-the-Air (OTA) Updates:
   - [ ] Inspect the OTA update mechanism used by the smart car.
   - [ ] Check that the updates are delivered securely, using encryption and authentication.
   - [ ] Verify that the OTA process includes integrity checks to ensure the updates haven't been tampered with.

## Remote Access:
   - [ ] Assess the remote access capabilities of the smart car, such as mobile apps or web interfaces.
   - [ ] Review the security measures in place for remote access, including strong authentication and encryption.
   - [ ] Disable or limit remote access features if they are not needed or deemed insecure.
   - [ ] Evaluate the security of remote access features, such as mobile apps or web interfaces. Test for vulnerabilities in authentication, session management, or data transmission.
   - [ ] Attempt to exploit any security weaknesses in the remote access systems to gain unauthorized control over the smart car.
   - [ ] Test the robustness of security controls like rate limiting, account lockouts, or intrusion detection systems to prevent unauthorized access.
   - [ ] Test the security of remote communication channels such as mobile apps, web interfaces, or APIs.
   - [ ] Verify if encryption is implemented correctly for remote communication.
   - [ ] Test for vulnerabilities in the authentication and session management mechanisms of remote communication systems.
   - [ ] Attempt to intercept and manipulate communication between the smart car and remote systems.

## Vulnerability Management:
   - [ ] Conduct regular vulnerability scans and penetration tests to identify weaknesses in the smart car's systems.
   - [ ] Establish a process for promptly applying security patches and updates to address any discovered vulnerabilities.
   - [ ] Stay informed about the latest security threats and advisories related to smart car technologies.
   - [ ] Assess the smart car's software for vulnerabilities, such as buffer overflows, SQL injections, or insecure data handling.
   - [ ] Perform static and dynamic code analysis to identify potential security flaws or coding errors that could be exploited.
   - [ ] Test the resistance of the software against common attack vectors like Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), or Remote Code Execution (RCE).
   
## CAN Bus Security Testing:
   1. Message Injection:
      - [ ] Send malformed or invalid CAN messages to test the system's resilience against message spoofing or unauthorized command execution.
      - [ ] Inject messages with altered source addresses or modified data payloads to assess the system's ability to detect and reject unauthorized messages.
   
   2. Bus Off Recovery:
      - [ ] Flood the CAN bus with a high volume of messages to test the system's response and recovery mechanisms.
      - [ ] Observe how the system handles bus errors, performs error recovery, and resumes normal operations.

   3. Replay Attacks:
      - [ ] Capture legitimate CAN bus messages and replay them to test if the system is vulnerable to unauthorized message playback.
      - [ ] Assess the system's ability to detect and prevent replayed messages from causing unintended actions or compromising security.

   4. Bus Monitoring:
      - [ ] Deploy a monitoring tool to analyze CAN bus traffic for anomalies, such as unexpected or unauthorized messages.
      - [ ] Identify abnormal communication patterns, unknown devices, or suspicious message content.
   
   5. ECU Authentication:
      - [ ] Verify that only authorized ECUs are allowed to communicate on the CAN bus.
      - [ ] Test the system's authentication mechanisms, such as digital signatures, cryptographic protocols, or secure key exchanges.
   
   6. Data Integrity and Confidentiality:
      - [ ] Modify CAN messages to test the system's ability to detect and prevent data tampering.
      - [ ] Evaluate encryption mechanisms for protecting sensitive data transmitted over the CAN bus.
   
   7. Bus Isolation:
      - [ ] Assess the system's ability to isolate critical components or ECUs from potentially compromised or less critical ones.
      - [ ] Test if an attack on one ECU can be contained and prevented from affecting the entire CAN bus network.

   8. Bus Load Analysis:
      - [ ] Test the system's performance and resilience under different bus load conditions.
      - [ ] Assess the impact of high message traffic on the system's security features and overall functionality.
   
   9. Error Handling and Fault Tolerance:
      - [ ] Introduce deliberate errors into CAN messages to test the system's error handling and fault tolerance mechanisms.
      - [ ] Verify that error conditions are properly detected, reported, and recovered from without compromising security.
   
  10. Denial-of-Service (DoS) Resilience:
      - [ ] Test the system's resistance against DoS attacks targeting the CAN bus.
      - [ ] Assess if the system can continue operating correctly and reject malicious or excessive messages.

  11. Network Segmentation:
      - [ ] Evaluate the effectiveness of network segmentation measures to isolate critical CAN bus segments from less secure areas.
      - [ ] Test if unauthorized access to one network segment can be prevented from affecting other segments.
   
  12. Secure Configuration Management:
      - [ ] Test the system's configuration management processes, ensuring that default passwords, insecure settings, or misconfigurations are addressed.
      - [ ] Verify that secure configuration practices are followed throughout the lifecycle of the CAN bus system.
   
  13. Redundancy and Failover Testing:
      - [ ] Test redundant CAN bus architectures and failover mechanisms to ensure seamless operation and data integrity in case of component failures or attacks.
   
## Infotainment System Testing:

   - [ ] Test for vulnerabilities in the smart car's infotainment system, including multimedia playback, navigation, and connectivity features.
   - [ ] Verify if the system is isolated from critical car functionalities to prevent potential attacks on safety-critical systems.
   - [ ] Test for vulnerabilities in Bluetooth, Wi-Fi, or cellular connectivity that could allow unauthorized access or data leakage.

## Sensor and Camera Security Testing:

   - [ ] Test for vulnerabilities in sensors and cameras used in smart cars, such as LiDAR, radar, or cameras for assisted driving or autonomous features.
   - [ ] Verify if the sensors and cameras can be manipulated or spoofed to provide false inputs to the smart car's systems.
   - [ ] Test for potential privacy risks associated with the collection and transmission of sensor and camera data.
   
## Reverse Engineering

   1. Goals and Objectives
      - [ ] Clearly define the goals and objectives of the reverse engineering process for the smart car.
      - [ ] Determine the specific aspects of the smart car's technology, systems, or components that need to be analyzed.

   2. Legal and Ethical Considerations
      - [ ] Ensure that reverse engineering activities comply with relevant laws, regulations, and intellectual property rights.
      - [ ] Obtain necessary permissions or legal agreements from the smart car manufacturer or relevant stakeholders.

   3. Documentation and Research
      - [ ] Gather available documentation, manuals, technical specifications, and any other relevant information about the smart car's architecture and components.
      - [ ] Conduct research to understand the underlying technologies, protocols, and standards used in the smart car.

   4. Tools and Equipment
      - [ ] Identify and prepare the necessary tools and equipment for the reverse engineering process, such as:
         - **Hardware Tools:** JTAG debuggers, logic analyzers, oscilloscopes, multimeters and HackRF.
         - **Software Tools:** IDA Pro, Ghidra, Binwalk, Wireshark, Bus Pirate and CAN bus analyzers.
         - **Programming Tools:** Python, C/C++ and assembly language.
         - **Hardware Interfaces:** JTAG adapters, CAN bus interfaces and USB-to-serial converters.
  
   5. Physical Inspection
      - [ ] Perform a thorough physical inspection of the smart car, examining its hardware components, connectors, circuit boards, and wiring.
      - [ ] Take detailed photographs or create diagrams to document the physical layout and connections.

   6. System Identification
      - [ ] Identify the different systems and subsystems present in the smart car, such as the infotainment system, engine control unit, braking system, or sensor modules.
      - [ ] Determine the communication protocols and interfaces used for inter-system communication.

   7. Reverse Engineering of Firmware and Software
      - [ ] Extract firmware and software from the smart car's systems for analysis.
      - [ ] Disassemble and decompile the firmware and software to understand their structure, functions, and algorithms.
      - [ ] Use tools like IDA Pro, Ghidra, or Binwalk for reverse engineering the firmware and software.

   8. Protocol Analysis
      - [ ] Capture and analyze network traffic between different components or systems of the smart car.
      - [ ] Identify the protocols and data formats used for communication, such as CAN bus, LIN bus, Ethernet, or wireless protocols.
      - [ ] Use tools like Wireshark, Bus Pirate, or CAN bus analyzers to analyze the network traffic and reverse engineer protocols.
      - [ ] Assess the security of wireless protocols used for vehicle-to-vehicle (V2V) and vehicle-to-infrastructure (V2I) communication, such as Dedicated Short-Range Communications (DSRC) or Cellular Vehicle-to-Everything (C-V2X).
      - [ ] Verify that protocols are hardened against common attacks such as Denial-of-Service (DoS), replay attacks, or Man-in-the-Middle (MitM) attacks.
      - [ ] Assess the implementation of secure key exchange protocols, such as Diffie-Hellman or Elliptic Curve Cryptography (ECC), to ensure secure communication and encryption key generation.
      - [ ] Verify the integrity and authenticity of sensor data transmitted through these protocols.

   9. Data Analysis
      - [ ] Identify and analyze data stored within the smart car's systems, such as configuration files, logs, or diagnostic data.
      - [ ] Reverse engineer file formats, encryption schemes, or compression algorithms used for data storage.
      - [ ] Use scripting languages like Python to extract and interpret meaningful information from the data.

  10. Security Analysis
      - [ ] Assess the security mechanisms implemented in the smart car, including authentication, access control, encryption, or intrusion detection.
      - [ ] Identify potential vulnerabilities, weaknesses, or attack vectors in the smart car's systems or software.
      - [ ] Conduct security testing and analysis using tools like fuzzers, static analysis tools, or penetration testing frameworks.

  11. Documentation and Reporting
      - [ ] Document all findings, observations, and insights gained during the reverse engineering process.
      - [ ] Create detailed reports that outline the smart car's architecture, components, protocols, security vulnerabilities, and recommendations for improvement.
      - [ ] Prepare clear and concise documentation that can be shared with relevant stakeholders or the smart car manufacturer.

  12. Responsible Disclosure
      - [ ] Follow responsible disclosure practices when reporting identified vulnerabilities or weaknesses to the smart car manufacturer or relevant security organizations.
      - [ ] Collaborate with the smart car manufacturer to address and remediate the identified security issues.

## Malware and Intrusion Detection Testing:

   - [ ] Test the smart car's resistance to malware or intrusion attempts.
   - [ ] Attempt to install and execute malicious software on the smart car's systems.
   - [ ] Test the effectiveness of intrusion detection and prevention mechanisms in detecting and responding to potential threats.

## Physical Security:
   - [ ] Evaluate the physical security measures of the smart car.
   - [ ] Ensure that physical access to critical components, such as the diagnostic port or electronic control units (ECUs), is restricted.
   - [ ] Assess the effectiveness of anti-theft mechanisms, such as immobilizers and tracking systems.
   - [ ] Evaluate the physical security measures of the smart car, including access to critical components like the diagnostic port or ECUs.
   - [ ] Test the effectiveness of anti-theft mechanisms like immobilizers or tracking systems to ensure they cannot be easily bypassed or tampered with.
   - [ ] Verify if physical tampering or manipulation of the smart car's components can lead to unauthorized access or control.
   - [ ] Assess the physical security measures of the smart car, such as keyless entry systems, immobilizers, or alarm systems.
   - [ ] Test for vulnerabilities in keyless entry systems, including relay attacks or signal interception.
   - [ ] Verify if physical tampering or manipulation of components can lead to unauthorized access or control over the smart car.
   
## Governance & Management (UN R155 & ISO 21434\)**

*Focus: Organizational processes, CSMS, and Supply Chain.*

* \[ \] **Organizational Cybersecurity Management (Clause 5\)**  
  * \[ \] **Cybersecurity Policy:** Confirm a policy exists acknowledging cybersecurity as a priority.  
  * \[ \] **Rules & Processes:** Verify processes are defined for all lifecycle phases (concept to decommissioning).  
  * \[ \] **Competence Management:** Ensure personnel have documented training/competence in automotive security.  
  * \[ \] **Audit Trails:** Confirm a continuous improvement process (Management Systems Audit) is active.  
* \[ \] **Project Dependent Management (Clause 6\)**  
  * \[ \] **Cybersecurity Plan:** Define roles, responsibilities, and dependency management for the specific project.  
  * \[ \] **Reuse Analysis:** Analyze carry-over parts (legacy ECUs) for security gaps against modern standards.  
  * \[ \] **Cybersecurity Case:** Maintain a living repository of all security work products (TARA, requirements, validation reports).  
  * \[ \] **Release for Post-Development:** Confirm security acceptance criteria are met before release.  
* \[ \] **Distributed Cybersecurity Activities (Clause 7 \- Supply Chain)**  
  * \[ \] **CIA Agreements:** Verify Cybersecurity Interface Agreements (CIAD) are signed with all Tier-1 suppliers.  
  * \[ \] **Supplier Capability:** Check evidence of supplier's own CSMS (e.g., TISAX assessment or ISO 21434 audit).  
  * \[ \] **Alignment:** Ensure supplier security activities are aligned with the OEM's Cybersecurity Plan.  
  * \[ \] **SBOM Management:** Ensure Software Bill of Materials (SBOM) is collected for all 3rd party libraries to track CVEs.  
* \[ \] **Third-Party Assessments**  
  * \[ \] **Independent Audits:** Engage third-party experts to perform independent audits of the security posture.  
  * \[ \] **Bug Bounty:** Consider bug bounty programs to incentivize external researchers to report vulnerabilities.

## Threat Analysis & Risk Assessment (TARA \- ISO 21434 Clause 15\)**

*Focus: Risk identification and CAL determination.*

* \[ \] **Asset Identification (Clause 15.3)**  
  * \[ \] **Data Assets:** Keys, PII, Calibration Data, Logs, Maps, Biometric templates.  
  * \[ \] **Functional Assets:** Braking, Steering, Acceleration, Battery Management, ADAS perception, Driver Monitoring.  
* \[ \] **Threat Scenario Identification (Clause 15.5)**  
  * \[ \] Map threats to damage scenarios (e.g., "Unintended braking", "Privacy leak", "Fleet-wide ransom").  
* \[ \] **Impact Rating (Clause 15.6)**  
  * \[ \] **Safety (SF):** Map to ISO 26262 ASIL levels (e.g., SF impacts \> ASIL B require stricter controls).  
  * \[ \] **Privacy (PM):** Assess impact of location tracking, voice recording, or camera feed interception.  
  * \[ \] **Financial (FM) & Operational (OM):** Rate impacts on fleet operations and recall costs.  
* \[ \] **Attack Path Analysis (Clause 15.7)**  
  * \[ \] **Attack Feasibility:** Evaluate based on Time, Expertise, Knowledge, Window of Opportunity, and Equipment.  
* \[ \] **Risk Determination (Clause 15.8)**  
  * \[ \] **Risk Value:** Classify risk (1-5) based on Impact vs. Feasibility matrix.  
* \[ \] **Risk Treatment Decision (Clause 15.9)**  
  * \[ \] **Treatment Options:** Select Avoid, Mitigate, Share/Transfer, or Accept.  
  * \[ \] **Cybersecurity Goals:** Define high-level goals for treated risks (e.g., "Prevent spoofing of braking commands").  
  * \[ \] **Cybersecurity Claims:** Document rationale for any "Risk Acceptance" (must be signed by mgmt).

## System Design & Architecture (Trust Anchors)**

*Focus: Hardware security foundations.*

* \[ \] **Secure Boot & Root of Trust (RoT)**  
  * \[ \] **Immutable RoT:** Verify the first instruction runs from immutable memory (Boot ROM).  
  * \[ \] **Public Key Storage:** Ensure Root Public Key hash is burned into OTP (One-Time Programmable) fuses.  
  * \[ \] **Fallback Mechanism:** Define behavior if verification fails (e.g., stay in Bootloader, do not boot OS).  
  * \[ \] **JTAG/Debug Lockdown:** Confirm JTAG is disabled via fuses in production (or protected by strong challenge-response).  
* \[ \] **Hardware Security Module (HSM) / Secure Enclave**  
  * \[ \] **Isolation:** Verify HSM runs on a dedicated core with private RAM/Flash.  
  * \[ \] **Side-Channel Protection:** Check resistance against DPA (Differential Power Analysis) and SPA.  
  * \[ \] **Secure Time:** Verify HSM manages a secure monotonic counter/timer (prevent rollback/replay).  
  * \[ \] **Crypto Primitives:** Ensure hardware acceleration for AES, ECC (P-256/Ed25519), and SHA-2/3.  
* \[ \] **Memory Protection**  
  * \[ \] **MPU/MMU:** Verify memory partitioning between Safety, Security, and App domains.  
  * \[ \] **ASLR/NX:** Ensure Address Space Layout Randomization and No-Execute bits are active.

## Cryptographic Implementation (AUTOSAR & Key Mgmt)**

*Focus: Crypto stack and lifecycle management.*

* \[ \] **AUTOSAR Crypto Stack**  
  * \[ \] **CSM (Crypto Service Manager):** Verify asynchronous job processing priority (Safety \> Entertainment).  
  * \[ \] **CryIf (Interface):** Ensure proper channel mapping to hardware (HSM) vs software primitives.  
  * \[ \] **KeyM (Key Manager):** Verify certificate parsing and key verification logic.  
* \[ \] **Key Lifecycle Management**  
  * \[ \] **Generation:** Keys generated on-board must use a TRNG (AIS-31 compliant).  
  * \[ \] **Injection:** Production keys must be injected in a secure environment (clean room) or via HSM-based secure provisioning.  
  * \[ \] **Storage:** Keys must never be in source code or plain text flash. Use HSM slots or encrypted key blobs (shielded by a master key).  
  * \[ \] **Destruction:** Verify "Factory Reset" securely wipes user data and ephemeral keys.  
* \[ \] **Algorithms & Suites**  
  * \[ \] **Symmetric:** AES-128/256 (GCM for auth-enc, CBC with HMAC). Avoid ECB.  
  * \[ \] **Asymmetric:** ECC (NIST P-256, Brainpool) for resource-constrained ECUs; RSA-2048/4096 for powerful nodes.  
  * \[ \] **Hashing:** SHA-256 or SHA-3. Avoid SHA-1 and MD5.

## In-Vehicle Network Security (SecOC & Ethernet)**

*Focus: Protecting CAN, LIN, and Automotive Ethernet.*

* \[ \] **Secure Onboard Communication (SecOC)**  
  * \[ \] **Freshness:** Verify implementation of Freshness Value Manager (FVM) (Timestamp or Counter based).  
  * \[ \] **MAC Truncation:** Ensure truncated MAC (e.g., 24 bits) provides sufficient collision resistance for the bus load.  
  * \[ \] **Data ID:** Verify binding of MAC to the specific Message ID to prevent masquerading.  
* \[ \] **Automotive Ethernet Security**  
  * \[ \] **VLAN Segmentation:** Separate Infotainment, Telematics, and Safety critical traffic.  
  * \[ \] **Firewalling:** Implement ingress/egress filtering on the Gateway Switch.  
  * \[ \] **SOME/IP Security:** Use TLS or DTLS for service-oriented communication.  
  * \[ \] **MACsec:** Enable IEEE 802.1AE (MACsec) for link-layer encryption if hardware supports it.  
* \[ \] **Intrusion Detection System (IDS)**  
  * \[ \] **IdsM (IDS Manager):** Verify reporting of "Smart Sensors" (reporting security events) to the IdsM.  
  * \[ \] **Heuristics:** Check for checks on message frequency, payload range, and invalid sequence IDs.  
* \[ \] **CAN Bus Penetration Testing (Detailed)**  
  * \[ \] **Message Injection:** Send malformed/invalid messages to test resilience against spoofing.  
  * \[ \] **Bus Off Recovery:** Flood the bus to test error recovery and resumption of normal operations.  
  * \[ \] **Replay Attacks:** Capture and replay legitimate messages to test protection (Freshness/Counter checks).  
  * \[ \] **Bus Monitoring:** Deploy tools to analyze traffic for anomalies, unknown devices, or suspicious payloads.  
  * \[ \] **ECU Authentication:** Verify only authorized ECUs communicate; test digital signatures/secure key exchanges.  
  * \[ \] **Data Integrity:** Modify CAN payloads to test if the system detects tampering (MAC checks).  
  * \[ \] **Bus Isolation:** Test if an attack on one ECU (e.g., Infotainment) is contained from Safety CAN.  
  * \[ \] **Bus Load Analysis:** specific test of security features under high bus load conditions.  
  * \[ \] **Error Handling:** Introduce deliberate errors to test fault tolerance without security compromise.  
  * \[ \] **DoS Resilience:** Test resistance against Denial-of-Service targeting the CAN bus.  
  * \[ \] **Network Segmentation:** Evaluate isolation between critical and non-critical segments.  
  * \[ \] **Redundancy:** Test failover mechanisms for data integrity during component failures.

## Diagnostics & Ports (UDS & OBD-II)**

*Focus: Access control for maintenance interfaces.*

* \[ \] **UDS Security (ISO 14229\)**  
  * \[ \] **Service 0x27 (Security Access):**  
    * \[ \] **Entropy:** Seeds must be random (TRNG). Fixed seeds are a critical fail.  
    * \[ \] **Delay:** Enforce 10s+ delay after 3 failed attempts.  
    * \[ \] **Levels:** Segregate "Read Only", "Write", and "Reprogramming" privileges.  
  * \[ \] **Service 0x29 (Authentication):** Implement certificate-based auth for modern architectures (PKI based).  
  * \[ \] **Service Routing:** Ensure the Gateway blocks critical UDS commands (e.g., ECU Reset, Write Memory) routed from OBD-II to Safety CAN while driving.  
* \[ \] **Physical Ports & Security**  
  * \[ \] **OBD-II Firewall:** The gateway must filter raw CAN frames from the OBD port unless an authenticated session is active.  
  * \[ \] **USB/Ethernet Ports:** Disable auto-mount and auto-run features on IVI ports.  
  * \[ \] **Anti-Theft:** Assess immobilizers and tracking systems; ensure they cannot be easily bypassed.  
  * \[ \] **Access Restriction:** Restrict physical access to critical ECUs and diagnostic ports.

## Connectivity & V2X Security**

*Focus: Wireless interfaces and vehicle-to-everything.*

* \[ \] **V2X / V2G (Vehicle-to-Grid)**  
  * \[ \] **IEEE 1609.2:** Verify usage of geometric/region-specific certificates.  
  * \[ \] **Pseudonymity:** Ensure certificates rotate frequently (e.g., every 5 mins or 1km) to prevent tracking.  
  * \[ \] **Misbehavior Detection:** Verify vehicle validates received Basic Safety Messages (BSM) for plausibility (position/speed consistency).  
  * \[ \] **ISO 15118 (Plug & Charge):** Verify TLS mutual authentication between Vehicle (EVCC) and Charger (SECC).  
* \[ \] **Telematics & Cloud**  
  * \[ \] **APN:** Use a private APN for vehicle telemetry; do not use public internet addresses for ECUs.  
  * \[ \] **Mutual TLS (mTLS):** Vehicle and Cloud must authenticate each other via certificates.  
  * \[ \] **SMS:** Disable SMS-based commands or require cryptographic signatures in the payload.  
* \[ \] **Remote Access & Mobile Apps**  
  * \[ \] **App Security:** Test mobile apps/web interfaces for auth vulnerabilities, session management, and data transmission.  
  * \[ \] **Credential Stuffing:** Test against automated login attempts using stolen credentials.  
  * \[ \] **Robustness:** Test rate limiting, account lockouts, and intrusion detection on remote endpoints.  
  * \[ \] **Communication Channels:** Verify encryption and integrity of APIs used for remote control (unlock/start).  
  * \[ \] **Exploitation:** Attempt to exploit remote access to gain unauthorized control.

## Software Updates (OTA & SUMS)**

*Focus: Safe and secure updates.*

* \[ \] **Uptane Framework / UN R156**  
  * \[ \] **Separation of Duties:** Verify separation between "Image Repository" and "Director Repository".  
  * \[ \] **Metadata Verification:** ECU must verify root metadata (signatures from multiple offline keys) before trusting the update.  
  * \[ \] **Time Server:** Ensure secure time source to prevent "Freeze" attacks (forcing vehicle to use old, vulnerable software).  
* \[ \] **Update Process**  
  * \[ \] **Rollback:** Automatic rollback to previous slot (A/B partitioning) if the new image fails to boot/authenticate.  
  * \[ \] **Pre-conditions:** Check for "Vehicle Stopped", "Gear in Park", "Battery \> X%" before flashing.  
  * \[ \] **Compatibility:** Verify new software version compatibility with existing hardware components.

## Operating System Hardening (Linux / Android / QNX)**

*Focus: High-compute nodes (IVI, ADAS).*

* \[ \] **Filesystem & Data Protection**  
  * \[ \] **dm-verity:** Read-only root filesystem with integrity verification.  
  * \[ \] **Encryption:** User data partition (contacts, logs) must be encrypted (e.g., fscrypt/LUKS).  
  * \[ \] **Data Wiping:** Verify secure data deletion mechanisms for decommissioning/selling.  
* \[ \] **Access Control**  
  * \[ \] **SELinux / AppArmor:** Enforce Mandatory Access Control (MAC) policies. No process runs as unconfined root.  
  * \[ \] **Capabilities:** Drop unused Linux capabilities (e.g., CAP\_SYS\_ADMIN) for services.  
  * \[ \] **Sandboxing:** Run infotainment apps in containers or restricted users.  
* \[ \] **Kernel**  
  * \[ \] **Config:** Disable kernel module loading after boot (CONFIG\_MODULE\_SIG\_FORCE).  
  * \[ \] **Syscalls:** Filter syscalls using seccomp-bpf.  
* \[ \] **Infotainment Isolation**  
  * \[ \] Verify IVI is isolated from critical car functionalities to prevent lateral movement to safety systems.

## Automotive SPICE & Testing (Verification)**

*Focus: Process and validation.*

* \[ \] **Static Analysis (SAST)**  
  * \[ \] **MISRA C/C++:** Verify compliance with MISRA coding standards (no undefined behaviors).  
  * \[ \] **CERT C:** Check against CERT secure coding rules.  
  * \[ \] **Code Analysis:** Scan for buffer overflows, SQL injections, and insecure data handling.  
* \[ \] **Dynamic Analysis (DAST) & Vulnerability Mgmt**  
  * \[ \] **Fuzzing:** Fuzz all external interfaces (CAN, Ethernet, Wi-Fi, Bluetooth, USB).  
  * \[ \] **Penetration Testing:** Conduct grey-box testing on the final integration level.  
  * \[ \] **Web Vectors:** Test against XSS, CSRF, RCE if web interfaces are present.  
  * \[ \] **Malware:** Test resistance to malware injection and execution on the system.  
  * \[ \] **Scanning:** Conduct regular vulnerability scans for open ports and misconfigurations.  
* \[ \] **Traceability**  
  * \[ \] Verify every Security Goal \-\> Functional Requirement \-\> Technical Requirement \-\> Test Case.

## AI & Machine Learning Security (Autonomous Driving)**

*Focus: Adversarial Machine Learning and Model Integrity.*

* \[ \] **Adversarial Robustness**  
  * \[ \] **Perturbation Testing:** Test perception models against digital perturbations (noise) and physical patches (e.g., stickers on stop signs).  
  * \[ \] **Data Poisoning:** Verify integrity of the training dataset to prevent backdoor injection.  
* \[ \] **Model Security**  
  * \[ \] **Model Extraction:** Protect the model weights (intellectual property) using encryption and TEEs.  
  * \[ \] **Input Validation:** Implement plausibility checks on inference outputs (e.g., "Car cannot move sideways instantly").

## Sensor Security (Physics Layer)**

*Focus: Hardware attacks on LiDAR, Radar, and Cameras.*

* \[ \] **Jamming & Saturation**  
  * \[ \] **LiDAR/Radar:** Verify system detects saturation/blinding attacks and enters a safe degradation mode.  
  * \[ \] **Camera:** Check behavior when cameras are blinded by lasers or strong light sources.  
* \[ \] **Spoofing (Relay Attacks)**  
  * \[ \] **Radar:** Test resilience against signal replay (ghost object generation).  
  * \[ \] **GPS/GNSS:** Ensure system cross-checks GPS location with wheel odometry and IMU to detect spoofing.  
  * \[ \] **Time Spoofing:** Ensure GNSS time is validated before being used for certificate expiration checks.  
* \[ \] **Sensor Fusion & Privacy**  
  * \[ \] **Consistency Check:** Verify that the fusion layer flags discrepancies (e.g., Camera sees object, LiDAR does not) as potential attacks.

## Privacy & Data Compliance (GDPR / CCPA)**

*Focus: Handling of PII and user consent.*

* \[ \] **Consent Management**  
  * \[ \] **Opt-in/Opt-out:** Verify UI allows users to manage data collection consent (e.g., telemetry, location).  
  * \[ \] **Right to Erasure:** Ensure a mechanism exists to delete all user data upon request or vehicle reset.  
* \[ \] **Data Minimization**  
  * \[ \] **Face Blurring:** Verify cameras blur faces/license plates before uploading data to the cloud.  
  * \[ \] **Anonymization:** Ensure telemetry data is decoupled from the VIN or User ID where possible.  
* \[ \] **Biometrics (Driver Monitoring)**  
  * \[ \] **Template Storage:** Biometric templates (face/fingerprint) must be stored in secure elements, never raw.  
  * \[ \] **Liveness Detection:** Test biometric systems against spoofing (photos, masks, silicone fingers).

## Backend & Fleet Management Security**

*Focus: The cloud infrastructure controlling the AV fleet.*

* \[ \] **Fleet Command Security**  
  * \[ \] **Command Authentication:** Every remote command (e.g., "Unlock", "Summon") must be signed and authorized.  
  * \[ \] **Rate Limiting:** Prevent mass-execution of commands (e.g., stopping 1000 cars simultaneously).  
* \[ \] **Cloud Infrastructure**  
  * \[ \] **API Security:** Secure API Gateways with OAuth2/OIDC and strict scope validation.  
  * \[ \] **Container Security:** Scan Docker/Kubernetes images for vulnerabilities; enforce least privilege.

## Forensics & Event Data Recorder (EDR)**

*Focus: Post-incident investigation integrity.*

* \[ \] **EDR Integrity**  
  * \[ \] **Write Protection:** Ensure crash data cannot be overwritten or deleted by the user or malware.  
  * \[ \] **Data Signing:** EDR logs should be digitally signed to prove they haven't been tampered with post-crash.  
* \[ \] **Retrieval Port**  
  * \[ \] **Access Control:** Physical retrieval via OBD/CDR tool requires authentication (Service 0x27).

## Hardware Attacks (Fault Injection & Side Channels)**

*Focus: Physical attacks on the PCB/Chips.*

* \[ \] **Fault Injection (FI)**  
  * \[ \] **Voltage Glitching:** Test ECU resilience against voltage drops intended to bypass boot checks.  
  * \[ \] **Clock Glitching:** Test resilience against clock manipulation.  
  * \[ \] **Laser FI:** (For high-security chips) verify shields/sensors against laser injection.  
* \[ \] **Physical Tampering**  
  * \[ \] **Anti-Tamper Mesh:** Check for active mesh on PCB to detect drilling/probing.  
  * \[ \] **Epoxy/Potting:** Verify critical components are potted to resist removal/probing.

## Production & Post-Production (Clauses 12 & 14\)**

*Focus: Manufacturing and End-of-Life.*

* \[ \] **Secure Manufacturing (Clause 12\)**  
  * \[ \] **Station Security:** Programming stations must be authenticated and malware-free.  
  * \[ \] **Key Injection:** Ensure keys are injected only once and the interface is permanently closed/locked afterwards.  
* \[ \] **Decommissioning (Clause 14\)**  
  * \[ \] **Data Wipe:** Verify "End of Life" procedure wipes all PII and cryptographic material.  
  * \[ \] **Revocation:** Ensure vehicle certificates can be revoked in the PKI backend upon scrapping.

## ISO/SAE 21434 Compliance Audit (Work Products)**

*Focus: Mandatory Work Products (WP) for UN R155 Type Approval.*

* \[ \] **WP-01: Cybersecurity Plan (Clause 6\)**  
* \[ \] **WP-02: Item Definition (Clause 9.3)**  
* \[ \] **WP-03: Cybersecurity Goals (Clause 9.4)**  
* \[ \] **WP-04: Cybersecurity Concept (Clause 9.5)**  
* \[ \] **WP-05: Cybersecurity Specifications (Clause 10.3)**  
* \[ \] **WP-06: Verification Report (Clause 10.4)**  
* \[ \] **WP-07: Validation Report (Clause 11\)**  
* \[ \] **WP-08: Production Control Plan (Clause 12\)**  
* \[ \] **WP-09: Incident Response Plan (Clause 13\)**  
  * \[ \] Procedures for identifying, reporting, and responding to breaches.  
* \[ \] **WP-10: Cybersecurity Case (Clause 6.4.7)**

## Incident Response:
   - [ ] Establish an incident response plan specifically tailored to smart car security incidents.
   - [ ] Define procedures for identifying, reporting, and responding to security breaches or suspicious activities.
   - [ ] Train relevant personnel on the proper execution of the incident response plan.

## Operational Security & User Awareness and Training:
   - [ ] Educate smart car owners/users about potential security risks and best practices.
   - [ ] Provide guidance on setting strong passwords, avoiding phishing attempts, and being cautious of untrusted networks.
   - [ ] Encourage regular software updates and responsible usage of remote access features.
   - [ ] Test the susceptibility of smart car users or employees to social engineering attacks, such as phishing emails, phone calls, or physical impersonation.
   - [ ] Assess the effectiveness of awareness training and security policies in place to mitigate social engineering risks.
   - [ ] Perform targeted social engineering attacks to identify potential weaknesses in the human element of smart car security.

## Regulatory Compliance:
   - [ ] Ensure that the smart car complies with relevant regulations and industry standards pertaining to security and data protection.
   - [ ] Stay informed about emerging regulations and adapt the security practices accordingly.
    
## Third-Party Assessments:
   - [ ] Engage third-party security experts to perform independent audits or assessments of the smart car's security posture.
   - [ ] Consider bug bounty programs to incentivize external researchers to report any discovered vulnerabilities.
