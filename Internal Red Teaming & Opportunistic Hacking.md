# Internal Red Team Assessment
## Comprehensive Checklist & Test Case Catalog

**Document Version:** 1.0  
**Assessment Type:** Internal Red Team / Adversary Simulation + Opportunistic Hacking

**Environment:** Corporate Internal Network  
**Classification:** Authorized Security Testing  
**Status:** Draft / Test Plan  

---

# 1. Document Control

| Field | Value |
|---|---|
| Assessment Name | Internal Red Team Assessment |
| Organization | `<Organization>` |
| Assessment Window | `<Start Date> - <End Date>` |
| Red Team Lead | `<Name>` |
| Blue Team Lead | `<Name>` |
| Rules of Engagement Owner | `<Name>` |
| Primary Network Ranges | `<CIDRs>` |
| Active Directory Domains | `<Domains>` |
| Cloud Tenants | `<Tenants>` |
| Critical Systems | `<Systems>` |
| Emergency Contact | `<Contact>` |
| Report Date | `<Date>` |

---

# 2. Assessment Objectives

The engagement should determine whether an attacker who gains an initial foothold inside the organization can:

- Discover internal infrastructure.
- Identify valuable identities and systems.
- Escalate privileges.
- Compromise additional endpoints.
- Abuse Active Directory.
- Move laterally.
- Access sensitive information.
- Compromise administrative infrastructure.
- Reach critical business systems.
- Cross network/security boundaries.
- Abuse cloud identity and infrastructure.
- Maintain access where permitted by the rules of engagement.
- Evade or trigger security monitoring.
- Exfiltrate representative data safely.
- Achieve defined attack objectives.
- Determine whether the SOC detects and responds to the simulated activity.

---

# 3. Rules of Engagement Checklist

## 3.1 Authorization

- [ ] Written authorization obtained.
- [ ] Executive sponsor identified.
- [ ] Technical owner identified.
- [ ] SOC/NOC contacts identified.
- [ ] Emergency contact identified.
- [ ] Legal/security approval obtained where required.
- [ ] Third-party authorization obtained where applicable.
- [ ] Cloud provider restrictions reviewed.
- [ ] Penetration-testing restrictions reviewed.
- [ ] Testing window approved.
- [ ] Testing timezone confirmed.

## 3.2 Scope

- [ ] Internal IP ranges documented.
- [ ] IPv6 ranges documented.
- [ ] Domain names documented.
- [ ] Active Directory domains documented.
- [ ] Forest/trust relationships documented.
- [ ] Endpoint populations documented.
- [ ] Server populations documented.
- [ ] Network segments documented.
- [ ] VPN ranges documented.
- [ ] Wireless networks documented.
- [ ] Guest networks documented.
- [ ] Management networks documented.
- [ ] Cloud environments documented.
- [ ] SaaS environments documented.
- [ ] Critical applications documented.
- [ ] Physical locations documented.

## 3.3 Explicitly Out of Scope

Document systems that must not be tested:

- [ ] Production databases.
- [ ] Safety-critical systems.
- [ ] Industrial/OT systems.
- [ ] Medical devices.
- [ ] Building-management systems.
- [ ] Emergency systems.
- [ ] Backup infrastructure.
- [ ] Executive systems.
- [ ] Third-party systems.
- [ ] Customer environments.
- [ ] Personal devices.
- [ ] Other: `<Define>`

## 3.4 High-Risk Actions

Explicitly determine whether the following are allowed:

- [ ] Credential spraying.
- [ ] Password auditing.
- [ ] Exploit validation.
- [ ] Privilege escalation testing.
- [ ] Lateral movement.
- [ ] Domain privilege escalation.
- [ ] Kerberos abuse simulation.
- [ ] NTLM abuse simulation.
- [ ] Token/session testing.
- [ ] Endpoint security bypass testing.
- [ ] EDR evasion testing.
- [ ] Persistence testing.
- [ ] Cloud privilege escalation.
- [ ] Data-access validation.
- [ ] Controlled exfiltration simulation.
- [ ] Denial-of-service testing.
- [ ] Social engineering.
- [ ] Phishing.
- [ ] Physical security testing.

---

# 4. Safety Controls

- [ ] Production-impact thresholds defined.
- [ ] Rate limits defined.
- [ ] Credential lockout thresholds understood.
- [ ] Account lockout monitoring enabled.
- [ ] Test accounts created where appropriate.
- [ ] Canary systems identified.
- [ ] Critical systems identified.
- [ ] Backup systems excluded or explicitly approved.
- [ ] Data handling procedure established.
- [ ] Sensitive data collection minimized.
- [ ] Destructive actions prohibited unless explicitly approved.
- [ ] Persistence duration defined.
- [ ] Cleanup procedure documented.
- [ ] Stop condition documented.
- [ ] Emergency shutdown process tested.

## Immediate Stop Conditions

Stop testing if:

- Production availability is threatened.
- Unexpected destructive behavior occurs.
- Safety-critical systems are affected.
- Large-scale account lockout occurs.
- Data corruption is observed.
- Unexpected customer impact occurs.
- Critical security controls fail in an uncontrolled manner.
- The client requests termination.
- Testing exceeds approved scope.

---

# 5. Engagement Preparation

## 5.1 Infrastructure Preparation

- [ ] Testing workstation prepared.
- [ ] Secure storage configured.
- [ ] Time synchronization verified.
- [ ] Logging enabled.
- [ ] Network connectivity confirmed.
- [ ] VPN access validated.
- [ ] Jump host access validated.
- [ ] Test credentials validated.
- [ ] Test certificates/keys configured.
- [ ] Secure communications channel established.

## 5.2 Evidence Collection

For every significant test, capture:

- Timestamp.
- Source host.
- Destination host.
- Source account.
- Destination account.
- Protocol.
- Authentication mechanism.
- Action performed.
- Result.
- Security control response.
- Relevant logs.
- Screenshots where useful.
- Detection alert ID.
- Incident/ticket ID.
- Cleanup confirmation.

---

# 6. Initial Access Simulation

## IA-001 — Valid Internal Credential Access

**Objective:** Determine whether valid internal credentials provide excessive access.

**Prerequisites:**
- Authorized test account.
- Approved access path.

**Test:**
1. Authenticate using the supplied/approved account.
2. Determine accessible systems.
3. Determine accessible shares/resources.
4. Determine whether privileges exceed the intended role.
5. Record access to sensitive systems.

**Expected Result:**
- Account should access only resources required for its assigned role.
- Excessive access should be denied or controlled.

**Evidence:**
- Authentication logs.
- Access-control results.
- Resource inventory.
- SIEM events.

---

## IA-002 — Credential Reuse

**Objective:** Determine whether one compromised credential works across unrelated systems.

**Test:**
- Validate the authorized credential against representative systems.
- Compare access across workstation, server, application, database, and administrative infrastructure.

**Expected Result:**
- Credentials should not provide unnecessary access across security boundaries.

---

## IA-003 — Credential Scope

Check whether a standard user can access:

- [ ] Workstations.
- [ ] File servers.
- [ ] Application servers.
- [ ] Databases.
- [ ] Management servers.
- [ ] Backup systems.
- [ ] Virtualization infrastructure.
- [ ] Network infrastructure.
- [ ] Security infrastructure.
- [ ] Cloud management interfaces.

---

# 7. Internal Network Discovery

## NET-001 — Network Asset Discovery

**Objective:** Determine whether an internal attacker can identify corporate assets.

Check for:

- [ ] Domain controllers.
- [ ] DNS servers.
- [ ] DHCP servers.
- [ ] File servers.
- [ ] Print servers.
- [ ] Web servers.
- [ ] Application servers.
- [ ] Database servers.
- [ ] Virtualization hosts.
- [ ] Backup servers.
- [ ] Monitoring systems.
- [ ] SIEM infrastructure.
- [ ] EDR infrastructure.
- [ ] Certificate infrastructure.
- [ ] Network-management systems.
- [ ] Routers.
- [ ] Switches.
- [ ] Firewalls.
- [ ] Wireless controllers.
- [ ] VPN infrastructure.

**Expected Result:**
Network segmentation and monitoring should limit unnecessary visibility.

---

## NET-002 — Service Enumeration

Assess exposure of:

- [ ] DNS.
- [ ] DHCP.
- [ ] LDAP.
- [ ] LDAPS.
- [ ] Kerberos.
- [ ] SMB.
- [ ] RPC.
- [ ] WinRM.
- [ ] SSH.
- [ ] RDP.
- [ ] HTTP/HTTPS.
- [ ] Database services.
- [ ] Remote management services.
- [ ] File transfer services.
- [ ] Monitoring services.

Record:

| Host | Service | Exposure | Authentication | Encryption | Risk |
|---|---|---|---|---|---|
| | | | | | |

---

## NET-003 — Network Segmentation Validation

Attempt approved access from:

- User VLAN → Server VLAN.
- User VLAN → Management VLAN.
- User VLAN → Security VLAN.
- User VLAN → Database VLAN.
- User VLAN → Backup VLAN.
- User VLAN → Domain Controller.
- Guest VLAN → Corporate VLAN.
- VPN → Internal VLAN.
- Contractor VLAN → Corporate VLAN.
- Server VLAN → Management VLAN.

**Expected Result:**
Only explicitly required communication should succeed.

---

# 8. Active Directory Assessment

# 8.1 AD Discovery

## AD-001 — Domain Discovery

Determine:

- [ ] Domain name.
- [ ] Forest name.
- [ ] Domain controllers.
- [ ] Global Catalog servers.
- [ ] Sites.
- [ ] Subnets.
- [ ] Trust relationships.
- [ ] Organizational Units.
- [ ] Security groups.
- [ ] Privileged groups.
- [ ] Service accounts.
- [ ] Computer accounts.
- [ ] Group Managed Service Accounts.
- [ ] Certificate Services.
- [ ] Federation infrastructure.

---

## AD-002 — Privileged Group Review

Review membership of:

- [ ] Domain Admins.
- [ ] Enterprise Admins.
- [ ] Schema Admins.
- [ ] Administrators.
- [ ] Account Operators.
- [ ] Backup Operators.
- [ ] Server Operators.
- [ ] Print Operators.
- [ ] DNS Admins.
- [ ] Remote Management groups.
- [ ] Custom administrative groups.

Check for:

- Excessive membership.
- Nested groups.
- Stale accounts.
- Service accounts.
- Personal accounts.
- Disabled accounts.
- Shared accounts.
- Unusual delegation.

---

## AD-003 — Nested Group Abuse

**Objective:** Determine whether indirect group membership creates unintended privilege.

Check:

- User → Group A → Group B → Privileged Group.
- Computer → Group → Administrative group.
- Service account → Nested privileged group.

**Expected Result:**
Privilege inheritance should be intentional and documented.

---

# 9. Active Directory Authentication Testing

## AD-010 — Kerberos Configuration

Assess:

- [ ] Kerberos-only authentication where appropriate.
- [ ] Legacy authentication dependencies.
- [ ] Weak encryption configuration.
- [ ] Service principal configuration.
- [ ] Delegation configuration.
- [ ] Service-account exposure.
- [ ] Time synchronization.
- [ ] Ticket lifetime configuration.

---

## AD-011 — NTLM Usage

Determine:

- Where NTLM is still used.
- Whether NTLM is required.
- Whether stronger authentication is available.
- Whether NTLM restrictions are implemented.

**Risk indicators:**

- NTLM broadly enabled.
- NTLM accepted by sensitive systems.
- NTLM accepted across trust boundaries.
- Unnecessary legacy authentication.

---

## AD-012 — LDAP Security

Check:

- [ ] LDAP signing.
- [ ] LDAP channel binding.
- [ ] LDAPS availability.
- [ ] Cleartext authentication prevention.
- [ ] Anonymous access.
- [ ] Excessive directory read access.

---

# 10. Active Directory Privilege Escalation

## AD-020 — ACL Abuse

Review whether low-privileged users can obtain dangerous permissions over:

- [ ] Users.
- [ ] Groups.
- [ ] Computers.
- [ ] OUs.
- [ ] Domain objects.
- [ ] GPOs.
- [ ] Certificate objects.
- [ ] Service accounts.

Look for dangerous rights such as:

- Password modification.
- Group membership modification.
- Object ownership.
- ACL modification.
- Account-control modification.
- GPO modification.
- Delegation modification.

---

## AD-021 — GPO Security

Review:

- [ ] GPO write permissions.
- [ ] GPO ownership.
- [ ] GPO delegation.
- [ ] Scripts.
- [ ] Scheduled tasks.
- [ ] Startup scripts.
- [ ] Software deployment.
- [ ] Administrative templates.
- [ ] Credential material in policies.

**Expected Result:**
Ordinary users must not be able to modify policies affecting privileged systems.

---

## AD-022 — Delegation Review

Assess:

- [ ] Unconstrained delegation.
- [ ] Constrained delegation.
- [ ] Resource-based constrained delegation.
- [ ] Delegation involving privileged accounts.
- [ ] Delegation involving domain controllers.
- [ ] Delegation involving service accounts.

---

# 11. Active Directory Certificate Services

## ADCS-001 — PKI Discovery

Identify:

- [ ] Certificate Authorities.
- [ ] Enterprise CAs.
- [ ] Certificate templates.
- [ ] Enrollment permissions.
- [ ] Auto-enrollment.
- [ ] Web enrollment.
- [ ] Administrative permissions.

---

## ADCS-002 — Certificate Template Review

Check for:

- [ ] Low-privileged enrollment.
- [ ] Authentication-enabled certificates.
- [ ] Dangerous subject/SAN configuration.
- [ ] Excessive enrollment rights.
- [ ] Weak template controls.
- [ ] Misconfigured EKUs.
- [ ] Manager approval bypass.
- [ ] Enrollment-agent exposure.

**Expected Result:**
Users should not be able to obtain certificates that provide unintended privileged authentication.

---

# 12. Credential Exposure

## CREDS-001 — Credential Material Discovery

Search only approved locations for:

- [ ] Configuration files.
- [ ] Scripts.
- [ ] Deployment files.
- [ ] Environment variables.
- [ ] Application configuration.
- [ ] Documentation.
- [ ] Shared drives.
- [ ] Software repositories.
- [ ] CI/CD systems.
- [ ] Backup repositories.
- [ ] Endpoint credential stores.

Record:

| Location | Credential Type | Privilege | Exposure | Remediation |
|---|---|---|---|---|
| | | | | |

---

## CREDS-002 — Password Policy

Assess:

- [ ] Minimum password length.
- [ ] Password history.
- [ ] Complexity.
- [ ] Lockout controls.
- [ ] Password expiration strategy.
- [ ] Weak/default passwords.
- [ ] Shared passwords.
- [ ] Password reuse.
- [ ] Service-account passwords.

---

## CREDS-003 — Secrets Management

Check whether secrets are stored in:

- [ ] Git repositories.
- [ ] Build systems.
- [ ] CI/CD variables.
- [ ] Cloud configuration.
- [ ] Scripts.
- [ ] Docker/container configuration.
- [ ] Configuration management.
- [ ] Wiki/documentation.
- [ ] Ticketing systems.
- [ ] Shared drives.

---

# 13. Endpoint Security

## END-001 — Endpoint Protection

Verify presence and effectiveness of:

- [ ] EDR.
- [ ] Antivirus.
- [ ] Host firewall.
- [ ] Disk encryption.
- [ ] Application control.
- [ ] Attack-surface reduction.
- [ ] Tamper protection.
- [ ] Security logging.

---

## END-002 — Local Administrator Access

Determine:

- [ ] Number of users with local admin.
- [ ] Shared local administrator accounts.
- [ ] Local admin password reuse.
- [ ] Local admin password management.
- [ ] Admin access on privileged workstations.

**Expected Result:**
Standard users should not have unnecessary local administrator privileges.

---

## END-003 — Endpoint Hardening

Check:

- [ ] Unnecessary services.
- [ ] Legacy protocols.
- [ ] Unnecessary remote access.
- [ ] Unrestricted scripting.
- [ ] Unsigned code execution.
- [ ] Weak application controls.
- [ ] Insecure scheduled tasks.
- [ ] Insecure services.
- [ ] Writable privileged directories.
- [ ] Excessive filesystem permissions.

---

# 14. Windows Security Controls

## WIN-001 — Security Policy

Review:

- [ ] UAC.
- [ ] Credential Guard.
- [ ] LSA protection.
- [ ] Windows Defender.
- [ ] ASR rules.
- [ ] PowerShell logging.
- [ ] Script-block logging.
- [ ] Command-line logging.
- [ ] Process creation auditing.
- [ ] Authentication auditing.

---

## WIN-002 — Administrative Interfaces

Assess:

- [ ] RDP.
- [ ] WinRM.
- [ ] SMB.
- [ ] RPC.
- [ ] Remote Services.
- [ ] Remote Registry.
- [ ] PowerShell remoting.

Check whether access is restricted to authorized administration networks.

---

# 15. Linux/Unix Security

## LNX-001 — Local Privilege Review

Assess:

- [ ] Sudo configuration.
- [ ] SUID/SGID programs.
- [ ] Writable privileged files.
- [ ] Cron jobs.
- [ ] Systemd services.
- [ ] Container permissions.
- [ ] SSH configuration.
- [ ] Stored credentials.
- [ ] Service accounts.

---

## LNX-002 — SSH Security

Check:

- [ ] Password authentication.
- [ ] Key authentication.
- [ ] Root login.
- [ ] Weak cryptography.
- [ ] Shared keys.
- [ ] Key reuse.
- [ ] Excessive authorized keys.
- [ ] Stale accounts.
- [ ] Bastion controls.

---

# 16. Lateral Movement

## LAT-001 — Workstation-to-Workstation

Determine whether one compromised workstation can access another.

**Expected Result:**
Peer-to-peer administrative access should be restricted.

---

## LAT-002 — Workstation-to-Server

Test authorized access to:

- [ ] File servers.
- [ ] Application servers.
- [ ] Database servers.
- [ ] Web servers.
- [ ] Management servers.

---

## LAT-003 — Server-to-Server

Determine whether compromise of a low-tier server allows access to:

- [ ] Domain controllers.
- [ ] Database infrastructure.
- [ ] Backup systems.
- [ ] Management systems.
- [ ] Security infrastructure.

---

## LAT-004 — Administrative Tier Separation

Validate:

**Tier 0**
- Domain controllers.
- Identity infrastructure.
- PKI.
- Identity administration.

**Tier 1**
- Servers.
- Application infrastructure.

**Tier 2**
- User endpoints.

Check whether credentials from one tier are usable in another.

---

# 17. SMB/File Share Security

## SMB-001 — Share Enumeration

Identify:

- [ ] Administrative shares.
- [ ] User shares.
- [ ] Department shares.
- [ ] Backup shares.
- [ ] Application shares.
- [ ] Software shares.

---

## SMB-002 — Anonymous/Guest Access

Check whether unauthenticated or guest users can access:

- [ ] Shares.
- [ ] Files.
- [ ] Directory listings.
- [ ] Sensitive metadata.

---

## SMB-003 — Sensitive File Discovery

Look for approved test patterns involving:

- Passwords.
- API keys.
- Private keys.
- Database credentials.
- Backup files.
- HR information.
- Financial information.
- Source code.
- Configuration files.
- Deployment credentials.

Do not collect unnecessary sensitive content.

---

# 18. Database Security

Assess:

- [ ] Database discovery.
- [ ] Authentication.
- [ ] Default accounts.
- [ ] Excessive permissions.
- [ ] Shared credentials.
- [ ] Application database credentials.
- [ ] Network exposure.
- [ ] Encryption.
- [ ] Backup exposure.
- [ ] Administrative access.
- [ ] Cross-database privileges.

Test whether a compromised application account can access unrelated databases.

---

# 19. Backup Infrastructure

## BAK-001 — Backup Access

Determine whether ordinary users or low-privileged accounts can access:

- [ ] Backup consoles.
- [ ] Backup repositories.
- [ ] Backup credentials.
- [ ] Backup APIs.
- [ ] Backup storage.

**Expected Result:**
Backup infrastructure should be isolated from ordinary corporate identities.

---

## BAK-002 — Recovery Security

Assess whether backup data could enable recovery of:

- Credentials.
- Domain databases.
- Application secrets.
- Sensitive files.
- Historical configurations.

---

# 20. Virtualization Infrastructure

Assess:

- [ ] VMware.
- [ ] Hyper-V.
- [ ] Proxmox.
- [ ] Cloud virtualization.
- [ ] Management consoles.
- [ ] Administrative APIs.
- [ ] Host access.
- [ ] VM snapshot access.
- [ ] VM backup access.

Determine whether compromise of a guest VM can lead to management-plane access.

---

# 21. Network Infrastructure

Assess authorized access to:

- [ ] Routers.
- [ ] Switches.
- [ ] Firewalls.
- [ ] VPN gateways.
- [ ] Wireless controllers.
- [ ] Load balancers.
- [ ] Network monitoring.
- [ ] Configuration-management systems.

Check for:

- Default credentials.
- Shared administrative accounts.
- Weak authentication.
- Excessive management exposure.
- Insecure protocols.
- Poor segmentation.
- Configuration backups containing credentials.

---

# 22. Wireless Security

## WIFI-001 — Corporate Wi-Fi

Assess:

- [ ] WPA configuration.
- [ ] Enterprise authentication.
- [ ] Certificate validation.
- [ ] Rogue AP detection.
- [ ] Client isolation.
- [ ] Network segmentation.
- [ ] Guest isolation.

---

## WIFI-002 — Guest Network

Verify:

- [ ] Guest → Internet.
- [ ] Guest → Corporate network blocked.
- [ ] Guest → Management network blocked.
- [ ] Guest → Internal DNS restricted.
- [ ] Guest → Internal applications blocked.

---

# 23. VPN Security

Assess:

- [ ] MFA.
- [ ] Device posture.
- [ ] Certificate authentication.
- [ ] Split tunneling.
- [ ] Full tunnel.
- [ ] VPN user privileges.
- [ ] Network segmentation.
- [ ] Stale accounts.
- [ ] Third-party access.
- [ ] Contractor access.

---

# 24. Privileged Access Management

Check:

- [ ] PAM deployment.
- [ ] Just-in-time administration.
- [ ] Privileged session recording.
- [ ] Credential rotation.
- [ ] Vault protection.
- [ ] Break-glass accounts.
- [ ] Emergency access.
- [ ] Administrative workstation controls.

Test whether privileged credentials can be used outside the intended PAM workflow.

---

# 25. MFA Assessment

Assess:

- [ ] MFA coverage.
- [ ] MFA for VPN.
- [ ] MFA for cloud.
- [ ] MFA for privileged accounts.
- [ ] MFA for remote administration.
- [ ] MFA for sensitive applications.
- [ ] Legacy authentication bypass.
- [ ] Recovery process.
- [ ] Enrollment process.
- [ ] Device replacement process.

---

# 26. Identity Lifecycle

Check:

- [ ] New employee provisioning.
- [ ] Employee transfer.
- [ ] Employee termination.
- [ ] Contractor lifecycle.
- [ ] Temporary accounts.
- [ ] Dormant accounts.
- [ ] Disabled accounts.
- [ ] Service accounts.
- [ ] Shared accounts.

---

# 27. Email Security

Assess:

- [ ] SPF.
- [ ] DKIM.
- [ ] DMARC.
- [ ] Internal spoofing controls.
- [ ] External spoofing controls.
- [ ] Attachment security.
- [ ] URL filtering.
- [ ] Malware filtering.
- [ ] Impersonation protection.
- [ ] Mailbox auditing.

---

# 28. Phishing Simulation

Only if explicitly authorized.

Test:

- [ ] Credential phishing resistance.
- [ ] MFA-resistant authentication.
- [ ] Attachment handling.
- [ ] Link handling.
- [ ] Reporting mechanism.
- [ ] User awareness.
- [ ] SOC detection.
- [ ] Mail security controls.

Measure:

| Metric | Result |
|---|---:|
| Messages delivered | |
| Messages blocked | |
| Users interacting | |
| Reports submitted | |
| Credentials submitted | |
| SOC detections | |
| Response time | |

---

# 29. Internal Application Security

Assess applications exposed internally.

Check:

- [ ] Authentication.
- [ ] Authorization.
- [ ] Session management.
- [ ] Role separation.
- [ ] Administrative functions.
- [ ] File upload.
- [ ] File download.
- [ ] API security.
- [ ] Input validation.
- [ ] Error handling.
- [ ] Sensitive information disclosure.
- [ ] Debug functionality.
- [ ] Default credentials.
- [ ] Secrets in configuration.
- [ ] Dependency vulnerabilities.

---

# 30. API Security

Assess:

- [ ] API authentication.
- [ ] Authorization.
- [ ] Object-level authorization.
- [ ] Function-level authorization.
- [ ] Token lifetime.
- [ ] Token revocation.
- [ ] API keys.
- [ ] Rate limiting.
- [ ] Sensitive endpoints.
- [ ] Administrative endpoints.
- [ ] Internal APIs.

---

# 31. Source Code & CI/CD

Assess:

- [ ] Source repositories.
- [ ] Build servers.
- [ ] Deployment servers.
- [ ] Artifact repositories.
- [ ] CI/CD credentials.
- [ ] Pipeline permissions.
- [ ] Branch protection.
- [ ] Secrets.
- [ ] Deployment keys.
- [ ] Service accounts.
- [ ] Runner permissions.

Determine whether compromise of a developer workstation can reach production deployment infrastructure.

---

# 32. Container Security

Assess:

- [ ] Container registries.
- [ ] Registry credentials.
- [ ] Container secrets.
- [ ] Privileged containers.
- [ ] Host mounts.
- [ ] Container service accounts.
- [ ] Kubernetes access.
- [ ] Cluster-admin permissions.
- [ ] Kubernetes API exposure.
- [ ] CI/CD integration.

---

# 33. Kubernetes Security

Check:

- [ ] Kubernetes API authentication.
- [ ] RBAC.
- [ ] Service accounts.
- [ ] Cluster-admin assignments.
- [ ] Secrets.
- [ ] Network policies.
- [ ] Admission controls.
- [ ] Pod security.
- [ ] Node permissions.
- [ ] Container runtime security.
- [ ] Cloud IAM integration.

---

# 34. Cloud Security

Perform equivalent assessment across:

- [ ] Microsoft Azure.
- [ ] AWS.
- [ ] Google Cloud.
- [ ] SaaS platforms.

---

## CLOUD-001 — Cloud Identity

Check:

- [ ] Human identities.
- [ ] Service principals.
- [ ] Workload identities.
- [ ] Managed identities.
- [ ] Access keys.
- [ ] MFA.
- [ ] Privileged roles.
- [ ] Conditional access.
- [ ] Legacy authentication.

---

## CLOUD-002 — Excessive Permissions

Look for:

- User → Admin role.
- Service account → Admin role.
- Application → Broad permissions.
- Developer → Production access.
- CI/CD → Broad cloud access.

---

## CLOUD-003 — Storage

Assess:

- [ ] Object storage.
- [ ] File storage.
- [ ] Snapshots.
- [ ] Backups.
- [ ] Public exposure.
- [ ] Cross-account access.
- [ ] Shared access credentials.

---

## CLOUD-004 — Network Security

Check:

- [ ] Security groups.
- [ ] Network ACLs.
- [ ] Peering.
- [ ] VPN.
- [ ] Private endpoints.
- [ ] Internet-facing resources.
- [ ] Management-plane exposure.

---

# 35. SaaS Security

Review:

- [ ] Microsoft 365.
- [ ] Google Workspace.
- [ ] Salesforce.
- [ ] GitHub/GitLab.
- [ ] Slack.
- [ ] Jira.
- [ ] Confluence.
- [ ] ServiceNow.
- [ ] Other critical SaaS.

Check:

- MFA.
- SSO.
- Conditional access.
- External sharing.
- Guest accounts.
- API tokens.
- OAuth applications.
- Administrator roles.
- Data export capabilities.

---

# 36. Data Access

## DATA-001 — Sensitive Data Identification

Identify categories:

- [ ] Customer information.
- [ ] Employee information.
- [ ] Financial information.
- [ ] Intellectual property.
- [ ] Source code.
- [ ] Credentials.
- [ ] Security information.
- [ ] Legal information.
- [ ] Strategic documents.

---

## DATA-002 — Access Boundary Testing

Determine whether a compromised standard user can access sensitive information outside their role.

---

## DATA-003 — Data Exfiltration Simulation

Use only approved synthetic or representative data.

Validate:

- [ ] Data can be identified.
- [ ] Data can be staged.
- [ ] DLP detects the activity.
- [ ] Network controls detect the transfer.
- [ ] SOC receives an alert.
- [ ] Response process begins.

Do not remove production data unless specifically authorized.

---

# 37. Persistence Simulation

Only perform persistence testing where explicitly authorized.

Assess whether an attacker could establish persistence through:

- [ ] Account modification.
- [ ] Scheduled tasks.
- [ ] Services.
- [ ] Startup mechanisms.
- [ ] Application configuration.
- [ ] Cloud identities.
- [ ] API credentials.
- [ ] OAuth applications.
- [ ] Certificates.
- [ ] Administrative configuration.

For each persistence mechanism:

- [ ] Creation detected.
- [ ] Modification detected.
- [ ] Alert generated.
- [ ] Persistence removed.
- [ ] Credentials rotated where required.

---

# 38. Endpoint Detection & Response

## EDR-001 — Detection Coverage

Validate telemetry for:

- [ ] Process creation.
- [ ] Authentication.
- [ ] Privilege changes.
- [ ] Network connections.
- [ ] Script execution.
- [ ] Persistence events.
- [ ] Credential-access indicators.
- [ ] Lateral movement indicators.
- [ ] Security-control modification.

---

## EDR-002 — Alert Quality

For each significant red-team action record:

| Test | Logged? | Alerted? | Severity | Analyst Response |
|---|---|---|---|---|
| Discovery | | | | |
| Authentication anomaly | | | | |
| Privilege change | | | | |
| Lateral movement | | | | |
| Persistence | | | | |
| Data access | | | | |
| Exfiltration simulation | | | | |

---

# 39. SIEM Detection Testing

Verify whether the SIEM receives:

- [ ] Windows logs.
- [ ] Linux logs.
- [ ] Domain controller logs.
- [ ] VPN logs.
- [ ] Firewall logs.
- [ ] EDR telemetry.
- [ ] Cloud logs.
- [ ] SaaS audit logs.
- [ ] Identity-provider logs.
- [ ] DNS logs.
- [ ] Proxy logs.
- [ ] Email-security logs.

---

# 40. SOC Detection & Response

## SOC-001 — Initial Detection

Record:

- First observable activity.
- First alert.
- First analyst review.
- First escalation.
- First containment action.

---

## SOC-002 — Mean Time to Detect

Calculate:

**MTTD = Detection Time − Attack Activity Time**

---

## SOC-003 — Mean Time to Respond

Calculate:

**MTTR = Response Time − Detection Time**

---

## SOC-004 — Attack Chain Detection

Determine whether SOC analysts can correlate:

1. Initial access.
2. Discovery.
3. Credential access.
4. Privilege escalation.
5. Lateral movement.
6. Data access.
7. Exfiltration.
8. Persistence.

---

# 41. Deception Controls

Check for:

- [ ] Honeypots.
- [ ] Canary credentials.
- [ ] Canary files.
- [ ] Decoy accounts.
- [ ] Decoy shares.
- [ ] Deception endpoints.

Determine whether interaction triggers alerts.

---

# 42. Network Monitoring

Assess visibility into:

- [ ] East-west traffic.
- [ ] North-south traffic.
- [ ] DNS.
- [ ] HTTP/HTTPS.
- [ ] SMB.
- [ ] LDAP.
- [ ] Kerberos.
- [ ] RDP.
- [ ] SSH.
- [ ] VPN.
- [ ] Cloud traffic.

---

# 43. DNS Security

Check:

- [ ] Internal DNS exposure.
- [ ] DNS logging.
- [ ] DNS filtering.
- [ ] Dynamic DNS.
- [ ] Split-horizon DNS.
- [ ] DNS administration.
- [ ] Unauthorized DNS changes.

---

# 44. Network Egress Controls

Validate whether internal systems can communicate externally without authorization.

Test categories:

- [ ] Direct Internet access.
- [ ] DNS.
- [ ] HTTP.
- [ ] HTTPS.
- [ ] Non-standard ports.
- [ ] Cloud services.
- [ ] File-transfer services.
- [ ] Unknown destinations.

---

# 45. Proxy Controls

Check whether proxy controls detect/block:

- [ ] Suspicious destinations.
- [ ] Newly registered domains.
- [ ] Unapproved file transfers.
- [ ] Sensitive information transmission.
- [ ] Unsanctioned cloud storage.
- [ ] Unknown applications.

---

# 46. Segmentation Matrix

Create a matrix:

| Source | Destination | Expected | Actual | Result |
|---|---|---|---|---|
| User | User | Restricted | | |
| User | Server | Limited | | |
| User | DC | Required only | | |
| User | Management | Blocked | | |
| User | Backup | Blocked | | |
| Guest | Corporate | Blocked | | |
| VPN | Corporate | Controlled | | |
| Server | DC | Required only | | |
| Server | Backup | Controlled | | |
| Admin | Tier 0 | Allowed | | |

---

# 47. Trust Relationship Testing

Identify:

- [ ] AD trusts.
- [ ] Forest trusts.
- [ ] External trusts.
- [ ] Cloud identity trusts.
- [ ] Application trusts.
- [ ] Third-party federation.

Determine whether compromise of one environment provides unintended access to another.

---

# 48. Third-Party Access

Assess:

- [ ] Vendor VPN.
- [ ] Vendor accounts.
- [ ] Supplier accounts.
- [ ] MSP access.
- [ ] Contractor access.
- [ ] External identities.
- [ ] Remote-management software.

Check:

- MFA.
- Least privilege.
- Time restrictions.
- Network restrictions.
- Logging.
- Account lifecycle.

---

# 49. Physical Security

If explicitly authorized:

## PHY-001 — Office Access

Test:

- [ ] Badge controls.
- [ ] Tailgating resistance.
- [ ] Visitor controls.
- [ ] Secure areas.
- [ ] Server-room access.
- [ ] Network-room access.

---

## PHY-002 — Unattended Systems

Assess:

- [ ] Unlocked workstations.
- [ ] Exposed documents.
- [ ] Exposed credentials.
- [ ] Network ports.
- [ ] Console access.

---

# 50. Privileged Workstation Security

Check:

- [ ] Dedicated administrator workstations.
- [ ] Separate admin accounts.
- [ ] Internet restrictions.
- [ ] EDR.
- [ ] Application control.
- [ ] Credential isolation.
- [ ] Administrative tier separation.

---

# 51. Security Control Tampering

Where authorized, assess whether a low-privileged or compromised account can modify:

- [ ] EDR.
- [ ] Antivirus.
- [ ] Firewall.
- [ ] Logging.
- [ ] SIEM agents.
- [ ] Monitoring agents.
- [ ] Backup agents.
- [ ] Security configurations.

**Expected Result:**
Security controls should be protected from unauthorized modification and generate high-priority alerts when modification is attempted.

---

# 52. Incident Response Validation

## IR-001 — Alert Escalation

Determine whether the SOC:

- [ ] Recognizes malicious activity.
- [ ] Identifies affected host.
- [ ] Identifies affected user.
- [ ] Identifies attack stage.
- [ ] Correlates related activity.
- [ ] Escalates appropriately.

---

## IR-002 — Containment

Determine whether responders can:

- [ ] Isolate endpoint.
- [ ] Disable account.
- [ ] Revoke sessions.
- [ ] Rotate credentials.
- [ ] Block network traffic.
- [ ] Remove persistence.
- [ ] Identify additional compromised assets.

---

## IR-003 — Eradication

Validate:

- [ ] Root cause identified.
- [ ] Persistence removed.
- [ ] Credentials rotated.
- [ ] Compromised systems identified.
- [ ] Backdoors removed.
- [ ] Security controls restored.

---

# 53. Purple-Team Test Cases

For each detection:

| ID | Technique Category | Red-Team Action | Expected Detection | Actual Detection | Result |
|---|---|---|---|---|---|
| PT-001 | Discovery | Authorized discovery simulation | SIEM/EDR | | |
| PT-002 | Authentication | Suspicious authentication | Identity alert | | |
| PT-003 | Privilege | Privilege modification simulation | IAM alert | | |
| PT-004 | Lateral Movement | Approved remote access | EDR/SIEM | | |
| PT-005 | Persistence | Persistence simulation | EDR | | |
| PT-006 | Data Access | Sensitive data access | DLP | | |
| PT-007 | Exfiltration | Synthetic data transfer | DLP/NDR | | |

---

# 54. Attack Path Analysis

For each discovered path document:

```text
Initial Foothold
      |
      v
Compromised User
      |
      v
Internal Discovery
      |
      v
Credential / Permission Weakness
      |
      v
Privilege Escalation
      |
      v
Lateral Movement
      |
      v
Higher Privilege
      |
      v
Critical Asset
      |
      v
Business Objective
```

Document:

- Starting privilege.
- Required conditions.
- Intermediate systems.
- Intermediate accounts.
- Security controls encountered.
- Detection points.
- Final privilege.
- Business impact.

---

# 55. Crown Jewel Assessment

Identify critical assets such as:

- [ ] Domain Controllers.
- [ ] Identity Provider.
- [ ] PKI.
- [ ] Backup infrastructure.
- [ ] ERP.
- [ ] Finance systems.
- [ ] HR systems.
- [ ] Source-code repositories.
- [ ] Production infrastructure.
- [ ] Customer databases.
- [ ] Cloud control plane.
- [ ] Security-management infrastructure.

For each:

| Asset | Attack Path | Required Privilege | Detection | Impact |
|---|---|---|---|---|
| | | | | |

---

# 56. Business Impact Validation

Determine whether the red-team path could result in:

- [ ] Unauthorized data access.
- [ ] Financial fraud.
- [ ] Intellectual-property theft.
- [ ] Customer-data exposure.
- [ ] Identity compromise.
- [ ] Administrative compromise.
- [ ] Production compromise.
- [ ] Ransomware-style impact.
- [ ] Operational disruption.
- [ ] Regulatory exposure.

---

# 57. Credential Hygiene Checklist

- [ ] No default passwords.
- [ ] No shared administrator passwords.
- [ ] No password reuse across systems.
- [ ] Service-account credentials protected.
- [ ] Secrets removed from repositories.
- [ ] Secrets removed from scripts.
- [ ] Secrets removed from documentation.
- [ ] API keys rotated.
- [ ] Stale credentials removed.
- [ ] MFA enforced.
- [ ] Privileged credentials isolated.
- [ ] Local administrator credentials randomized.
- [ ] Password vaulting implemented.

---

# 58. Logging Checklist

## Identity

- [ ] Successful authentication.
- [ ] Failed authentication.
- [ ] Privilege changes.
- [ ] Group changes.
- [ ] MFA events.
- [ ] Account creation.
- [ ] Account deletion.
- [ ] Password changes.

## Endpoint

- [ ] Process creation.
- [ ] Command execution.
- [ ] Script execution.
- [ ] Service creation.
- [ ] Scheduled task creation.
- [ ] Security-policy changes.

## Network

- [ ] Firewall events.
- [ ] DNS queries.
- [ ] VPN connections.
- [ ] Proxy activity.
- [ ] East-west traffic.

## Cloud

- [ ] IAM changes.
- [ ] API activity.
- [ ] Role changes.
- [ ] Storage access.
- [ ] Administrative operations.

---

# 59. Detection Coverage Matrix

| Attack Stage | Technique | Log Source | Detection | Alert | Analyst Action |
|---|---|---|---|---|---|
| Initial Access | | | | | |
| Discovery | | | | | |
| Credential Access | | | | | |
| Privilege Escalation | | | | | |
| Lateral Movement | | | | | |
| Persistence | | | | | |
| Collection | | | | | |
| Exfiltration | | | | | |
| Impact | | | | | |

---

# 60. Risk Rating

Suggested rating model:

## Critical

Use when:

- Domain/identity infrastructure can be compromised by a low-privileged user.
- Sensitive production/customer data is broadly accessible.
- Security boundaries can be bypassed.
- Administrative compromise can be achieved with minimal prerequisites.
- Critical business systems can be compromised.

## High

Use when:

- Significant privilege escalation is possible.
- Major network segmentation weaknesses exist.
- Sensitive systems are accessible.
- Important credentials are exposed.
- Monitoring fails to detect meaningful attack activity.

## Medium

Use when:

- Exploitation requires several prerequisites.
- Exposure is limited.
- Compromise affects non-critical systems.
- Detection exists but response is weak.

## Low

Use when:

- Finding has limited security impact.
- Exploitation requires unusual circumstances.
- Compensating controls substantially reduce risk.

---

# 61. Finding Template

For every finding use:

```markdown
## FINDING-XXX — <Title>

### Severity
Critical / High / Medium / Low / Informational

### Category
<Identity / AD / Network / Endpoint / Cloud / Application / Detection>

### Description
<What was discovered>

### Security Impact
<What an attacker could achieve>

### Attack Path
<High-level attack path>

### Preconditions
<Required access or conditions>

### Affected Assets
<List assets>

### Evidence
<Screenshots, logs, timestamps, identifiers>

### Detection
<Whether SOC/EDR/SIEM detected activity>

### Business Impact
<Business consequence>

### Root Cause
<Underlying control weakness>

### Recommendation
<Remediation>

### Priority
<P0/P1/P2/P3>

### Retest Requirement
<Yes/No>

### Retest Result
<Pending / Passed / Failed>
```

---

# 62. Evidence Checklist

For every finding collect:

- [ ] Timestamp.
- [ ] Hostname.
- [ ] IP address.
- [ ] Username.
- [ ] Domain.
- [ ] Relevant application.
- [ ] Security-control result.
- [ ] Screenshot.
- [ ] Relevant log.
- [ ] SIEM alert.
- [ ] EDR alert.
- [ ] Ticket/incident number.
- [ ] Reproduction notes.
- [ ] Remediation evidence.

Avoid retaining:

- Unnecessary passwords.
- Private keys.
- Customer data.
- Personal information.
- Unrelated sensitive documents.

---

# 63. Cleanup Checklist

## Accounts

- [ ] Test accounts removed.
- [ ] Temporary privileges removed.
- [ ] Temporary group memberships removed.
- [ ] Temporary credentials revoked.

## Endpoints

- [ ] Test files removed.
- [ ] Test services removed.
- [ ] Test scheduled tasks removed.
- [ ] Test configurations reverted.
- [ ] Test software removed.

## Cloud

- [ ] Temporary roles removed.
- [ ] Temporary API keys revoked.
- [ ] Temporary resources removed.
- [ ] Temporary security groups removed.

## Network

- [ ] Temporary firewall rules removed.
- [ ] Temporary VPN access removed.
- [ ] Temporary routes removed.

## Credentials

- [ ] Test passwords rotated.
- [ ] Exposed credentials rotated.
- [ ] API tokens revoked.
- [ ] Certificates revoked where necessary.

---

# 64. Retesting Checklist

For every remediated finding:

- [ ] Original condition reproduced.
- [ ] Remediation verified.
- [ ] Original attack path retested.
- [ ] Access denied as expected.
- [ ] Detection verified.
- [ ] Logging verified.
- [ ] No alternate path identified.
- [ ] Finding marked closed.

---

# 65. Final Assessment Checklist

## Identity

- [ ] AD reviewed.
- [ ] Privileged groups reviewed.
- [ ] Delegation reviewed.
- [ ] ACLs reviewed.
- [ ] ADCS reviewed.
- [ ] Authentication reviewed.
- [ ] MFA reviewed.
- [ ] PAM reviewed.

## Network

- [ ] Asset discovery.
- [ ] Service exposure.
- [ ] Segmentation.
- [ ] VPN.
- [ ] Wireless.
- [ ] Egress.
- [ ] Management network.

## Endpoints

- [ ] Windows.
- [ ] Linux.
- [ ] EDR.
- [ ] Local admin.
- [ ] Hardening.
- [ ] Logging.

## Applications

- [ ] Internal web apps.
- [ ] APIs.
- [ ] Databases.
- [ ] Source code.
- [ ] CI/CD.
- [ ] Containers.

## Cloud

- [ ] IAM.
- [ ] Storage.
- [ ] Network.
- [ ] Compute.
- [ ] Secrets.
- [ ] SaaS.

## Data

- [ ] Sensitive data discovery.
- [ ] Access controls.
- [ ] DLP.
- [ ] Exfiltration detection.

## Detection

- [ ] SIEM.
- [ ] EDR.
- [ ] NDR.
- [ ] DLP.
- [ ] Identity monitoring.
- [ ] SOC response.

## Response

- [ ] Detection.
- [ ] Triage.
- [ ] Containment.
- [ ] Eradication.
- [ ] Recovery.
- [ ] Lessons learned.

---

# 66. Executive Metrics

Report at minimum:

| Metric | Result |
|---|---:|
| Total assets assessed | |
| User endpoints assessed | |
| Servers assessed | |
| Critical assets assessed | |
| Valid attack paths | |
| Critical findings | |
| High findings | |
| Medium findings | |
| Low findings | |
| Privilege-escalation paths | |
| Lateral-movement paths | |
| Sensitive-data access paths | |
| Critical assets reachable | |
| Detection opportunities | |
| Detected attack stages | |
| Undetected attack stages | |
| Mean Time to Detect | |
| Mean Time to Respond | |
| Findings requiring retest | |

---

# 67. Attack Path Scoring

For each attack path calculate:

```text
Attack Path Risk =
Initial Access Difficulty
+ Privilege Escalation Difficulty
+ Lateral Movement Difficulty
+ Detection Weakness
+ Asset Criticality
+ Business Impact
```

Recommended qualitative categories:

| Factor | Low | Medium | High | Critical |
|---|---|---|---|---|
| Initial Access | Difficult | Moderate | Easy | Trivial |
| Privilege Escalation | Difficult | Moderate | Easy | Trivial |
| Lateral Movement | Difficult | Moderate | Easy | Trivial |
| Detection | Strong | Partial | Weak | None |
| Asset Criticality | Low | Moderate | High | Critical |
| Business Impact | Low | Moderate | High | Severe |

---

# 68. Recommended Test Case ID Structure

Use consistent identifiers:

```text
ROE-xxx    Rules of Engagement
IA-xxx     Initial Access
NET-xxx    Network
AD-xxx     Active Directory
ADCS-xxx   Certificate Services
CREDS-xxx  Credentials
END-xxx    Endpoint
WIN-xxx    Windows
LNX-xxx    Linux
LAT-xxx    Lateral Movement
SMB-xxx    File Sharing
DB-xxx     Database
BAK-xxx    Backup
VIRT-xxx   Virtualization
NETDEV-xxx Network Devices
WIFI-xxx   Wireless
VPN-xxx    VPN
PAM-xxx    Privileged Access
MFA-xxx    MFA
MAIL-xxx   Email
APP-xxx    Applications
API-xxx    APIs
CICD-xxx   CI/CD
CONT-xxx   Containers
K8S-xxx    Kubernetes
CLOUD-xxx  Cloud
SAAS-xxx   SaaS
DATA-xxx   Data
PERS-xxx   Persistence
EDR-xxx    EDR
SIEM-xxx   SIEM
SOC-xxx    SOC
IR-xxx     Incident Response
PHY-xxx    Physical
PT-xxx     Purple Team
```

---

# 69. Master Test Execution Tracker

| ID | Test Case | Scope | Priority | Status | Result | Evidence | Finding |
|---|---|---|---|---|---|---|---|
| ROE-001 | Authorization | Governance | P0 | | | | |
| NET-001 | Asset Discovery | Network | P1 | | | | |
| NET-002 | Service Enumeration | Network | P1 | | | | |
| NET-003 | Segmentation | Network | P0 | | | | |
| AD-001 | Domain Discovery | AD | P1 | | | | |
| AD-002 | Privileged Groups | AD | P0 | | | | |
| AD-003 | Nested Groups | AD | P0 | | | | |
| AD-010 | Kerberos Configuration | AD | P1 | | | | |
| AD-011 | NTLM Usage | AD | P1 | | | | |
| AD-012 | LDAP Security | AD | P1 | | | | |
| AD-020 | ACL Review | AD | P0 | | | | |
| AD-021 | GPO Security | AD | P0 | | | | |
| AD-022 | Delegation | AD | P0 | | | | |
| ADCS-001 | PKI Discovery | ADCS | P1 | | | | |
| ADCS-002 | Certificate Templates | ADCS | P0 | | | | |
| CREDS-001 | Credential Discovery | Identity | P0 | | | | |
| CREDS-002 | Password Policy | Identity | P1 | | | | |
| END-001 | Endpoint Protection | Endpoint | P1 | | | | |
| END-002 | Local Admin | Endpoint | P0 | | | | |
| LAT-001 | Workstation Lateral Movement | Network | P0 | | | | |
| LAT-002 | Server Access | Network | P0 | | | | |
| BAK-001 | Backup Access | Infrastructure | P0 | | | | |
| CLOUD-001 | Cloud Identity | Cloud | P0 | | | | |
| CLOUD-002 | Cloud Privileges | Cloud | P0 | | | | |
| DATA-001 | Sensitive Data | Data | P0 | | | | |
| DATA-003 | Exfiltration Simulation | Data | P0 | | | | |
| EDR-001 | EDR Coverage | Detection | P0 | | | | |
| SIEM-001 | SIEM Coverage | Detection | P0 | | | | |
| SOC-001 | Detection | SOC | P0 | | | | |
| IR-001 | Escalation | IR | P0 | | | | |
| IR-002 | Containment | IR | P0 | | | | |
| PT-001 | Purple Team Validation | Detection | P1 | | | | |

---

# 70. Minimum Internal Red-Team Coverage

A mature internal red-team assessment should, at minimum, answer these questions:

### Initial Access
- Can an attacker establish an internal foothold?
- What can the compromised identity see?
- What credentials become available?

### Identity
- Can a standard user become privileged?
- Can privileges cross administrative tiers?
- Are privileged credentials isolated?

### Active Directory
- Can low-privileged users influence privileged objects?
- Are delegation paths secure?
- Is ADCS securely configured?
- Is legacy authentication sufficiently restricted?

### Network
- Can an attacker move between security zones?
- Can workstations communicate with each other?
- Can user networks reach management infrastructure?

### Endpoints
- Are local administrators controlled?
- Is EDR effective?
- Is security telemetry complete?

### Lateral Movement
- Can one compromised workstation lead to servers?
- Can servers lead to identity infrastructure?
- Can compromised credentials be reused?

### Data
- Can sensitive information be reached?
- Can it be transferred outside approved boundaries?
- Does DLP detect the activity?

### Cloud
- Can corporate identity compromise lead to cloud administrative access?
- Are service identities overprivileged?
- Are production and development environments separated?

### Detection
- Does the SOC see the attack?
- Can analysts reconstruct the attack chain?
- How quickly is the activity detected?

### Response
- Can the SOC isolate affected hosts?
- Can accounts be disabled?
- Can credentials be revoked?
- Can persistence be removed?

### Business Impact
- Can an attacker reach crown-jewel systems?
- What is the shortest path?
- What security controls stop that path?
- What controls fail to stop it?

---

# 71. Final Red-Team Deliverables

The final engagement package should contain:

1. **Executive Summary**
2. **Scope and Rules of Engagement**
3. **Attack Narrative**
4. **Attack Path Diagrams**
5. **Critical Findings**
6. **High-Risk Findings**
7. **Detailed Technical Findings**
8. **Active Directory Assessment**
9. **Network Segmentation Assessment**
10. **Credential Exposure Assessment**
11. **Endpoint Security Assessment**
12. **Cloud Security Assessment**
13. **Data Access Assessment**
14. **Detection & SOC Assessment**
15. **Incident Response Assessment**
16. **Purple-Team Results**
17. **Risk-Ranked Remediation Plan**
18. **Evidence Appendix**
19. **Cleanup Confirmation**
20. **Retest Plan**

---

# 72. Remediation Priority Framework

## P0 — Immediate

- Identity/domain compromise path.
- Critical data exposure.
- Critical infrastructure compromise.
- Security-control bypass.
- Unrestricted administrative access.

## P1 — Urgent

- High-impact privilege escalation.
- Significant segmentation failure.
- Broad credential exposure.
- Major detection gaps.
- Production access from low-trust environments.

## P2 — Important

- Moderate privilege issues.
- Limited segmentation problems.
- Weak endpoint configuration.
- Incomplete logging.

## P3 — Hardening

- Informational weaknesses.
- Defense-in-depth improvements.
- Minor configuration issues.
- Documentation improvements.

---

# 73. Final Quality Gate

Before closing the engagement confirm:

- [ ] Every in-scope network was assessed.
- [ ] Every major identity system was assessed.
- [ ] Active Directory was assessed.
- [ ] Privileged access was assessed.
- [ ] Segmentation was tested.
- [ ] Lateral movement was assessed.
- [ ] Endpoint controls were assessed.
- [ ] Cloud environments were assessed.
- [ ] Critical applications were assessed.
- [ ] Sensitive data access was assessed.
- [ ] Detection coverage was assessed.
- [ ] SOC response was assessed.
- [ ] Incident response was exercised.
- [ ] Attack paths were documented.
- [ ] Evidence was collected.
- [ ] Cleanup was completed.
- [ ] Temporary accounts/permissions were removed.
- [ ] Exposed credentials were rotated where necessary.
- [ ] Client stakeholders were notified of critical findings.
- [ ] Retesting requirements were documented.
- [ ] Final report was reviewed.
- [ ] Scope closure was confirmed.

---

# 74. Overall Assessment Conclusion

The final conclusion should answer:

> **"If an attacker compromises one ordinary internal identity or workstation, how far can they realistically progress toward the organization's most important assets, and which controls prevent or detect that progression?"**

The assessment should therefore prioritize **attack paths and business impact**, rather than simply producing a list of isolated vulnerabilities.

A strong final assessment should identify:

- The most realistic initial access scenarios.
- The shortest privilege-escalation paths.
- The easiest lateral-movement paths.
- The most dangerous identity weaknesses.
- The most exposed sensitive data.
- The most important segmentation failures.
- The strongest defensive controls.
- The most significant detection gaps.
- The SOC's ability to reconstruct and contain the attack.
- The smallest set of remediation actions that will eliminate the highest-risk attack paths.

# 75. Opportunistic Hacking Test Cases

## 75.1 Purpose

Opportunistic testing simulates an attacker who has gained limited internal access but does **not** yet have a specific target.

The objective is to discover:

- Forgotten systems.
- Misconfigured services.
- Weak authentication.
- Exposed administrative interfaces.
- Unintended trust relationships.
- Credential leakage.
- Shadow IT.
- Legacy systems.
- Development/test infrastructure.
- Backup infrastructure.
- Management interfaces.
- Unnecessary network exposure.
- Sensitive information exposed through ordinary internal access.

The emphasis is on **breadth of discovery followed by controlled validation**.

---

# 76. Opportunistic Discovery

## OPP-001 — Unintended Asset Discovery

Determine whether an ordinary internal user can identify:

- [ ] Unknown servers.
- [ ] Development systems.
- [ ] Test systems.
- [ ] Legacy systems.
- [ ] Forgotten virtual machines.
- [ ] Temporary systems.
- [ ] Network appliances.
- [ ] Printers.
- [ ] Cameras.
- [ ] IoT devices.
- [ ] NAS devices.
- [ ] Hypervisors.
- [ ] Management systems.
- [ ] Security appliances.
- [ ] Monitoring systems.

### Expected Result

Asset inventory should reasonably correspond with what can actually be discovered from the internal network.

### Questions

- Is there an asset that security does not know exists?
- Is the asset owner known?
- Is the asset patched?
- Is it monitored?
- Is authentication required?
- Does it belong to a different security zone?

---

## OPP-002 — Legacy System Discovery

Identify:

- [ ] Legacy Windows systems.
- [ ] Legacy Linux systems.
- [ ] Unsupported applications.
- [ ] Deprecated protocols.
- [ ] Old database servers.
- [ ] Old network appliances.
- [ ] Unsupported web applications.
- [ ] Forgotten development environments.

### Risk Indicators

- Unsupported OS.
- No EDR.
- Weak authentication.
- Unencrypted protocols.
- Default credentials.
- No centralized logging.

---

## OPP-003 — Shadow IT

Identify unauthorized or unmanaged:

- [ ] Cloud services.
- [ ] File-sharing services.
- [ ] Remote-access software.
- [ ] VPN services.
- [ ] Web applications.
- [ ] Development servers.
- [ ] Personal cloud storage.
- [ ] SaaS applications.
- [ ] Network appliances.

Record:

| Asset | Owner | Purpose | Managed? | Security Monitoring | Risk |
|---|---|---|---|---|---|
| | | | | | |

---

# 77. Opportunistic Service Testing

## OPP-010 — Unnecessary Services

Look for internally exposed services that appear unnecessary.

Categories:

- [ ] Remote administration.
- [ ] File sharing.
- [ ] Database.
- [ ] Web management.
- [ ] Monitoring.
- [ ] Development.
- [ ] Debugging.
- [ ] Backup.
- [ ] Remote desktop.
- [ ] API endpoints.

For each service determine:

- Owner.
- Business purpose.
- Authentication.
- Authorization.
- Encryption.
- Network exposure.
- Logging.
- Patch status.

---

## OPP-011 — Administrative Interfaces

Identify administrative consoles exposed to ordinary user networks.

Examples:

- [ ] Firewall consoles.
- [ ] Switch management.
- [ ] Router management.
- [ ] Hypervisor consoles.
- [ ] Backup consoles.
- [ ] EDR consoles.
- [ ] Monitoring consoles.
- [ ] Printer administration.
- [ ] Storage administration.
- [ ] Application administration.

### Expected Result

Administrative interfaces should be reachable only from appropriate management networks or through controlled privileged-access mechanisms.

---

## OPP-012 — Default Configuration

Check authorized systems for:

- [ ] Default accounts.
- [ ] Default passwords.
- [ ] Vendor sample applications.
- [ ] Default certificates.
- [ ] Default API keys.
- [ ] Default management ports.
- [ ] Default community strings.
- [ ] Unchanged installation settings.

---

# 78. Opportunistic Web Testing

## OPP-020 — Internal Web Application Discovery

Identify:

- [ ] Internal portals.
- [ ] Admin portals.
- [ ] Development applications.
- [ ] Test applications.
- [ ] Monitoring dashboards.
- [ ] Documentation portals.
- [ ] API documentation.
- [ ] Debug interfaces.
- [ ] Health endpoints.
- [ ] Management consoles.

---

## OPP-021 — Authentication Weaknesses

Assess:

- [ ] Missing authentication.
- [ ] Weak authentication.
- [ ] Shared credentials.
- [ ] Default credentials.
- [ ] Missing MFA.
- [ ] Broken SSO.
- [ ] Legacy authentication.
- [ ] Excessive session lifetime.
- [ ] Insecure password-reset mechanisms.

---

## OPP-022 — Authorization Boundary

Determine whether an ordinary user can access:

- [ ] Administrator pages.
- [ ] Other users' records.
- [ ] Internal configuration.
- [ ] Application secrets.
- [ ] Debug information.
- [ ] Management APIs.
- [ ] Administrative APIs.

---

# 79. Opportunistic Information Disclosure

## OPP-030 — Internal Documentation

Review authorized internal resources for accidental disclosure of:

- [ ] Passwords.
- [ ] API keys.
- [ ] Connection strings.
- [ ] VPN details.
- [ ] Network diagrams.
- [ ] Administrative procedures.
- [ ] Infrastructure details.
- [ ] Backup information.
- [ ] Security architecture.
- [ ] Production credentials.

---

## OPP-031 — File Metadata

Assess whether accessible documents reveal:

- Usernames.
- Hostnames.
- Internal IP addresses.
- File paths.
- Application names.
- Software versions.
- Infrastructure information.

---

## OPP-032 — Source Code Exposure

Check accessible repositories for:

- [ ] Credentials.
- [ ] API keys.
- [ ] Certificates.
- [ ] Connection strings.
- [ ] Deployment credentials.
- [ ] Cloud identities.
- [ ] Internal endpoints.
- [ ] Administrative functionality.

Do not unnecessarily copy or retain secret material.

---

# 80. Opportunistic Credential Hunting

## OPP-040 — Credential Exposure Locations

Review approved locations such as:

- [ ] Shared drives.
- [ ] Scripts.
- [ ] Configuration files.
- [ ] Documentation.
- [ ] Repositories.
- [ ] Deployment systems.
- [ ] Ticket attachments.
- [ ] Internal wikis.
- [ ] Automation platforms.
- [ ] Backup configurations.

---

## OPP-041 — Credential Reuse Validation

Where explicitly authorized, determine whether discovered credentials provide access to:

- [ ] Other workstations.
- [ ] Servers.
- [ ] Applications.
- [ ] VPN.
- [ ] Cloud.
- [ ] SaaS.
- [ ] Network infrastructure.

### Expected Result

Credentials should be narrowly scoped and preferably unique to their intended service.

---

# 81. Opportunistic Trust Testing

## OPP-050 — Trust Boundary Discovery

Identify relationships between:

- Corporate network.
- Development network.
- Test network.
- Production network.
- Guest network.
- BYOD network.
- IoT network.
- Management network.
- Security network.
- Cloud.
- Third-party environments.

---

## OPP-051 — Unexpected Trust

Determine whether low-trust systems can communicate with:

- [ ] Domain controllers.
- [ ] Management systems.
- [ ] Databases.
- [ ] Backup infrastructure.
- [ ] Security infrastructure.
- [ ] Production systems.

---

# 82. Opportunistic Database Discovery

Identify internally accessible:

- [ ] SQL databases.
- [ ] NoSQL databases.
- [ ] Search engines.
- [ ] Cache systems.
- [ ] Message queues.
- [ ] Data warehouses.

Check for:

- Authentication.
- Encryption.
- Network restrictions.
- Anonymous access.
- Excessive permissions.
- Sensitive data exposure.

---

# 83. Opportunistic Backup Discovery

Look for:

- [ ] Backup servers.
- [ ] Backup shares.
- [ ] Snapshot storage.
- [ ] Archive systems.
- [ ] Cloud backup.
- [ ] Configuration backups.

Assess whether backup infrastructure could expose:

- Credentials.
- System configurations.
- Sensitive documents.
- Database dumps.
- Identity infrastructure data.

---

# 84. Opportunistic Monitoring/Security Infrastructure

Determine whether an ordinary user can access:

- [ ] SIEM dashboards.
- [ ] EDR portals.
- [ ] Vulnerability scanners.
- [ ] Network monitoring.
- [ ] Asset inventory.
- [ ] Backup monitoring.
- [ ] Security ticketing.

### Expected Result

Security infrastructure should not be broadly accessible to ordinary users.

---

# 85. Opportunistic Printer/IoT Testing

Identify:

- [ ] Network printers.
- [ ] Cameras.
- [ ] Door controllers.
- [ ] Conference systems.
- [ ] Smart displays.
- [ ] VoIP devices.
- [ ] Badge systems.
- [ ] Specialized appliances.

Check:

- Authentication.
- Firmware.
- Management interfaces.
- Default credentials.
- Network segmentation.
- Sensitive information exposure.

---

# 86. Opportunistic Remote Access

Identify unauthorized or unexpected remote-access mechanisms:

- [ ] Remote desktop tools.
- [ ] SSH.
- [ ] Remote support software.
- [ ] VPN clients.
- [ ] Web-based remote consoles.
- [ ] Vendor remote-management systems.

Determine:

- Who owns it?
- Why does it exist?
- Who can use it?
- Is MFA enforced?
- Is activity logged?
- Is it centrally managed?

---

# 87. Opportunistic Attack Path Escalation

When an interesting weakness is found:

```text
Discovery
   |
   v
Interesting Asset
   |
   v
Authentication Boundary
   |
   v
Privilege Boundary
   |
   v
Trust Relationship
   |
   v
Sensitive System
```

The tester should validate the **minimum necessary steps** to determine impact rather than continuing toward unnecessary compromise.

---

# 88. Wi-Fi Pentesting

# 88.1 Wireless Scope

Document:

- [ ] Corporate SSIDs.
- [ ] Guest SSIDs.
- [ ] BYOD SSIDs.
- [ ] IoT SSIDs.
- [ ] Voice SSIDs.
- [ ] Warehouse SSIDs.
- [ ] Temporary SSIDs.
- [ ] Hidden SSIDs.
- [ ] Outdoor wireless.
- [ ] Remote-office wireless.
- [ ] Branch-office wireless.

---

# 89. WIFI-001 — Wireless Reconnaissance

Identify authorized wireless infrastructure:

- SSID.
- BSSID.
- Authentication type.
- Encryption type.
- Channel.
- Band.
- Access-point location.
- Signal coverage.
- Associated security zone.

Record:

| SSID | Security | Authentication | Network | Location | Risk |
|---|---|---|---|---|---|
| | | | | | |

---

# 90. WIFI-002 — Rogue AP Detection

Determine whether the organization can identify unauthorized access points.

Test conceptually:

- Authorized AP.
- Unauthorized AP.
- Misconfigured AP.
- Personal hotspot.
- Duplicate corporate SSID.

Check:

- [ ] Wireless IDS/IPS.
- [ ] WLC monitoring.
- [ ] SOC visibility.
- [ ] Alert generation.
- [ ] Incident response.

---

# 91. WIFI-003 — Corporate SSID Security

Assess:

- [ ] WPA2-Enterprise.
- [ ] WPA3-Enterprise.
- [ ] 802.1X.
- [ ] Certificate authentication.
- [ ] EAP configuration.
- [ ] RADIUS security.
- [ ] Client certificate validation.
- [ ] Protected management frames.
- [ ] Strong cryptographic configuration.

### Expected Result

Corporate wireless should use enterprise authentication and strong encryption appropriate to organizational requirements.

---

# 92. WIFI-004 — Pre-Shared Key Security

Where PSK is authorized:

Assess:

- [ ] Password strength.
- [ ] Password reuse.
- [ ] Shared access.
- [ ] Guest exposure.
- [ ] Key rotation.
- [ ] Employee knowledge of PSK.
- [ ] Former employee access.

### Important

Do not conduct uncontrolled password attacks against production wireless networks. Use approved test credentials or controlled test infrastructure where possible.

---

# 93. WIFI-005 — 802.1X Authentication

Test:

- [ ] User authentication.
- [ ] Device authentication.
- [ ] Certificate validation.
- [ ] RADIUS authentication.
- [ ] Account disablement.
- [ ] Expired credentials.
- [ ] Revoked certificates.
- [ ] Guest onboarding.

---

# 94. WIFI-006 — Certificate Validation

Determine whether clients properly validate the authentication server certificate.

Assess:

- [ ] Trusted CA configuration.
- [ ] Server identity validation.
- [ ] Certificate expiration.
- [ ] Certificate deployment.
- [ ] Certificate revocation handling.

### Risk

Poor certificate validation can expose wireless credentials to unauthorized authentication infrastructure.

---

# 95. WIFI-007 — Guest Network Isolation

Validate:

```text
Guest Wi-Fi
    |
    +----> Internet       ALLOWED
    |
    +----> Corporate LAN  BLOCKED
    |
    +----> Servers        BLOCKED
    |
    +----> Management     BLOCKED
    |
    +----> Printers       As required
```

Test access toward:

- [ ] Domain services.
- [ ] File shares.
- [ ] Internal web applications.
- [ ] Databases.
- [ ] Network management.
- [ ] Security infrastructure.

---

# 96. WIFI-008 — BYOD Segmentation

Determine whether personally managed devices are isolated from:

- [ ] Corporate endpoints.
- [ ] Servers.
- [ ] Identity infrastructure.
- [ ] Management networks.
- [ ] Sensitive applications.

---

# 97. WIFI-009 — IoT Wireless Segmentation

Identify whether IoT wireless devices can communicate with:

- [ ] User endpoints.
- [ ] Servers.
- [ ] Domain infrastructure.
- [ ] Management infrastructure.
- [ ] Other IoT devices.

---

# 98. WIFI-010 — Client Isolation

Assess whether wireless clients can communicate directly with one another.

Test separately for:

- Corporate.
- Guest.
- BYOD.
- IoT.

### Expected Result

Client-to-client communication should be enabled only where there is a documented business requirement.

---

# 99. WIFI-011 — Wireless-to-LAN Boundary

Determine whether wireless clients can access internal network segments beyond their intended zone.

Record:

| Wireless Network | Destination | Expected | Actual | Result |
|---|---|---|---|---|
| Corporate | Server | Controlled | | |
| Guest | Corporate | Blocked | | |
| BYOD | Corporate | Restricted | | |
| IoT | User LAN | Blocked | | |
| IoT | Internet | Controlled | | |

---

# 100. WIFI-012 — Wireless Administrative Interfaces

Check whether wireless users can reach:

- [ ] Access-point management.
- [ ] Wireless controller.
- [ ] RADIUS.
- [ ] Network management.
- [ ] Switch management.
- [ ] Monitoring interfaces.

---

# 101. WIFI-013 — Rogue/Unauthorized Client Detection

Assess whether the wireless infrastructure identifies:

- Unauthorized devices.
- Unknown MAC addresses.
- Unexpected devices.
- Duplicate device identities.
- Suspicious associations.

---

# 102. WIFI-014 — MAC-Based Access Control

If MAC filtering is used, determine whether it is treated as:

- Primary security control.
- Supplemental control.

### Expected Result

MAC filtering should not be relied upon as the primary authentication mechanism for sensitive wireless networks.

---

# 103. WIFI-015 — Wireless Credential Lifecycle

Check:

- [ ] Employee onboarding.
- [ ] Employee offboarding.
- [ ] Device replacement.
- [ ] Lost device.
- [ ] Certificate revocation.
- [ ] Password rotation.
- [ ] Guest expiration.
- [ ] Contractor expiration.

---

# 104. WIFI-016 — Wireless Coverage

Assess whether corporate wireless extends unintentionally into:

- [ ] Public areas.
- [ ] Parking lots.
- [ ] Neighboring offices.
- [ ] Shared buildings.
- [ ] Uncontrolled areas.
- [ ] Outdoor spaces.

### Objective

Determine whether the wireless attack surface extends beyond the intended physical boundary.

---

# 105. WIFI-017 — Physical Wireless Exposure

Where authorized, evaluate wireless exposure from:

- Lobby.
- Parking area.
- Building perimeter.
- Reception.
- Shared workspace.
- Adjacent office.

Record:

- Location.
- SSIDs visible.
- Authentication type.
- Approximate signal strength.
- Whether corporate access is possible.

Do not attempt unauthorized access to neighboring organizations' networks.

---

# 106. WIFI-018 — Wireless Monitoring

Determine whether the SOC receives visibility into:

- [ ] Rogue AP.
- [ ] Suspicious association.
- [ ] Authentication failures.
- [ ] Unusual authentication patterns.
- [ ] Unauthorized devices.
- [ ] Wireless controller changes.
- [ ] RADIUS anomalies.

---

# 107. WIFI-019 — Wireless Authentication Failure Detection

Use approved test accounts to generate controlled authentication failures.

Measure:

- Alert generated?
- Alert severity?
- Number of failures required?
- SOC response?
- Account lockout?
- Wireless containment?

---

# 108. WIFI-020 — Wireless Security Logging

Verify logging for:

- Authentication success.
- Authentication failure.
- Device association.
- Device disassociation.
- AP changes.
- SSID changes.
- Configuration changes.
- RADIUS events.
- Administrative access.

---

# 109. WIFI-021 — Corporate-to-Guest Boundary

Verify that corporate users cannot unintentionally bridge:

```text
Corporate Wi-Fi
       |
       X
       |
Guest Network
```

Look for:

- Shared credentials.
- Automatic connection.
- Bridging.
- Dual-homed devices.
- Misconfigured routing.

---

# 110. WIFI-022 — Dual-Homed Device Risk

Assess authorized test scenarios involving a device connected to:

- Corporate Wi-Fi + wired network.
- Corporate Wi-Fi + guest Wi-Fi.
- Corporate Wi-Fi + cellular hotspot.
- Guest Wi-Fi + corporate VPN.

Determine whether the device can create an unintended network bridge.

---

# 111. WIFI-023 — VPN over Wireless

Assess whether:

- Guest wireless can establish corporate VPN.
- BYOD wireless can establish corporate VPN.
- Device posture is validated.
- MFA is required.
- VPN users are placed into appropriate network segments.

---

# 112. WIFI-024 — Wireless-to-VPN Trust

Determine whether a device connecting from an untrusted wireless network receives more access than intended after establishing VPN connectivity.

---

# 113. WIFI-025 — Wireless Device Management

For managed endpoints assess:

- [ ] MDM enrollment.
- [ ] Device certificates.
- [ ] NAC.
- [ ] Endpoint posture.
- [ ] EDR.
- [ ] Disk encryption.
- [ ] OS compliance.

---

# 114. WIFI-026 — Network Access Control

Assess NAC behavior for:

- Managed device.
- Unmanaged device.
- Unknown device.
- Non-compliant device.
- Guest device.
- IoT device.

Expected behavior:

| Device | Expected Network |
|---|---|
| Managed corporate | Corporate |
| Unmanaged | Restricted |
| Guest | Guest |
| IoT | IoT |
| Non-compliant | Quarantine |

---

# 115. WIFI-027 — Wireless VLAN Assignment

Validate that authentication results in the correct VLAN/network.

Check for:

- [ ] User-based assignment.
- [ ] Device-based assignment.
- [ ] Role-based assignment.
- [ ] Guest assignment.
- [ ] Quarantine assignment.

---

# 116. WIFI-028 — Wireless Management Plane Isolation

Wireless clients should not normally have direct access to:

- Wireless controllers.
- Access-point management.
- Switch management.
- Router management.
- Firewall management.
- RADIUS administration.

---

# 117. WIFI-029 — Wireless Firmware & Configuration

Review:

- [ ] Firmware support status.
- [ ] Security patches.
- [ ] Management authentication.
- [ ] Administrative MFA.
- [ ] Configuration backups.
- [ ] Configuration access.
- [ ] Default settings.

---

# 118. WIFI-030 — Wireless Configuration Secrets

Check authorized configuration repositories for:

- [ ] RADIUS secrets.
- [ ] PSKs.
- [ ] API tokens.
- [ ] Administrative credentials.
- [ ] Certificates.
- [ ] Private keys.

---

# 119. Opportunistic + Wi-Fi Combined Attack Paths

The following combinations should be explicitly tested.

## COMBO-001 — Guest Wi-Fi → Internal Network

```text
Guest Wi-Fi
    |
    v
Network Discovery
    |
    v
Internal Service
    |
    v
Authentication Boundary
    |
    v
Corporate Resource
```

Determine whether guest access can reach any unintended internal service.

---

## COMBO-002 — BYOD → Corporate

```text
BYOD
 |
 v
Wireless Network
 |
 v
Internal Discovery
 |
 v
Corporate Application
 |
 v
Sensitive Data
```

---

## COMBO-003 — Wi-Fi → Internal Management

Determine whether a wireless foothold can reach:

- Network management.
- Hypervisors.
- Backup systems.
- Security systems.
- Administrative interfaces.

---

## COMBO-004 — Wi-Fi → AD

Determine whether wireless access provides unintended access to:

- DNS.
- LDAP.
- Kerberos.
- SMB.
- Domain controllers.
- Administrative services.

---

## COMBO-005 — Wi-Fi → Credential Exposure

Determine whether wireless users can access:

- Internal documentation.
- Shared drives.
- Source repositories.
- Configuration systems.
- Application portals.

---

# 120. Opportunistic Hacking Master Checklist

### Discovery

- [ ] Unknown assets.
- [ ] Legacy systems.
- [ ] Development systems.
- [ ] Test systems.
- [ ] Shadow IT.
- [ ] IoT.
- [ ] Printers.
- [ ] Network appliances.

### Services

- [ ] Unnecessary services.
- [ ] Management interfaces.
- [ ] Default configurations.
- [ ] Weak authentication.
- [ ] Legacy protocols.

### Credentials

- [ ] Shared credentials.
- [ ] Exposed credentials.
- [ ] Reused credentials.
- [ ] Secrets in source code.
- [ ] Secrets in documentation.
- [ ] Secrets in configuration.

### Trust

- [ ] Network trust.
- [ ] AD trust.
- [ ] Cloud trust.
- [ ] Application trust.
- [ ] Third-party trust.

### Applications

- [ ] Internal applications.
- [ ] APIs.
- [ ] Admin panels.
- [ ] Debug interfaces.
- [ ] Authorization boundaries.

### Infrastructure

- [ ] Backup.
- [ ] Virtualization.
- [ ] Monitoring.
- [ ] Security infrastructure.
- [ ] Network infrastructure.

---

# 121. Wi-Fi Master Checklist

### Wireless Discovery

- [ ] Corporate SSIDs.
- [ ] Guest SSIDs.
- [ ] BYOD SSIDs.
- [ ] IoT SSIDs.
- [ ] Rogue AP detection.
- [ ] Physical coverage.

### Authentication

- [ ] WPA2/WPA3.
- [ ] Enterprise authentication.
- [ ] 802.1X.
- [ ] RADIUS.
- [ ] Certificate validation.
- [ ] PSK management.

### Segmentation

- [ ] Guest isolation.
- [ ] BYOD isolation.
- [ ] IoT isolation.
- [ ] Client isolation.
- [ ] Wireless-to-LAN controls.
- [ ] Wireless-to-management controls.
- [ ] VPN segmentation.

### Endpoint/NAC

- [ ] Device identity.
- [ ] Device posture.
- [ ] MDM.
- [ ] Certificates.
- [ ] NAC.
- [ ] Quarantine.

### Monitoring

- [ ] Authentication logging.
- [ ] Rogue AP detection.
- [ ] Unauthorized device detection.
- [ ] RADIUS monitoring.
- [ ] Wireless controller logging.
- [ ] SOC integration.

### Physical

- [ ] Building perimeter.
- [ ] Parking area.
- [ ] Reception.
- [ ] Shared areas.
- [ ] Adjacent areas.

---

# 122. Expanded Master Assessment Matrix

| Domain | Test Area | Priority | Coverage |
|---|---|---:|---|
| Governance | ROE | P0 | |
| Internal | Asset discovery | P1 | |
| Internal | Service discovery | P1 | |
| Internal | Opportunistic services | P1 | |
| Internal | Shadow IT | P1 | |
| Internal | Credential exposure | P0 | |
| Internal | Trust relationships | P0 | |
| AD | Domain security | P0 | |
| AD | Privileged groups | P0 | |
| AD | ACLs | P0 | |
| AD | GPO | P0 | |
| AD | Delegation | P0 | |
| ADCS | Certificate templates | P0 | |
| Endpoint | Local admin | P0 | |
| Endpoint | EDR | P0 | |
| Network | Segmentation | P0 | |
| Network | Egress | P1 | |
| Network | Management plane | P0 | |
| Wi-Fi | Corporate authentication | P0 | |
| Wi-Fi | Guest isolation | P0 | |
| Wi-Fi | BYOD isolation | P0 | |
| Wi-Fi | IoT isolation | P1 | |
| Wi-Fi | Rogue AP detection | P1 | |
| Wi-Fi | NAC | P1 | |
| Wi-Fi | Wireless monitoring | P1 | |
| Wi-Fi | Physical coverage | P1 | |
| Applications | Internal applications | P1 | |
| Applications | APIs | P1 | |
| Cloud | IAM | P0 | |
| Cloud | Storage | P1 | |
| Cloud | Network | P1 | |
| Data | Sensitive data | P0 | |
| Data | DLP | P0 | |
| Detection | SIEM | P0 | |
| Detection | EDR | P0 | |
| Detection | SOC | P0 | |
| Response | Containment | P0 | |
| Response | Eradication | P0 | |

---

# 123. Recommended Engagement Flow

For a realistic assessment, combine the three methodologies rather than running them as completely separate exercises.

```text
                    ┌────────────────────┐
                    │ Authorized Scope    │
                    └─────────┬──────────┘
                              │
                              v
                    ┌────────────────────┐
                    │ Wireless Recon     │
                    └─────────┬──────────┘
                              │
                              v
                    ┌────────────────────┐
                    │ Internal Access    │
                    └─────────┬──────────┘
                              │
                 ┌────────────┴────────────┐
                 v                         v
       ┌──────────────────┐       ┌──────────────────┐
       │ Red-Team Path    │       │ Opportunistic    │
       │                  │       │ Discovery        │
       └────────┬─────────┘       └────────┬─────────┘
                │                          │
                └────────────┬─────────────┘
                             v
                    ┌────────────────────┐
                    │ Identity / AD      │
                    └─────────┬──────────┘
                              │
                              v
                    ┌────────────────────┐
                    │ Privilege Paths    │
                    └─────────┬──────────┘
                              │
                              v
                    ┌────────────────────┐
                    │ Lateral Movement   │
                    └─────────┬──────────┘
                              │
                    ┌─────────┴──────────┐
                    v                    v
             ┌──────────────┐     ┌──────────────┐
             │ Crown Jewels │     │ Sensitive    │
             │              │     │ Data         │
             └──────┬───────┘     └──────┬───────┘
                    │                    │
                    └─────────┬──────────┘
                              v
                    ┌────────────────────┐
                    │ Detection / SOC    │
                    └─────────┬──────────┘
                              │
                              v
                    ┌────────────────────┐
                    │ Response Validation│
                    └─────────┬──────────┘
                              │
                              v
                    ┌────────────────────┐
                    │ Cleanup + Retest   │
                    └────────────────────┘
```

---

# 124. Final Combined Objective

The combined assessment should ultimately answer:

> **"Starting from the most realistic foothold available to an attacker—including corporate Wi-Fi, guest/BYOD wireless, a compromised employee endpoint, or an opportunistically discovered internal service—how far can the attacker progress, what can they access, what security controls stop them, and how quickly does the organization detect and respond?"**

The strongest assessment is therefore not simply:

**"We found X vulnerabilities."**

It should demonstrate:

**Foothold → Discovery → Opportunity → Credential/Privilege → Lateral Movement → Crown Jewel → Detection → Response**

while separately documenting the weaknesses discovered opportunistically along the way.
