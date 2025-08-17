# HTTP Responses – Notes for Cybersecurity

When you interact with a web application, the **server sends back an HTTP response** to let you know whether your request was successful or something went wrong.  
These responses include a **status code** and a short explanation (Reason Phrase) that describes how the server handled your request.

---

## 📌 Status Line
The **first line** of an HTTP response is called the **Status Line**. It has three parts:

1. **HTTP Version** – The version of HTTP being used.  
2. **Status Code** – A three-digit number showing the result.  
3. **Reason Phrase** – Human-readable explanation of the status code.  

**Example:**
HTTP/1.1 200 OK
---

## 🔹 Status Codes and Reason Phrases
Status codes are grouped into **five main categories**:

| Category | Range | Meaning |
|----------|-------|---------|
| **Informational** | 100–199 | Request received, continue process. |
| **Successful** | 200–299 | Request processed successfully. |
| **Redirection** | 300–399 | Resource moved, client should use another URL. |
| **Client Error** | 400–499 | Problem with the client’s request (bad URL, no auth, etc.). |
| **Server Error** | 500–599 | Problem on the server while processing request. |

---

## 🔹 Common Status Codes
- **100 Continue** – The server got part of the request and is ready for more.  
- **200 OK** – Request successful, resource returned.  
- **301 Moved Permanently** – Resource has moved to a new URL permanently.  
- **404 Not Found** – The server couldn’t find the requested resource.  
- **500 Internal Server Error** – Server encountered an error while processing.  

---

## 🔹 Response Headers
HTTP response headers are **key-value pairs** sent by the server to provide additional information about the response.  

### Required Response Headers
| Header | Example | Purpose |
|--------|---------|---------|
| **Date** | `Date: Fri, 23 Aug 2024 10:43:21 GMT` | Timestamp of response generation. |
| **Content-Type** | `Content-Type: text/html; charset=utf-8` | Defines type of content (HTML, JSON, XML, etc.) and charset. |
| **Server** | `Server: nginx` | Indicates server software (often hidden for security). |

---

### Other Common Response Headers
- **Set-Cookie**  
Set-Cookie: sessionId=38af1337es7a8; HttpOnly; Secure- Sends cookies from server to client.  
- Use **HttpOnly** (block JavaScript access) and **Secure** (HTTPS only).  

- **Cache-Control**  
Cache-Control: max-age=600- Defines caching rules.  
- Use `no-cache` or `no-store` for sensitive data.  

- **Location**  
Location: /index.html- Used in **3xx redirections** to tell the client where to go.  
- Must be validated to avoid **open redirect vulnerabilities**.  

---

## 🔹 Response Body
The **response body** contains the actual content the server sends back:  
- HTML pages  
- JSON data  
- Images  
- Files  

### Security Practices
- Always **sanitize and escape user-generated content** in the response.  
- Prevent injection attacks such as **XSS**.  

---

## ✅ Key Takeaways for Cybersecurity
- Status codes help understand request outcomes (success, client error, server error).  
- Sensitive info should not be leaked via response headers.  
- Set cookies securely (`HttpOnly`, `Secure`).  
- Avoid open redirects by validating the `Location` header.  
- Always sanitize data in the response body to prevent **XSS**.  
