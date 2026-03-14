
# Active Directory Simulation – naztechai

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **naztechai**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**Naztechai** is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8 Client PC (HR Department)
- 1 x Windows 8 Client PC (Digital-Marketing Department)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.4.1)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8)   PC2 (Win 8)
```

| Device        | IP Address      | Role                        |
|---------------|----------------|-----------------------------|
| Windows Server| 10.0.4.3  | AD Domain Controller (DC)   |
| Windows 8 PC  | 10.0.4.5 (DHCP)   | Client (HR)           |
| Windows 8 PC | 10.0.4.4 (DHCP) | Client (Digital-Marketing)              |

---

## Domain Configuration

- **Domain Name**: `Naztechai.net`
- **Server Name**: `naztechai`
- **Static IP**: `10.0.4.1`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
CyberTech.local
├── OU: Digital-Marketing Department
│   └── Users: Toni.DM
    

├── OU: HR Department
│   └── Users: Ken.HR
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `DisablePoweroffRestartoptions`
- **Linked to**: OU: HR Department
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `System` > `Removable Storage Access`
  - Set **"Remove and prevent all access to shutdown, restart and hibernate commands"** to **Enabled**

Result: Command disabled for all users in the **HR OU**.

---

## Screenshots

- [AD Domain Structure](https://github.com/chinazamathiasokeke/Active-Directory-Simulation-naztechai.net/blob/main/screenshots/OUS-group-and-user.png)
- [GPO Editor Screenshot](https://github.com/chinazamathiasokeke/Active-Directory-Simulation-naztechai.net/blob/main/screenshots/group-poilcy-management.png)
- [PC joined to domain](https://github.com/chinazamathiasokeke/Active-Directory-Simulation-naztechai.net/blob/main/screenshots/windows-machine-connection.png)
- [Result of denied command to shutdown, restart access](https://github.com/chinazamathiasokeke/Active-Directory-Simulation-naztechai.net/blob/main/screenshots/Access-to-shutdown-denied.png)
- [Control Panael Access Denied](https://github.com/chinazamathiasokeke/Active-Directory-Simulation-naztechai.net/blob/main/screenshots/control-panal-disable.png)
- [Access To CommandPrompt Denied](https://github.com/chinazamathiasokeke/Active-Directory-Simulation-naztechai.net/blob/main/screenshots/access-to-CommandPrompt-denied.jpeg)
---

## Key Takeaways

- Gained practical experience with Windows Server roles and domain setup
- Implemented centralized access control using Group Policy
- Learned how to structure users and departments with OUs
- Applied IAM concepts in a real-world simulated environment

---

## Author

**CHINAZA M. OKEKE**  
Cybersecurity Analyst  
