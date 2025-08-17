# 🌐 HTTP Messages

**HTTP messages** are packets of data exchanged between a **client (user/browser)** and a **web server**.  
They are the foundation of how web applications communicate, showing how requests and responses flow between both sides.

---

## 🔹 Types of HTTP Messages
1. **HTTP Requests** → Sent by the client to trigger actions on the web application.  
   Example: Logging in, requesting a webpage, submitting a form.  

2. **HTTP Responses** → Sent by the server as a reply to the client’s request.  
   Example: Returning a webpage, confirming login success, sending API data.  

---

## 📝 Structure of an HTTP Message
Each HTTP message follows a standard format consisting of **four main parts**:

### 🚀 Start Line
- Acts as the *introduction* of the message.  
- **Request**: Includes the **HTTP method**, **URL**, and **protocol version**.  
  - Example: `POST /login HTTP/1.1`  
- **Response**: Includes the **protocol version**, **status code**, and **status message**.  
  - Example: `HTTP/1.1 200 OK`  

### 📑 Headers
- Contain **key-value pairs** providing extra instructions and metadata.  
- Examples:  
  - `Host: example.com`  
  - `Content-Type: application/json`  
  - `Authorization: Bearer <token>`  
- Used for: security, content type, caching rules, and session management.  

### ➖ Empty Line
- A required **blank line** between **headers** and **body**.  
- Without it, the message could be misread or cause errors.  

### 📦 Body
- Contains the **actual data** being transferred.  
- **Request Body**: User-submitted data (e.g., login credentials, form inputs).  
- **Response Body**: Content returned by the server (e.g., HTML page, JSON API data).  

---

## 📊 Example

### 🔹 HTTP Request (Login)
POST /login HTTP/1.1
Host: www.example.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 32

username=alice&password=12345

### 🔹 HTTP Response (Login Success)
