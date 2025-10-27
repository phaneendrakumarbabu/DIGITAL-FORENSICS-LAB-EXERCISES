
# 🧩 Ex.No.6 — The Sleuth Kit (TSK)

---

## 🎯 Aim
To use **The Sleuth Kit (TSK)**, a collection of command-line tools, to analyze a disk image (`4Dell Latitude CPi.E01`), examine its file system, and recover digital evidence.

---

## ⚙️ Prerequisites & Installation

### 1️⃣ Sleuth Kit Tools  
Download the Windows version of Sleuth Kit (`sleuthkit-4.14.0-win32.zip`) and extract it to a known location, for example:
```

C:\Users\sleuthkit-4.14.0-win32

```

### 2️⃣ Evidence Files  
Download the sample disk image files (`4Dell Latitude CPi.E01` and `4Dell Latitude CPi.E02`) from the link provided in the lab manual.

### 3️⃣ Case Folder  
Create a folder for your investigation, e.g.:
```

C:\Forensics_Lab

````
Place the evidence files inside this folder.

---

## 🧪 Procedure

### 🔹 Step 1: Open Command Prompt & Navigate

- Open **Command Prompt (cmd.exe)** as Administrator.  
- Navigate to the `bin` folder inside your Sleuth Kit directory, where all tools are stored.

```bash
C:\Windows\System32> cd C:\Users\sleuthkit-4.14.0-win32\bin
````

<p align="center">
<img width="534" height="79" alt="Screenshot 2025-10-25 084644" src="https://github.com/user-attachments/assets/587309bf-6160-46ee-b8d2-9ba54a988b9d" />
</p>

---

### 🔹 Step 2: List Partitions (`mmls`)

* Run `mmls` to view the partition table and identify the **starting sector offset**.
* The image path must be in quotes.

```bash
mmls.exe "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```

📌 The NTFS partition (Slot 002) starts at **sector 63** — this offset will be used later.

<p align="center">
<img width="819" height="319" alt="Screenshot 2025-10-25 084720" src="https://github.com/user-attachments/assets/d954ec00-9ba4-4f0e-98ec-ff0b433588c8" />
</p>

---

### 🔹 Step 3: Analyze File System (`fsstat`)

* Use the offset (63) to analyze the file system details.

```bash
fsstat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```

<p align="center">
<img width="694" height="645" alt="Screenshot 2025-10-25 084902" src="https://github.com/user-attachments/assets/1567b244-f6b7-4663-846e-7c8914942ca7" />
</p>

---

### 🔹 Step 4: List Files & Directories (`fls`)

* List all files and directories recursively.
* Redirect the output to a text file.

```bash
fls.exe -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\file_list.txt
```

📄 **Result:** The full directory structure is stored in `file_list.txt`.

<p align="center">
<img width="1120" height="43" alt="image" src="https://github.com/user-attachments/assets/639f5181-39a9-4c35-855a-471b81146948" />
</p>

---

### 🔹 Step 5: Analyze File Metadata (`istat`)

* From `file_list.txt`, locate an interesting file — e.g., `Mr. Evil.bmp` (inode 9871).
* Extract metadata to a text report.

```bash
istat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\metadata_Mr_Evil.txt
```

<p align="center">
<img width="1886" height="338" alt="image" src="https://github.com/user-attachments/assets/726eb8d2-3ad3-4913-9631-7bb0deac00be" />
</p>

---

### 🔹 Step 6: Recover a File (`icat`)

* Recover a file using its inode number (9871) and save it as a BMP.

```bash
icat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\RECOVERED_Mr_Evil.bmp
```

<p align="center">
<img width="1363" height="362" alt="image" src="https://github.com/user-attachments/assets/8a302fb6-52f8-4987-b010-4490ddebb878" />
</p>

---

### 🔹 Step 7: Generate an Event Timeline (`mactime`)

#### (a) Generate a Body File

```bash
fls.exe -m / -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\body.txt
```

#### (b) Create the Timeline Report

```bash
mactime.pl -b C:\Forensics_Lab\body.txt > C:\Forensics_Lab\timeline.txt
```

<p align="center">
<img width="1655" height="160" alt="image" src="https://github.com/user-attachments/assets/bd0a0b07-4c8f-47a0-8437-6179b96fba8e" />
</p>

---

## ✅ Result

By following the above steps, we successfully used **The Sleuth Kit (TSK)** to:

* Identify partitions using `mmls`
* Analyze file system details with `fsstat`
* List directories and deleted files via `fls`
* Extract file metadata using `istat`
* Recover deleted files with `icat`
* Build a complete **file activity timeline** using `mactime`

All evidence files and recovered data are saved under `C:\Forensics_Lab`.

---

## 🧠 Conclusion

The experiment demonstrates how **The Sleuth Kit (TSK)** is an essential open-source forensic toolkit.
It helps investigators:

* Examine partitions and file systems
* Recover deleted or hidden files
* Generate evidence-based activity timelines

Thus, TSK provides a robust foundation for **digital forensic investigation and data recovery**.

---

## 🏫 Student Details

| **Name**                              | **Register Number** | **Branch**          | **College**             |
| ------------------------------------- | ------------------- | ------------------- | ----------------------- |
| 🧑‍💻 Goru Naga Phaneendra Kumar Babu | 99230041067         | CSE - Cybersecurity | Kalasalingam University |

---

⭐ *End of Experiment — Ex.No.6 (The Sleuth Kit)* ⭐


