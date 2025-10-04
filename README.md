# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information

![WhatsApp Image 2025-10-04 at 11 25 57_6b9dfb70](https://github.com/user-attachments/assets/59dc92c1-1421-4bc4-ad36-eb7b52f1b24a)

![WhatsApp Image 2025-10-04 at 11 50 13_b04fb0bb](https://github.com/user-attachments/assets/7374421c-a64e-4fa0-ac88-b22d71e3880f)

![WhatsApp Image 2025-10-04 at 11 54 30_9d13d2e0](https://github.com/user-attachments/assets/40b6453a-b0b6-4a6e-b8b2-f7609ecb2781)

![WhatsApp Image 2025-10-04 at 11 55 06_99142687](https://github.com/user-attachments/assets/609e869e-7846-4238-b145-fb0a491477a3)

![WhatsApp Image 2025-10-04 at 11 55 28_cdb447a9](https://github.com/user-attachments/assets/d897bc59-1406-418d-8f19-9d30aa733bd1)

![WhatsApp Image 2025-10-04 at 11 56 17_d505e617](https://github.com/user-attachments/assets/b834fdfc-b6d2-4a9f-92a6-ae4ff174af78)


## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

