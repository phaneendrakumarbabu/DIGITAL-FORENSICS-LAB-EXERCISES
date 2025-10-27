# 🧩 Experiment No. 4 — Analyze Email Headers and Detect Email Spoofing Using Mail Header Analyzer

---

## 👨‍💻 Student Details
| **Name** | **Register No.** | **Branch** | **College** |
|-----------|------------------|-------------|--------------|
| **Goru Naga Phaneendra Kumar Babu** | **99230041067** | **CSE - Cybersecurity** | **Kalasalingam University** |

---

## 🧪 Course / Lab Details
**Course Name:** Digital Forensics Laboratory  
**Experiment No.:** 4  
**Title:** Analyze Email Headers and Detect Email Spoofing Using Mail Header Analyzer  

---

## 🎯 Aim
To analyze email headers and identify possible **email spoofing** or **phishing attempts** using the **Mail Header Analyzer** tool.

---

## 🧰 Requirements
- **Mail Header Analyzer** (Online or offline tool)  
- **Email client** such as Gmail / Outlook / Yahoo  
- **WHOIS / IP Lookup tools** for tracing IP addresses  
- **Internet connection** to verify email origin servers  

---

## 🧠 Description

An **email header** contains hidden metadata that records the journey of an email from the sender to the recipient.  
It includes technical information such as:
- **Sender and Receiver details**
- **Mail servers passed through (Received headers)**
- **Authentication details (SPF, DKIM, DMARC)**  
- **Date, Message-ID, and routing path**

Attackers can **forge (spoof)** the sender’s address to deceive users — a common method in **phishing, malware delivery, and business email compromise (BEC)**.

Analyzing these headers helps forensic investigators:
- Identify the **real sender IP address**  
- Trace **email routing paths**  
- Check **authentication mechanisms (SPF/DKIM/DMARC)**  
- Detect signs of **fraudulent or spoofed emails**

---

## ⚙️ Procedure — Steps to Analyze Email Headers

---

### 🧾 Step 1: Obtain the Email Header
In Gmail:
- Open the suspicious email.  
- Click on the **three dots (⋮)** near the reply button.  
- Select **“Show Original”** to view the raw email header.

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.26.55.jpeg" alt="Step 1">
</p>

---

### 🧩 Step 2: View the Raw Header Information
The raw header displays all technical routing data such as sender domain, mail server IPs, timestamps, and security checks.

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.27.16.jpeg" alt="Step 2">
</p>

---

### 🧠 Step 3: Use Mail Header Analyzer
- Open an online **Mail Header Analyzer** (like Google’s or MXToolbox).  
- It automatically parses headers into readable format.

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.27.34.jpeg" alt="Step 3">
</p>

---

### 🧩 Step 4: Paste Header Text for Analysis
- Copy the entire raw header from Gmail’s **Show Original** window.  
- Paste it into the analyzer and click **Analyze Header**.

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.27.46.jpeg" alt="Step 4">
</p>

---

### 🧱 Step 5: Interpret Key Header Fields
The analyzer highlights important header fields such as:
- **From** — Claimed sender  
- **To** — Recipient  
- **Subject** — Email subject line  
- **Return-Path** — Where replies are sent (useful for spoof detection)  
- **Received** — The path email took (each server adds one)  
- **Message-ID** — Unique identifier  
- **SPF / DKIM / DMARC** — Authentication mechanisms  

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.28.00.jpeg" alt="Step 5">
</p>

---

### 🌐 Step 6: Analyze IP Addresses and Server Path
- Identify the **originating IP** from the first “Received” line.  
- Use **WHOIS** or **IP lookup** tools to find the **geographical location** and **organization** of the sending mail server.  
- Check for **inconsistent server names** or **unexpected locations** (e.g., email claiming from India but originating in Russia).

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.28.13.jpeg" alt="Step 6">
</p>

---

### 🔐 Step 7: Examine Authentication Results (SPF, DKIM, DMARC)
- **SPF (Sender Policy Framework):** Verifies if the sending IP is authorized by the domain’s DNS.  
- **DKIM (DomainKeys Identified Mail):** Confirms that the message hasn’t been tampered with.  
- **DMARC (Domain-based Message Authentication, Reporting, and Conformance):** Defines how emails failing SPF/DKIM should be handled.

> 💡 If any of these fail, it’s a strong indicator of **spoofing or phishing**.

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.29.05.jpeg" alt="Step 7a">
</p>

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.29.19.jpeg" alt="Step 7b">
</p>

<p align="center">
  <img width="700" src="https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/9fbbaf3e036c541c5ecf03ce8b980e220c3d37a3/images/WhatsApp%20Image%202025-09-01%20at%2012.29.29.jpeg" alt="Step 7c">
</p>

---

## 📊 Expected Output
After analyzing the email header:
- The **Mail Header Analyzer** highlights all critical fields.  
- The tool displays **SPF/DKIM/DMARC results** clearly (Pass/Fail).  
- **Suspicious IP addresses**, domains, or hostnames are identified.  
- If SPF or DKIM fails, the email is likely **spoofed**.  
- Investigators can trace the **actual source** of the email and confirm **phishing attempts**.

---

## 🧠 Conclusion
By analyzing the email header using **Mail Header Analyzer**, we can:
- Detect forged or spoofed sender details.  
- Identify the **true origin** of an email message.  
- Understand the **email routing path** and server details.  
- Strengthen digital forensic skills in **email investigation and cybercrime detection**.

---

## 🧾 Result
Successfully analyzed email headers using the **Mail Header Analyzer tool** and detected potential spoofing by verifying **SPF**, **DKIM**, and **DMARC** authentication failures.

---

