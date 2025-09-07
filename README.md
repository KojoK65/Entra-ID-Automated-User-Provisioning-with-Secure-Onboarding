# 👥 Entra ID: Automated User Provisioning with Secure Onboarding

## 🎯 Project Objective  
This project demonstrates how to automate the creation of users in Microsoft Entra ID using Microsoft Graph and Azure Cloud Shell. The goal was to simulate enterprise-level user onboarding at scale, with users dynamically assigned to department-based security groups for better identity organization and access control.

---

## 🛠️ What I Did

### 1. Connected to Microsoft Graph in Cloud Shell  
- Opened **Azure Cloud Shell** and selected the PowerShell environment  
- Installed and imported the **Microsoft Graph SDK**  
- Signed into Graph with the required permissions to manage users and directory data  
- Verified the session was authenticated and ready to interact with Entra ID  

**✅ Successfully connected to Microsoft Graph**
<br>
<img width="70%" src="https://github.com/user-attachments/assets/494b2b09-5be1-4bbc-be72-7436195992c0" />

---

### 2. Generated a List of Users  
- Created a script that generated 500 users with randomized names and departments  
- Each user was given key attributes such as:
  - `UserPrincipalName`
  - `DisplayName`
  - `MailNickname`
  - `Department`  
- Exported all user data into a CSV file named `lab-users.csv` for bulk import

**📄 CSV file with generated user data**
<br>
<img width="70%" src="https://github.com/user-attachments/assets/14960fe7-730b-45c2-9be4-b260df2b6d41" />

---

### 3. Bulk Created Users in Entra ID  
- Used Microsoft Graph to loop through the CSV and create each user account  
- Set a strong initial password for all users and enforced password change on first sign-in  
- Captured and logged creation results for verification  
- All 500 users were successfully created without errors

**📈 Output showing successful creation of 500 users**
<br>
<img width="70%" src="https://github.com/user-attachments/assets/b3b8748a-c25e-49ed-8460-fe1ce4a6e2a3" />

---

### 4. Verified Users in Entra Admin Center  
- Logged into [entra.microsoft.com](https://entra.microsoft.com)  
- Went to **Users > All Users**  
- Verified the new accounts by filtering for:
  - `MailNickname` starting with `lab-`
  - Specific departments like Sales, HR, IT, etc.  
- Opened individual profiles to confirm correct department and display name values

**✅ Verified newly created users in Entra Admin Center**
<br>
<img width="70%" src="https://github.com/user-attachments/assets/9bf702b1-9101-4a4c-af38-e72cbe6025ee" />

**👤 User profile view with department**
<br>
<img width="70%" src="https://github.com/user-attachments/assets/2893a057-47ad-4815-9ca1-ebab69dba7c1" />

---

### 5. Created Dynamic Security Groups by Department  
- In Entra ID, created dynamic security groups for each department  
- Used rules like `(user.department -eq "Sales")` to auto-populate groups  
- Confirmed that users were automatically added to their respective groups based on department field  
- This step supports policy-based access management in future scenarios

**🧩 List of dynamic security groups by department**
<br>
<img width="70%" src="https://github.com/user-attachments/assets/f0eb41c2-235f-48c7-9120-a1d607a612bd" />

**👥 Members of the Finance department group**
<br>
<img width="70%" src="https://github.com/user-attachments/assets/825a90aa-02a5-4b0d-97d6-8542579eae18" />

---

## 📈 Skills Demonstrated  
- 🔄 **Identity lifecycle automation** using Microsoft Graph API  
- 👤 **User provisioning at scale** with CSV-based imports  
- 🛡️ **Role-based access control** using dynamic group assignment  
- ☁️ **Cloud-based identity management** with Microsoft Entra ID  

---
