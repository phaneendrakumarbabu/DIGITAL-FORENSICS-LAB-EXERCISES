 `Ex_No_6_The_Sleuth_Kit_TSK.md` — 

---

```markdown
# Ex.No.6 — The Sleuth Kit (TSK)

---

## Aim
To use **The Sleuth Kit (TSK)**, a collection of command-line tools, to analyze a disk image (`4Dell Latitude CPi.E01`), examine its file system, and recover digital evidence.

---

## 🛠️ Prerequisites & Installation

1. **Sleuth Kit Tools:**  
   Download the Windows version of Sleuth Kit (`sleuthkit-4.14.0-win32.zip`) and extract it to a known location, e.g.:
```

C:\Users\sleuthkit-4.14.0-win32

```

2. **Evidence Files:**  
Download the sample disk image files (`4Dell Latitude CPi.E01` and `4Dell Latitude CPi.E02`) from the Google Drive link provided in the lab manual.

3. **Case Folder:**  
Create a dedicated folder for your investigation, for example:
```

C:\Forensics_Lab

````
Place the evidence files inside this folder.

---

## Procedure

### Step 1: Open Command Prompt & Navigate
- Open the Command Prompt (`cmd.exe`) **as Administrator**.  
- Navigate to the `bin` directory inside your Sleuth Kit folder.  
This is where all the executable tools (`.exe`) are located.

```bash
C:\Windows\System32> cd C:\Users\sleuthkit-4.14.0-win32\bin
````

<p align="center">
<img width="534" height="79" alt="Screenshot 2025-10-25 084644" src="https://github.com/user-attachments/assets/587309bf-6160-46ee-b8d2-9ba54a988b9d" />
</p>

---

### Step 2: List Partitions (`mmls`)

* Use the `mmls` (list partitions) command to view the partition table of the disk image.
  This helps identify the **offset** (starting sector) of the partition to analyze.
* The path to the image file must be in quotes.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> mmls.exe "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```

📁 **Tip:**
The output shows the NTFS/exFAT (0x07) partition (Slot 002) starts at sector **63**.
This offset will be used in subsequent commands.

<p align="center">
<img width="819" height="319" alt="Screenshot 2025-10-25 084720" src="https://github.com/user-attachments/assets/d954ec00-9ba4-4f0e-98ec-ff0b433588c8" />
</p>

---

### Step 3: Analyze File System (`fsstat`)

* Use the `fsstat` (file system statistics) command to get detailed information about the partition.
* Use the `-o 63` flag to specify the partition offset.
* The command displays the result on-screen.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> fsstat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```

<p align="center">
<img width="694" height="645" alt="Screenshot 2025-10-25 084902" src="https://github.com/user-attachments/assets/1567b244-f6b7-4663-846e-7c8914942ca7" />
</p>

---

### Step 4: List Files and Directories (`fls`)

* Use the `fls` (file list) command to recursively list all files and directories in the partition.
* Use the `-r` flag for recursion and redirect (`>`) the output to a text file for easier review.
* No terminal output will appear after execution.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> fls.exe -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\file_list.txt
```

📁 **Tip:**
You can open the `file_list.txt` file in your case folder to view the complete directory structure.

<p align="center">
<img width="1120" height="43" alt="image" src="https://github.com/user-attachments/assets/639f5181-39a9-4c35-855a-471b81146948" />
</p>

---

### Step 5: Analyze File Metadata (`istat`)

* Use the `istat` (inode statistics) command to display metadata about a specific file, such as MAC times (Modified, Accessed, Changed).
* From `file_list.txt`, identify an interesting file — here, `Mr. Evil.bmp`.
* Its inode number is `9871`.
* Redirect the output to a metadata report file.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> istat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\metadata_Mr_Evil.txt
```

<p align="center">
<img width="1886" height="338" alt="image" src="https://github.com/user-attachments/assets/726eb8d2-3ad3-4913-9631-7bb0deac00be" />
</p>

---

### Step 6: Recover a File (`icat`)

* Use the `icat` (inode cat) command to extract and recover a file using its inode number.
* Use inode `9871` and redirect the output to save it as a `.bmp` file.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> icat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\RECOVERED_Mr_Evil.bmp
```

<p align="center">
<img width="1363" height="362" alt="image" src="https://github.com/user-attachments/assets/8a302fb6-52f8-4987-b010-4490ddebb878" />
</p>

---

### Step 7: Create an Event Timeline (`mactime`)

* Generate a timeline of all file activity on the system.

#### (a) Generate a Body File

This file records MAC (Modified, Accessed, Changed) times for all files.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> fls.exe -m / -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\body.txt
```

#### (b) Generate the Timeline Report

Use the `mactime.pl` script to convert the body file into a readable chronological report.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> mactime.pl -b C:\Forensics_Lab\body.txt > C:\Forensics_Lab\timeline.txt
```

<p align="center">
<img width="1655" height="160" alt="image" src="https://github.com/user-attachments/assets/bd0a0b07-4c8f-47a0-8437-6179b96fba8e" />
</p>

---

## ✅ Result

By following these steps, we successfully used **The Sleuth Kit (TSK)** to analyze the `4Dell Latitude CPi.E01` disk image.
We were able to:

* List the partition table (`mmls`) and identify the correct partition offset (63).
* Analyze file system metadata using `fsstat`.
* List all files and directories, including deleted ones (`fls`).
* View metadata of a specific file (`istat` with inode 9871).
* Recover the file `Mr. Evil.bmp` using `icat`.
* Generate a full chronological timeline of system activity using `mactime`.

All evidence files and recovered data are now stored in the `C:\Forensics_Lab` folder, ready for further documentation and reporting.

---

## 🧠 Conclusion

The experiment demonstrates the use of **The Sleuth Kit (TSK)** for digital forensic analysis.
By using its command-line utilities, investigators can:

* Examine disk partitions and file systems,
* Recover deleted or hidden files, and
* Reconstruct timelines of file system activity.

Hence, TSK serves as a reliable open-source toolkit for forensic disk image analysis and evidence recovery.


