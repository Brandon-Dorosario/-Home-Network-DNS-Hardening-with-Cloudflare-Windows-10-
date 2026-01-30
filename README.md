Overview

This project documents how I implemented secure DNS resolution on a Windows 10 system where the ISP gateway restricted DNS configuration.

The goal was to improve privacy, prevent DNS interception, and demonstrate practical networking troubleshooting.

Problem

ISP router locked DNS settings

No bridge mode available

DNS traffic could be monitored or redirected

Solution

Configured Cloudflare DNS (1.1.1.1 / 1.0.0.1)

Enabled encrypted DNS (DNS over HTTPS) in Google Chrome

Verified secure DNS resolution via Cloudflare diagnostic tools


<img width="717" height="655" alt="ethipv4dns" src="https://github.com/user-attachments/assets/888515fa-ca4a-4a05-8e1e-193c9980fcde" />


<img width="705" height="229" alt="googledns" src="https://github.com/user-attachments/assets/6cc1b889-9991-473e-8110-eb6294603902" />


<img width="602" height="143" alt="cloudflareconfirmation" src="https://github.com/user-attachments/assets/0b3ce5cd-6b15-47d2-aebf-045c966f45cb" />



Skills Demonstrated

DNS resolution fundamentals

Troubleshooting ISP network limitations

Endpoint-level network configuration

Security-focused problem solving

Technical documentation

Verification

Cloudflare DNS verification page confirmed:

Using Cloudflare DNS

DNS over HTTPS enabled

Technologies Used

Windows 10

Google Chrome

Cloudflare DNS (1.1.1.1)

DNS over HTTPS (DoH)
