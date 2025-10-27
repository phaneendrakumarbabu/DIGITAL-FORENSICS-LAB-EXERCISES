# 🧪 Ex.No.2 — TestDisk: Open-Source Data Recovery Tool

---

## 🏫 Student Details
| **Name** | **Goru Naga Phaneendra Kumar Babu** |
|-----------|------------------------------------|
| **Register Number** | 99230041067 |
| **Branch** | CSE - Cybersecurity |
| **College** | Kalasalingam University |

---

## 💻 Course / Lab  
**Digital Forensics Lab**

---

## 🎯 Aim
To use **TestDisk** step by step to recover a missing partition and repair a corrupted one.

---

## 🧠 Objective
- To understand the working of the **TestDisk** recovery tool.  
- To recover deleted or corrupted partitions using forensic methodology.  
- To safely restore lost files without altering original data.

---

## 🧰 Requirements
- **Operating Systems:** Windows, Linux, or macOS  
- **Software:** TestDisk (open-source tool by CGSecurity)  
- **Privileges:** Administrative / root access  

---

## ⚙️ Installation

| **Platform** | **Command / Steps** |
|---------------|---------------------|
| **Linux (Debian/Ubuntu)** | `sudo apt-get install testdisk` |
| **macOS (Homebrew)** | `brew install testdisk` |
| **Windows** | Download from [CGSecurity Official Site](https://www.cgsecurity.org/) and run `testdisk_win.exe` |

---

## 🧾 Procedure

### 🔹 Step 1: Create a Log File
- Launch TestDisk using:
  - `sudo testdisk` (Linux/macOS)  
  - `testdisk_win.exe` (Windows)
- Select **[Create]** to generate a log file for tracking your recovery session.  
  This log helps document all actions taken during recovery.

<p align="center">
<img width="1106" height="635" src="https://github.com/user-attachments/assets/e8a9203d-b855-436d-93b1-acc965956c93" />
</p>

---

### 🔹 Step 2: Select the Drive to Analyze
- TestDisk lists all detected drives.  
- Use **Up/Down arrow keys** to select the drive with missing or damaged partitions.  
- Choose **[Proceed]** to continue.

<p align="center">
<img width="1098" height="635" src="https://github.com/user-attachments/assets/ab73948e-e51b-40e4-8ee7-018213426f0e" />
</p>

---

### 🔹 Step 3: Choose the Partition Table Type
- TestDisk automatically detects the partition table (e.g., **Intel/PC**, **EFI GPT**, etc.).  
- Accept the suggested value and press **Enter**.

<p align="center">
<img width="1097" height="644" src="https://github.com/user-attachments/assets/3c4156ec-95bc-400e-8bfb-8bfcf0d1955c" />
</p>

---

### 🔹 Step 4: Analyze Current Partition Structure
- From the main menu, choose **[Analyse]** and press **Enter**.  
- The tool displays the current partition table and scans for inconsistencies or missing partitions.

<p align="center">
<img width="1103" height="633" src="https://github.com/user-attachments/assets/6533e8ad-c50d-4d0e-85df-ed8d363c0218" />
</p>

---

### 🔹 Step 5: Perform a Quick Search
- Select **[Quick Search]** to begin scanning for lost partitions.  
- Found partitions are listed, and pressing **p** lets you preview their contents.  
- Deleted entries usually appear in **red**.  
- Press **q** to return to results.

<p align="center">
<img width="1098" height="637" src="https://github.com/user-attachments/assets/c4d01faa-441c-4789-93d7-c8ac5b6ec88b" />
</p>

---

### 🔹 Step 6: Perform a Deeper Search
- If Quick Search fails, select **[Deeper Search]** to scan the disk sector by sector.  
- This process takes longer but locates hidden or fragmented partitions.  
- Use **p** to preview files and confirm partition validity.

<p align="center">
<img width="1099" height="637" src="https://github.com/user-attachments/assets/5f7a6814-4f1d-425a-bd40-579ebc1a9671" />
</p>

---

### 🔹 Step 7: Modify Partition Status
- After locating the correct partitions, use **Left/Right arrow keys** to set their type:

| Symbol | Meaning |
|---------|----------|
| **P** | Primary |
| ***:** | Bootable |
| **L** | Logical |
| **D** | Deleted |

<p align="center">
<img width="1100" height="638" src="https://github.com/user-attachments/assets/bec038c0-7c0d-4e7c-a0a0-84dbeee45bae" />
</p>

✅ Ensure that recoverable partitions are **Primary or Logical**, not **Deleted**.

---

### 🔹 Step 8: Write the Partition Table
- Once satisfied, choose **[Write]** to save changes.  
- Press **Y** to confirm.  
- This updates the partition table on disk.

⚠️ **Caution:** This action is irreversible — review your selections carefully.

<p align="center">
<img width="1089" height="643" src="https://github.com/user-attachments/assets/0c163668-bbd8-4220-a926-8255f93e49a0" />
</p>

<p align="center">
<img width="1101" height="637" src="https://github.com/user-attachments/assets/bfcaefe2-abce-44ee-b6e6-b9e9fd25bcc4" />
</p>

---

### 🔹 Step 9: Recover Files
- If you only need specific files:  
  - Press **p** to open a partition’s file list.  
  - Use **:** to mark files/folders.  
  - Press **C** (uppercase) to copy them.  
  - Choose a safe destination on another drive and press **C** again to paste.

---

### 🔹 Step 10: Exit and Restart
- After recovery, choose **[Quit]** to exit TestDisk.  
- If a partition table was rewritten, **restart** your system so OS detects the recovered partitions.

---

## 🧩 Observation
| Parameter | Description |
|------------|-------------|
| Tool Used | TestDisk |
| Type | Open-source data recovery tool |
| Function | Restores lost partitions and recovers deleted files |
| Output | Recovered partition / file system successfully |

---

## ✅ Result
TestDisk successfully detected and recovered missing or corrupted partitions. The tool also allowed restoration of individual deleted files, demonstrating its reliability for forensic and data recovery tasks.

---

## 🔐 Forensic Importance
- **Integrity Preservation:** TestDisk performs recovery without overwriting original evidence data.  
- **Traceability:** Log files document every step of the recovery process for chain-of-custody.  
- **Non-destructive Recovery:** Safe for use in forensic imaging or analysis environments.

---

## 🧮 Advantages
1. Open-source and cross-platform.  
2. Recovers lost partitions, boot sectors, and FAT/NTFS/ext file systems.  
3. Creates detailed recovery logs for forensic documentation.  
4. Works even with damaged or corrupted disks.  

---

## ❌ Limitations
- Command-line interface (less user-friendly for beginners).  
- Cannot fix severely damaged drives with physical errors.  
- Requires understanding of partition types and structures.  

---

## 💡 Best Practices
- Always work on **disk images**, not original drives.  
- Save recovered files to a **different storage device**.  
- Use **FTK Imager** or **dd** beforehand to clone suspect drives.  
- Maintain a **forensic logbook** of every action performed.

---

## 🏁 Conclusion
This experiment demonstrates the usage of **TestDisk**, an open-source forensic tool for recovering lost or corrupted partitions. The tool proved effective for data recovery, partition table repair, and digital forensic analysis without compromising original evidence.

---

✨ *Prepared by:* **Goru Naga Phaneendra Kumar Babu**  
🎓 *CSE – Cybersecurity | Kalasalingam University*  
🆔 *Register No.: 99230041067*
