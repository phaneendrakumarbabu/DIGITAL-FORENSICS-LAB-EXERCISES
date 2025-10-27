
# 🧪 **Ex.No.3 – Wireshark: Network Packet Capture & Analysis**

---

## 🏫 **Student Details**
| **Name** | **Goru Naga Phaneendra Kumar Babu** |
|-----------|------------------------------------|
| **Register Number** | 99230041067 |
| **Branch** | CSE - Cybersecurity |
| **College** | Kalasalingam University |

---

## 🧭 **Course / Lab:** Digital Forensics Lab  
## 🔢 **Experiment No.:** 3  
## 🌐 **Title:** Wireshark – Network Packet Capture and Analysis Tool  
**Website Used:** [http://demo.testfire.net/](http://demo.testfire.net/)

---

## 🎯 **Aim**
To use **Wireshark** for capturing, analyzing, and understanding network packets — and to demonstrate how **plaintext credentials** sent over HTTP can be intercepted.

---

## 🧠 **Objective**
- To understand how data travels through network layers.  
- To learn how to capture live packets using Wireshark.  
- To inspect HTTP traffic and identify plaintext login data.  
- To understand the security risks of unencrypted data transmission.

---

## 📘 **Theory**

### 🧩 What is Wireshark?
Wireshark is an open-source **network protocol analyzer** used for capturing and inspecting the data that flows across a network in real time. It helps in understanding how protocols work, identifying network issues, and performing digital forensic investigations.

### ⚙️ **Working Principle**
Wireshark captures packets directly from the **Network Interface Card (NIC)** using a packet capture library (like **libpcap** on Linux or **WinPcap/Npcap** on Windows).  
Each captured packet is decoded according to the OSI model layers — Physical, Data Link, Network, Transport, and Application — and displayed in a human-readable format.

### 📊 **Common Use Cases**
- Network troubleshooting  
- Security auditing and digital forensics  
- Protocol reverse engineering  
- Malware and intrusion detection  
- Education and research

---

## 🧰 **Tools & Requirements**
| **Software / Hardware** | **Description** |
|--------------------------|----------------|
| Wireshark | Packet capturing and analysis tool |
| Web Browser | To generate HTTP traffic |
| Test Website | [http://demo.testfire.net/](http://demo.testfire.net/) |
| Internet Connection | For live packet transmission |

---

## ⚙️ **Procedure: Capturing Plaintext Passwords**

### 🔹 Step 1 — Start Capturing Packets
1. Launch **Wireshark**.  
2. Choose your active network interface (usually **Wi-Fi**).  
3. Click the blue **shark fin icon 🦈** to start packet capture.

<p align="center">
<img width="859" height="620" src="https://github.com/user-attachments/assets/d2d2f108-c7c4-4802-ac9e-c8635263ca5c" />
</p>

<p align="center">
<img width="750" height="550" src="https://github.com/user-attachments/assets/542d082e-68d0-427d-a595-e90c7a25d1c0" />
</p>

---

### 🔹 Step 2 — Generate Login Traffic
1. Open your browser and go to **http://demo.testfire.net/**.  
2. Enter sample credentials to simulate a login request:  
   - **Username:** `testuser`  
   - **Password:** `password123`  
3. Click the **Login** button — even though it fails, the data has been sent to the server.

<p align="center">
<img width="645" height="420" src="https://github.com/user-attachments/assets/52371b26-88cc-4578-8535-4c50f6c7516d" />
</p>

---

### 🔹 Step 3 — Stop Capture & Apply Filter
1. Return to Wireshark and click the **Stop (🟥)** button.  
2. Apply a filter to find HTTP POST requests:
   ```http
   http.request.method == "POST"

3. This will display packets containing login form data.

<p align="center">
<img width="600" height="400" src="https://github.com/user-attachments/assets/9feaba3d-7443-4b27-ad5c-96c0cd9076e0" />
</p>

---

### 🔹 Step 4 — Inspect the Packet for Credentials

1. Select the POST packet (for example, `POST /userinfo.php`).
2. Expand:

   * **Hypertext Transfer Protocol**
   * **HTML Form URL Encoded**
3. You’ll find:

   ```
   username = testuser
   password = password123
   ```

   in **plaintext**.

<p align="center">
<img width="856" height="632" src="https://github.com/user-attachments/assets/da7fe228-4fa9-4c43-805a-ed1b2129a955" />
</p>

---

## 🧾 **Observation**

| **Parameter**   | **Details**                      |
| --------------- | -------------------------------- |
| Protocol        | HTTP                             |
| Method Used     | POST                             |
| Captured Fields | Username, Password               |
| Encryption      | None                             |
| Result          | Credentials visible in plaintext |

---

## ✅ **Result**

Wireshark successfully captured the HTTP POST request containing **plaintext credentials**.
This confirms that:

* **HTTP transmits data without encryption.**
* **Sensitive information** like usernames and passwords can be easily intercepted.

---

## ⚠️ **Security Analysis**

* HTTP is **insecure** because data is sent as plain text.
* Any attacker on the same network can **sniff** login credentials.
* HTTPS encrypts data using **TLS (Transport Layer Security)**, making interception impractical.
* Always ensure websites use HTTPS, especially during login or transactions.

---

## 🌍 **Real-World Importance**

* Network administrators use Wireshark to diagnose slow connections and detect intrusions.
* Cybersecurity professionals analyze malicious payloads and sniff suspicious data packets.
* Ethical hackers demonstrate **Man-in-the-Middle (MITM)** attacks to educate users about encryption.

---

## 🧮 **Advantages of Using Wireshark**

1. Free and open-source tool.
2. Supports 2,000+ protocols for analysis.
3. Provides both live capture and offline analysis.
4. Offers graphical statistics and conversation flow.
5. Essential for learning network forensics and ethical hacking.

---

## ❌ **Limitations**

* Cannot capture encrypted HTTPS credentials.
* Requires admin/root privileges.
* Generates large data files in heavy traffic networks.
* Misuse for illegal data interception can be punishable.

---

## 🏁 **Conclusion**

This experiment demonstrates that **Wireshark** is a powerful tool for inspecting and analyzing network data. By capturing an HTTP login request, it proves that sensitive information can be viewed in plaintext when encryption is not used.
This emphasizes the **importance of HTTPS** in maintaining privacy and security in modern networks.

---

✨ *Prepared by:* **Goru Naga Phaneendra Kumar Babu**
🎓 *CSE – Cybersecurity | Kalasalingam University*
🆔 *Register No.: 99230041067*

