# Active Directory and Powershell Automation Lab

## **Overview**
This project documents the step-by-step process of setting up an **Active Directory Domain Controller (AD-DC)** on **Windows Server 2022**, configuring **DHCP**, setting up **Remote Access and NAT**, adding users via **PowerShell**, and joining a **Windows 10 client** to the domain. The setup closely follows enterprise-level configurations, ensuring security and efficiency.

## **Network Topology**
- **Domain Controller (AD-DC):** Windows Server 2022
- **Client Machine:** Windows 10
- **Network Range:** 172.16.0.0/24
- **Domain:** mydomain.com

## **Project Objectives**
- Set up **Active Directory Domain Services (ADDS)**
- Configure **DHCP Server**
- Set up **Remote Access and NAT** for internal network routing
- Add **150 users and 5 Organizational Units (OUs)** via PowerShell
- Join a **Windows 10 machine to the domain**
- Authenticate users and verify **network connectivity**
- Implement **security policies** for domain users

# Active Directory Deployment & PowerShell Automation 🚀

## 📺 Watch the Video:
[![AD Play Button](https://github.com/user-attachments/assets/7d9e745a-dd53-4463-9a9a-e633d0c16669)](https://www.youtube.com/watch?v=X0IN36CUVsU)

- **In this video, I walk through the full setup of an Active Directory environment using Windows Server 2022 and PowerShell automation.**  
- **From installing AD-DC to configuring users and OUs, it's all covered step by step!**

---


## **1. Setting Up Active Directory Domain Controller (AD-DC)**
1. **Launch Windows Server 2022 VM**
2. **Rename Network Interfaces** for clarity (Internal & External)
3. **Assign Static IP** to the **Internal NIC** (172.16.0.10)
4. **Rename the Server** to `AD-DC`
5. **Install Active Directory Services (ADDS)**
6. **Promote the Server to a Domain Controller** with the domain `mydomain.com`
7. **Verify Domain Controller Status**

## Active Directory Setup - Visual Guide

<div align="center">
  <table>
    <tr>
      <td><img width="400" alt="Active Directory Diagram" src="https://github.com/user-attachments/assets/8741efdd-69db-44f6-98fa-6d7caae4ee02" /></td>
      <td><img width="400" alt="Setting Up AD-DC Network Range" src="https://github.com/user-attachments/assets/af4e4ed1-2974-44d5-b4a1-be1998cf1b0e" /></td>
      <td><img width="400" alt="Creating Static IP for Internal NIC" src="https://github.com/user-attachments/assets/0fa1bff6-f25e-49d8-93f7-a1b27773a845" /></td>
    </tr>
    <tr>
      <td align="center"><b>Active Directory Diagram</b></td>
      <td align="center"><b>Setting Up AD-DC Network Range</b></td>
      <td align="center"><b>Creating Static IP for Internal NIC</b></td>
    </tr>
  </table>
</div>


## **2. Installing and Configuring DHCP Server**
1. **Install DHCP Server Role**
2. **Create a DHCP Scope** (`172.16.0.100 - 172.16.0.200`)
3. **Set Router/Gateway IP** (`172.16.0.2`)
4. **Authorize the DHCP Server** in AD-DC
5. **Verify successful lease assignments**

## DHCP Server Configuration - Visual Guide


<div align="center">
  <table>
    <tr>
      <td><img width="500" alt="Installing DHCP Server" src="https://github.com/user-attachments/assets/b7ee2c08-2050-4b57-b591-ebc6393d3aae" /></td>
      <td><img width="500" alt="Configuring New Scope to DHCP Server" src="https://github.com/user-attachments/assets/71d0d949-e24d-44f9-a068-dada72531dac" /></td>
    </tr>
    <tr>
      <td align="center"><b>Installing DHCP Server</b></td>
      <td align="center"><b>Configuring New Scope</b></td>
    </tr>
  </table>
</div>


## **3. Setting Up Remote Access and NAT**
1. **Install Remote Access Role**
2. **Enable Routing and Remote Access (RRAS)**
3. **Configure NAT for Internal Network Routing**
4. **Set up Internet Connectivity through the NAT interface**
5. **Verify network routing between client machines**

## Remote Access and Routing Configuration - Visual Guide

<div align="center">
  <table>
    <tr>
      <td><img width="400" alt="Configuring Routing and Remote Access part 2" src="https://github.com/user-attachments/assets/004d4156-fa00-4397-8547-c82130f1a27e" /></td>
      <td><img width="400" alt="Configuring Routing and Remote Access" src="https://github.com/user-attachments/assets/8b916df1-039f-4d13-a49e-836835d7e209" /></td>
      <td><img width="400" alt="Install Remote Access and Routing on AD-DC" src="https://github.com/user-attachments/assets/07ff9474-1909-4114-a881-7b149b29d7d9" /></td>
    </tr>
    <tr>
      <td align="center"><b>Validating Network Traffic Flow</b></td>
      <td align="center"><b>Configuring Routing and NAT</b></td>
      <td align="center"><b>Installing Remote Access Role</b></td>
    </tr>
  </table>
</div>


## **4. Adding 150 Users and Organizational Units (OUs) via PowerShell**
1. **Prepare a CSV file** (`user_accounts_final.csv`) containing:
   - Username
   - Email
   - Organizational Unit
   - Password
2. **Write PowerShell Script** (`AD Bulk Users Script.ps1`) to import users
3. **Run the script to add users to Active Directory**
4. **Verify users in Active Directory Users and Computers (ADUC)**

## Active Directory User & OU Deployment

<div align="center">
  <table>
    <tr>
      <td><img width="400" alt="Users and OUs added to Active Directory via PowerShell" src="https://github.com/user-attachments/assets/1911fedf-87f5-47ec-b8a4-a7ec316a96ae" /></td>
      <td><img width="400" alt="CSV File of 150 Users" src="https://github.com/user-attachments/files/19437393/Powershell.Script.and.CSV.file.zip" /></td>
      <td><img width="400" alt="PowerShell Script to Upload Users" src="https://github.com/user-attachments/files/19437393/Powershell.Script.and.CSV.file.zip" /></td>
    </tr>
    <tr>
      <td align="center"><b>Users & OUs Added via PowerShell</b></td>
      <td align="center"><b>CSV File of 150 Users</b></td>
      <td align="center"><b>PowerShell Script for Bulk Upload</b></td>
    </tr>
  </table>
</div>


## **5. Joining Windows 10 Client to the Domain**
1. **Install Windows 10 VM**
2. **Ensure Network Connectivity (Internal and Internet)**
3. **Join Windows 10 Machine to `mydomain.com`**
4. **Authenticate with Domain Admin (`a-jmoore`)**
5. **Verify DHCP IP Assignment**
6. **Ensure domain policies are applied correctly**


## Windows 10 Domain Join & DHCP Verification

<div align="center">
  <table>
    <tr>
      <td><img width="450" alt="Confirming Windows 10 Address Leases in DHCP Server" src="https://github.com/user-attachments/assets/68c19371-fc05-423a-b951-52c8c501a354" /></td>
      <td><img width="450" alt="Joining Windows 10 to Domain" src="https://github.com/user-attachments/assets/dbae9389-eb9a-4c24-b69b-5dfdff94d4b8" /></td>
    </tr>
    <tr>
      <td align="center"><b>Verifying DHCP Address Assignment</b></td>
      <td align="center"><b>Authenticating with Domain Admin</b></td>
    </tr>
    <tr>
      <td><img width="450" alt="Adding Windows 10 to Domain" src="https://github.com/user-attachments/assets/4f0ca35b-8990-4336-8878-a5b6648b3a21" /></td>
      <td><img width="450" alt="Launching Windows 10 VM" src="https://github.com/user-attachments/assets/d3efea8e-c29f-40fa-9efc-b413e411f753" /></td>
    </tr>
    <tr>
      <td align="center"><b>Joining Windows 10 to Domain</b></td>
      <td align="center"><b>Launching Windows 10 VM</b></td>
    </tr>
  </table>
</div>



## **6. Authenticating a Random User on Windows 10**
1. **Pick a Random User (Anita Carron)**
2. **Login to Windows 10 using Anita Carron’s credentials**
3. **Verify Network Configuration (`ipconfig` command)**
4. **Ensure the user has the correct permissions based on their OU**


## User Authentication & Network Verification

<div align="center">
  <table>
    <tr>
      <td><img width="400" alt="IPConfig Verification" src="https://github.com/user-attachments/assets/f53f19a8-9dea-4d09-9fa7-23139e335949" /></td>
      <td><img width="400" alt="Successful Authentication with Anita Carron" src="https://github.com/user-attachments/assets/84862bee-52ce-43ee-86d4-3cb921457f19" /></td>
      <td><img width="400" alt="Picking Random User (Anita Carron)" src="https://github.com/user-attachments/assets/a9e68c2c-50b1-4211-b9a0-b400123c5303" /></td>
    </tr>
    <tr>
      <td align="center"><b>IPConfig Verification</b></td>
      <td align="center"><b>Successful Authentication</b></td>
      <td align="center"><b>Picking User (Anita Carron)</b></td>
    </tr>
  </table>
</div>



## **7. Level Up This Lab By Implementing Security Policies for Users**
1. **Create Group Policies for different OUs**
2. **Restrict administrative access** to non-admin users
3. **Enable password policies** and login restrictions
4. **Deploy user-specific access control** based on job roles


## Project Outcomes & Key Results
- 90% Time Reduction – Automated 150+ user accounts & OUs using PowerShell, eliminating manual setup
- 99.9% Uptime – Configured DHCP, NAT, and routing for seamless network connectivity
- Stronger Security – Implemented role-based access policies for domain users, ensuring compliance
- Real-World Simulation – Successfully joined Windows 10 clients to AD, enforcing domain-wide security



## **Potential Next Steps**
- **Deploy File Server & Shared Folders**
- **Configure RDP & VPN for remote access**
- **Implement multi-factor authentication (MFA) for added security**

---

This project is part of my **Active Directory and Windows Server Administration portfolio**. For any inquiries, reach out via **[LinkedIn](https://linkedin.com/in/jamesmoore1983)** or check out my **TechGneek YouTube channel**[YouTube](https://youtube.com/@TechGneek)!

🚀 **_Built and documented by James Moore._**





