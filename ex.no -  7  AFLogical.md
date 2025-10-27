# 🧪 **Ex.No: 7 — Using AFLogical OSE to Extract Data from an Android Device**

---

## 🏛️ **Kalasalingam University**
### 🧩 *Department of Cybersecurity*

---

### 👨‍💻 **Experiment Details**

| **Field** | **Details** |
|------------|-------------|
| **Experiment No** | 7 |
| **Title** | Using AFLogical OSE to Extract Data from an Android Device |
| **Submitted By** | *Goru Naga Phaneendra Kumar Babu* |
| **Register No** | *99230041067* |
| **Department** | *Cybersecurity* |

---

## 🎯 **Aim**

To perform **logical data extraction** from an Android device using **AFLogical OSE (Open Source Edition)** and analyze the extracted data for forensic purposes.

---

## 📘 **Theory**

**AFLogical OSE (Open Source Edition)** is part of the **Open Source Android Forensics Project** designed for **logical acquisition** of data from Android devices.  

It helps investigators collect **non-destructive** evidence without rooting the device.  
The tool extracts important data such as:
- 📇 Contacts  
- 💬 SMS / MMS Messages  
- 📞 Call Logs  
- 🗓️ Calendar Entries  
- 🌐 Browser History  

This process ensures **data integrity** and is ideal for preliminary forensic investigations.

---

## ⚙️ **Requirements**

| **Hardware / Software** | **Description** |
|---------------------------|------------------|
| 🖥️ System | Windows / Linux |
| 📱 Device | Android phone with USB Debugging enabled |
| 🔌 Connection | USB Cable |
| 🧰 Tool | AFLogical OSE |

---

## 🧾 **Procedure**

1. **Download & Install AFLogical OSE** on your system.  
2. **Enable Developer Options** → Turn on **USB Debugging** on the Android device.  
3. **Connect the Device** to the system using a USB cable.  
4. **Launch AFLogical OSE** — it will automatically detect the connected device.  
5. **Grant Permissions** on the Android device when prompted.  
6. Select the data types to extract — *Contacts, Messages, Call Logs, etc.*  
7. The tool will perform the extraction and save results as `.csv` files.  
8. The extracted data will be stored at `/sdcard/forensics/`.  
9. Copy these files to your system for further forensic analysis.

---

## 🖼️ **Screenshots**

### 📸 Step 1 — Launching AFLogical OSE  
![Screenshot 1](https://github.com/user-attachments/assets/bf3d4690-98b2-4afc-9dcc-1b88deef2e71)

### 📸 Step 2 — Device Detection  
![Screenshot 2](https://github.com/user-attachments/assets/c16b02ed-1e48-4946-a562-043abb3e9e25)

### 📸 Step 3 — Data Extraction Process  
![Screenshot 3](https://github.com/user-attachments/assets/f84a2449-99e1-4a7f-8854-58f2964be372)

### 📸 Step 4 — Selecting Data Categories  
![Screenshot 4](https://github.com/user-attachments/assets/3bebf98b-8dab-4d04-ba44-1dc70d7d2d62)

### 📸 Step 5 — Extraction Completed  
![Screenshot 5](https://github.com/user-attachments/assets/b02f289c-3de4-42f5-90c1-518131a6e4f7)

### 📸 Step 6 — Output File Structure  
![Screenshot 6](https://github.com/user-attachments/assets/545baf69-e750-410a-b07a-657d60b91e97)

### 📸 Step 7 — Viewing Extracted Data  
![Screenshot 7](https://github.com/user-attachments/assets/22f021cb-f711-4268-88cb-eba0ed6c5684)

---

## 📈 **Result**

✅ Successfully extracted logical data (Contacts, Messages, Call Logs) from an Android device using **AFLogical OSE**.  
The extracted files were stored in `.csv` format for analysis.

---

## 🧩 **Advantages**

- No need for rooting the device.  
- Preserves original data integrity.  
- Simple and user-friendly interface.  
- Supports multiple data formats (Contacts, SMS, Call Logs).  

---

## 📚 **Conclusion**

AFLogical OSE is a reliable open-source tool for performing **logical data extraction** in Android forensic investigations.  
It helps retrieve vital information without tampering with the device, making it suitable for **preliminary forensic analysis** and **evidence collection**.

---

## 🧠 **Learning Outcome**

By performing this experiment, I learned:
- How to use AFLogical OSE for logical extraction.  
- How forensic tools extract and store mobile data securely.  
- The importance of data integrity in digital forensics.

---

✨ **Submitted By:**  
**Goru Naga Phaneendra Kumar Babu**  
**Reg No:** 99230041067  
**Department of Cybersecurity**  
**Kalasalingam University**


