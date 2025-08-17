# 🌐 Uniform Resource Locator (URL)

A **Uniform Resource Locator (URL)** is a **web address** that lets you access online content—such as webpages, videos, photos, or other media.  
It guides your browser to the correct resource on the Internet.

---

## 🔹 Anatomy of a URL
A URL is made up of several parts, each with a specific role.  
Understanding these parts is important for:
- Browsing the web  
- Developing web applications  
- Troubleshooting network or application issues  

**Main Components:**

---

### 1. 📜 Scheme
- Defines the **protocol** used to access the resource.  
- Common schemes:
  - `http://` → HyperText Transfer Protocol  
  - `https://` → Secure version (encrypted communication)  
- **Security Note**: HTTPS is strongly recommended because it prevents eavesdropping and tampering.  

---

### 2. 👤 User
- Some URLs can contain **user credentials** (e.g., username).  
- Format: `user@domain.com`  
- Rare today because it’s insecure → credentials can leak.  
- **Security Risk**: Avoid using login details inside URLs.  

---

### 3. 🌍 Host / Domain
- Identifies the **website** being accessed.  
- Must be unique and registered through domain registrars.  
- Example: `www.example.com`  
- **Security Note**: Watch out for **typosquatting** (fake domains mimicking real ones for phishing).  

---

### 4. 🔌 Port
- Indicates the **doorway (port)** used for communication with the server.  
- Common ports:
  - `80` → HTTP  
  - `443` → HTTPS  
- Range: `1 – 65535`  
- Example: `https://example.com:443`  

---

### 5. 📂 Path
- Specifies the **file or resource location** on the server.  
- Example: `/about/index.html`  
- **Security Note**: Access controls must be enforced to prevent unauthorized access.  

---

### 6. ❓ Query String
- Starts with `?` and contains **key=value pairs**.  
- Example: `?search=web+security&page=2`  
- Used for:
  - Search terms  
  - Form inputs  
- **Security Note**: Query strings can be **tampered with** → must validate inputs to prevent **injection attacks**.  

---

### 7. 🔗 Fragment
- Starts with `#` and points to a **specific section** within a webpage.  
- Example: `#section2`  
- Helps users jump directly to headings or content blocks.  
- **Security Note**: Though often ignored by servers, fragments can still be misused → sanitize input.  

---

## 📌 Summary
A URL is like a **map** that guides your browser to the right online resource.  
- **Scheme, User, Host, and Port** → define *where* and *how* to connect.  
- **Path, Query, and Fragment** → define *what specific resource* to retrieve.  
- From a **cybersecurity perspective**, every part of the URL must be handled carefully to prevent misuse (e.g., phishing, injection attacks, or unauthorized access).  
