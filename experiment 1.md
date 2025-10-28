# 🧩 **Experiment No. 1 — FTK Imager: A Forensic Imaging Tool Overview**

---

---

## 🧑‍💻 **Student Details**

| 🔹 **Name** | **Goru Naga Phaneendra Kumar Babu** |
|-------------|--------------------------------------|
| 🆔 **Register Number** | **99230041067** |
| 💻 **Branch** | **CSE - Cybersecurity** |
| 🎓 **College** | **Kalasalingam University** |

---


## 🧠 **Aim**
To acquire both **volatile memory (RAM)** and **non-volatile memory (Disk Image)** using **FTK Imager**, and understand the importance of forensic imaging in digital investigations.

---

## 🎯 **Objective**
1. Learn how to use **FTK Imager** to acquire volatile and non-volatile data.  
2. Understand the significance of **write-blocking** and **hash verification**.  
3. Ensure the **forensic integrity** of collected evidence using hash algorithms.  
4. Gain hands-on experience in capturing **RAM and disk images** for forensic analysis.

---

## ⚙️ **Tool Requirements**

| **Component** | **Details** |
| :------------- | :----------- |
| **Tool Name** | FTK Imager |
| **Developer** | Exterro (formerly AccessData) |
| **Supported OS** | Windows 7/8/10/11 (64-bit) |
| **Download Link** | [FTK Imager Official Page](https://www.exterro.com/digital-forensics-software/ftk-imager) |

---

## 🧩 **Part A — Acquiring Volatile Memory (RAM) Using FTK Imager**

### 🔹 Step 1: Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the FTK Imager icon → **Run as Administrator**.

![Image](https://github.com/user-attachments/assets/d45f9bbf-2df5-4b2c-82bf-62471d4e78ce)

---

### 🔹 Step 2: Initiate Memory Capture
- In the top menu bar, click **File → Capture Memory**.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/f462b449-6b1e-4c47-ba2f-1f50cf7b97af" />

---

### 🔹 Step 3: Configure Destination
A dialog box will appear to set the **destination path** and **filename**.

- **Destination Path:** Choose an **external drive** or folder.  
- **Filename:** Default is `memdump.mem`; you can rename it.  
- **Options:**
  - ✅ *Include pagefile.sys* → captures virtual memory.
  - ✅ *Create AD1 file* → stores the dump in AccessData’s container format.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/484dee02-b3aa-43a9-b76a-41b890729922" />

---

### 🔹 Step 4: Start Memory Capture
- Click **Capture Memory** to begin the acquisition.  
- A progress bar indicates status.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/30e357c4-0fac-47ce-8896-98105eecb8c1" />

---

### 🔹 Step 5: Wait for Completion
- The time depends on total **RAM size**.  
- Once finished, the memory dump will be available in the chosen folder.  
- The resulting file can be analyzed using tools like **Volatility** or **Autopsy**.

---

## 🧱 **Part B — Acquiring Non-Volatile Memory (Disk Image) Using FTK Imager**

### 🔹 Step 1: Start the Process
- In FTK Imager, go to **File → Create Disk Image...**

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/e2a72525-43e7-45e4-ae78-63b067413617" />

---

### 🔹 Step 2: Select Source Evidence Type
Choose the source you want to image:

| **Option** | **Description** |
| :---------- | :--------------- |
| **Physical Drive** | Full disk including all partitions and unallocated space |
| **Logical Drive** | Specific partition (e.g., C:) |
| **Image File** | Converts an existing image |
| **Contents of Folder** | Captures selected folder only |

<img width="1356" height="767" alt="Image" src="https://github.com/user-attachments/assets/875e6028-ea41-4402-b73c-af5cc080fda8" />

---

### 🔹 Step 3: Select the Source Drive
- Select the physical drive connected through a **write-blocker**.  
- Click **Finish** to confirm.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/2efe2c5d-c93d-4afa-a2a5-4937eab469ff" />

---

### 🔹 Step 4: Configure Image Destination
- Click **Add...** → Choose **image type** and **destination**.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/25b48ff5-572a-462b-b41e-c063aa3fcca4" />

**Choose Image Type:**
- 🧱 **E01 (EnCase Format)** – Recommended; supports compression and metadata.  
- 📁 **Raw (DD)** – Simple bit-for-bit copy without metadata.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/91175f3c-0868-488b-bf0a-14b339cb5457" />

**Fill in Evidence Details:**
- Case Number  
- Examiner Name  
- Description / Notes

This metadata is stored inside the image for **forensic documentation**.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/b676246a-71b8-489f-abff-12a36cdfbcfa" />

---

### 🔹 Step 5: Set Output Options
- Choose a **destination folder** (different from source drive).  
- Set **image fragment size** (0 = single file).  
- Click **Finish**.

---

### 🔹 Step 6: Start Imaging
- Check **“Verify images after creation”** to ensure data integrity.  
- Click **Start** to begin disk imaging.

<img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/a23f3fd9-fd2f-48ea-ad09-5ea6ce7684ff" />

---

### 🔹 Step 7: Completion and Hash Verification
- FTK Imager automatically computes **MD5** and **SHA1 hashes**.  
- Matching hashes confirm **forensic integrity** of the acquired image.

| **Hash Type** | **Purpose** |
| :------------- | :----------- |
| **MD5** | Ensures file integrity |
| **SHA-1** | Confirms authenticity across copies |

---

## 🧾 **Result**
✅ Successfully captured **RAM dump** and **disk image** using **FTK Imager**.  
Both volatile and non-volatile memory acquisitions were verified through **hash validation** to maintain forensic integrity.

---

## 🧩 **Conclusion**
This experiment demonstrated the **importance of forensic imaging** in digital investigations.  
Using **FTK Imager**, both **volatile** (RAM) and **non-volatile** (disk) data were safely acquired and verified.  
The process reinforced key forensic principles such as:
- **Chain of custody**
- **Data integrity verification**
- **Use of write-blockers**
- **Proper evidence documentation**

---

## 📚 **References**
- 🔗 [FTK Imager Official Website](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- 📘 *AccessData FTK Imager User Guide*  
- 🧠 *Nelson, Phillips, Steuart — Guide to Computer Forensics and Investigations (Cengage Learning)*  

---

✨ *End of Experiment — Digital Forensics Lab (Kalasalingam University)* ✨
