# OWASP Web Application Security Testing Checklist
- Available in [PDF](OWASP/OWASP%20Web%20Application%20Security%20Testing%20Checklist.pdf) or [Docx](OWASP/OWASP%20Web%20Application%20Security%20Testing%20Checklist.docx) for printing
-  [Trello Board to copy yours](https://trello.com/b/zTSkJPkL/owasp-web-checklist)

## Table of Contents

* [Information Gathering](#Information)
* [Configuration Management](#Configuration)
* [Secure Transmission](#Transmission)
* [Authentication](#Authentication)
* [Session Management](#Session)
* [Authorization](#Authorization)
* [Data Validation](#Validation)
* [Denial of Service](#Denial)
* [Business Logic](#Business)
* [Cryptography](#Cryptography)
* [Risky Functionality - File Uploads](#File)
* [Risky Functionality - Card Payment](#Card)
* [HTML 5](#HTML)

### <a name="Information">Information Gathering</a>
- [x] Manually explore the site
- [ ] Spider/crawl for missed or hidden content
- [x] Check for files that expose content, such as robots.txt, sitemap.xml, .DS_Store
- [ ] Check the caches of major search engines for publicly accessible sites
- [ ] Check for differences in content based on User Agent (eg, Mobile sites, access as a Search engine Crawler)
- [x] Perform Web Application Fingerprinting
- [x] Identify technologies used
- [x] Identify user roles
- [x] Identify application entry points
- [x] Identify client-side code
- [ ] Identify multiple versions/channels (e.g. web, mobile web, mobile app, web services)
- [ ] Identify co-hosted and related applications
- [x] Identify all hostnames and ports
- [ ] Identify third-party hosted content


### <a name="Configuration">Configuration Management</a>

- [x] Check for commonly used application and administrative URLs
- [ ] Check for old, backup and unreferenced files
- [x] Check HTTP methods supported and Cross Site Tracing (XST)
- [x] Test file extensions handling
- [x] Test for security HTTP headers (e.g. CSP, X-Frame-Options, HSTS)
- [ ] Test for policies (e.g. Flash, Silverlight, robots)
- [ ] Test for non-production data in live environment, and vice-versa
- [ ] Check for sensitive data in client-side code (e.g. API keys, credentials)


### <a name="Transmission">Secure Transmission</a>

- [x] Check SSL Version, Algorithms, Key length
- [x] Check for Digital Certificate Validity (Duration, Signature and CN)
- [x] Check credentials only delivered over HTTPS
- [x] Check that the login form is delivered over HTTPS
- [x] Check session tokens only delivered over HTTPS
- [x] Check if HTTP Strict Transport Security (HSTS) in use



### <a name="Authentication">Authentication</a>
- [ ] Test for user enumeration
- [x] Test for authentication bypass
- [x] Test for bruteforce protection
- [x] Test password quality rules
- [x] Test remember me functionality
- [x] Test for autocomplete on password forms/input
- [x] Test password reset and/or recovery
- [x] Test password change process
- [ ] Test CAPTCHA
- [x] Test multi factor authentication
- [x] Test for logout functionality presence
- [x] Test for cache management on HTTP (eg Pragma, Expires, Max-age)
- [x] Test for default logins
- [ ] Test for user-accessible authentication history
- [x] Test for out-of channel notification of account lockouts and successful password changes
- [ ] Test for consistent authentication across applications with shared authentication schema / SSO



### <a name="Session">Session Management</a>
- [x] Establish how session management is handled in the application (eg, tokens in cookies, token in URL)
- [x] Check session tokens for cookie flags (httpOnly and secure)
- [x] Check session cookie scope (path and domain)
- [x] Check session cookie duration (expires and max-age)
- [x] Check session termination after a maximum lifetime
- [x] Check session termination after relative timeout
- [x] Check session termination after logout
- [x] Test to see if users can have multiple simultaneous sessions
- [x] Test session cookies for randomness
- [x] Confirm that new session tokens are issued on login, role change and logout
- [ ] Test for consistent session management across applications with shared session management
- [ ] Test for session puzzling
- [x] Test for CSRF and clickjacking



### <a name="Authorization">Authorization</a>
- [x] Test for path traversal
- [x] Test for bypassing authorization schema
- [x] Test for vertical Access control problems (a.k.a. Privilege Escalation)
- [x] Test for horizontal Access control problems (between two users at the same privilege level)
- [x] Test for missing authorization


### <a name="Validation">Data Validation</a>
- [ ] Test for Reflected Cross Site Scripting
- [ ] Test for Stored Cross Site Scripting
- [ ] Test for DOM based Cross Site Scripting
- [ ] Test for Cross Site Flashing
- [ ] Test for HTML Injection
- [x] Test for SQL Injection
- [ ] Test for SOQL Injection
- [ ] Test for LDAP Injection
- [ ] Test for ORM Injection
- [ ] Test for XML Injection
- [ ] Test for XXE Injection
- [ ] Test for SSI Injection
- [ ] Test for XPath Injection
- [ ] Test for XQuery Injection
- [ ] Test for IMAP/SMTP Injection
- [x] Test for Code Injection
- [ ] Test for Expression Language Injection
- [ ] Test for Command Injection
- [ ] Test for Overflow (Stack, Heap and Integer)
- [ ] Test for Format String
- [ ] Test for incubated vulnerabilities
- [ ] Test for HTTP Splitting/Smuggling
- [ ] Test for HTTP Verb Tampering
- [ ] Test for Open Redirection
- [ ] Test for Local File Inclusion
- [ ] Test for Remote File Inclusion
- [ ] Compare client-side and server-side validation rules
- [ ] Test for NoSQL injection
- [ ] Test for HTTP parameter pollution
- [ ] Test for auto-binding
- [ ] Test for Mass Assignment
- [ ] Test for NULL/Invalid Session Cookie


### <a name="Denial">Denial of Service</a>
- [x] Test for anti-automation
- [ ] Test for account lockout
- [ ] Test for HTTP protocol DoS
- [ ] Test for SQL wildcard DoS


### <a name="Business">Business Logic</a>
- [ ] Test for feature misuse
- [ ] Test for lack of non-repudiation
- [ ] Test for trust relationships
- [x] Test for integrity of data
- [x] Test segregation of duties


### <a name="Cryptography">Cryptography</a>
- [x] Check if data which should be encrypted is not
- [ ] Check for wrong algorithms usage depending on context
- [x] Check for weak algorithms usage
- [x] Check for proper use of salting
- [x] Check for randomness functions


### <a name="File">Risky Functionality - File Uploads</a>
- [x] Test that acceptable file types are whitelisted
- [x] Test that file size limits, upload frequency and total file counts are defined and are enforced
- [ ] Test that file contents match the defined file type
- [ ] Test that all file uploads have Anti-Virus scanning in-place.
- [x] Test that unsafe filenames are sanitised
- [x] Test that uploaded files are not directly accessible within the web root
- [ ] Test that uploaded files are not served on the same hostname/port
- [x] Test that files and other media are integrated with the authentication and authorisation schemas


### <a name="Card">Risky Functionality - Card Payment</a>
- [ ] Test for known vulnerabilities and configuration issues on Web Server and Web Application
- [ ] Test for default or guessable password
- [ ] Test for non-production data in live environment, and vice-versa
- [ ] Test for Injection vulnerabilities
- [ ] Test for Buffer Overflows
- [ ] Test for Insecure Cryptographic Storage
- [ ] Test for Insufficient Transport Layer Protection
- [ ] Test for Improper Error Handling
- [ ] Test for all vulnerabilities with a CVSS v2 score > 4.0
- [ ] Test for Authentication and Authorization issues
- [ ] Test for CSRF


### <a name="HTML">HTML 5</a>
- [ ] Test Web Messaging
- [ ] Test for Web Storage SQL injection
- [ ] Check CORS implementation
- [ ] Check Offline Web Application


Source: [OWASP](https://www.owasp.org/index.php/Web_Application_Security_Testing_Cheat_Sheet)
