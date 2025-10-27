
# 🧩 **Ex.No.6 — The Sleuth Kit (TSK)**  
### 🔍 *Digital Forensic Analysis Using Command-Line Tools*

---

## 🏫 **Student Information**

| **Name**                              | **Register Number** | **Branch**          | **College**              |
|--------------------------------------|---------------------|---------------------|--------------------------|
| 🧑‍💻 Goru Naga Phaneendra Kumar Babu | 99230041067         | CSE - Cybersecurity | Kalasalingam University  |

---

## 🎯 **Aim**
To use **The Sleuth Kit (TSK)**, a collection of open-source command-line tools, to **analyze a disk image**, examine its **file system**, and **recover digital evidence** for forensic investigation.

---

## 🧠 **Objective**
- To understand the **role of TSK** in digital forensics.  
- To learn how to **mount, analyze, and recover** data from a disk image.  
- To extract and interpret **metadata and timestamps** of files.  
- To reconstruct a **forensic timeline of events**.

---

## 📘 **Theory**

### 🔹 What is The Sleuth Kit (TSK)?
**The Sleuth Kit (TSK)** is a powerful **digital forensic framework** used to analyze disk images, file systems, and partitions. It provides tools for investigators to inspect evidence at a **low-level**, such as sectors, inodes, and metadata.

It supports:
- **File system analysis** (FAT, NTFS, EXT, HFS+)
- **Deleted file recovery**
- **Timeline generation (MAC times)**
- **Automated data carving**

TSK is typically used with **Autopsy**, its GUI front-end, but can also be used **independently via command-line**, which is ideal for precise forensic control.

---

### 🔹 Forensic Concepts Used
- **Partition Table Analysis:** Using `mmls` to view disk layout.  
- **File System Statistics:** Using `fsstat` to extract metadata.  
- **File Listing & Recovery:** Using `fls`, `icat`, and `istat`.  
- **Timeline Analysis:** Using `mactime` to reconstruct file activity.

---

## ⚙️ **Prerequisites & Setup**

### 🧰 Tools Required
- **Operating System:** Windows / Linux  
- **Tool:** The Sleuth Kit (`sleuthkit-4.14.0-win32.zip`)  
- **Sample Evidence:** `4Dell Latitude CPi.E01`, `4Dell Latitude CPi.E02`  
- **Text Editor:** Notepad / Visual Studio Code  
- **Command Prompt / PowerShell**

---

### 🔧 Installation Steps

1️⃣ **Download Sleuth Kit (TSK):**  
   Extract the zip file to a convenient folder, e.g.  
```

C:\Users\sleuthkit-4.14.0-win32

```

2️⃣ **Prepare Evidence Files:**  
Copy your `.E01` evidence image files into a working directory:  
```

C:\Forensics_Lab

````

3️⃣ **Set Up Case Folder:**  
Keep all outputs, recovered files, and reports inside `C:\Forensics_Lab`.

---

## 🧪 **Procedure**

### 🔹 Step 1: Open Command Prompt
Navigate to the `bin` folder where all TSK tools are stored.
```bash
cd C:\Users\sleuthkit-4.14.0-win32\bin
````

<p align="center">
<img width="534" height="79" alt="cmd_path" src="https://github.com/user-attachments/assets/587309bf-6160-46ee-b8d2-9ba54a988b9d" />
</p>

---

### 🔹 Step 2: Partition Analysis — `mmls`

Display the partition table of the evidence file.

```bash
mmls.exe "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```

📊 *Result:* The NTFS partition starts at **sector 63** — this offset is required for further analysis.

<p align="center">
<img width="819" height="319" alt="mmls_output" src="https://github.com/user-attachments/assets/d954ec00-9ba4-4f0e-98ec-ff0b433588c8" />
</p>

---

### 🔹 Step 3: File System Statistics — `fsstat`

Analyze the NTFS file system using the discovered offset.

```bash
fsstat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```

📄 This command extracts metadata such as:

* File system type
* Volume serial number
* Cluster size and sector size
* Root directory entries

<p align="center">
<img width="694" height="645" alt="fsstat_output" src="https://github.com/user-attachments/assets/1567b244-f6b7-4663-846e-7c8914942ca7" />
</p>

---

### 🔹 Step 4: List Files — `fls`

List all files and directories recursively and save them.

```bash
fls.exe -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\file_list.txt
```

📁 The output contains active and deleted files.

<p align="center">
<img width="1120" height="43" alt="fls_output" src="https://github.com/user-attachments/assets/639f5181-39a9-4c35-855a-471b81146948" />
</p>

---

### 🔹 Step 5: Analyze Metadata — `istat`

Extract file metadata for a specific inode.

```bash
istat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\metadata_Mr_Evil.txt
```

📌 Reveals information like:

* File creation, modification, and access times (MAC times)
* Logical/physical block locations
* File size and allocation details

<p align="center">
<img width="1886" height="338" alt="istat_output" src="https://github.com/user-attachments/assets/726eb8d2-3ad3-4913-9631-7bb0deac00be" />
</p>

---

### 🔹 Step 6: Recover File — `icat`

Recover the file using its inode number.

```bash
icat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\RECOVERED_Mr_Evil.bmp
```

✅ *Recovered file saved successfully in your case folder.*

<p align="center">
<img width="1363" height="362" alt="icat_output" src="https://github.com/user-attachments/assets/8a302fb6-52f8-4987-b010-4490ddebb878" />
</p>

---

### 🔹 Step 7: Generate Event Timeline — `mactime`

#### (a) Create Body File

```bash
fls.exe -m / -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\body.txt
```

#### (b) Generate Timeline

```bash
mactime.pl -b C:\Forensics_Lab\body.txt > C:\Forensics_Lab\timeline.txt
```

📆 The timeline shows **creation, modification, access, and deletion** times for each file — critical for reconstructing user activity.

<p align="center">
<img width="1655" height="160" alt="timeline_output" src="https://github.com/user-attachments/assets/bd0a0b07-4c8f-47a0-8437-6179b96fba8e" />
</p>

---

## 📊 **Observation Table**

| **Command** | **Purpose**               | **Output**                   |
| ----------- | ------------------------- | ---------------------------- |
| `mmls`      | Display partition details | Partition table with offsets |
| `fsstat`    | View file system metadata | NTFS structure info          |
| `fls`       | List files recursively    | File directory list          |
| `istat`     | Show inode metadata       | File MAC timestamps          |
| `icat`      | Extract files by inode    | Recovered file               |
| `mactime`   | Build activity timeline   | Chronological user activity  |

---

## ✅ **Result**

Successfully performed forensic analysis using **The Sleuth Kit (TSK)** by:

* Identifying and interpreting partitions
* Extracting file metadata
* Recovering deleted files
* Generating a timeline of activities

All evidence files and recovered data are saved under:

```
C:\Forensics_Lab
```

---

## 🧩 **Inference**

This experiment demonstrates the **practical use of Sleuth Kit tools** in **digital forensics** to:

* Uncover hidden or deleted data
* Trace system activities
* Support legal or investigative processes
  TSK thus serves as a **vital forensic framework** for data recovery and evidence preservation.

---

## ✨ **Conclusion**

Through this experiment, we explored the capabilities of **The Sleuth Kit (TSK)** in conducting low-level forensic investigations.
It reinforced understanding of **NTFS internals**, **inode structures**, and **timeline analysis**, making it a crucial tool for cybersecurity professionals.

---

> 🔐 *“Every byte leaves a trace — the investigator’s job is to follow it.”*

---

⭐ **End of Experiment — Ex.No.6 (The Sleuth Kit)** ⭐


