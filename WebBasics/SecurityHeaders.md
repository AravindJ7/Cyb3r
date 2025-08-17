# HTTP Security Headers – Notes for Cybersecurity

**HTTP Security Headers** improve the overall security of a web application by protecting against attacks like **Cross-Site Scripting (XSS), clickjacking, MIME sniffing, and data leaks**.  
You can check headers of any website using [securityheaders.io](https://securityheaders.io/).

We will cover the following important headers:

- **Content-Security-Policy (CSP)**
- **Strict-Transport-Security (HSTS)**
- **X-Content-Type-Options**
- **Referrer-Policy**

---

## 🔹 Content-Security-Policy (CSP)
The **CSP header** helps prevent attacks such as **XSS** by restricting what content (scripts, styles, media, etc.) can be loaded on a website.  
It defines **trusted sources** (domains) for different types of content.

### Example:
Content-Security-Policy: default-src 'self'; script-src 'self' https://cdn.tryhackme.com; style-src 'self'
### Breakdown:
- **default-src 'self'** – Only allow resources from the current domain.  
- **script-src 'self' https://cdn.tryhackme.com** – Allow scripts from the current domain and from `cdn.tryhackme.com`.  
- **style-src 'self'** – Allow styles only from the current domain.  

✅ Using `'self'` means only the website’s own domain is trusted.  

---

## 🔹 Strict-Transport-Security (HSTS)
Forces browsers to always connect using **HTTPS**, protecting against downgrade/MITM attacks.  

### Example:
Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
### Breakdown:
- **max-age=63072000** – Validity period in seconds (here = 2 years).  
- **includeSubDomains** – Apply HSTS to all subdomains too.  
- **preload** – Allows site to be included in browser preload lists for HSTS.  

---

## 🔹 X-Content-Type-Options
Prevents browsers from **MIME sniffing** (guessing content type incorrectly, which can cause attacks).

### Example:
X-Content-Type-Options: nosniff
### Breakdown:
- **nosniff** – Tells the browser to trust only the declared `Content-Type` header, not guess.  

✅ Helps prevent XSS by blocking execution of malicious files served with wrong MIME types.  

---

## 🔹 Referrer-Policy
Controls how much **referrer information** is sent to other websites when users click links.  
This prevents leaking sensitive URLs to external sites.

### Examples:


Referrer-Policy: no-referrer
Referrer-Policy: same-origin
Referrer-Policy: strict-origin
Referrer-Policy: strict-origin-when-cross-origin
### Breakdown:
- **no-referrer** – Don’t send any referrer information.  
- **same-origin** – Send referrer only if destination is the same origin.  
- **strict-origin** – Send only the origin (domain) when going from HTTPS → HTTPS.  
- **strict-origin-when-cross-origin** –  
  - Full URL sent for same-origin requests.  
  - Only origin sent for cross-origin (HTTPS → HTTPS).  

---

## ✅ Key Takeaways
- **CSP**: Restrict sources of scripts, styles, and other content → reduces XSS risk.  
- **HSTS**: Enforce HTTPS, prevent downgrade/MITM attacks.  
- **X-Content-Type-Options**: Prevent MIME type sniffing.  
- **Referrer-Policy**: Limit referrer info exposure to protect privacy.  
