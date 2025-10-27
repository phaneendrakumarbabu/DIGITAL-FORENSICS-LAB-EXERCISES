# 🧪 **Experiment-1: Evidence Acquisition Using FTK Imager**

---

## 🏫 **Student Details**
| **Name** | **Goru Naga Phaneendra Kumar Babu** |
|-----------|------------------------------------|
| **Register Number** | 99230041067 |
| **Branch** | CSE - Cybersecurity |
| **College** | Kalasalingam University |

---

## 🧭 **Course / Lab:** Digital Forensics Lab  
## 🔢 **Experiment No.:** 1  
## 🧰 **Title:** Evidence Acquisition Using FTK Imager  

---

## 🎯 **Aim**
To capture **RAM data** and create a **forensic disk image** using **FTK Imager**.

---

## 🧩 **Requirements**
- **FTK Imager**  
- **Windows Operating System**  

---

## 📘 **Description**
- **FTK Imager** is a forensic acquisition tool used to create **exact copies (disk images)** of storage devices.  
- It enables capturing **RAM data**, entire drives, or specific partitions **without altering** the original evidence.  
- Forensic investigators use it to **preview, preserve, and export** data for further forensic analysis.  

---

## 🧠 **Part A — Acquiring Volatile Memory (RAM) Using FTK Imager**

### 🪜 **Step 1:**  
Right-click on **FTK Imager** and select **Run as Administrator**.  

![Step 1](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-08-30%20at%2000.00.09.jpeg)

---

### 🪜 **Step 2:**  
In the top menu bar, click **File → Capture Memory**.  

![Step 2](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.13.03.jpeg)

---

### 🪜 **Step 3:**  
In the dialog box:  
- Select a **destination path** and **file name** with `.mem` extension.  
- *(Optional)* You can also select **Pagefile** and **AD1 file** options.  

![Step 3](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.14.14.jpeg)

---

### 🪜 **Step 4:**  
Click **Capture Memory** to begin acquisition of memory.  

![Step 4](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.14.40.jpeg)

---

### 🪜 **Step 5:**  
A green **progress bar** shows the capture status.  
- The time depends on the system’s RAM size.  
- Once completed, the **captured memory file** will appear in the chosen destination folder.  

![Step 5](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/a68fa1804f0037d81615f5246641cf397bafce5e/images/WhatsApp%20Image%202025-09-01%20at%2015.03.33.jpeg)

---

## 💾 **Part B — Acquiring Non-Volatile Memory (Disk Image) Using FTK Imager**

### 🪜 **Step 1:**  
Click **File → Create Disk Image** from the menu bar.  

![Step 1](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.15.39.jpeg)

---

### 🪜 **Step 2:**  
Select the **source evidence type**:  
- Physical Drive  
- Logical Drive  
- Image File  
- Contents of a Folder  

![Step 2](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.16.01.jpeg)

---

### 🪜 **Step 3:**  
Select the **drive** you want to image and click **Finish**.  

![Step 3](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.16.15.jpeg)

---

### 🪜 **Step 4:**  
In the **Create Image** dialog, click **Add** to define the image type.  

![Step 4](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.16.31.jpeg)

---

### 🪜 **Step 5:**  
Choose the **image type**:  
- Raw (dd)  
- SMART  
- E01 *(Recommended)*  
- AFF  

![Step 5](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.17.14.jpeg)

---

### 🪜 **Step 6:**  
Fill in **case information** such as:  
- Case Number  
- Evidence Number  
- Examiner Name  
- Description  
- Notes  

Then click **Next**.  

![Step 6](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.17.24.jpeg)

---

### 🪜 **Step 7:**  
Choose the **destination folder** and enter a **file name** for the image.  

![Step 7](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.17.38.jpeg)

---

### 🪜 **Step 8:**  
Set **compression**, **split size**, and click **Finish**.  
Then click **Start** to begin imaging.  

![Step 8](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/88dd3dcf55bf6caaf1833c97ad1758f771348668/images/WhatsApp%20Image%202025-09-01%20at%2012.18.06.jpeg)

---

FTK Imager will show progress and automatically **generate hash values** (MD5/SHA1).  
If the hash values **match**, it confirms the **forensic integrity** of the acquired image.  

---

## 🧾 **Result**
Using **FTK Imager**, both **volatile (RAM)** and **non-volatile (disk)** data were successfully acquired.  
The generated **hash values matched**, ensuring that the forensic image was **authentic and unaltered**.

---

## 🏁 **Conclusion**
**FTK Imager** is a vital tool in digital forensics for **evidence acquisition**.  
It enables investigators to:
- Capture **RAM data** and **disk images** safely  
- Verify data integrity using hash functions  
- Preserve original evidence for analysis and legal use  

Thus, FTK Imager ensures **accurate and reliable forensic evidence acquisition**.

---

✨ *Prepared by:* **Goru Naga Phaneendra Kumar Babu**  
🎓 *CSE – Cybersecurity | Kalasalingam University*  
🆔 *Register No.: 99230041067*
