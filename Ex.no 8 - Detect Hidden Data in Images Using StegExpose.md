


# 🧩 Ex.No.8 — Detect Hidden Data in Images Using StegExpose

---

### 🏫 **College:** Kalasalingam University  
### 👨‍🎓 **Name:** Goru Naga Phaneendra Kumar Babu  
### 🧾 **Register No:** 99230041067  
### 💻 **Branch:** CSE – Cybersecurity  

---

## 🎯 **Aim**
To **detect hidden (steganographic) data** in image files using the **StegExpose** tool and analyze its **detection accuracy**.

---

## 🎓 **Objectives**
1. Understand the concept of **Steganography** and **Steganalysis**.  
2. Learn how to use **StegExpose** for hidden data detection.  
3. Evaluate the detection accuracy using **different image datasets**.

---

## 🧠 **Theory**

### 🔹 Steganography  
The art of **hiding secret data** within non-secret media files such as **images, audio, or videos** without visibly altering them.

### 🔹 Steganalysis  
The process of **detecting and analyzing** such hidden information to determine if a file contains concealed data.

---

### ⚙️ About **StegExpose**
**StegExpose** is an **open-source steganalysis tool** designed to detect **hidden messages in images**.  
It combines multiple statistical detection techniques to identify irregularities caused by steganographic embedding.

#### 🔍 Detection Techniques Used:
| Technique | Description |
|------------|-------------|
| **Sample Pair Analysis (SPA)** | Detects hidden data based on pixel pair statistics. |
| **RS Analysis** | Analyzes the correlation between pixel groups. |
| **Chi-Square Attack** | Examines frequency anomalies in pixel values. |
| **Primary Sets** | Identifies embedding noise through statistical distribution. |

---

## 🧰 **Requirements**

| Component | Details |
|------------|----------|
| **Operating System** | Windows / Linux |
| **Software Required** | Java (JDK 8 or above) |
| **Tool** | StegExpose.jar |
| **Input Files** | Normal & Steganographically modified images (`.jpg`, `.png`) |

---

## ⚙️ **Algorithm / Procedure**

### 🪜 Step 1: Download and Setup
- Download **StegExpose.jar** from GitHub.  
- Ensure **Java JDK / JRE** is properly installed on your system.

> 📸 Example Setup Screenshot  
> <img width="800" alt="image" src="https://github.com/user-attachments/assets/8f6f5aa9-c907-4868-b9b8-3f249939fc0e" />

---

### 🪜 Step 2: Prepare Image Files
Prepare two categories of image samples:
1. 🖼️ **Original Images** — no hidden data.  
2. 🕵️ **Stego Images** — data embedded using tools like:
   - [OpenStego](https://www.openstego.com)
   - [SilentEye](https://sourceforge.net/projects/silenteye/)

---

### 🪜 Step 3: Run StegExpose
1. Open **Command Prompt / Terminal**.  
2. Navigate to the folder containing `StegExpose.jar` and images.  
3. Run the following command:

   ```bash
   java -jar StegExpose.jar <image_folder_path> -t 0.2 -a
````

**Parameters:**

| Parameter             | Meaning                            |
| --------------------- | ---------------------------------- |
| `<image_folder_path>` | Folder path containing test images |
| `-t 0.2`              | Threshold value (default = 0.2)    |
| `-a`                  | Analyze all images automatically   |

---

### 🪜 Step 4: Observe the Output

After execution, StegExpose generates a report:

* 📁 **Output File:** `StegExposeResults.csv`
* 📊 **Contents Include:**

  * File Name
  * Suspiciousness Score
  * Classification (Clean / Stego)

---

### 🪜 Step 5: Analyze and Interpret Results

| Suspicion Score             | Classification |
| --------------------------- | -------------- |
| **≤ Threshold (e.g., 0.2)** | 🟢 Clean Image |
| **> Threshold (e.g., 0.2)** | 🔴 Stego Image |

> 📈 Tip: You can adjust the threshold (`-t`) to balance **false positives** and **false negatives**.

---

## 💻 **Sample Command**

```bash
java -jar StegExpose.jar C:\Images -t 0.3 -a
```

📝 This command scans all images in `C:\Images` with a **threshold of 0.3** and performs a full automatic analysis.

---

## 📊 **Result**

After running the analysis:

* The **CSV report** provides each file’s **suspicion score**.
* Images with high scores are likely **steganographic**.

| File Name  | Suspicion Score | Classification |
| ---------- | --------------- | -------------- |
| image1.jpg | 0.12            | Clean          |
| image2.png | 0.35            | Stego          |
| image3.jpg | 0.28            | Stego          |

---

## 🧾 **Conclusion**

Using **StegExpose**, hidden data in images can be effectively detected using multiple steganalysis algorithms.
The tool provides a **quantitative score** that helps in differentiating between **clean and modified** images, making it valuable for **digital forensics investigations**.

---

> 💡 **Note:** StegExpose works best on **lossless formats** (like PNG) and **medium-resolution images**. Detection accuracy may vary depending on embedding technique and image quality.

---

### 🌐 **References**

* [StegExpose GitHub Repository](https://github.com/b3dk7/StegExpose)
* [OpenStego Official Site](https://www.openstego.com)
* [SilentEye Steganography Tool](https://sourceforge.net/projects/silenteye/)

---

✨ *End of Experiment — Ex.No.8: Detect Hidden Data in Images Using StegExpose* ✨

```

---

Would you like me to make a **dark-mode themed version** of this Markdown (with embedded CSS for GitHub Pages or PDF export)?  
It’ll make your lab record look **futuristic and professional** — perfect for cybersecurity documentation.
```


Sure — here’s your completed **Markdown lab record** with your personal details and clean visual formatting.
Copy it into a `.md` file or directly upload to GitHub for a polished look.

````markdown
# 🧩 Ex.No.8 — Detect Hidden Data in Images Using StegExpose

---

### 🏫 **College:** Kalasalingam University  
### 👨‍🎓 **Name:** Goru Naga Phaneendra Kumar Babu  
### 🧾 **Register No:** 99230041067  
### 💻 **Branch:** CSE – Cybersecurity  

---

## 🎯 **Aim**
To **detect hidden (steganographic) data** in image files using the **StegExpose** tool and analyze its **detection accuracy**.

---

## 🎓 **Objectives**
1. Understand the concept of **Steganography** and **Steganalysis**.  
2. Learn how to use **StegExpose** for hidden data detection.  
3. Evaluate detection accuracy using **different image datasets**.

---

## 🧠 **Theory**

### 🔹 Steganography  
The art of **hiding secret data** within non-secret media files such as **images, audio, or videos** without visibly altering them.

### 🔹 Steganalysis  
The process of **detecting and analyzing** such hidden information to determine if a file contains concealed data.

---

### ⚙️ About **StegExpose**
**StegExpose** is an **open-source steganalysis tool** designed to detect **hidden messages in images**.  
It combines multiple statistical detection techniques to identify irregularities caused by steganographic embedding.

#### 🔍 Detection Techniques Used
| Technique | Description |
|------------|-------------|
| **Sample Pair Analysis (SPA)** | Detects hidden data based on pixel pair statistics. |
| **RS Analysis** | Analyzes correlation between pixel groups. |
| **Chi-Square Attack** | Examines frequency anomalies in pixel values. |
| **Primary Sets** | Identifies embedding noise through statistical distribution. |

---

## 🧰 **Requirements**

| Component | Details |
|------------|----------|
| **Operating System** | Windows / Linux |
| **Software Required** | Java (JDK 8 or above) |
| **Tool** | StegExpose.jar |
| **Input Files** | Normal & Steganographically modified images (`.jpg`, `.png`) |

---

## ⚙️ **Algorithm / Procedure**

### 🪜 Step 1 – Download and Setup
- Download **StegExpose.jar** from GitHub.  
- Ensure **Java JDK / JRE** is installed.  

> 📸 Example Setup Screenshot  
> <img width="800" alt="image" src="https://github.com/user-attachments/assets/8f6f5aa9-c907-4868-b9b8-3f249939fc0e" />

---

### 🪜 Step 2 – Prepare Image Files
Prepare two categories of image samples:
1. 🖼️ **Original Images** — no hidden data  
2. 🕵️ **Stego Images** — data embedded using tools such as  
   - [OpenStego](https://www.openstego.com)  
   - [SilentEye](https://sourceforge.net/projects/silenteye/)

---

### 🪜 Step 3 – Run StegExpose
1. Open **Command Prompt / Terminal**.  
2. Navigate to the folder containing `StegExpose.jar` and your images.  
3. Run:

   ```bash
   java -jar StegExpose.jar <image_folder_path> -t 0.2 -a
````

| Parameter             | Meaning                       |
| --------------------- | ----------------------------- |
| `<image_folder_path>` | Folder path containing images |
| `-t 0.2`              | Threshold value (default 0.2) |
| `-a`                  | Analyze all images            |

---

### 🪜 Step 4 – Observe the Output

After execution, StegExpose generates
📁 **Output File:** `StegExposeResults.csv`

**Report Columns:**

* File Name
* Suspiciousness Score
* Classification (Clean / Stego)

---

### 🪜 Step 5 – Interpret the Results

| Suspicion Score       | Classification |
| --------------------- | -------------- |
| **≤ Threshold (0.2)** | 🟢 Clean Image |
| **> Threshold (0.2)** | 🔴 Stego Image |

> 💡 Adjust the threshold (`-t`) to reduce false positives or negatives.

---

## 💻 **Sample Command**

```bash
java -jar StegExpose.jar C:\Images -t 0.3 -a
```

📝 Scans all images in `C:\Images` with a threshold of 0.3 and performs full analysis.

---

## 📊 **Result**

| File Name  | Suspicion Score | Classification |
| ---------- | --------------- | -------------- |
| image1.jpg | 0.12            | Clean          |
| image2.png | 0.35            | Stego          |
| image3.jpg | 0.28            | Stego          |

---

## 🧾 **Conclusion**

Using **StegExpose**, hidden data in images can be effectively detected using multiple steganalysis algorithms.
The tool provides a **quantitative score** that helps differentiate between **clean** and **modified** images — valuable in **digital forensics investigations**.

---

> ⚠️ **Note:** StegExpose performs best on **lossless formats** (e.g., PNG). Detection accuracy depends on embedding technique and image quality.

---

### 🌐 **References**

* [StegExpose GitHub Repository](https://github.com/b3dk7/StegExpose)
* [OpenStego Official Site](https://www.openstego.com)
* [SilentEye Tool](https://sourceforge.net/projects/silenteye/)

---

]
