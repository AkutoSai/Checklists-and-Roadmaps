# API, OWASP Top 10 & General Web Application VAPT Checklist

## 1. Injection
- Identify areas where untrusted data is sent as part of a command or query.
- Simulate Injection attacks using OWASP ZAP/ Burp Suite by inserting malicious data into these areas.

## 2. Broken Authentication
- Test for user enumeration during login and password reset functionality.
- Test for weak account lockout settings.
- Test session timeouts and user logouts.

## 3. Sensitive Data Exposure
- Check if all sensitive data are encrypted at rest and in transit.
- Try to access sensitive data from client-side resources like cookies and local storage.
- Ensure sensitive data is not leaked in URLs or logs.

## 4. XML External Entity (XXE)
- Test how the application processes XML data.
- Attempt to exploit a potential XXE by defining an external entity with a known protocol handler to test if the application passes unexpected values.

## 5. Broken Access Control
- Carry out privilege escalation tests.
- Test to ensure that incorrect user roles can't access unauthorized functions or data.
- Test for IDOR (Insecure Direct Object References) vulnerabilities.

## 6. Security Misconfigurations
- Check if unnecessary features, components, pages, or services are disabled.
- Check if default accounts have been removed or change their passwords.
- Check for unnecessary printing of stack traces or other debug information.

## 7. Cross-Site Scripting (XSS)
- Check if the application sanitizes and escapes untrusted data.
- Attempt to inject script tags in user inputs.

## 8. Insecure Deserialization
- Test how the application manages serialization and if integrity checks are in place.
- Attempt to manipulate object data to exploit potential vulnerabilities.

## 9. Using Components with Known Vulnerabilities
- Perform component analysis to identify potential insecure components or libraries.
- Leverage tools such as OWASP dependency checker for analysis.

## 10. Insufficient Logging and Monitoring
- Verify all login, access control failures, server-side input validation failures are logged with enough user context to identify suspicious accounts.
- Test incident response and recovery with simulated attacks.

# General Web Application VAPT Checklist

## IDOR/Authorisation
- Direct browse to all pages reserved for high privileged user while unauthenticated or logged in as the least privilege user
- Business Logic Scenario: Check for Privilege Elevation between roles
- Business Logic Scenario: Check to access to data from customer A with customer B by modifying the sequential id parameters sent in the requests
- Business Logic Scenario: Try accessing URLs directly with encrypted query strings (used to identify the user) to verify unauthorized access
- Business Logic Scenario: Abuse refund feature: Modification of refund amount, Initiating refund on behalf of other users
- Business Logic Scenario: Attempt resetting other users password by misusing the reset password functionality (by tampering with the parameters like email / id / unique identifiers)
- Try to access other users personal data
- After accessing the dashboard, change the email ID to get the privilege of other user
- Delete other users account by modifying user id
- Try to book appointment of User B with User's A's login page
- Try to bypass the details pages and access review page. 
- Business Logic Scenario: Access other users payment receipts, appointment letters, other documents (if any)

## Payment Tampering
- Test all parameters that carry the transaction amount
- Test all parameters that carry the transaction currency
- Business Logic Scenario: Check for payment bypass
-with valid response
-by changing the parameters

## Session Management Testing
- Verify session timeout enforced in a reasonable amount of time
- Check for session fixation (not invalidating/re-issuing current session token after authenticating or forcing a known session ID on a user)
- If the site is secure (HTTPS), check if the session ID passed over an unencrypted connection at any stage (HTTP)
- Check is the session ID is sent in a GET request at any stage. Verify if it is possible to force it into the GET request.
- Test if concurrent logins are possible
- User stays logged in even after closing the browser window

## Authentication Testing
- Test for bypassing authentication by forced browsing
- Test for bypassing authentication by SQL Injection on the login page
- Test if password reset/reminder can be guessed or bypassed.
- After logout, verify that the session has indeed been terminated server-side and attempt re-accessing the application using the old session id
- Test if adequate password strength requirements enforced
- Verify that re-authentication is enforced for critical tasks (change password, transfer funds, etc.)

## SQL Injection
- All suspicious parameters (POST & GET parameters, SOAP Headers, etc.) manually tested for (Blind) SQL Injection and Command injection.
- All cookies tested for SQL Injection

## Cross Site Scripting (XSS)
- All suspicious parameters (POST & GET parameters, SOAP Headers, etc.) manually tested for Cross-Site Scripting.
- All cookies tested for Cross Site Scripting
- HTTP Request headers (Language, etc.) tested for Cross-Site Scripting
- XSS payloads have been appended to URLs to test for Cross-Site Scripting
- Client-side validations (DOM)

## Generic User Input Validation Testing
- Attempt exotic encoding of parameter data (e.g. different types of encoding schemes, double encoding, etc.)
- Check for the possibility of injecting Server Side Includes (SSI). Note presence of any pages with extensions .stm, .shtm and .shtml

## Cross Site Request Forgery (CSRF)
- Ensure sufficient authorisation (or re-authorisation) is required for critical/potentially vulnerable transactions
- Check if vulnerable requests are automatically authorised based on 1) submitted session token/cookie 2) "remember -me" functionality 3) Kerberos token (AD)

## Open Redirects
- Ensure that any redirect functionality only allows "safe" redirects to pages on the same domain
- Check for host header injection

## Testing Custom Application Features
- Test custom application features (upload, import, customization, etc.) for possible vulnerabilities
- For uploads check if the user can upload malicious scripts or large files to the web server (at least upload - "helloworld.php" and attempt to browse to it)
- Perform CAPTCHA bypass, if CAPTCHA is implemented
- Perform OTP bypass, if OTP is implemented
- Reuse the OTP/captcha value
- Capture JWT token to identify the secret message used to encrypt the token
- Determine the logic to generate the JWT token
- Business Logic: Modify/delete data of previously booked appointment
- Upload / download files in other user's profile by changing the reference number.
- Without logout close the browser, open the application and check for the previous session
- User navigates to different website and with the help of browser back button try to access the application and check for active session"
- Server side validation for mandatory data

## Business Logic Testing
- Attempt full path disclosure attacks
- Test all cookie values for parameter change / manipulation
- Test all parameter values for parameter change / manipulation
- Check for any other business logic scenario bypass/ abuse (if any applicable basis the application design)
- Analyse GET and POST requests processed by the application.
- Verify whether the application sends sensitive information such as passwords in GET requests at any point in time"
- Test for web application fingerprint
- Check for rate limiting on the sensitive functionalities / actions
- Test for HTTP methods
- Check for directory listing / browsing
- Check if default technology files are accessible over the Internet (Tomcat, PHP, etc.)
- Check if admin interfaces of web or application servers is accessible over the Internet
- Verify whether HTTPS is used to encrypt credentials and / or sensitive data
- Bot related issues/ bypassing the initial pages to access some other pages/steps/functions
- If Waitlist functionality exists in the application then try to bypass the functionality and book the appointments.
- Try to raise the refund request for higher amount than actual amount
- URL Tamper from Server Response
- Manipulate time or any other parameter in appointment/ticket
- Try to raise the refund request for same IRL number multiple time and with different amount

## Cloudflare/WAF Bypass
- Add public IP and domain to the Host file and try to access the application
- Try to find real IP hidden behind cloudflare

## Miscellaneous
- Check for any flaws in cloud services (if any applicable basis the application implementation using any cloud service provider)
- Try enumerating & exploiting AWS server
- Try to identify misconfigured s3 buckets
- Any vulnerability found for technologies used in the application
- Tech Stack
- Port Enumeration
- DNS Recon
- Error Handling
- Login without accepting T&C checkbox on login page (Bypass client side validations)
- Bypass OTP validation and login in the app (By client side validation)
- Bypass OTP validation and login in the app (By server side validation)
- Do payment without accepting T&C on Review & Pay page
- Edit user details after successful payment and booking
- Check if User A can add multiple entries in same booking request 

# API (General)

## API Security Checklist

1. **Authentication and Authorization:**
   - [ ] Implement strong authentication mechanisms such as OAuth 2.0, JWT, or API keys.
   - [ ] Use secure password storage techniques like hashing and salting.
   - [ ] Enforce strong password policies.
   - [ ] Implement role-based access controls (RBAC) to ensure appropriate authorization.
   - [ ] Regularly review and update access control policies.

2. **Input Validation:**
   - [ ] Validate and sanitize all input data to prevent injection attacks like SQL injection, XSS, and command injection.
   - [ ] Implement whitelist validation for input fields to only allow expected characters and reject all others.
   - [ ] Perform server-side validation for all API requests.

3. **Secure Transmission:**
   - [ ] Use SSL/TLS protocols (preferably TLS 1.3) for secure communication over the network.
   - [ ] Implement strong cipher suites and secure protocols.
   - [ ] Use secure HTTP methods (HTTPS) for transmitting sensitive data.
   - [ ] Encrypt sensitive data at rest.

4. **Rate Limiting and Throttling:**
   - [ ] Implement rate limiting and throttling mechanisms to prevent API abuse and DDoS attacks.
   - [ ] Set appropriate limits for requests per minute, hour, or day based on expected usage patterns.
   - [ ] Monitor and analyze traffic to identify and block suspicious or excessive requests.

5. **Error Handling:**
   - [ ] Implement proper error handling and error messages to avoid information leakage.
   - [ ] Avoid returning detailed error messages that could expose internal system details.
   - [ ] Log errors securely and monitor logs for suspicious activities.

6. **API Versioning and Documentation:**
   - [ ] Implement versioning to ensure backward compatibility and smooth transition between API versions.
   - [ ] Maintain up-to-date and comprehensive API documentation.
   - [ ] Clearly define and enforce deprecation policies for old API versions.

7. **Secure Third-Party Integrations:**
   - [ ] Conduct security assessments of third-party APIs and only integrate trusted and well-vetted services.
   - [ ] Regularly review third-party API security practices and updates.
   - [ ] Follow secure coding practices when integrating external APIs.

8. **Threat Protection:**
   - [ ] Implement security measures like Web Application Firewalls (WAF) to detect and mitigate attacks.
   - [ ] Use intrusion detection and prevention systems (IDS/IPS) to monitor and protect against potential threats.
   - [ ] Implement anomaly detection mechanisms to identify abnormal behavior patterns.

9. **Data Privacy and Protection:**
   - [ ] Comply with relevant data protection regulations (e.g., GDPR, CCPA).
   - [ ] Implement privacy controls like data anonymization and encryption.
   - [ ] Regularly audit and assess data handling practices.

10. **Secure Development Lifecycle (SDL):**
    - [ ] Conduct security code reviews and penetration testing.
    - [ ] Follow secure coding practices and frameworks (e.g., OWASP Top Ten).
    - [ ] Implement vulnerability management processes to identify and address security flaws.

11. **Monitoring and Logging:**
    - [ ] Implement real-time monitoring of API requests, responses, and system logs.
    - [ ] Use log aggregation and analysis tools to identify security incidents.
    - [ ] Set up alerts for suspicious activities or potential security breaches.

12. **Security Training and Awareness:**
    - [ ] Provide security awareness training for developers, administrators, and users.
    - [ ] Regularly update security knowledge and stay informed about emerging threats.
    - [ ] Foster a culture of security and encourage responsible disclosure of vulnerabilities.
