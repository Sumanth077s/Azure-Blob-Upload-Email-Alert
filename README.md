# 📩 Azure Blob Upload Email Alert

## 📌 Overview
This project demonstrates a **no-code automation** using **Azure Logic Apps** and **Azure Blob Storage**.  
Whenever a file is uploaded to a Blob Storage container, the Logic App automatically triggers and sends an **email notification** with the file details.  

This solution removes the need for manual monitoring of cloud storage and ensures users are alerted in real-time.

---

## 🛠️ Architecture
1. **Azure Blob Storage** – Stores uploaded files.  
2. **Logic Apps** – Monitors the Blob container and triggers workflows.  
3. **Email Connector (Outlook/Gmail)** – Sends an alert email when a new file is detected.  

**Workflow:**  
`User uploads file → Logic App detects change → Email sent with file details`

---

## 🚀 Features
- No-code workflow automation.  
- Real-time email alerts on file uploads.  
- Dynamic email content (includes file name).  
- Easy to extend (Teams/Slack notifications, file logging, etc.).  

---

## 📂 Project Setup

### 1. Create a Storage Account
- Go to **Azure Portal → Storage accounts → + Create**.  
- Configure with standard settings and create a container named `uploads`.

### 2. Create a Logic App
- Search **Logic Apps → + Create**.  
- Choose **Consumption Plan**.  
- Open **Logic App Designer → Blank Logic App**.

### 3. Add Trigger
- Select **When a blob is added or modified (V2)**.  
- Connect to your storage account.  
- Container: `uploads`.

### 4. Add Action
- Choose **Outlook / Gmail → Send an Email (V2)**.  
- Configure:
  - **To**: your email  
  - **Subject**: `New file uploaded: @{triggerBody()?['Name']}`  
  - **Body**: `A new file has been uploaded: @{triggerBody()?['Name']}`  

### 5. Save & Test
- Upload a file (`test.txt`) into the `uploads` container.  
- Check your inbox → You’ll receive an instant alert.  

---

## 📸 Screenshots
- Storage account with `uploads` container.  
- Logic App workflow in Designer.  
- Example email received.  

---

## 📊 Future Enhancements
- Send alerts to **Microsoft Teams / Slack**.  
- Log file uploads into **Excel / SharePoint**.  
- Add approval workflows before processing files.  

---

## 🧰 Tools & Services Used
- **Azure Blob Storage**  
- **Azure Logic Apps**  
- **Outlook / Gmail Connector**  

---

## ✅ Outcome
Successfully built a **cloud-based automation** that monitors Blob Storage and sends **real-time email alerts** on file uploads — without writing any code.
