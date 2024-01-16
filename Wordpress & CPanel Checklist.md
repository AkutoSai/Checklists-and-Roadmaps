## WordPress & CPanel Configuration Review

### General Settings
- **Verify site title and tagline:**
  - Test Case: Update site title and tagline and confirm changes are reflected on the site.

- **Check and update the WordPress URL and site URL:**
  - Test Case: Change both URLs and confirm the site functions correctly without broken links.

- **Ensure correct timezone settings:**
  - Test Case: Change timezone settings and verify that post timestamps and scheduled events reflect the new timezone.

- **Review and update date and time format:**
  - Test Case: Change date and time format and ensure it is correctly applied to posts, comments, and other relevant sections.

- **Check the default category and post format settings:**
  - Test Case: Change default category and post format, create a new post, and confirm it inherits the updated settings.

- **Verify the homepage and posts page settings:**
  - Test Case: Update homepage and posts page settings and ensure the correct pages are displayed.

### Security Settings
- **Confirm the use of secure login credentials:**
  - Test Case: Attempt to log in with incorrect credentials and ensure appropriate login failure messages are displayed.

- **Enable two-factor authentication (2FA):**
  - Test Case: Activate 2FA and confirm that users are prompted for an additional authentication method during login.

- **Review and update the WordPress salts and keys:**
  - Test Case: Regenerate salts and keys, and verify that existing user sessions are invalidated.

- **Check file permissions for core WordPress files:**
  - Test Case: Modify file permissions on a core file and confirm the site displays the appropriate error.

- **Ensure directory listing is disabled:**
  - Test Case: Attempt to access a directory without an index file and ensure directory listing is not displayed.

- **Disable XML-RPC if not needed:**
  - Test Case: Disable XML-RPC and verify that the site functions correctly, especially for mobile apps and remote publishing tools.

- **Confirm SSL certificate installation:**
  - Test Case: Access the site over HTTPS and ensure the SSL certificate is valid and correctly configured.

### User Management
- **Review and manage user roles:**
  - Test Case: Change a user's role and verify that the user has the appropriate permissions and restrictions.

- **Remove unused or unnecessary user accounts:**
  - Test Case: Delete a user account and confirm that associated content is properly reassigned or removed.

- **Ensure strong passwords for all user accounts:**
  - Test Case: Set a weak password for a user and verify that the system enforces password strength requirements.

- **Verify and update author archives settings:**
  - Test Case: Change author archive settings and confirm that the author archive page reflects the updates.

- **Confirm email notifications for user actions:**
  - Test Case: Perform an action that triggers an email notification (e.g., new user registration) and verify that the email is sent.

### Theme and Plugin Settings
- **Update and review active theme:**
  - Test Case: Update the theme and ensure that the site's appearance is consistent, and no layout or functionality issues arise.

- **Disable or remove unused themes:**
  - Test Case: Delete an unused theme and verify that the site still functions as expected.

- **Review and update active plugins:**
  - Test Case: Update a plugin and confirm that the site remains stable and that any new features or fixes are applied.

- **Disable or remove unnecessary plugins:**
  - Test Case: Deactivate and delete unnecessary plugins, ensuring that the site functionality is not compromised.

- **Check for theme and plugin updates:**
  - Test Case: Regularly check for theme and plugin updates and apply them, ensuring compatibility and stability.

- **Confirm proper use of child themes:**
  - Test Case: Create and activate a child theme, make changes, and verify that the child theme inherits from the parent correctly.

### Database and Performance
- **Optimize and repair the WordPress database:**
  - Test Case: Run the database optimization and repair tools and confirm that the database operates more efficiently.

- **Check and optimize database tables:**
  - Test Case: Review and optimize specific database tables to improve overall performance.

- **Verify proper use of caching mechanisms:**
  - Test Case: Enable and configure a caching plugin, and ensure that page loading times are reduced.

- **Confirm the use of a Content Delivery Network (CDN):**
  - Test Case: Enable a CDN and verify that static content is served from the CDN, improving page load times.

- **Check for broken links and optimize images:**
  - Test Case: Use a broken link checker and image optimizer to ensure all links are valid, and images are optimized for web usage.

- **Review and update the number of post revisions:**
  - Test Case: Adjust the number of post revisions and verify that the database size and performance are affected accordingly.

### Backups
- **Confirm regular backup schedule:**
  - Test Case: Schedule a backup and ensure that it runs at the specified time, creating a complete and restorable backup.

- **Test the restoration process from backups:**
  - Test Case: Perform a restoration from a backup and confirm that the site is returned to its state at the time of the backup.

- **Ensure backups are stored in a secure location:**
  - Test Case: Store backups in a location with restricted access and verify that unauthorized users cannot access or delete backups.

- **Check backup file integrity:**
  - Test Case: Regularly check the integrity of backup files to ensure they are not corrupted and can be successfully restored.

### SEO Configuration
- **Confirm the use of an SEO plugin (e.g., Yoast SEO):**
  - Test Case: Install and configure an SEO plugin, and verify that meta tags and other SEO settings are applied.

- **Review and update meta tags and descriptions:**
  - Test Case: Modify meta tags and descriptions and confirm that search engine results reflect the changes.

- **Verify the generation of XML sitemaps:**
  - Test Case: Check for the existence of an XML sitemap and ensure it includes all relevant pages.

- **Check robots.txt for proper configurations:**
  - Test Case: Review and modify the robots.txt file, and verify that search engines adhere to the specified directives.

---

## cPanel Configuration Review

### Account Settings
- **Verify account contact information:**
  - Test Case: Update account contact information and ensure that notifications and communications are sent to the correct email address.

- **Confirm account resource limits:**
  - Test Case: Exceed resource limits intentionally and validate that appropriate warnings or restrictions are enforced.

- **Review and update notification preferences:**
  - Test Case: Adjust notification preferences and verify that notifications are received according to the updated settings.

- **Check and update account password:**
  - Test Case: Change the account password and confirm that the new password is accepted for subsequent logins.

### Security Settings (cPanel)
- **Enable and configure ModSecurity:**
  - Test Case: Enable ModSecurity and simulate a request that triggers a rule, confirming that ModSecurity correctly blocks or logs the request.

- **Review and update PHP settings:**
  - Test Case: Modify PHP settings (e.g., upload_max_filesize) and ensure changes take effect without causing issues.

- **Confirm server-side encryption settings:**
  - Test Case: Enable server-side encryption for emails and files, and verify that data is properly encrypted and decrypted.

- **Enable and configure CageFS:**
  - Test Case: Enable CageFS and verify that users are isolated, preventing one user's processes from affecting another user's processes.

- **Check for any security-related notifications:**
  - Test Case: Trigger a security-related event (e.g., brute force login attempts) and confirm that the system generates and sends appropriate notifications.

- **Verify IP address access restrictions:**
  - Test Case: Restrict access to cPanel based on IP addresses and ensure that access is only granted from specified IPs.

### Domain Management
- **Review and update domain information:**
  - Test Case: Update domain contact information and verify that the WHOIS information is updated accordingly.

- **Check DNS configurations for accuracy:**
  - Test Case: Modify DNS records (e.g., add a new record) and confirm that the changes are reflected in the DNS settings.

- **Confirm proper SSL certificate installation:**
  - Test Case: Install an SSL certificate and verify that the domain is accessible over HTTPS without warnings.

- **Review and update domain aliases:**
  - Test Case: Add or remove domain aliases and confirm that the alias settings are correctly applied.

### Email Configuration
- **Verify email account settings:**
  - Test Case: Create a new email account and confirm that emails can be sent and received using the configured settings.

- **Confirm email forwarding configurations:**
  - Test Case: Set up email forwarding and validate that emails are correctly forwarded to the specified addresses.

- **Review and update spam filter settings:**
  - Test Case: Adjust spam filter settings and verify that spam emails are appropriately identified and filtered.

- **Test email sending and receiving functionality:**
  - Test Case: Send test emails internally and externally, ensuring successful delivery and receipt.

- **Check for email account quotas:**
  - Test Case: Set email account quotas and verify that users cannot exceed their allocated storage limits.

### Backup Configuration
- **Confirm regular account backup schedule:**
  - Test Case: Schedule an account-level backup and validate that the backup runs as per the specified schedule.

- **Test the restoration process from backups:**
  - Test Case: Perform a restoration from a backup and confirm that the account is restored to its state at the time of the backup.

- **Ensure backups are stored in a secure location:**
  - Test Case: Store backups in a restricted directory and verify that unauthorized users cannot access or delete backup files.

- **Check backup file integrity:**
  - Test Case: Regularly check the integrity of backup files to ensure they are not corrupted and can be successfully restored.

### File Management
- **Review and manage file permissions:**
  - Test Case: Modify file permissions on a critical file and confirm that unauthorized access is restricted.

- **Confirm disk usage and quotas:**
  - Test Case: Monitor disk usage and quotas, and validate that users cannot exceed their allocated disk space.

- **Verify the existence of an index file in each directory:**
  - Test Case: Access directories without an index file and confirm that directory listings are not displayed.

- **Check for suspicious or unnecessary files:**
  - Test Case: Regularly scan for and remove any suspicious or unnecessary files to ensure the integrity of the file system.

- **Review and update file access logs:**
  - Test Case: Modify file access log settings and confirm that the logs are updated and accessible with the new configurations.

### Database Management
- **Verify MySQL/MariaDB Database Setup:**
  - Test Case: Create a new database and user, assign the user to the database with appropriate privileges, and confirm that the connection is successful.

- **Test phpMyAdmin Access:**
  - Test Case: Access phpMyAdmin and ensure that you can perform database operations such as table creation, data insertion, and SQL queries.

- **Review Database Backups:**
  - Test Case: Perform a backup of a database and verify that the backup file is generated correctly and can be restored without issues.

### FTP and File Transfer
- **Confirm FTP Account Functionality:**
  - Test Case: Create an FTP account, connect using an FTP client, and validate that file transfers are successful.

- **Test File Manager Functionality:**
  - Test Case: Use the cPanel File Manager to upload, download, and modify files, confirming that changes are reflected correctly.

### Security and Access Control
- **Review IP Deny Manager:**
  - Test Case: Add an IP address to the IP Deny Manager and verify that access from the specified IP is denied.

- **Check SSL/TLS Configuration:**
  - Test Case: Review and update SSL/TLS configurations, ensuring that secure connections are established without warnings.

- **Verify SSH Access:**
  - Test Case: Enable and configure SSH access, connecting via SSH, and confirm that secure shell access is functional.

### Resource Usage Monitoring
- **Check Resource Usage in cPanel:**
  - Test Case: Monitor resource usage within cPanel, ensuring that resource consumption (CPU, memory, disk space) is within acceptable limits.

- **Verify Awstats and Webalizer:**
  - Test Case: Access Awstats and Webalizer statistics, ensuring that web traffic analytics are generated and displayed accurately.

### Cron Jobs
- **Review and Test Cron Jobs:**
  - Test Case: Set up a cron job to execute a specific task at a scheduled time, confirming that the task is performed as expected.

- **Verify Email Notifications for Cron Jobs:**
  - Test Case: Configure cron jobs to send email notifications upon completion, and confirm that notifications are received.

### DNS Zone Management
- **Add/Edit DNS Records:**
  - Test Case: Add or edit DNS records (A, CNAME, MX, etc.) and verify that changes are reflected in DNS lookups.

- **Test DNS Propagation:**
  - Test Case: Update DNS records and confirm that changes propagate correctly across the internet, affecting all relevant DNS servers.

### Server Performance and Health
- **Review Server Information in cPanel:**
  - Test Case: Check server information in cPanel, including server load, memory usage, and disk space, ensuring that values are within acceptable ranges.

- **Test Apache and PHP Configuration:**
  - Test Case: Modify Apache and PHP configurations, restart services, and confirm that changes are applied without causing service disruptions.

### Additional cPanel Features
- **Check Autoresponders and Forwarders:**
  - Test Case: Set up email autoresponders and forwarders, and confirm that emails are forwarded or autoresponders are triggered as configured.

- **Review and Test Subdomains:**
  - Test Case: Create, modify, and delete subdomains, ensuring that they resolve correctly and do not interfere with the main domain.

- **Verify SSL Configuration for Subdomains:**
  - Test Case: Install and configure SSL certificates for subdomains, ensuring secure access via HTTPS.

- **Test Softaculous Auto Installer:**
  - Test Case: Use Softaculous to install and uninstall applications, confirming that installations are successful and removals are clean.

---
