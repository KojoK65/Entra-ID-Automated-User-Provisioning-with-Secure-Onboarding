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

📸 *Screenshot showing successful connection to Microsoft Graph*

---

### 2. Generated a List of Users  
- Created a script that generated 500 users with randomized names and departments  
- Each user was given key attributes such as:
  - `UserPrincipalName`
  - `DisplayName`
  - `MailNickname`
  - `Department`  
- Exported all user data into a CSV file named `lab-users.csv` for bulk import

📸 *Screenshot showing the generated CSV file with user data*

---

### 3. Bulk Created Users in Entra ID  
- Used Microsoft Graph to loop through the CSV and create each user account  
- Set a strong initial password for all users and enforced password change on first sign-in  
- Captured and logged creation results for verification  
- All 500 users were successfully created without errors

📸 *Screenshot showing user creation output*  
📸 *Screenshot showing final confirmation message with user count*

---

### 4. Verified Users in Entra Admin Center  
- Logged into [entra.microsoft.com](https://entra.microsoft.com)  
- Went to **Users > All Users**  
- Verified the new accounts by filtering for:
  - `MailNickname` starting with `lab-`
  - Specific departments like Sales, HR, IT, etc.  
- Opened individual profiles to confirm correct department and display name values

📸 *Screenshot showing filtered list of new users*  
📸 *Screenshot showing user profile with department and UPN*

---

### 5. Created Dynamic Security Groups by Department  
- In Entra ID, created dynamic security groups for each department  
- Used rules like `(user.department -eq "Sales")` to auto-populate groups  
- Confirmed that users were automatically added to their respective groups based on department field  
- This step supports policy-based access management in future scenarios

📸 *Screenshot showing all dynamic security groups*  
📸 *Screenshot showing members of the Sales department group*

---

## 📈 Skills Demonstrated  
- 🔄 **Identity lifecycle automation** using Microsoft Graph API  
- 👤 **User provisioning at scale** with CSV-based imports  
- 🛡️ **Role-based access control** using dynamic group assignment  
- ☁️ **Cloud-based identity management** with Microsoft Entra ID  

---
