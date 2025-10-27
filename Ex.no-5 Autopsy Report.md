# 🧩 **Ex.No.5 — Using Autopsy to Create a Case and Import Evidence**

---

## 🏫 **Student Information**

| **Name**                              | **Register Number** | **Branch**          | **College**              |
|--------------------------------------|---------------------|---------------------|--------------------------|
| 🧑‍💻 Goru Naga Phaneendra Kumar Babu | 99230041067         | CSE - Cybersecurity | Kalasalingam University  |

---

## 🎯 **Aim**
To analyze a forensic disk image using **Autopsy**, identify artifacts, and extract **digital evidence** for investigation.

---

## 📘 **Theory**

### 🔹 What is Autopsy?
**Autopsy** is a powerful **open-source digital forensics platform** used for analyzing disk images, mobile data, and memory dumps.  
It provides a **graphical interface** for The Sleuth Kit (TSK) and allows forensic investigators to examine evidence **without using complex command-line tools**.

### 🔹 Key Features
- File system and partition analysis  
- Keyword searching and hash filtering  
- Email and web artifact recovery  
- Timeline creation and user activity reconstruction  
- Reporting and evidence export  

Autopsy is widely used in **law enforcement, cybersecurity, and academic forensics labs** to perform investigations efficiently and accurately.

---

## ⚙️ **Installation**

### 🪄 Steps:
1️⃣ **Download:**  
   Visit the official website — [https://www.autopsy.com/download](https://www.autopsy.com/download)

2️⃣ **Install:**  
   Follow on-screen instructions for your operating system (Windows, Linux, or macOS).

3️⃣ **Launch:**  
   Open Autopsy via the desktop shortcut or the start menu.

---

## 🧪 **Procedure**

---

### 🔹 **Step 1 — Create a New Case**

- Launch **Autopsy** and click **“New Case.”**
- Enter the **Case Name**, **Case Number**, **Examiner Name**, and **Case Directory** for storing data.
- Click **Next** to continue.

<p align="center">
<img width="800" alt="Step 1" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im1.png" />
</p>

---

### 🔹 **Step 2 — Configure Case Details**

- Specify where the case data will be stored.
- Add optional details such as **examiner name**, **department**, and **notes**.
- Click **Finish** to create the case structure.

<p align="center">
<img width="800" alt="Step 2" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im2.png" />
</p>

---

### 🔹 **Step 3 — Add a Data Source**

Choose a data source to analyze:
- **Select the Source Type** (e.g., disk image, logical files, or local disk).  
- **Browse and select** the evidence image file (e.g., `.E01`, `.raw`, `.dd`).  
- **Configure Ingest Modules** such as:
  - File Type Identification  
  - Keyword Search  
  - Hash Lookup  
  - EXIF and Web History Analysis  
- Click **Start Analysis** to begin.

<p align="center">
<img width="800" alt="Step 3" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im3.png" />
</p>

---

### 🔹 **Step 4 — Initial Analysis and Overview**

Once ingestion begins:
- Monitor **Ingest Progress** at the bottom panel.  
- Explore **Resulting Artifacts** such as:
  - Recently opened files  
  - Web downloads  
  - USB activity  
  - Image and document files  
- Use the **Tree Viewer** to browse directories and filter specific file types.

<p align="center">
<img width="800" alt="Step 4" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im4.png" />
</p>

---

### 🔹 **Step 5 — Reporting**

#### 🧾 Generate Report:
- After completing the analysis, click **Generate Report**.  
- Choose report type (HTML, CSV, Excel, or XML).  
- Select which modules or results to include (keywords, hash hits, files, etc.).  

<p align="center">
<img width="800" alt="Step 5" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im5.png" />
</p>

#### 📤 Export Findings:
- Export specific files or directories of interest.
- Save reports for submission or further analysis.

<p align="center">
<img width="800" alt="Report Progress" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im6.png" />
</p>

#### 📋 Sample Generated Reports:

<p align="center">
<img width="800" alt="Reports" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im7.png" />
</p>

📄 Example text from report:

<p align="center">
<img width="800" alt="Report Text" src="https://github.com/Krishnabhargav08/DIGITAL-FORENSICS-LAB-EXERCISES/blob/972f703be7a3d1f082240d8c75b82fb83a26e45c/images/Ex-5%20im8.png" />
</p>

---

### 🔹 **Step 6 — Case Closure and Archiving**

- Once the investigation is completed, **close the case** using the toolbar option.  
- Archive the **case folder and reports** securely for future reference or court submission.  
- Maintain **chain of custody** documentation.

---

## 📊 **Observation Table**

| **Step** | **Action Performed** | **Output / Result** |
|-----------|----------------------|----------------------|
| Step 1 | Create a new case | New investigation folder created |
| Step 2 | Enter case details | Case metadata stored |
| Step 3 | Add data source | Disk image imported successfully |
| Step 4 | Analyze evidence | Artifacts displayed and categorized |
| Step 5 | Generate report | Reports exported in HTML/CSV |
| Step 6 | Close and archive | Case stored securely |

---

## ✅ **Result**
Successfully used **Autopsy** to create a forensic case, import a disk image, analyze artifacts, generate a report, and securely archive the evidence.  
The platform provided insights into user activity, file metadata, and recovered artifacts efficiently.

---

## 🧩 **Inference**
This experiment demonstrated the process of **digital evidence examination** using Autopsy.  
It highlights the tool’s ability to:
- Streamline forensic workflows  
- Recover deleted data  
- Analyze user activities  
- Generate legally admissible reports  

---

## ✨ **Conclusion**
Autopsy provides a **comprehensive forensic solution** for investigators.  
Its integration with **The Sleuth Kit (TSK)** allows powerful backend analysis with a simple interface.  
This makes Autopsy an essential tool for **cybersecurity professionals, digital forensic examiners, and law enforcement agencies**.

---

> 🕵️ *“Digital evidence never lies — Autopsy helps you uncover the truth byte by byte.”*

---

⭐ **End of Experiment — Ex.No.5 (Using Autopsy)** ⭐
