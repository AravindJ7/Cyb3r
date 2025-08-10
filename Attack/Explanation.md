# Man-in-the-Middle (MitM) Attack: Types and Prevention Methods

---

## What is a Man-in-the-Middle (MitM) Attack?

A **Man-in-the-Middle attack** happens when an attacker secretly intercepts and possibly alters the communication between two parties who believe they are directly communicating with each other. The attacker can eavesdrop, steal sensitive information, or inject malicious data without the knowledge of the original parties.

---

## Common Types of Man-in-the-Middle Attacks

1. **Eavesdropping Attack**  
   Attacker listens to the communication secretly (e.g., capturing data on unsecured Wi-Fi).

2. **Session Hijacking**  
   Attacker steals session cookies or tokens to impersonate a user and take over a session.

3. **SSL Stripping**  
   Attacker downgrades HTTPS connections to HTTP, making the communication unencrypted and readable.

4. **DNS Spoofing (DNS Cache Poisoning)**  
   Attacker redirects a domain name to a fake IP address to intercept or modify traffic.

5. **IP Spoofing**  
   Attacker masquerades as a trusted IP address to intercept or alter traffic.

6. **Wi-Fi Eavesdropping / Rogue Wi-Fi Access Point**  
   Attacker sets up a fake Wi-Fi hotspot and intercepts all traffic from connected users.

---

## How Does a MitM Attack Work? (Simplified)

1. User A wants to communicate with User B.  
2. Attacker intercepts the communication channel.  
3. Attacker relays messages between A and B, capturing or modifying data.  
4. Neither A nor B realize they are talking through the attacker.

---

## Prevention Methods for Man-in-the-Middle Attacks

1. **Use Strong Encryption (HTTPS / TLS)**  
   Always use HTTPS websites and services with strong TLS encryption to prevent interception of data.

2. **Verify SSL/TLS Certificates**  
   Browsers warn about invalid certificates—never ignore these warnings. Use certificate pinning if possible.

3. **Use VPNs**  
   VPNs encrypt traffic between you and the VPN server, making interception harder on insecure networks.

4. **Avoid Public / Untrusted Wi-Fi**  
   Avoid sensitive transactions on open Wi-Fi networks, or use a VPN if you must.

5. **Implement Multi-Factor Authentication (MFA)**  
   Even if attackers hijack credentials, MFA adds an extra layer of protection.

6. **Use Strong Authentication Protocols**  
   Protocols like SSH, WPA3 (for Wi-Fi), and secure DNS (DNSSEC) help prevent spoofing.

7. **Keep Software and Firmware Updated**  
   Patch vulnerabilities that attackers exploit to intercept or hijack connections.

8. **Use Secure DNS**  
   DNSSEC or DNS over HTTPS (DoH) can prevent DNS spoofing.

9. **Educate Users**  
   Teach users not to click suspicious links and to verify the legitimacy of Wi-Fi networks.

---

