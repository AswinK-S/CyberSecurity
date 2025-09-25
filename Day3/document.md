## 7. Most Critical Vulnerabilities

### Vulnerability 1: SMB Signing Not Required
- **Severity:** Medium  
- **Description:** An unauthenticated, remote attacker can exploit this to conduct man-in-the-middle (MITM) attacks against the SMB server. The remote SMB server does not require message signing, making communication vulnerable to interception.  
- **Affected System:** SMB Server  
- **Recommendation:**  
  - **Windows:**  
    1. Open Group Policy Editor:  
       `Computer Configuration → Windows Settings → Security Settings → Local Policies → Security Options`  
    2. Enable **"Microsoft network server: Digitally sign communications (always)"**.  
    3. Reboot the system.  
  - **Samba (Linux):**  
    1. Edit Samba configuration:  
       ```bash
       sudo nano /etc/samba/smb.conf
       ```
    2. Add or update:  
       ```
       server signing = mandatory
       ```
    3. Restart Samba:  
       ```bash
       sudo systemctl restart smbd
       ```
- **References:**  
  - [Microsoft Docs: SMB Signing](https://learn.microsoft.com/en-us/windows-server/security/group-policy/smb-signing)  
  - [Samba Server Signing Documentation](https://www.samba.org/samba/docs/current/man-html/smb.conf.5.html)

---

### Vulnerability 2: SSL Certificate Cannot Be Trusted
- **Severity:** Medium  
- **Description:** The server's SSL certificate chain cannot be verified. This can happen due to a self-signed certificate, missing intermediate certificates, expired certificates, or bad signatures. This breaks trust and increases risk of MITM attacks.  
- **Affected System:** HTTPS Server  
- **Recommendation:**  
  - **For Public Servers:**  
    1. Purchase a certificate from a trusted Certificate Authority (CA) such as Let's Encrypt, DigiCert, or GlobalSign.  
    2. Install the certificate along with the full chain of intermediate certificates.  
    3. Ensure validity dates and signature algorithms are correct.  
  - **For Internal Servers:**  
    1. Use an internal CA and install the CA certificate on all clients that need to trust it.  
    2. Replace self-signed certificates with trusted ones.  
    3. Keep certificates updated before expiration.  
- **Example (Apache):**
    ```bash
    SSLCertificateFile /etc/ssl/certs/your_domain.crt
    SSLCertificateKeyFile /etc/ssl/private/your_domain.key
    SSLCertificateChainFile /etc/ssl/certs/chain.pem
    ```
    Restart Apache:  
    ```bash
    sudo systemctl restart apache2
    ```
- **References:**  
  - [Let’s Encrypt Documentation](https://letsencrypt.org/docs/)  
  - [SSL Best Practices](https://sslmate.com/help/ssl-best-practices/)
