# -WLAN-Threat-Modeling-Using-OWASP-Threat-Dragon-and-STRIDE
Threat modeling of a small WLAN network using OWASP Threat Dragon and the STRIDE framework to identify and mitigate wireless security threats.
# WLAN Threat Modeling Using OWASP Threat Dragon and STRIDE

A practical lab report on threat modeling of a small Wireless Local Area Network (WLAN) environment using both manual paper-based analysis and the OWASP Threat Dragon tool. The lab applies the STRIDE framework to identify, categorize, and mitigate security threats across the network.

---

## Overview

This project demonstrates how threat modeling can be applied to a WLAN network to identify vulnerabilities, map attack paths, and design appropriate security controls. The analysis was performed using a structured step-by-step approach combining manual thinking and digital tool-based modeling.

---

## Tools Used

- **OWASP Threat Dragon v2.5.0** — Open-source threat modeling tool for creating system diagrams and identifying threats using the STRIDE framework
- **Paper-Based Modeling** — Manual sketching of the network architecture before digital implementation
- **STRIDE Framework** — Structured threat categorization model (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege)

---

## Getting OWASP Threat Dragon

OWASP Threat Dragon is free and open-source. You can access it in two ways:

### Option 1 — Use it Online (No Installation)
Run it directly in your browser with no setup required:
>  [https://www.threatdragon.com](https://www.threatdragon.com)

### Option 2 — Download the Desktop App
Download the desktop version for Windows, macOS, or Linux:
>  [https://github.com/OWASP/threat-dragon/releases](https://github.com/OWASP/threat-dragon/releases)

### Option 3 — Run it Locally with npm
If you have Node.js installed, you can run it locally:
```bash
git clone https://github.com/OWASP/threat-dragon.git
cd threat-dragon
npm install
npm start
```

### Additional Resources
- 📖 Official Documentation: [https://owasp.org/www-project-threat-dragon](https://owasp.org/www-project-threat-dragon)
- 💻 GitHub Repository: [https://github.com/OWASP/threat-dragon](https://github.com/OWASP/threat-dragon)
- 🎓 OWASP STRIDE Guide: [https://owasp.org/www-community/Threat_Modeling](https://owasp.org/www-community/Threat_Modeling)

---

## System Architecture

The modeled WLAN network consists of the following components:

| Component | Role |
|---|---|
| Internet | External / untrusted network |
| Router | Controls network access |
| Wireless Access Point | Distributes wireless connectivity |
| Laptop | User device |
| Smartphone | Mobile device |
| Printer | Network-connected device |
| Shared Data Storage | Files and shared data |

A **trust boundary** separates the internal network from the external internet. Data flows from the internet through the router to the access point and then to all connected devices.

---

## Step-by-Step Process

### Step 1 — Paper-Based Threat Modeling
The WLAN system was first sketched manually on paper to visualize how all devices are connected. Key components such as the router, wireless access point, and client devices were identified. Assets were listed and possible threats were thought through using an attacker mindset before moving to digital implementation.

### Step 2 — Creating the Model in OWASP Threat Dragon
A new threat model project was created in OWASP Threat Dragon with the following configuration:

- **Title:** WLAN Network Threat Model
- **Diagram Type:** STRIDE
- **Owner:** Joseph Erhuma Kpenyimk Yanney
- **Reviewer:** Dr. Aryeh

System components were added to the diagram using the following element types:

- **Process:** Router, Wireless Access Point
- **Actors:** Laptop, Smartphone, Printer, Internet
- **Store:** Shared Files/Data
- **Data Flow:** Connections between all components
- **Trust Boundary:** Internal network boundary separating trusted and untrusted zones

### Step 3 — Identifying Assets
The following assets were identified as requiring protection:

- Router configuration
- Wireless Access Point
- User devices (Laptop, Smartphone)
- Shared files and data
- Network traffic
- Printer

### Step 4 — Threat Identification Using STRIDE
Threats were identified and categorized using the STRIDE model:

| STRIDE Category | Threat Description |
|---|---|
| **Spoofing** | Fake access points or device impersonation |
| **Tampering** | Modification of network traffic or device configurations |
| **Repudiation** | Users denying actions due to absence of logs |
| **Information Disclosure** | Data interception over unencrypted Wi-Fi |
| **Denial of Service (DoS)** | Network flooding attacks disrupting availability |
| **Elevation of Privilege** | Unauthorized admin access to network devices |

### Step 5 — Vulnerability Identification
The following vulnerabilities were discovered during the analysis:

- Weak Wi-Fi passwords
- Outdated router firmware
- Lack of traffic encryption
- No network monitoring in place
- Poor access control policies
- Misconfigured network devices

### Step 6 — Threat Mitigation (Security Controls)
Each identified threat was addressed with appropriate security controls:

**Spoofing**
- Use WPA3 authentication
- Disable open Wi-Fi networks
- Enable MAC address filtering

**Tampering**
- Use encrypted communication (HTTPS, WPA3)
- Enable firmware integrity checks

**Repudiation**
- Enable logging and monitoring systems
- Maintain audit trails for all network activity

**Information Disclosure**
- Encrypt all wireless traffic
- Use VPN where necessary

**Denial of Service**
- Configure firewall rules
- Enable traffic filtering and rate limiting

**Elevation of Privilege**
- Change all default router credentials
- Apply regular firmware updates
- Enforce role-based access control (RBAC)

---

## Key Findings

The threat modeling process revealed that WLAN networks are highly vulnerable when not properly secured. The most critical risks identified were:

- Unauthorized access due to weak or missing authentication
- Data interception over unsecured wireless communication
- Misconfiguration of routers and access point devices

Using OWASP Threat Dragon made it easier to visualize attack paths and understand how an attacker could move laterally within the network. The STRIDE model ensured no major attack vector was overlooked.

---

## Conclusion

This lab successfully demonstrated how threat modeling can be used to analyze and improve the security posture of a WLAN network. By identifying assets, applying the STRIDE framework, and designing targeted mitigations, the network's overall security can be significantly strengthened.

The combination of paper-based modeling and OWASP Threat Dragon provided both conceptual understanding and practical hands-on experience. Understanding attacker thinking is key to proactively defending systems before attacks occur.

---

*All analysis was performed in a controlled lab environment for educational purposes.*
