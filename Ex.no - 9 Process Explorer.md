# 🧪 **Ex.No: 9 – Using Process Explorer to Identify Suspicious Processes**

---

## 🏫 **Student Details**
| **Name** | **Goru Naga Phaneendra Kumar Babu** |
|-----------|------------------------------------|
| **Register Number** | 99230041067 |
| **Branch** | CSE - Cybersecurity |
| **College** | Kalasalingam University |

---

## 🧭 **Course / Lab:** Digital Forensics Lab  
## 🔢 **Experiment No.:** 9  
## 🧰 **Title:** Using Process Explorer to Identify Suspicious Processes  

---

## 🎯 **Aim**
To use **Microsoft Sysinternals Process Explorer** to monitor system activities and identify any **suspicious or malicious processes** running on a Windows computer.

---

## 🧩 **Requirements**
- Windows Operating System  
- Internet Connection  
- **Process Explorer** (Microsoft Sysinternals Suite)  
- *(Optional)* Antivirus Software — e.g., Windows Defender / Malwarebytes  

---

## 📘 **Description**
**Process Explorer** is part of the **Microsoft Sysinternals Suite**.  
It is a powerful tool used to view detailed information about system processes.  
This tool helps forensic investigators and administrators to:
- Analyze active processes  
- Detect suspicious or malicious behavior  
- Monitor CPU and memory usage  
- Verify process authenticity via **digital signatures**

---

## ⚙️ **Step-by-Step Procedure**

### 🪟 **Step 1: Download and Setup Process Explorer**
1. Visit: 🔗 [Microsoft Sysinternals – Process Explorer](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer)  
2. Click **Download Process Explorer**.  
3. Extract the ZIP file to a folder.  
4. Right-click `procexp64.exe` → Select **Run as Administrator**.  

---

### 🧭 **Step 2: Understanding the Interface**
1. Main window shows all running processes in a **hierarchical tree view**.  
2. Displays details like **PID**, **CPU**, **Memory**, and **Company Name**.  
3. Color Codes:
   - 🟩 **Green:** Newly started processes  
   - 🟥 **Red:** Terminated processes  
   - 🟦 **Light Blue:** Processes by current user  
   - 🟪 **Pink:** Suspended processes  

![Process Explorer Interface](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/20813074f7e55b479108660a16f276f69e56ad41/images/9.1.jpeg)

---

### 🔍 **Step 3: Identify Suspicious Processes**
1. Look for **unfamiliar or oddly named processes** (e.g., `xkdjeo.exe`, `abc123.exe`).  
2. Check **Company Name** and **Description** — genuine apps show known publishers.  
3. Right-click → **Properties** → **Image Tab** → verify **Path**:
   - ✅ Safe: `C:\Windows\System32\`
   - ⚠️ Suspicious: `C:\Users\<User>\AppData\Temp\` or `Downloads\`
4. Check **Digital Signature**:
   - ✔️ Valid → Trusted  
   - ❌ Invalid / None → Potential malware  

![Checking Process Details](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/326db74a3770e2ba22207f5a48b737f17307f683/images/9.10.jpeg)

---

### 📊 **Step 4: Analyze Process Behavior**
1. Observe **CPU**, **Memory**, and **I/O usage**.  
2. Unusual high resource usage → may indicate malware.  
3. Right-click → **Properties** → **TCP/IP Tab** to check unknown network connections.  
4. Examine **Handles** and **DLLs Tabs** for suspicious files or libraries.  

![Process Analysis](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/326db74a3770e2ba22207f5a48b737f17307f683/images/9.4.jpeg)

---

### 🕵️ **Step 5: Verify Process Legitimacy**
1. Google the process name — e.g., `svchost.exe` vs `svhost.exe` (typo = malware).  
2. Visit 🔗 [VirusTotal](https://www.virustotal.com) to scan or check the file.  
3. Cross-check using **ProcessLibrary.com** or official vendor websites.  

![VirusTotal Check](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/326db74a3770e2ba22207f5a48b737f17307f683/images/9.6.jpeg)

---

### 🧹 **Step 6: Take Appropriate Action**
- **If Malicious:**
  - Right-click → **Kill Process**  
  - Delete the file from its directory  
- **If Unsure:**
  - Right-click → **Suspend Process** for further investigation  
- **After Removal:**
  - Perform a **Full System Scan** with antivirus tools  

![Killing Malicious Process](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/326db74a3770e2ba22207f5a48b737f17307f683/images/9.8.jpeg)

---

### 💻 **Step 7: Example Observation**
| **Detail** | **Observation** |
|-------------|----------------|
| **Process Name** | `faangpath_simple_template.pdf` |
| **CPU Usage** | 70% |
| **Path** | `C:\Users\Admin\AppData\Temp\faangpath_simple_template.pdf` |
| **Digital Signature** | None |
| **Company Name** | Unknown |
| **Network Activity** | Connected to unknown IPs |
| **Online Check (VirusTotal)** | Detected as Trojan |
| **Action Taken** | Suspended → Killed → Deleted → Full Scan Performed |

![Example Observation](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/326db74a3770e2ba22207f5a48b737f17307f683/images/9.9.jpeg)

---

## 🧾 **Result**
Using **Process Explorer**, suspicious processes were identified based on their:
- CPU usage  
- File path  
- Digital signature  
- Network activity  

Malicious processes were terminated and removed, ensuring **system integrity and security**.

---

## 🏁 **Conclusion**
**Process Explorer** is an essential forensic tool that offers detailed visibility into active processes.  
It enables cybersecurity analysts and forensic investigators to:
- **Detect** suspicious processes  
- **Analyze** resource behavior and signatures  
- **Eliminate** malicious threats effectively  

Hence, it serves as a powerful utility in the **Digital Forensics Investigation Toolkit**.

---

✨ *Prepared by:* **Goru Naga Phaneendra Kumar Babu**  
🎓 *CSE – Cybersecurity | Kalasalingam University*  
🆔 *Register No.: 99230041067*
