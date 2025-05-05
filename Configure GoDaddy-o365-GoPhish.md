After puchasing domain from GoDaddy, goto My Products > Scroll down to Websites & Marketing > Purchase "Microsoft 365 Email Essentials Plan".

In the same dashboard setup email.

Navigate back to My Products > Go to "Email & Office Dashboard" > Select Manage > Click on "Advance Security" Setting and Enable "SMTP Authentication"

Add following DNS records:
  1. CNAME: Name - selector1._domainkey | Data - selector1-<domain>-com._domainkey.<id>.y-v1.dkim.mail.microsoft.
  2. CNAME: Name - selector2._domainkey | Data - selector2-<domain>-com._domainkey.<id>.y-v1.dkim.mail.microsoft.
  3. MX: Name - @ | Data - <domain>-com.mail.protection.outlook.com. (Priority: 0)
  4. MX: Name - @	| Data - smtp.office365.com. (Priority: 0)
  5. TXT: Name - @ | Data - v=spf1 include:spf.protection.outlook.com -all

Sign in to your o365 Account.

Go to "https://mysignins.microsoft.com/security-info", and setup MFA via Authenticator.

Go to "https://entra.microsoft.com/#view/Microsoft_AAD_IAM/TenantProperties.ReactView" > "Manage Security Defaults" > Disable it > In other option select "I have alternate Authentication method/policied configured" > Click on Save.

Navigate to "https://security.microsoft.com/dkimv2" > Status for all domains shown in the Accepted List should be "Valid". If not, toggle "Enable" option. If CNAME were properly configured status will be shown as "Valid", If not, configure CNAME properly in Domain DNS setting in GoDaddy as shown in alert pop-up message box.

Go to GoPhish Sending Profile and configure as mentioned below:
  1. SMTP-From: <Sending Domain to Bypass SPF-Checks>
  2. Host: smtp.office365.com:587
  3. Username: o365 Email ID
  4. Password: One which was created while configuring email in GoDaddy

If email gets flagged or blacklisted somewhere, configure Port Forwarding

PS: It's better to install GoPhish on Phishing Server itself.
