# Credential Extraction via Burp Suite

## Introduction
This document outlines the process of capturing login credentials on DVWA using Burp Suite in a controlled penetration testing environment. The objective is to understand how insecure authentication mechanisms work and how to mitigate such vulnerabilities.

---

## Project Details
- **Project Title:** Credential Extraction via Burp Suite
- **Date:** February 2025

---

## Phase 1: Setup

### Required Tools
- [VirtualBox](https://www.virtualbox.org/)
- [Kali Linux](https://www.kali.org/get-kali/#kali-platforms)
- [DVWA (Damn Vulnerable Web App)](https://github.com/digininja/DVWA) (Refer to the video guide for proper setup)
- Apache & MariaDB (for hosting DVWA locally)
- [Burp Suite](https://portswigger.net/burp/documentation/desktop/getting-started/download-and-install)

### Installation Guide
1. Install VirtualBox and set up Kali Linux.
2. Configure Apache & MariaDB using the following commands:
   ```sh
   sudo service apache2 start    
   sudo service mariadb start  
   ```
3. Download and configure DVWA:
   - Open `http://localhost/DVWA` in a browser. (case sensitive)
   - Complete the database setup by referring to the video resources provided below.
4. Install and configure Burp Suite for intercepting requests.

### Video Resources:
- Virtual Box & Kali Linux Setup
- DVWA Setup
- Burp Suite Setup

### Screenshots:
/Images/1.png

/Images/2.png

/Images/3.png

/Images/4.png

/Images/5.png

/Images/6.png

/Images/7.png

/Images/8.png

/Images/9.png

---

## Phase 2: Capturing Credentials

### Intercepting Login Requests with Burp Suite
1. Open Burp Suite, go to `Proxy > Intercept`, and ensure Intercept is ON.
2. Use Burp Suite’s browser to navigate to `http://localhost/DVWA/login.php`.
3. Click **Forward** in Burp Suite to allow the captured request to proceed to the server.
4. Enter any credentials (e.g., `admin/password123`) and attempt to log in.
5. The intercepted HTTP request will display the credentials in plaintext.

### Screenshot:
![Intercepted Request](path/to/screenshot2.png)

---

## Phase 3: Extracting Credentials

### Captured HTTP Request Example
(Sample HTTP request with credentials in plaintext)

### Key Findings
- The username and password are transmitted in plaintext, making them vulnerable to interception.
- This highlights security flaws in unencrypted authentication systems.

### Screenshot:
![Captured Credentials](path/to/screenshot3.png)

---

## Phase 4: Implications and Prevention

### What This Demonstrates
- Understanding vulnerabilities in login mechanisms.
- Practical application of Burp Suite for security testing.
- How attackers can exploit unencrypted credential transmission.

### Prevention
1. **Secure Authentication:** Implement strong password hashing (e.g., bcrypt, Argon2) and multi-factor authentication (MFA) to protect user credentials.
2. **Use HTTPS:** Enforce HTTPS with SSL/TLS certificates to encrypt data in transit and prevent man-in-the-middle attacks.
3. **Secure Sessions:** Implement secure session management with HTTP-only, secure, and same-site cookies to prevent session hijacking.

---

## Important Reference Resources
- [Basic Project Idea](https://www.instagram.com/reel/DGBWj5LtEOs/?igsh=NHV3bmc0Zm5ybzFi)
- [DVWA GitHub Repository](https://github.com/digininja/DVWA)
- [DVWA Setup Guide](https://www.youtube.com/watch?v=WkyDxNJkgQ4)
- [Burp Suite Download](https://portswigger.net/burp/documentation/desktop/getting-started/download-and-install)
- [Burp Suite Configuration](https://www.youtube.com/watch?v=ZWKqxQF6aow&t=21s)

---

## Notes
Replace `path/to/screenshotX.png` with the actual image paths before uploading to GitHub.

