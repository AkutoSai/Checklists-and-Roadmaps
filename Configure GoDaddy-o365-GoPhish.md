## PS: It's better to install GoPhish on Phishing Server itself.
### Step 1: After puchasing domain from GoDaddy, goto My Products > Scroll down to Websites & Marketing > Purchase _Microsoft 365 Email Essentials Plan_.

### Step 2: In the same dashboard setup email.

### Step 3: Navigate back to My Products > Go to *Email & Office Dashboard* > Select Manage > Click on *Advance Security* Setting and Enable *SMTP Authentication*.

### Step 4: Add following DNS records:
  1. CNAME: Name - selector1._domainkey | Data - selector1-<domain>-com._domainkey.<id>.y-v1.dkim.mail.microsoft.
  2. CNAME: Name - selector2._domainkey | Data - selector2-<domain>-com._domainkey.<id>.y-v1.dkim.mail.microsoft.
  3. MX: Name - @ | Data - <domain>-com.mail.protection.outlook.com. (Priority: 0)
  4. MX: Name - @	| Data - smtp.office365.com. (Priority: 0)
  5. TXT: Name - @ | Data - v=spf1 include:spf.protection.outlook.com -all

### Step 5: Sign in to your o365 Account.

### Step 6: Go to *https://mysignins.microsoft.com/security-info*, and setup MFA via Authenticator.

### Step 7: Go to *https://entra.microsoft.com/#view/Microsoft_AAD_IAM/TenantProperties.ReactView* > *Manage Security Defaults* > Disable it > In other option select _I have alternate Authentication method/policied configured_ > Click on Save.

### Step 8: Navigate to *https://security.microsoft.com/dkimv2* > Status for all domains shown in the Accepted List should be *Valid*. If not, toggle *Enable* option. If CNAME were properly configured status will be shown as *Valid*, If not, configure CNAME properly in Domain DNS setting in GoDaddy as shown in alert pop-up message box.

### Step 9: Go to GoPhish Sending Profile and configure as mentioned below:
  1. SMTP-From: <Sending Domain to Bypass SPF-Checks>
  2. Host: smtp.office365.com:587
  3. Username: o365 Email ID
  4. Password: One which was created while configuring email in GoDaddy

### Step 10: If email gets flagged or blacklisted somewhere, considor Port Forwarding
