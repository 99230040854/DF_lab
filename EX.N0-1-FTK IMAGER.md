# Ex.No.1    FTK Imager: A Forensic Imaging Tool Overview

## Acquiring Volatile Memory (RAM) Using FTK Imager
<br>


### Steps to Capture RAM Using FTK Imager
<br>

### 1. Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the FTK Imager icon and select **Run as administrator**.
<br>
<br>

![WhatsApp Image 2025-08-29 at 21 53 56_496e4388](https://github.com/user-attachments/assets/e316ad41-2e9e-4705-8eef-d96f8a429cd4)

 
<br>
<br>

### 2. Initiate Memory Capture
- In the top menu bar, click **File → Capture Memory...** from the dropdown list.
  <br>
<br>

  ![WhatsApp Image 2025-08-31 at 16 11 06_166286b6](https://github.com/user-attachments/assets/fcf594a2-b415-4ff2-a144-e7c2d2316f61)


<br>
<br>

### 3. Configure Destination
A dialog box will appear where you configure where and how the memory will be saved.

- **Destination Path:**  
  Click **Browse** to select a folder on an **external drive** (not the system drive).  

- **Destination Filename:**  
  You can keep the default `memdump.mem` or assign a more descriptive name.

- **Optional: Include pagefile.sys**  
  Check this box to capture `pagefile.sys`, which is virtual memory stored on the disk.  
  > Note: This may increase capture size and duration, but can contain valuable artifacts.

- **Optional: Create AD1 file**  
  Saves the memory dump in an AccessData-specific container file.  
  > Generally not necessary if using tools like **Volatility** for analysis.



<br>
<br>

<img width="1920" height="1080" alt="Screenshot (58)" src="https://github.com/user-attachments/assets/753b6aa3-c0f5-4906-bc47-87999362bf91" />



 
<br>
<br>

### 4. Start Capture
- Click the **Capture Memory** button to begin acquisition.
<br>
<br>


<img width="1920" height="1080" alt="Screenshot (59)" src="https://github.com/user-attachments/assets/04f5ddf9-a8a8-41ef-8094-a0895cf072f7" />


<br>
<br>

### 5. Wait for Completion
- A progress bar will indicate the capture status.  
- Capture time depends on the system’s RAM size.  
- Once finished, the memory dump file will be available in the destination folder.
---
<br>
<br>

## Acquiring Non-Volatile Memory (Disk Image) Using FTK Imager


### 1. Start the Process
- In FTK Imager, go to the top menu bar: **File → Create Disk Image...**.

<br>
<br>

![WhatsApp Image 2025-08-31 at 19 00 39_c2d4732d](https://github.com/user-attachments/assets/84d50997-96e9-45ee-ba32-afd8ad5a8857)



<br>
<br>

### 2. Select Source Evidence Type
A window will appear asking you to choose the source type:

- **Physical Drive:** Images the entire disk, including all partitions, unallocated space, and the Master Boot Record (MBR).  
- **Logical Drive:** Images a specific partition (e.g., C: drive).  
- **Image File:** Converts or copies an existing image file.  
- **Contents of a Folder:** Creates an image of a specific folder only.  

> **Tip:** For full forensic imaging, select **Physical Drive**.
<br>
<br>
<p align="center">

![WhatsApp Image 2025-08-31 at 19 01 18_0a8226d1](https://github.com/user-attachments/assets/a4eaab1a-78b1-4a67-b91f-b3131ecd37fb)

<br>
<br>

### 3. Select the Source Drive
- From the dropdown, choose the physical drive to image (connected via **write-blocker**).  
- Click **Finish**.
 <br>
<br>
<p align="center">

  ![WhatsApp Image 2025-08-31 at 19 02 07_438a7c8d](https://github.com/user-attachments/assets/c4b805d4-b358-4918-b8cb-90e0d5138be3)

</p>
<br>
<br>

### 4. Configure the Image Destination
- Click **Add...** in the "Create Image" window to define the image **format** and **destination**.
  <br>
<br>
<p align="center">
![WhatsApp Image 2025-08-31 at 19 02 32_1573ce9b](https://github.com/user-attachments/assets/f7cfc9e5-a4ca-40fd-b6ae-aaa6b373e96d)


<br>

#### Options:

- **Image Type:**  
  - **E01 (EnCase Format):** Recommended; includes compression, metadata, and error-checking.  
  - **Raw (DD):** Bit-for-bit copy with no extra features.
<br>
<br>
<p align="center">

  ![WhatsApp Image 2025-08-31 at 19 03 46_c2afd856](https://github.com/user-attachments/assets/9f6dd5ac-0d5b-4e04-af5e-20b0bdd9c205)

</p>
<br>
<br>

- **Fill in Evidence Item Information:**  
  - Enter case details, examiner name, and description.  
  - This information is stored in the image metadata (important for documentation).
 <p align="center">

  <img width="1920" height="1080" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/ed18f099-42ca-4882-ba8f-81c96483758b" />



</p>
<br>
<br>

- **Choose Destination Folder:**  
  - Must be a different drive from the source.  
  - Name the image file (e.g., `Case001_SuspectHDD`).  

- **Image Fragment Size:**  
  - Set a value to split the image into multiple parts.  
  - Set to `0` for a single image file.
  <br>
  <br>
  
<p align="center">

<img width="1920" height="1080" alt="Screenshot (61)" src="https://github.com/user-attachments/assets/f2045e0a-46e2-49ba-bd05-fba7888cf668" />


<br>
<br>


### 5. Start the Imaging Process
- Click **Finish** to return to the "Create Image" screen.  
- **Check "Verify images after they are created"** to calculate hash values and ensure integrity.  
- Click **Start**.
  <br>
  <br>
  <p align="center">
 
 <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/336cbde7-3182-44bd-b438-7f18fcc2494d" />


 <img width="1365" height="767" alt="Image" src="https://github.com/user-attachments/assets/a23f3fd9-fd2f-48ea-ad09-5ea6ce7684ff" />

</p>
<br>
<br>

### 6. Completion and Hash Verification
- The imaging process may take time depending on the drive size.  
- After completion, FTK Imager verifies the hashes automatically.  
- A final window shows **MD5** and **SHA1** hashes for both the source drive and image.  
- Matching hashes confirm the forensic image’s integrity.

---
## Notes

- Always use a **write-blocker** to prevent modifications to the evidence.  
- **Hash verification** is critical to maintain a chain of custody and admissibility in court.  
- **Image Fragmentation** is useful for large drives or storage limitations.
---

## References

- [FTK Imager Official Website](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- FTK Imager Documentation
