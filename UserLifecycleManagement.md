# M365 User Lifecycle Management Project

## Project Overview
This project simulates a **real-world IT Support / System Administrator task**: managing user lifecycle in Microsoft 365.  
It includes creating users, assigning licenses, provisioning Teams and SharePoint, setting up task tracking, and enforcing security policies.

---

## Scenario
HR requested the following:  
1. Create a new employee: **Navya Sruthi**  
2. Remove a leaver from the organization  
3. Assign proper licenses and group membership  

Goal: Demonstrate **end-to-end onboarding and security compliance** in M365.

---

## Step 1: User Creation
- Log in to Microsoft 365 Admin Center: [https://admin.microsoft.com](https://admin.microsoft.com)  
- Navigate: **Users → Active Users → Add a user**  
- Fill details:
  - Name: Navya Sruthi  
  - Username: navya.sruthi@yourtenant.onmicrosoft.com  
  - Password: Auto-generate / Force password change  
- Assign **Microsoft 365 E5 license**  
- Add to **Sales Department** group  

**Screenshot placeholder:**  
`/screenshots/01_UserCreation.png`

---

## Step 2: Teams & SharePoint Provisioning
- Sales Department Team created automatically when group created in Teams  
- Channels created for structured collaboration:
  - General (default)  
  - Deals  
  - Reports  
  - Client Calls  
- SharePoint site linked automatically for document storage  

**Screenshot placeholder:**  
`/screenshots/02_TeamsSetup.png`  


---

## Step 3: Task Tracking
- Planner integration attempted, fallback used **Excel in Teams** for Sales Pipeline:  
  Columns: Customer Name | Deal Stage | Owner | Value | Close Date | Status  
- Tasks assigned to Navya or other team members for practice  

**Screenshot placeholder:**  
`/screenshots/04_ExcelTasks.png`

---

## Step 4: Security & Policies
### A) Conditional Access – MFA
- Applied MFA to Sales Department via Azure AD Conditional Access  
- Steps:
  1. Azure AD → Security → Conditional Access → + New Policy  
  2. Assign **Sales Department** group → Cloud apps: All  
  3. Grant → Require multi-factor authentication → Enable policy  

**Screenshot placeholder:**  
`/screenshots/05_MFASetup.png`  

### B) Mail Flow Rule – Block Credit Card Numbers
- Exchange Online mail flow rule created:
  - Condition: Email contains “Credit Card”  
  - Action: Block message and notify user  
- Test result: Normal emails delivered, sensitive info blocked  

**Screenshot placeholder:**  
 

### C) Teams Meeting Policy
- Disabled anonymous users in Sales Department Team meetings  

**Screenshot placeholder:**  
`/screenshots/07_TeamsMeetingPolicy.png`

---

## Step 5: Testing & Verification
- Verified user Navya can log in and access:
  - Outlook (with MFA)  
  - Teams channels and files  
  - SharePoint document library  
- Mail flow rule successfully blocked simulated credit card info  

**Screenshot placeholder:**  
`/screenshots/08_TestMFA.png`  
`/screenshots/09_TestMailFlow.png`

---

## Step 6: Deliverables
1. `/docs/UserLifecycleManagement.md` – this documentation  
2. `/scripts/CreateUsers.ps1` – PowerShell script for bulk user creation  
3. `/samples/userlist.csv` – sample CSV for bulk creation  
4. `/screenshots/` – visual evidence of all steps  

---

## Conclusion
This project demonstrates **hands-on M365 user lifecycle management**, **security enforcement**, and **team collaboration provisioning**.  
It is a practical example of what IT Support / System Admins do in real-world organizations.

