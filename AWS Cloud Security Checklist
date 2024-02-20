# AWS Cloud Security Comprehensive Checklist

## **I. Infrastructure Protection**

## VPC (Virtual Private Cloud) Security

    - Every single service in your architecture should live within a VPC.
    - Use specific NACL Inbound and Outbound rules.
    - Use Security Group Inbound and Outbound rules with IP whitelisting.
    - Enable VPC flow logs to CloudWatch.
    - Public subnets with controlled internet access.
    - Private subnets for services with no internet access.
    - Keep databases in private subnets.

### 1. **VPC Configuration**

**Test Case**: Ensure VPCs are correctly configured and don't allow unrestricted inbound or outbound traffic.

**Methods**: Review your VPC settings, especially the security group rules and network access control lists (NACLs). They should be tightly controlled to allow only necessary traffic to/from resources.

**Tools**: Use AWS Management Console or AWS CLI to check VPC configurations.

### 2. **Unused VPCs**

**Test Case**: Check for any unused VPCs and remove them.

### 3. **Isolation of Resources**

**Test Case**: Ensure that your resources are isolated correctly. Databases, application servers, and other sensitive resources should be in private subnets that are not directly reachable from the internet.

**Methods**: Segment your resources into separate subnets and utilize subnet security groups. For example, databases should be stored in private subnets without route tables leading to an internet gateway.

**Tools**: AWS Management Console, AWS CLI

### 4. **Encryption of Traffic**

**Test Case**: Check whether traffic between your VPC and on-premises resources is encrypted, especially if sensitive data is communicated.

**Methods**: Setting up a VPN connection or using AWS Direct Connect with a private virtual interface.

**Tools**: AWS VPC VPN Connections, AWS Direct Connect 

### 5. **VPC Flow Logs**

**Test Case**: Ensure VPC Flow Logs are enabled for monitoring and troubleshooting security and network issues.

**Methods**: Enable VPC Flow Logs to capture information about IP traffic in your VPC. Following this, monitor the logs for unusual traffic patterns or security issues.

**Tools**: AWS VPC Flow Logs, Amazon CloudWatch, Amazon S3

### 6. **Default VPC Security**

**Test Case**: Ensure default security settings are tightened. By default, all VPCs come with a default security group that allows all outbound traffic and all inbound traffic from instances assigned to the same security group.

**Methods**: Customise the inbound and outbound traffic rules of your default security group and avoid using it for new instances.

**Tools**: AWS Management Console, AWS CLI

### 7. **Network Access Control Lists (NACLs)**

**Test Case**: Ensure that your NACLs are configured to allow only necessary traffic and block traffic from known malicious IP addresses.

**Methods**: Review and update the inbound and outbound rules in your NACLs.

**Tools**: AWS Management Console, AWS CLI

### 8. **Security Group Configuration**

**Test Case**: Check if security group rules allow traffic from unknown or large IP ranges.

**Methods**: Limit the IP ranges allowed in your inbound and outbound rules. Ensure you are allowing traffic only from trusted and necessary IP addresses or ranges.

**Tools**: AWS Management Console, AWS CLI

## **9. VPC Peering Connections**

**Test Case**: Review peering connections between VPCs. It is essential to whitelist only necessary IP ranges or specific VPCs for secure interaction.

**Methods**: Regular audits of VPC peering configurations. Use private hosted zones in Route 53, limiting the exposure of resources.

**Tools**: AWS Management Console, AWS CLI, Amazon Route 53.

## **10. NAT Gateway Safety**

**Test Case**: Ensure NAT Gateways are, if used, configured correctly. They could expose your resources to the internet.

**Methods**: NAT gateways should be placed within public subnets with restrictive security rules. Associated route tables must also be configured to ensure only necessary internet traffic is allowed.

**Tools**: AWS Management Console, AWS CLI.

## **11. Elastic Ip’s**

**Test Case**: Ensure that there are no unused Elastic IPs because they are limited in number and lead to unnecessary charges.

**Methods**: Regularly conduct an audit to check the usage of Elastic IPs and release them when not required.

**Tools**: AWS CLI.

## **12. EC2 Security and Compliance**

**Test Case**: Review and maintain the configurations of EC2 instances for security and compliance.

**Methods**: Regularly patch instances, review IAM roles, and ensure they have restrictive inbound and outbound rules.

**Tools**: AWS Inspector, AWS CLI, AWS Management Console. 

## **13. Protocol Security**

**Test Case**: Ensure IP protocols like ICMP are blocked unless explicitly necessary.

**Methods**: Review security group settings and ensure they do not allow traffic from unnecessary protocols.

**Tools**: AWS CLI, AWS Management Console.

## **14. Proper Subnets Implementation**

**Test Case**: Validate that subnets are properly used for different workloads like private subnets for Databases, public subnets for Internet-facing applications.

**Methods**: Regularly review the subnet implementation.

**Tools**: AWS CLI, AWS Management Console.
  
Note: VPC acts as a security boundary, and proper design and periodic monitoring help keep your applications and data secure in AWS cloud infrastructure.

## **15. Resource Endpoints**

**Test Case**: Ensure your VPC has correct endpoint policies. Endpoints allow you to connect your VPC to supported AWS services securely.

**Methods**: Create VPC endpoints with restrictive access policies. Limit endpoint access only to specific resources.

**Tools**: AWS Management Console, AWS CLI.

## **16. Route Tables**

**Test Case**: Inspect your route tables for any unintended routes that can allow traffic to or from undesired sources.

**Methods**: Route tables should be properly configured. Make sure there are no routes that could expose your instances to the internet unnecessarily.

**Tools**: AWS Management Console, AWS CLI.

## **17. Transit Gateways & Direct Connect**

**Test Case**: For larger organizations, make sure that your Transit Gateways and Direct Connect settings are properly configured to secure your network infrastructure.

**Methods**: The subnet associations, route tables, and other configurations should be correct for limiting traffic to necessary services only.

**Tools**: AWS Management Console, AWS CLI.

## **18. VPC Endpoint Services**

**Test Case**: Restrict permissions for VPC endpoint services. 

**Methods**: Use IAM policies, Security Group rules, and access control lists to tighten the controls. 

**Tools**: IAM, Security Groups and Access Control Lists.

## **19. Control of Unused IPs**

**Test Case**: Regularly review and release unused Elastic IPs to avoid extra costs and maximize resource usage.

**Methods**: Documentation of Elastic IP usage and regular review of their necessity.

**Tools**: AWS Management Console, AWS CLI.

## **20. Integration with On-Premise Services**

**Test Case**: Ensure secure integration if your VPC is connected with on-premise services or other non-AWS services.

**Methods**: Make use of AWS VPN, Direct Connect, Transit Gateway, etc., and use encryption for data in transit.

**Tools**: AWS VPN, AWS Direct Connect, AWS Transit Gateway.

## **II. Encryption, IAM & EC2**

    - Use AWS KMS for key management.
    - For data at rest, use encrypted EBS volumes and S3 buckets with secured policies.
    - Set up individual IAM accounts with the least privileges.
    - Rotate credentials regularly.
    - Validate IAM roles for services and implement least privilege.
    - Ensure MFA (Multi-Factor Authentication) is enabled for all users.
    - Use hardened AMIs.
    - Regularly patch and maintain AMIs.
    - Do not use root account, use IAM roles.

## **1. Data at Rest Encryption**

**Test Case**: Ensure that data at rest is encrypted in AWS services that support it.

**Methods**: Services like S3, EBS, and RDS provide built-in features to encrypt data at rest. Make sure they are enabled.

**Tools**: AWS CLI, AWS Management Console

## **2. Data in Transit Encryption**

**Test Case**: Confirm if the data is encrypted when transmitted over a network where it's deemed necessary.

**Method**: Use SSL/TLS for transmitting sensitive data.

**Tools**: Amazon CloudFront, Elastic Load Balancing

## **3. KMS Keys**

**Test Case**: Regularly rotate your KMS keys.

**Method**: Enable automatic key rotations in AWS KMS.

**Tool**: AWS Key Management Service (KMS)

## **4. Encryption Algorithms**

**Test Case**: Ensure that strong SSL/TSL encryption algorithms (TLS 1.2 or later) are used.

**Method**: Regular audits.

**Tool**: SSL Labs SSL Server Test, AWS CLI

# IAM (Identity and Access Management) Checklist

## **1. IAM Policies**

**Test Case**: Grant least privilege access. Ensure IAM policies assigned to users/groups/roles follow the least privilege principle.

**Methods**: Regularly review IAM policies and roles for excessive permissions.

**Tools**: AWS IAM Access Analyzer, AWS Management Console, AWS CLI

## **2. Root Account**

**Test Case**: Use root account only when absolutely necessary.

**Methods**: Create individual IAM users for daily tasks, even for administrative tasks.

**Tools**: AWS Management Console

## **3. IAM Users**

**Test Case**: Regularly review IAM users for any inactive users.

**Methods**: Regularly audit the activity of IAM users and revoke access for inactive users promptly.

**Tools**: AWS CloudTrail, AWS IAM Access Analyzer

## **4. MFA tokens**

**Test Case**: Implement Multi-Factor Authentication (MFA) for all user accounts to improve account security.

**Methods**: Enforce MFA at the account level.

**Tools**: AWS MFA

## **5. Access Keys Rotation**

**Test Case**: Regularly rotate IAM user access keys.

**Methods**: Regularly update IAM user access keys.

**Tools**: AWS Management Console, AWS CLI

## **6. IAM Role Cross-Account Access**

**Test Case**: Review cross-account role permissions.

**Methods**: Ensure cross-account IAM roles are not overly permissive.

**Tools**: AWS Management Console, AWS CLI

# IAM (Identity and Access Management) Continued

## **7. Version IAM Policies**

**Test Case**: Use versioning for IAM policies to preserve, retrieve, and default to an older version of a policy.

**Methods**: Ensure policy versioning is enabled and managed correctly.

**Tools**: AWS Management Console, AWS CLI

## **8. Password Policies**

**Test Case**: Adopt strong password policies for IAM users.

**Methods**: Enforce password policies like password age, minimum length, required types of characters etc.

**Tools**: AWS Management Console

## **9. Service roles**

**Test Case**: Regularly review and update service roles

**Methods**: Check regularly to ensure that service roles follow the principle of least privilege and that unused roles are removed.

**Tools**: AWS Management Console, AWS IAM Access Analyzer

## **10. Federation SSO**

**Test Case**: If accounts are federated with an external identity provider, ensure SSO access is secure

**Methods**: Regularly audit your federation settings. Ensure only necessary SSO Access is granted.

**Tools**: AWS Management Console, AWS CLI

## **11. Create Role-Based Access Policies**

**Test Case**: Instead of assigning permissions to individual users, assign them to roles.

**Methods**: Create roles based on job function and then assign them to users.

**Tools**: AWS IAM

## **5. Encrypt Sensitive Data Fields**

**Test Case**: Sensitive data fields such as credit card numbers in your application's database should be encrypted.

**Method**: Use encryption SDKs or RDS functionality for data fields encryption.

**Tool**: AWS Encryption SDK, AWS RDS

## **6. Key Management**

**Test Case**: Ensure secure key management practices.

**Method**: Keys should be rotated and only made accessible to authorized services and roles.

**Tool**: AWS KMS, CloudHSM

## **7. Client-Side Encryption**

**Test Case**: If sensitive data is transmitted to customers, ensure client-side encryption.

**Methods**: Use SSL/TLS or other forms of encryption to protect customer data.

**Tools**: AWS Certificate Manager, AWS CLI, SDKs

## **8. EBS Snapshots**

**Test Case**: All EBS snapshots should be encrypted, regardless of whether the original EBS volumes were encrypted.

**Methods**: Use EBS snapshot copy command to copy and encrypt your unencrypted snapshot.

**Tools**: AWS Management Console, AWS CLI

## IAM (Identity and Access Management) Continued

## **9. Integration with AWS Organizations**

**Test Case**: If using AWS Organizations, ensure the right policies are in place for management and control of IAM configurations across all accounts.

**Methods**: Regular audits and use service control policies (SCPs) to set fine-grained permissions.

**Tools**: AWS Organizations

## **10. Deny Rules**

**Test Case**: Use 'Deny' rules in IAM permission policies to enforce restriction.

**Methods**: When defining IAM policies, use 'Deny' as necessary over 'Allow' permissions.

**Tools**: IAM 

## **11. Reducing Access**

**Test Case**: Regularly review IAM rules to reduce over-permissive access.

**Methods**: Monitor and adapt IAM permissions regularly to make sure no user or role has unnecessary permissions.

**Tools**: IAM Access Analyzer 

## **12. SSH Public Keys**

**Test Case**: Rotate SSH public keys regularly.

**Methods**: Use AWS Key Pair feature, set key lifespan and renewal policies.

**Tools**: AWS Management Console, AWS CLI

## **13. Encryption Algorithms & Protocols**

**Test Case**: Make sure that you are using updated and secure encryption algorithms and protocols.

**Method**: Use algorithms like RSA, AES for encryption and SHA-256 or higher for hash generation. Avoid deprecated protocols.

**Tool**: AWS KMS, CloudHSM

## **14. Encryption of All AWS Storage**

**Test Case**: Across all AWS storage services (S3, EFS, etc.), confirm that data is encrypted.

**Method**: Enable built-in encryption mechanism provided by AWS Storage services.

**Tool**: AWS Management Console, AWS CLI

## **15. Elastic Filesystem (EFS) Encryption**

**Test Case**: If you are using AWS EFS, check if data at rest and in transit to/from EFS is encrypted.

**Method**: Use AWS Key Management Service for encryption.

**Tool**: AWS Management Console, AWS CLI

## **16. Encryption for Compute Services**

**Test Case**: Encrypt data within EC2 instances and ECS containers.

**Methods**: Use OS-level security to encrypt files at the system level, use EBS encryption to encrypt the entire EC2 instance.

**Tools**: AWS CLI, Volume encryption APIs for Amazon EC2.

Note: IAM and Encryption are two significant areas when it comes to AWS Cloud Security. With IAM, ensuring that identities are correctly set up and mandated for all users and resources could go a long way towards securing the environment. While encryption ensures that data remains secure even if a breach occurs and is vital in enhancing data security. Regular audits are required to ensure optimal functioning of IAM controls and Encryption mechanisms in AWS Cloud.

## **II. Data Protection (Database and S3 Bucket)**

    - Ensure backups, snapshots, and versioning for your databases are enabled.
    - Use AWS managed database services like RDS, Aurora, DynamoDB, for automatic patching and backups.
    - Regularly patch and maintain databases.
    - Protect data in transit and at rest.
    - Enable bucket versioning to keep all versions of an object (including all writes and deletes) in your bucket.
    - Restrict permission and enable logging.

## **1. Encryption Enabled Databases**

**Test Case**: Ensure data at rest is encrypted for RDS and DynamoDB services.

**Methods**: Use the AWS Management Console to enable encryption for new instances of RDS and DynamoDB.

**Tools**: AWS KMS, AWS Management Console

## **2. Regular Patching**

**Test Case**: Regularly apply patches to your databases.

**Methods**: Enable auto minor version upgrade for RDS instances.

**Tools**: Amazon RDS, AWS Management Console

## **3. IAM Database Authentication**

**Test Case**: Use AWS Identity and Access Management (IAM) credentials to authenticate to your database.

**Methods**: IAM database authentication can be used as an additional layer of security on top of normal database credentials.

**Tools**: Amazon RDS, AWS IAM

## **4. Enable Backups**

**Test Case**: Ensure that your databases are being backed up frequently.

**Methods**: Enable automatic backups for RDS and on-demand backups for DynamoDB.

**Tools**: Amazon RDS, Amazon DynamoDB

## **5. Isolate Databases**

**Test Case**: Keep your databases in private subnets that are not exposed to the internet.

**Methods**: Use Amazon VPC to control public access to instances.

**Tools**: AWS VPC, AWS Management Console

## **6. Restrict Access**

**Test Case**: Review and update S3 bucket policies so that they allow access only to necessary services and users.

**Methods**: Update S3 bucket policies, use IAM policies for fine-grained access control, and validate Access Control Lists (ACLs).

**Tools**: AWS IAM, AWS S3 management console

## **7. Enable Versioning**

**Test Case**: Enable versioning on all buckets.

**Methods**:  This provides an additional layer of protection by storing all versions of an object (including all writes and deletes).

**Tools**: Amazon S3

## **8. Enable Logging**

**Test Case**: Enable access logging for audit trails.

**Methods**: S3 bucket logging captures and stores server access in log files.

**Tools**: Amazon S3, AWS CloudTrail.

## **9. Encryption At Rest**

**Test Case**: Data at rest must be encrypted.

**Methods**: Use server-side encryption with either Amazon S3 managed keys (SSE-S3), AWS KMS, or client-side encryption.

**Tools**: Amazon S3, AWS KMS

## **10. Encryption In Transit**

**Test Case**: Data transmitted to and from AWS S3 must be encrypted in transit.

**Method**: Ensure to use SSL endpoints for your S3 Buckets.

**Tool**: AWS CLI, SDKs

## **11. Regularly Monitor Bucket Permissions**

**Test Case**: Periodically check and correct any publicly accessible S3 buckets.

**Methods**: Use AWS Trusted Advisor or IAM to look at bucket permissions.

**Tools**: AWS Trusted Advisor, IAM. 

Note: Maintaining proper security hygiene for databases and S3 buckets is just as crucial as network-level security. Regular audits, versioning, backups, encryption in transit, and at rest and managing public permissions are some of the important aspects needed to ensure data security and integrity.

## **III. VAPT (Vulnerability Assessment and Penetration Testing)**

    - Using AWS Inspector which is an automated security assessment service that helps improve the security and compliance.
    - Conducted manually or using tools like AWS Zone and Network & Security Configuration.
    - Penetration testing requires prior approval from AWS.

**1. Scanning and Discovery**

**Test Case**: Identify the critical assets of the system and the possible ways in which they can be exploited.

**Methods**: Use automated tools to scan the software, hardware, and network services for vulnerabilities.

**Tools**: Nexpose, Nessus, OpenVAS

**2. Vulnerability Assessment**

**Test Case**: Evaluate the system to identify any security vulnerabilities.

**Methods**: Use vulnerability databases like CVEs and automated security testing tools to initiate an in-depth evaluation.

**Tools**: Nessus, Nexpose

**3. Penetration Testing**

**Test Case**: Attempt to exploit identified vulnerabilities to assess the potential impact on the system.

**Methods**: Use ethical hacking techniques, go beyond normal system functionality to identify hidden vulnerabilities.

**Tools**: Metasploit, Kali Linux, Burp Suite

# Penetration Testing Continued 

**1. Social Engineering Penetration Test**

   - **Phishing Test**:
   
     **Test Case**: Safely simulate phishing attacks to raise user awareness and test their ability to recognize and report suspicious emails.
     
     **Methods**: Craft phishing emails that mimic real attack vectors. Provide training to users who fall for the simulated attacks.
     
     **Tools**: Gophish, Phishme

   - **Pretexting Test**:
   
     **Test Case**: Test employees' inclination towards revealing sensitive information.
     
     **Methods**: Simulate scenarios where the attacker pretends to need certain information to confirm the identity of the person they are talking to.
     
     **Tools**: Manual intervention based on the scenarios created

**2. Physical Penetration Testing**

   - **Access Control Test**:
   
     **Test Case**: Test the effectiveness of physical access controls.
     
     **Methods**: Attempt to access physically secure areas without proper authorization.
     
     **Tools**: Manual techniques, lock picking tools for advanced testers

**3. Wireless Network Penetration Testing**

   - **Network Sniffing Test**:
   
     **Test Case**: Test the ability to capture and use data packets from the network.
     
     **Methods**: Use network sniffing tools to capture the data packets.
     
     **Tools**: Wireshark, Ettercap
     
   - **Cracking Wi-Fi Password**:
   
     **Test Case**: Test the strength of your Wi-Fi network's password.
     
     **Methods**: Attempt to crack the Wi-Fi password using various attacks.
     
     **Tools**: Aircrack-ng, Kismet

**4. Web Application Penetration Testing**

   - **Remote File Inclusion (RFI) Test**:
   
     **Test Case**: Test for RFI vulnerabilities in web applications.
     
     **Methods**: Attempt to exploit any web applications by including remote files.
     
     **Tools**: OWASP ZAP, Burp Suite

   - **Unvalidated Redirects and Forwards Tests**:
   
     **Test Case**: Test for unvalidated redirects and forwards vulnerabilities in web applications.
     
     **Methods**: Attempt to exploit commonly overlooked security risk involving unvalidated redirects and forwards.
     
     **Tools**: Burp Suite, OWASP ZAP

**5. Cloud Penetration Testing**

   - **Cloud Storage Test**:
   
     **Test Case**: Examine the security measures in place for cloud storage.
     
     **Methods**: Attempt access to data hosted on cloud storage without permission.
     
     **Tools**: AWS Trusted Advisor, Microsoft Azure Security Center

**6. Serverless Infrastructure Penetration Testing**

   - **Function-Level Permission Test**
   
     **Test Case**: Test the permissions at the function level in serverless infrastructures.

     **Methods**: Attempt unauthorized access to function instances.

     **Tools**: Cloud-specific tools such as AWS Trusted Advisor, Azure Security Center

**7. Container Orchestration Systems Penetration Testing**

   - **Access Controls Test**

     **Test Case**: Examine the effective implementation of access controls in container orchestration systems like Kubernetes.

     **Methods**: Attempt unauthorized operations in the container orchestration systems.

     **Tools**: kube-bench, kube-hunter

**8. Business Logic Testing**

   - **Business Process/Logic Tests**

     **Test Case**: Examine the application's business logic for potential vulnerabilities.

     **Methods**: Identify and exploit flaws in how the application enforces business rules.

     **Tools**: No specific tools because these tests are often conducted manually due to their unique nature.

**4. Tailored Threat Modeling**

**Test Case**: Specifically model threats for the given application, system, or organization.

**Methods**: Understand the system architecture, data flow, and user roles to identify potential areas of attack.

**Tools**: Microsoft Threat Modeling tool, OWASP Threat Dragon

**5. Remediation**

**Test Case**: Fix identified security vulnerabilities.

**Methods**: Prioritize vulnerabilities based on risk and criticality, and implement fixes or mitigations.

**Tools**: Remediation can include manual processes or patch management tools like ManageEngine Patch Manager or Ivanti Patch

**6. Re-Testing**

**Test Case**: Perform re-testing to ensure all vulnerabilities are properly fixed or mitigated.

**Methods**: Run the same testing procedures after the vulnerabilities have been addressed to confirm their successful remediation.

**Tools**: Same as initial testing.

**7. Documentation and Reporting**

**Test Case**: Document all findings, actions taken, and any areas that need further attention.

**Methods**: Write a detailed report containing all necessary information about the tests and findings.

**Tools**: No specific tools, could be done in Word processor or presentation software.

**8. Regular Scans and Updates**

**Test Case**: Continually monitor the system for new vulnerabilities.

**Methods**: Schedule regular scans and keep all software and security definitions updated.

**Tools**: All the previously mentioned tools are used in a continuous manner.

## **IV. Monitoring**

1. **CloudTrail**
    - Log, continuously monitor, and retain account activity.
    - Identify unusual behavior in your AWS accounts

2. **CloudWatch**
    - Monitor your resources and applications in real-time.
    - Collect and track metrics and log files.

3. **Config**
    - Evaluates configurations and configuration changes.
    - Tracks changes in AWS resource configurations.

## **V. Incident Response**

1. **GuardDuty**
    - Security threat detection service.
    - Identify unexpected and potentially unauthorized or malicious activity.

2. **VPC Flow Logs**
   - Can be used for debugging connection problems, identifying security issues, etc.


## **VI. Compliance Validation**

1. **AWS Artifact**, a compliance reporting tool - 
    - Download audit reports, GDPR-specific reports.
  
2. **AWS Trusted Advisor** to help reduce cost, increase performance, and improve security by optimizing your AWS environment.

