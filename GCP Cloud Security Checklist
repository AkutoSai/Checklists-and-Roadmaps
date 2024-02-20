# GCP Cloud Security Checklist

## Identity and Access Management (IAM)

### General
- [ ] Enable 2-step verification in GCP.
- [ ] Ensure service accounts are used sparingly for specific purposes.
- [ ] Delete service accounts that are no longer in use.

### Users & Groups
- [ ] Ensure all users and groups have defined roles.
- [ ] Regularly review and update user access permissions.
- [ ] Remove users who are no longer part of the organization.

### Roles
- [ ] Grant minimum necessary access by using predefined roles whenever possible.
- [ ] Use custom roles sparingly.
- [ ] Never grant an individual user a direct owner role to a project.

### Service Accounts
- [ ] Define service accounts with minimal necessary access.
- [ ] Schedule reminders to rotate service account keys every 90 days.

## Network Security

### Firewall rules
- [ ] Ensure firewall rules do not allow ingress from '0.0.0.0/0' to SSH (22), RDP (3389), and ICMP.
- [ ] Establish and document a process for regularly reviewing firewall rules.

### Encryption
- [ ] Enable transport level encryption for sensitive data.
- [ ] Use Cloud Key Management Service (Cloud KMS) or Customer-Supplied Encryption Keys (CSEKs) for encryption key management.

### Virtual Private Cloud (VPC)

- [ ] Implement Virtual Private Clouds (VPCs) to isolate networks for services, applications, and users.
- [ ] Ensure VPC subnets are properly designed to fit growth and changes in traffic patterns.
- [ ] Restrict VPC interconnection to necessary instances to minimize vulnerability exposure.
- [ ] Enable VPC Flow Logs for network monitoring and forensics.

### Cloud VPN and Interconnect

- [ ] Utilize Cloud VPN for secure network connection to your GCP environment.
- [ ] If using Dedicated Interconnect or Partner Interconnect, ensure you set up Cloud Router to exchange routes between Google Cloud and your network.

### Load Balancing

- [ ] Utilize Google Cloud Armor with the Cloud Load Balancing service for defense against network and application-layer DDoS attacks.
- [ ] Set up URL Maps to route traffic to the correct service and improve application security.

### Private Google Access

- [ ] Enable private Google Access for on-premises hosts to ensure they access Google services securely over a private network.

### Shared VPC (XPN)

- [ ] Configure Shared VPC to allow centralized network administrators to manage network resources, ensuring more control over network security.
- [ ] Restrict user permissions for modifying Shared VPC to avoid unintended changes.

### Cloud NAT

- [ ] For instances without public IP addresses, use Cloud NAT to enable outgoing connections to the internet.
- [ ] Regularly review NAT logs for any unusual outbound connection requests.

### DNS Security

- [ ] Use Cloud DNS or DNSSEC for secure, scalable, and reliable DNS serving.
- [ ] Regularly review DNS queries and responses for any DNS tunneling attempts.

### Traffic Control

- [ ] Enable VPC Service Controls to prevent data exfiltration.
- [ ] Implement Traffic Director for secure and easy traffic control on microservice architectures.

### Network Telemetry

- [ ] Regularly monitor network health and performance using Network Intelligence Center.
- [ ] Enable Network Topology for visualizing and monitoring network performance in near real time.

## Configuration Review

### General
- [ ] Disable public IP addresses for VM instances.
- [ ] Enable automatic OS patches.

## Configuration Management 

### Infrastructure as Code (IaC)
- [ ] Utilize IaC tools such as Cloud Deployment Manager or Terraform for reliable and predictable changes and configuration.

### Binary Authorization
- [ ] Employ Binary Authorization to ensure only trusted container images are deployed on GKE.
- [ ] Enforce binary authorization using custom policies to provide even greater control.

### Configuration Connector
- [ ] Use Config Connector to manage GCP resources through Kubernetes.

### Environment Variables
- [ ] Store sensitive information like API keys or database credentials in environment variables instead of hard-coded in the application.

## Application Security

### Web Security Scanner
- [ ] Use Google Cloud's Web Security Scanner for identifying common security vulnerabilities in your App Engine, Compute Engine, and GKE applications.

### Managed SSL Certificates
- [ ] Use Google-managed SSL certificates for secure connection between users and your site.

### Access Approval
- [ ] Enable Access Approval to approve access to your data or configurations.

## Cloud Functions Security

### Security Controls
- [ ] Implement execution permissions using IAM to control function invocation.
- [ ] Use VPC Service Controls to mitigate data exfiltration risks.

### Secure Triggers
- [ ] Secure HTTP triggers using IAM or Firebase Authentication.
- [ ] Use Cloud Pub/Sub or Cloud Storage triggers for private functions.

### Connection
- [ ] Employ Serverless VPC Access to connect a function to a VPC network.

## Storage Security

### Access Control 
- [ ] Fine-tune access controls for Cloud Storage using IAM, ACLs, or signed URLs / signed policy documents.
- [ ] Restrict public access to your buckets and contents.

### Data Protection
- [ ] Use Customer-Managed Encryption Keys (CMEK) or Customer-Supplied Encryption Keys (CSEK) for additional control over encryption.

### Uniform Bucket-Level Access
- [ ] Enforce uniform bucket-level access to simplify managing access to Cloud Storage buckets.

## Backup and Recovery

### Persistent Disk Snapshots 
- [ ] Regularly schedule persistent disk snapshots for backup.
- [ ] Replicate snapshots across regions to protect against regional outages.

### Database Backups
- [ ] Enable automatic backups on Cloud SQL and Firestore databases.
- [ ] Regularly export data from Firestore, Datastore, and Bigtable for backup.
 
### Disaster Recovery
- [ ] Create a Disaster Recovery (DR) plan tailored to your business requirements.

## Security Command Center

### Security Health Analytics
- [ ] Enable Security Health Analytics in Security Command Center to automatically detect and help you remediate potential security risks.

### Event Threat Detection
- [ ] Enable Event Threat Detection to automatically detect suspicious activity in your logs.

### Security Marks
- [ ] Use security marks in Security Command Center to add security-related metadata to your GCP resources.

### Anomaly Detection
- [ ] Enable Anomaly Detection in Security Command Center to identify potential security anomalies in your GCP data.

### Phishing Protection
- [ ] Use Phishing Protection in Security Command Center to help protect your website from phishing attacks.

## Serverless Application Security

### Runtime Environment
- [ ] Use the most updated runtime environment for your Cloud Functions and App Engine apps.

### Dependency Tracking
- [ ] Regularly update and review the dependencies of your serverless applications.

### Function Permissions
- [ ] Employ the principle of least privilege when setting execution permissions for your Cloud Functions.

### Secure Data
- [ ] Use Secret Manager to store and manage sensitive data like API keys or passwords securely.

### Storage
- [ ] Ensure all Cloud Storage buckets are the least privilege.
- [ ] Ensure all Cloud Storage buckets are not publicly accessible.

### Datastore
- [ ] Enable automatic backups on Datastore databases.
- [ ] Regularly evaluate the sensitivity of data in the datastore and the permissions with access.

## Logging and Monitoring

### General
- [ ] Enable log retention and archival for long term storage.
- [ ] Regularly review logs for abnormal behavior.

### Monitoring
- [ ] Use GCP's Stackdriver to monitor the health of resources.
- [ ] Set up alerts on Stackdriver for abnormal resource behavior.

### Trace & Debug
- [ ] Regularly conduct trace route requests to debug latency issues.
- [ ] Regularly conduct network tests to debug and analyze networking issues.

## Threat and Vulnerability Management

### General
- [ ] Regular penetration testing and vulnerability scanning.
- [ ] Use Cloud Security Scanner to identify security vulnerabilities in your web applications.

### Cloud Security Command Center
- [ ] Activate Cloud Security Command Center (Cloud SCC) for centralized and holistic view of security health.
- [ ] Use Cloud SCC to gain insights into potential vulnerabilities from Google Cloud Console.

### Incidence Response
- [ ] Define a comprehensive incidence response plan.
- [ ] Regularly conduct incidence response drills.

## Data Protection

### Encryption
- [ ] Use Google's default encryption for data at rest.
- [ ] Use customer-managed encryption keys where appropriate for extra control over key rotation and revocation.

### Data Loss Prevention (DLP)
- [ ] Use Cloud Data Loss Prevention (DLP) to discover, classify, and mask sensitive elements in your data.

### Data Access
- [ ] Restrict access to sensitive data only to roles and identities that absolutely require it.
- [ ] Regularly rotate and review access controls and permissions.

## Best Practices in App Development

### Security Libraries
- [ ] Use libraries provided by Cloud Identity Platform to avoid storing credentials in your application.

### API Security
- [ ] Use API keys to identify project, not to authenticate an user.
- [ ] Disable API endpoints that your applications are not using.

### Container Security
- [ ] Use minimal base images for containers.
- [ ] Keep open source and third party components in the container images up-to-date and regularly check for vulnerabilities.

## Compliance and Governance

### Cloud Audit Logs
- [ ] Use Cloud Audit logs to maintain a audit trail for actions within GCP.

### Resource Manager
- [ ] Organize your cloud resources hierarchically using Resource Manager to manage permissions and policies on resources effectively.

### Retention and Deletion
- [ ] Know the data retention timelines and policies for the services you use.
- [ ] Securely delete data from GCP when it is no longer needed, considering deleting disks, snapshots, images, persistent disks, and Cloud Storage objects.

## AI and Machine Learning (ML) Security

### ML Model Training
- [ ] Secure your ML training data and treat them as sensitive.
- [ ] Regularly evaluate the compute resources used for training ML models for vulnerabilities.

### AI Platform Notebooks Instances
- [ ] Limit the number of users who have Editor role on AI Platform Notebooks instances, and regularly audit this role.

### AI Platform Pipelines
- [ ] Regularly review and update the permissions for service accounts used by AI Platform Pipelines.

## Training and Awareness

### Security Training
- [ ] Regularly conduct security training for your team.
- [ ] Understand the shared responsibility model of GCP.

### Best Practices
- [ ] Regularly review Google Cloud documentation to keep up to date with the latest best practices and features for security.
