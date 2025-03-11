# Generic Test Cases:
   - [ ] Improper Code Obfuscation
   - [ ] Root Detection Bypass [With Frida/Objection, Magisk]
   - [ ] Emulator Detection Bypass
   - [ ] SSL Pinning Bypass [With Frida/Objection, Internal Certificate ".0", installing a VPN profile/agent and Manual Code Tampering]
   - [ ] Dead Code Injection
   - [ ] Android - Debuggable
   - [ ] Android - Exported
   - [ ] MinSDK (Outdated Android Version Supported)
   - [ ] Weak Cryptographic Algorithm
   - [ ] ClearText communication (True)
   - [ ] Content Resolvers
   - [ ] Custom/Dangerous Permissions
   - [ ] createPackageContext
   - [ ] Dynamic Code Loading
   - [ ] Implicit Intent Hijacking
   - [ ] Activity Hijacking [https://github.com/cyberchoudhary09/Android-Static-Exploitation-Toolkit]
   - [ ] Service Hijacking
   - [ ] Directories exported to FileProvider
   - [ ] Insecure API/Library
   - [ ] Insecure Broadcast Reciever [https://github.com/cyberchoudhary09/Android-Static-Exploitation-Toolkit]
   - [ ] Boradcast thief
   - [ ] Malicious Broadcast Injection
   - [ ] Redundance Permission Granted
   - [ ] Misconfigured DNS
   - [ ] Insecure M-to-M setup
   - [ ] Intent Redirection
   - [ ] RawSQL Queries in Use
   - [ ] Path Traversal
   - [ ] Insecure WebView Implementation (Native Bridges, Insecure URI loading)
   - [ ] Permission-bases access control to exported components
   - [ ] Clipboard Access
   - [ ] Sticky broadcast
   - [ ] Android TapJacking [https://github.com/dzmitry-savitski/tapjacker/releases/tag/untagged-73df61a0a60b24f1b93c]
   - [ ] StrandHogg Attack (Task Affinity Vulnerability)
   - [ ] Test and Debug feature
   - [ ] Unsafe Deserialization
   - [ ] Unsafe Download Manager
   - [ ] Unsafe Hostname Verifier
   - [ ] Unsafe X509TrustManager
   - [ ] Use of Native Code
   - [ ] XML External Entities Injection
   - [ ] Weak PRNG
   - [ ] Zip Path Traversal
   - [ ] Jauns Vulnerability
   - [ ] Debug Certificate
   - [ ] Improperly Exposed Directories to FileProvider
   - [ ] Log Info Disclosure
   - [ ] Sensitive Data Stored in External Storage
   - [ ] Private IP Disclosure
   - [ ] Application build contains Obsolete Files
   - [ ] Android Backup Vulnerability
   - [ ] Analytics data sent to 3rd parties
   - [ ] Screen capture/screenshot
   - [ ] Applicatio Background Caching

## Insecure Data Storage:
   - [ ] Unencrypted Credentials/Sensitive Information/PII/Account Metadata/APIs in Databases (SQLite db)
   - [ ] Unencrypted Credentials/Sensitive Information/PII/Account Metadata/APIs in Memory Dump
   - [ ] Unencrypted Credentials/Sensitive Information/PII/Account Metadata/APIs in SharedPreferences
   - [ ] Allow Global File Permission on App Data
   - [ ] Store sensitive information stored in temp file
   - [ ] Sensitive data stored in external storage
   - [ ] Hard coded sensitive information in Application Code/Manifest File/Strings XML
   - [ ] App/Web Caches Sensitive Data Leak
   - [ ] Testing for Sensitive Information in Cookie Stores
   - [ ] Testing for Sensitive Information in KeyStore
   - [ ] Testing for file cache
   - [ ] Android Dictionary Cache

## Misconfigured TLS Protection:
   - [ ] Failure to Implement Trusted Issuers
   - [ ] Third-party Data Transit on Unencrypted Channel
   - [ ] Certificate Chain is not Validated
   - [ ] Insecure permissions on Unix domain sockets
   - [ ] Insecure use of network sockets
   - [ ] Network traffic - http-https
   - [ ] No Certificate Pinning
   - [ ] Ignore SSL Certificate Error
   - [ ] Cleartext information under SSL Tunnel
   - [ ] Invalid SSL Certificate

## Misconfigured Authorization and Authentication:
   - [ ] Attacker can bypass Second Level Authentication
   - [ ] Direct Reference to internal resource without authentication
   - [ ] Cleartext password in Response
   - [ ] Application does not have Logout Functionality
   - [ ] Authentication bypassed
   - [ ] Improper or NO implementation of Change Password Page
   - [ ] Use Spoof-able Values for Authenticating User (IMEI, Android ID)

## Session Misconfiguration:
   - [ ] Improper Session Timeout
   - [ ] Concurrent Logins
   - [ ] Improper cookie attributes
   - [ ] Weak cookie hashing
   - [ ] Persistent cookies
   - [ ] Using device identifier as session
   - [ ] Cookie caching
   - [ ] Session fixation
   - [ ] Improper session validation
   - [ ] Account Lockout not implemented

## Weak Server Side Controls (Domain/API):
   - [ ] Application is Vulnerable to XSS (Webview and JS dependency)
   - [ ] Malicious File Upload
   - [ ] SQL Injection
   - [ ] Application is vulnerable to LDAP Injection
   - [ ] Application is vulnerable to OS Command Injection
   - [ ] Cross Origin Resource Sharing
   - [ ] Improper Input Validation - Server Side
   - [ ] Detailed Error page shows internal sensitive information
   - [ ] Application Allows HTTP Methods apart from GET and POST
   - [ ] Cross Site Request Forgery (CSRF)/SSRF
   - [ ] Cacheable HTTPS Responses
   - [ ] Server/OS fingerprinting is possible
   - [ ] Directory Browsing
   - [ ] URL Modification
   - [ ] Privilege Escalation
   - [ ] Open URL Redirects are possible
   - [ ] Sensitive information sent as a querystring parameter
   - [ ] No Rate Limiting
   - [ ] Misconfigured WAF
   - [ ] Misconfigured Headers
   - [ ] Potential Unwanted Ports

# Configuration for Windows

- Install Python and ADB and configure environment variables
- pip install frida frida-tools objection
Install Frida server from Frida Github Releases section [Push Frida server file basis android architecture]
- adb push frida-server-16.5.1-android-x86_64 /data/local/custom-server [create "custom-server" folder]
- chmod 777 frida-server-16.5.1-android-x86_64
- adb shell /data/local/custom-server/frida-server-16.5.1-android-x86_64 & [In case permission is denied run "adb shell su && /data/local/custom-server/frida-server-16.5.1-android-x86_64 &"]

# Install & Configure Magisk on Emulator
   - https://github.com/shakalaca/MagiskOnEmulator
   - https://systemweakness.com/rooting-emulator-and-installing-magisk-c3cbd34ec436

## To verify device architecture
- adb shell getprop ro.product.cpu.abi

## To convert certs
- openssl x509 -inform der -in Burpy.der -out Burpy.pem
- openssl x509 -inform PEM -subject_hash_old -in Burpy.pem
- mv Burpy.pem 9a5ba575.0
- adb push 9a5ba575.0 /system/etc/security/cacerts/

## For read only file system error:
- adb shell
- su
-  "mount -o remount, rw /" or "mount -o rw,remount /" or "mount -no rw,remount /" or "mount -o rw,remount /system" || Reset to original state "mount -o ro,remount /" [Use the commands without (")]
- Exit the shell and push certificate.

# Android Studio (Read-only system error)
- Add "C:\Users\<User>\AppData\Local\Android\Sdk\emulator" to system path.
- emulator -list-avds
- emulator -avd <avd-name> -writable-system
- adb root
- adb remount

## Configuring Burp & Android Emulator Proxy
- Genymotion Emulator >> Keep NAT
- Whatever emulator is in use  - set proxy IP as same as system's current network proxy & PORT to 8085
- Burp Proxy Settings - PORT to 8085 & Interface to "All"
- Set global proxy with ADB -- "adb shell settings put global http_proxy IP:PORT"
- Rollback to "No Proxy Setting" -- "adb shell settings put global http_proxy :0"

## Check for running services and applications in Frida in new terminal
- frida-ps -U | frida-ps -U -a -i

## Open Objection
- objection --gadget "Take name from Frida services or keep package name if available" device-type
- objection --gadget "Take name from Frida services or keep package name if available" explore
- android root disable
- android sslpinning disable

## Using Frida
- frida --codeshare dzonerzy/fridantiroot -f <package-name> -U [Root Detection Bypass]
- frida --codeshare fdciabdul/frida-multiple-bypass -f <package-name> -U [Multi Detection Bypass]
- frida --codeshare pcipolloni/universal-android-ssl-pinning-bypass-with-frida -f <package-name> -U [SSL Pinning Bypass]

## To run multiple scripts with Frida
- frida -U -f [App ID] -l script1.js -l script2.js

## Using Magisk
- Magisk > Install module MagiskHide Props Config > Conceal app icon and package name > settings > configure deny list > select <package_name> + Frida > multi bypass script
