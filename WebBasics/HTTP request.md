# HTTP Requests – Notes for Cybersecurity

An **HTTP request** is what a user sends to a web server to interact with a web application and make something happen.  
Since these requests are often the first point of contact between the user and the server, knowing how they work is **super important**—especially for cybersecurity.

---

## 📌 Basic Structure of an HTTP Request
1. **Request Line (Start Line)**  
2. **Headers**  
3. **Request Body** (optional – only for POST, PUT, PATCH, etc.)

---

## 🔹 Request Line
The **request line** (or start line) is the first part of an HTTP request and tells the server what kind of request it’s dealing with.  

Format:
METHOD /path HTTP/version

### Example
    GET /login HTTP/1.1
---

## 🔹 HTTP Methods
The HTTP method tells the server **what action** the client wants to perform.

| Method  | Description | Security Concerns |
|---------|-------------|-------------------|
| **GET** | Fetch data from the server without changes. | Don’t expose sensitive info in URL; avoid tokens/passwords in GET. |
| **POST** | Sends data to server (create/update). | Validate and sanitize input (SQLi, XSS). |
| **PUT** | Replace or update resources. | Ensure authorization before changes. |
| **DELETE** | Removes resources from server. | Allow only authorized users. |
| **PATCH** | Update part of a resource. | Validate input to avoid inconsistencies. |
| **HEAD** | Like GET but retrieves only headers. | Useful for metadata, but no body returned. |
| **OPTIONS** | Shows available methods for a resource. | Disable if not needed (info disclosure). |
| **TRACE** | Echoes request for debugging. | Often disabled (security risk). |
| **CONNECT** | Creates secure connections (e.g., HTTPS). | Used in tunneling/encrypted comms. |

---

## 🔹 URL Path
The **URL path** specifies where to find the resource.

Example:  
https://tryhackme.com/api/users/123
Path: /api/users/123
### Security Practices
- Validate URL paths (prevent unauthorized access).  
- Sanitize paths (avoid injection).  
- Protect sensitive data.  

---

## 🔹 HTTP Versions
| Version | Year | Key Features |
|---------|------|--------------|
| **HTTP/0.9** | 1991 | Only supported GET. |
| **HTTP/1.0** | 1996 | Added headers & content types. |
| **HTTP/1.1** | 1997 | Persistent connections, caching, chunked encoding. |
| **HTTP/2** | 2015 | Multiplexing, header compression, prioritization. |
| **HTTP/3** | 2022 | Uses QUIC protocol for speed & security. |

✅ **Most systems still use HTTP/1.1** but upgrading to HTTP/2/3 improves performance and security.  

---

## 🔹 Common Request Headers
| Header | Example | Purpose |
|--------|---------|---------|
| **Host** | `Host: tryhackme.com` | Specifies the target server. |
| **User-Agent** | `User-Agent: Mozilla/5.0` | Identifies client/browser. |
| **Referer** | `Referer: https://google.com/` | Shows source of request. |
| **Cookie** | `Cookie: sessionid=abc123;` | Stores user/session data. |
| **Content-Type** | `Content-Type: application/json` | Defines request body format. |

---

## 🔹 Request Body
Used in requests like **POST, PUT, PATCH** where data is sent to the server.  
Formats include:

### 1. URL Encoded
`application/x-www-form-urlencoded`  
Data in `key=value` pairs separated by `&`.

**Example:**
POST /profile HTTP/1.1
Host: tryhackme.com
Content-Type: application/x-www-form-urlencoded

name=Aleksandra&age=27&country=US
---

### 2. Form Data
`multipart/form-data`  
Used for sending multiple parts, like **file uploads**.

**Example:**
POST /upload HTTP/1.1
Host: tryhackme.com
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary

------WebKitFormBoundary
Content-Disposition: form-data; name="username"

aleksandra
------WebKitFormBoundary
Content-Disposition: form-data; name="profile_pic"; filename="aleksandra.jpg"
Content-Type: image/jpeg

[Binary Data Here]
------WebKitFormBoundary--
---

### 3. JSON
`application/json`  
Structured as key-value pairs in `{ }`.

**Example:**


POST /api/user HTTP/1.1
Host: tryhackme.com
Content-Type: application/json

{
"name": "Aleksandra",
"age": 27,
"country": "US"
}


---

### 4. XML
`application/xml`  
Uses **tags** to wrap data.

**Example:**
POST /api/user HTTP/1.1
Host: tryhackme.com
Content-Type: application/xml

<user> <name>Aleksandra</name> <age>27</age> <country>US</country> </user> ```
✅ Key Takeaways for Cybersecurity

Don’t expose sensitive info in URLs.

Validate & sanitize all input.

Authorize before allowing PUT/DELETE.

Disable OPTIONS/TRACE if not needed.

Upgrade to HTTP/2 or HTTP/3 for better security.