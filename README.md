# 🖥️ Windows 11 Hardening Lab

My focus was endpoint hardening. I had only read about it, so I decided to put it into practice. This write-up shows how I secured a Windows 11 VM using Group Policy, Windows Defender, BitLocker, and other built-in security features. I approached this as a novice. The goal was to apply **endpoint security best practices** and showcase what I learned from articles, online materials, and blogs in my cybersecurity portfolio.

---

## 🛡️ What is Hardening?

**Hardening** is the process of securing a system by reducing its attack surface. It involves setting security configurations, disabling unnecessary features, applying updates, and adding protective controls.


**Purpose & Importance:**  
- Reduces vulnerabilities that attackers can exploit  
- Strengthens defenses against malware, ransomware, and unauthorized access
- Ensures compliance with security standards and best practices 
- Protects sensitive data from theft or accidental exposure

Think of endpoint hardening like securing a newly purchased house.
- You close and lock all the doors and windows → (disable unnecessary ports and services).
- You replace the old locks with stronger ones → (set strong password and account lockout policies).
- You install cameras and alarms → (enable logging and monitoring with tools like Sysmon/Windows Defender).
- You set up motion-sensor lights around the house → (firewall blocking inbound traffic by default).
- You install a safe to protect valuables → (enable BitLocker encryption for sensitive data).

The goal is simply to reduces the attack surface by securing the  system (less ways for attackers to break in).

---

## 📚 Table of Contents
- [🔑 Step 1: Account Policies](#-step-1-account-policies)  
- [🔄 Step 2: Windows Updates](#-step-2-windows-updates)  
- [🛡 Step 3: Windows Defender Antivirus](#-step-3-windows-defender-antivirus)  
- [🌐 Step 4: Windows Firewall](#-step-4-windows-firewall)  
- [📦 Step 5: Application & Feature Control](#-step-5-application--feature-control)  
- [🔐 Step 6: Disk Encryption](#-step-6-disk-encryption)  
- [📊 Screenshots](#-screenshots)  

---

## 🔑 Step 1: Account Policies

Type '**Group Policy**' in Windows search bar, and select '**Edit Group Policy**' or press '**Win+R**', type '**gpedit.msc**'.

**Path:**  
`Computer Configuration → Windows Settings → Security Settings → Account Policies → Password Policy`

- Minimum Password Length = **12 characters**  
- Passwords must meet **complexity requirements**  

**Path:**  
`Computer Configuration → Windows Settings → Security Settings → Account Policies → Account Lockout Policy`

- Account lockout threshold = **5 invalid attempts**  
- Account lockout duration = **30 minutes**  

✅ **Why?**  
Prevents brute-force attacks and protects accounts from repeated login attempts.

---

## 🔄 Step 2: Windows Updates

- Turned on **Automatic Updates**  

✅ **Why?**  
Unpatched systems are one of the biggest attack vectors. Automatic updates ensure vulnerabilities are quickly patched.

---

## 🛡 Step 3: Windows Defender Antivirus

- Enabled **Real-time protection**  
- Enabled **Cloud-delivered protection**  
- Enabled **Tamper protection**  

✅ **Why?**  
Ensures malware cannot disable antivirus or bypass protections.

---

## 🌐 Step 4: Windows Firewall

**Path:**  
`Computer Configuration → Windows Settings → Security Settings → Windows Firewall with Advanced Security`

- Verified **Domain, Private, and Public profiles = ON**  
- Configured to **block inbound connections by default**  

✅ **Why?**  
Blocks unauthorized access and prevents malware from exposing services to attackers.

---

## 📦 Step 5: Application & Feature Control

- Enabled **SmartScreen** (App & Browser Control → Reputation-based protection)  
- Removed unnecessary **bloatware apps**  

✅ **Why?**  
Reduces the attack surface and prevents malicious applications from executing.

---

## 🔐 Step 6: Disk Encryption

- Enabled **BitLocker** for full disk encryption  

✅ **Why?**  
Protects sensitive data at rest. If the machine is stolen, attackers cannot read the disk without the recovery key.

---

## 🖼 Screenshots

<details close>
<summary>Click to View</summary>

<p align="center">
  <img src="https://github.com/user-attachments/assets/c72bd134-6322-47dc-a8af-1bfe14813907" width="80%" alt="Screenshot 1" /> 
  <img src="https://github.com/user-attachments/assets/673c33a0-a61b-495d-b07d-ee107d6d3650" width="80%" alt="Screenshot 2" />
  <img src="https://github.com/user-attachments/assets/7e70d90d-fba8-436a-874f-3b7bb5ab0472" width="80%" alt="Screenshot 3" />
  <img src="https://github.com/user-attachments/assets/3bac75c5-c371-4d62-85c5-5c25b478a357" width="80%" alt="Screenshot 4" />
  <img src="https://github.com/user-attachments/assets/5629fd4a-8210-4061-b2bb-852c3259547c" width="80%" alt="Screenshot 5" />
  <img src="https://github.com/user-attachments/assets/ebed387e-a6cd-4556-806e-a7c5895eeca3" width="80%" alt="Screenshot 6" />
  <img src="https://github.com/user-attachments/assets/8630c281-a090-443f-8f8d-31a896c88bab" width="80%" alt="Screenshot 7" />
</p>

</details>

---

🔗 This project is part of my **learning path toward becoming a SOC Analyst (Blue Team).**
