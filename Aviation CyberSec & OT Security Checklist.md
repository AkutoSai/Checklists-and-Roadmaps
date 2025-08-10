# **Comprehensive Aviation CyberSec & OT Security Checklist**

****Compiled from various sources (Symposiums, Research Papers etc.)**

## **1\. Aviation Cyber Security (General)**

### **1.1. Governance & Management**

* \[ \] Establish a dedicated aviation cybersecurity governance framework with board-level endorsement.  
* \[ \] Define and assign cybersecurity roles and responsibilities (e.g., CISO) with clear authority.  
* \[ \] Develop and maintain a comprehensive cybersecurity policy aligned with aviation standards (e.g., ICAO, EASA, FAA).  
* \[ \] Implement a Security Management System (SeMS) for cybersecurity, ensuring it fosters a "Just Culture" for non-punitive reporting of vulnerabilities.  
* \[ \] Conduct regular, dynamic cybersecurity risk assessments for all assets, considering hybrid threats (cyber-physical).  
* \[ \] Establish and maintain a complete asset inventory of all IT, OT, and cyber-physical systems.  
* \[ \] Implement a third-party/vendor risk management program.  
* \[ \] Ensure cybersecurity requirements and audit rights are included in all supplier and vendor contracts.  
* \[ \] Develop and regularly test a Cyber Incident Response Plan (CIRP) that is integrated with the overall organizational crisis management plan.  
* \[ \] Conduct regular, role-based cybersecurity awareness training for all personnel, including specialized training for leadership, flight crews, and engineers.

### **1.2. Technical Controls (IT & OT)**

* \[ \] Implement strict network segmentation to isolate critical flight and operational systems from corporate IT networks, using Demilitarized Zones (DMZs).  
* \[ \] Adopt a Zero Trust Architecture mindset, especially for connections to and within OT networks.  
* \[ \] Utilize firewalls, Intrusion Detection/Prevention Systems (IDS/IPS) tailored for aviation and OT protocols.  
* \[ \] Implement robust access control measures (e.g., Role-Based Access Control, principle of least privilege) and conduct regular access rights reviews.  
* \[ \] Enforce strong password policies and mandate multi-factor authentication (MFA) for all remote access and critical system access.  
* \[ \] Implement a risk-based patch management program for all IT and OT systems, with a process for testing patches and using compensating controls for unpatchable systems.  
* \[ \] Secure all data, both at rest and in transit, using strong, up-to-date encryption standards.  
* \[ \] Implement endpoint protection and application whitelisting on all connected devices (e.g., EFBs, maintenance laptops, operator workstations).  
* \[ \] Monitor network traffic for anomalous activity 24/7 using a Security Information and Event Management (SIEM) system tuned for aviation-specific threats.  
* \[ \] Secure physical access to all critical infrastructure, including data centers, control rooms, radar sites, and aircraft.  
* \[ \] Develop and implement a secure software development lifecycle (SDLC) for any custom applications.

## **2\. Airspace Security & Risk Assessment**

* \[ \] Conduct a comprehensive threat and risk assessment of the entire airspace ecosystem, including geopolitical risks from conflict zones.  
* \[ \] Identify all critical assets within the airspace (e.g., communication links, navigation aids, surveillance systems).  
* \[ \] Analyze potential attack vectors against airspace operations (e.g., jamming, spoofing, data injection, malicious UAVs).  
* \[ \] Model the potential impact of a cyber-attack on airspace safety and efficiency.  
* \[ \] Develop risk mitigation strategies for identified threats, fueled by diverse intelligence sources (government, third-party, OSINT).  
* \[ \] Establish secure communication protocols for all air-to-ground and ground-to-ground data links.  
* \[ \] Monitor for and respond to unauthorized Unmanned Aircraft Systems (UAS) incursions, and assess risks from advanced UAV attack scenarios (e.g., "ghost aircraft" injection).  
* \[ \] Implement procedures for validating the integrity of flight plan data throughout its lifecycle.  
* \[ \] Establish a framework for sharing actionable threat intelligence between ANSPs, airlines, and national security agencies.  
* \[ \] Regularly review and update the airspace risk assessment, and test contingency plans for airspace disruptions (e.g., GNSS outage) through realistic drills.

## **3\. ANSP (Air Navigation Service Provider) Security**

### **3.1. Air Traffic Management (ATM)**

* \[ \] Secure all ATM systems, including flight data processing, trajectory prediction, and flow management systems.  
* \[ \] Verify that inherent security features of modern ATM platforms are correctly configured and monitored.  
* \[ \] Implement access controls to prevent unauthorized modifications to flight plans or air traffic control instructions.  
* \[ \] Ensure the integrity and availability of all data used for ATM decision-making.  
* \[ \] Develop contingency procedures for operating during a cyber-attack on ATM systems, including failover to manual or redundant systems.  
* \[ \] Secure data links between ATM systems and other ANSP domains (CNS, AIM).

### **3.2. Communication, Navigation, and Surveillance (CNS)**

* \[ \] **Communication:**  
  * \[ \] Secure Voice Communication Systems (VCS) against interception, jamming, and disruption.  
  * \[ \] Secure Controller-Pilot Data Link Communications (CPDLC) against message tampering and spoofing.  
  * \[ \] Encrypt all critical ground-to-ground and air-to-ground communication links where feasible.  
* \[ \] **Navigation:**  
  * \[ \] Protect ground-based navigation aids (e.g., VOR, DME, ILS) from signal interference and spoofing.  
  * \[ \] Monitor the integrity of Global Navigation Satellite System (GNSS) signals.  
* \[ \] **Surveillance:**  
  * \[ \] Secure all surveillance data feeds (PSR, SSR, ADS-B, WAM) from data injection or manipulation.  
  * \[ \] Ensure the integrated surveillance system is resilient to the failure or compromise of a single data source.

### **3.3. Aeronautical Information Management (AIM)**

* \[ \] Secure the entire lifecycle of aeronautical data, from origination to distribution.  
* \[ \] Implement digital signatures and other integrity checks for all aeronautical publications (e.g., NOTAMs, AIPs).  
* \[ \] Control access to systems used for creating and managing aeronautical information.  
* \[ \] Ensure the availability and integrity of System-Wide Information Management (SWIM) infrastructure.  
* \[ \] Validate the integrity of data received from external sources before integration into AIM systems.

### **3.4. Search and Rescue (SAR) & Meteorology (MET)**

* \[ \] Secure communication systems used for coordinating SAR operations.  
* \[ \] Ensure the integrity and availability of data used for SAR planning and execution.  
* \[ \] Protect meteorological data systems from manipulation that could affect flight planning and safety.  
* \[ \] Secure the dissemination channels for weather information to pilots and controllers.

## **4\. Surveillance Systems (PSR, SSR, TCAS, ADS-B, WAM)**

### **4.1. Primary & Secondary Surveillance Radar (PSR/SSR)**

* \[ \] Secure the physical infrastructure, power, and environmental controls of radar sites.  
* \[ \] Protect data links between radar heads and processing centers.  
* \[ \] Implement measures to detect and filter out false or manipulated radar returns.  
* \[ \] Secure the configuration and maintenance interfaces of radar systems.

### **4.2. TCAS (Traffic Collision Avoidance System)**

* \[ \] Ensure TCAS software and hardware are from trusted sources and have not been tampered with.  
* \[ \] Implement procedures to verify the integrity of TCAS advisories.  
* \[ \] Train pilots on how to respond to potentially anomalous TCAS behavior, including false or suppressed advisories.

### **4.3. ADS-B (Automatic Dependent Surveillance-Broadcast) & WAM (Wide Area Multilateration)**

* \[ \] Formally document the inherent vulnerabilities of ADS-B (unencrypted, unauthenticated) in the risk register.  
* \[ \] Implement ADS-B data validation and integrity checks, using multi-source correlation (e.g., comparing with PSR/WAM) to detect spoofing.  
* \[ \] Deploy ground-based monitoring systems to correlate ADS-B data with other surveillance sources.  
* \[ \] Secure the ground stations and central IT processors for WAM against data manipulation and DoS attacks.  
* \[ \] Evaluate and plan for the implementation of encrypted/authenticated ADS-B (when available).  
* \[ \] Protect against denial-of-service attacks targeting ADS-B receivers or WAM infrastructure.

## **5\. GNSS Security & Security Management Systems (SeMS)**

### **5.1. GNSS Spoofing & Jamming**

* \[ \] Formally recognize GNSS interference as a deliberate security threat, not just a technical issue.  
* \[ \] Deploy GNSS interference detection and monitoring systems at airports and in critical airspace.  
* \[ \] Assess the resilience of the overall Positioning, Navigation, and Timing (PNT) strategy, promoting multi-constellation/multi-frequency receivers.  
* \[ \] Implement Receiver Autonomous Integrity Monitoring (RAIM) and other onboard integrity checks.  
* \[ \] Develop and practice contingency procedures for loss or degradation of GNSS signals, ensuring pilot proficiency in alternative navigation (e.g., IRS).  
* \[ \] Integrate data from Inertial Reference Systems (IRS) to validate GNSS position data.  
* \[ \] Establish a reporting mechanism for pilots and controllers to share information on suspected GNSS interference events.

### **5.2. Security Management System (SeMS) Integration**

* \[ \] Ensure the SeMS framework explicitly includes cybersecurity as a key risk domain.  
* \[ \] Integrate the Cyber Incident Response Plan (CIRP) with the overall emergency and crisis response plan managed under the SeMS.  
* \[ \] Use SeMS processes for proactive hazard identification and risk management of cyber threats.  
* \[ \] Incorporate cybersecurity performance indicators (KPIs) into the SeMS safety performance monitoring.  
* \[ \] Ensure SeMS training and promotion activities include cybersecurity awareness.

## **6\. ASBU (Aviation System Block Upgrades) Framework**

* \[ \] For every planned ASBU module implementation, conduct a dedicated cybersecurity threat and risk assessment ("Security by Design").  
* \[ \] Ensure "Security" is a key performance area considered during the business case analysis for any ASBU module.  
* \[ \] Verify that new IP-based CNS/ATM systems introduced under ASBU comply with OT security principles (e.g., strict segmentation).  
* \[ \] Ensure interoperability and data exchange protocols defined in ASBU modules are implemented securely.  
* \[ \] Update network architecture and security controls to support the new functionalities introduced by ASBU blocks.  
* \[ \] Plan for the secure decommissioning of legacy systems being replaced by ASBU modules.  
* \[ \] Ensure that cybersecurity dependencies between different ASBU modules are identified and managed.  
* \[ \] Accompany ASBU deployment with specific cybersecurity training for technical and operational staff on new systems and risks.

## **7\. Human Factors & Insider Threat**

* \[ \] Implement a formal insider threat mitigation program with both technical and procedural controls.  
* \[ \] Conduct thorough pre-employment and ongoing background screening for personnel in sensitive or critical roles.  
* \[ \] Utilize User and Entity Behavior Analytics (UEBA) to monitor for anomalous activity on critical networks and systems.  
* \[ \] Conduct regular, mandatory training on social engineering, phishing, and other manipulation tactics.  
* \[ \] Enforce a clean desk policy and controls on removable media usage.  
* \[ \] Establish clear policies and procedures for revoking access immediately upon employee termination or role change.

## **8\. Supply Chain & Third-Party Security**

* \[ \] Extend SeMS security principles to all External Service Providers (ESPs), including ground handling, catering, and maintenance.  
* \[ \] Conduct security assessments of all third-party vendors and suppliers before integration.  
* \[ \] Mandate explicit cybersecurity requirements, including the right to audit, in all third-party contracts.  
* \[ \] Establish a secure, monitored, and time-limited process for remote access by vendors, with all sessions logged.  
* \[ \] Assess the security posture of all Cloud Service Providers (CSPs) and ensure secure configuration of cloud environments.  
* \[ \] Develop a Software Bill of Materials (SBOM) for critical applications to manage vulnerabilities in third-party components.  
* \[ \] Assess readiness to participate in supply chain security validation and trust frameworks (e.g., IATA SeMS Certification).
