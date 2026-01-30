My ISP gateway does not allow manual DNS configuration or bridge mode, so I implemented a device-level DNS workaround using Cloudflare and encrypted DNS within Google Chrome.

This setup improves privacy, security, and DNS performance without modifying ISP hardware.

Network Environment

Operating System: Windows 10

ISP: Xfinity (DNS locked at gateway level)

Router Access: Limited (no bridge mode / DNS override)

Browser: Google Chrome

Objective

Bypass ISP-enforced DNS routing

Route DNS queries through Cloudflare DNS

Enable encrypted DNS (DNS over HTTPS)

Improve privacy and security at the endpoint level

Cloudflare DNS Servers Used
Primary DNS:   1.1.1.1
Secondary DNS: 1.0.0.1

Implementation Steps
Step 1 — Access Network Adapter Settings

Press Windows + R

Enter:

ncpa.cpl


Press Enter to open Network Connections

Step 2 — Configure DNS on Active Adapter

Right-click the active network adapter (Ethernet or Wi-Fi)

Select Properties

Open Internet Protocol Version 4 (IPv4)

Choose:

Use the following DNS server addresses

Enter:

Preferred DNS:   1.1.1.1
Alternate DNS:   1.0.0.1

<img width="717" height="655" alt="ethipv4dns" src="https://github.com/user-attachments/assets/ba8f1958-89ed-46ab-adc8-31d5076eeb6c" />


Save changes

This ensures Cloudflare DNS is preferred at the operating system level.

Step 3 — Enable Encrypted DNS in Google Chrome

Open Chrome Settings

Navigate to:

Privacy and Security → Security


Enable:

Use Secure DNS

Select provider:

Cloudflare (1.1.1.1)

<img width="705" height="229" alt="googledns" src="https://github.com/user-attachments/assets/ef58fad9-8ff8-4911-9f58-fcedd56cb0dc" />



This forces Chrome to use DNS over HTTPS (DoH), encrypting DNS requests and bypassing ISP DNS interception.

Step 4 — Verification

To confirm functionality, navigate to:

https://1.1.1.1/help


Successful configuration displays:

✅ Using Cloudflare DNS: YES

✅ DNS over HTTPS: YES

This confirms DNS queries are encrypted and resolved by Cloudflare.

Why This Works

Although the ISP router distributes DNS information via DHCP, modern browsers like Chrome support independent encrypted DNS resolution.

By enabling Secure DNS:

Browser → Encrypted DNS tunnel → Cloudflare → Internet


The ISP is unable to intercept, redirect, or log domain lookups.

Benefits of Using Cloudflare DNS
🔐 Improved Privacy

DNS queries are encrypted using DNS over HTTPS

Prevents ISP DNS monitoring and manipulation

Cloudflare does not sell user DNS data

🛡️ Enhanced Security

Protection against DNS spoofing and hijacking

Reduced exposure to malicious domains

Optional malware and content filtering available

⚡ Faster DNS Resolution

Cloudflare operates one of the largest global DNS networks

Typically lower DNS latency compared to ISP DNS

🧠 Real-World Networking Experience

Demonstrates understanding of:

DNS resolution

ISP gateway limitations

Encrypted DNS

Endpoint-level security controls

Mirrors real enterprise troubleshooting scenarios

Key Takeaway

Even when ISP hardware restricts DNS configuration, secure DNS can still be implemented at the endpoint and application layer.

This project demonstrates a practical workaround using industry-standard tools and highlights how encryption can be used to regain control over network behavior.
