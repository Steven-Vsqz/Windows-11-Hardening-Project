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

In short, hardening turns a standard system into a **resilient and secure endpoint**.  

---

## 📚 Table of Contents
- [🔑 Step 1: Account Policies](#-step-1-account-policies)  
- [🔄 Step 2: Windows Updates](#-step-2-windows-updates)  
- [🛡 Step 3: Windows Defender Antivirus](#-step-3-windows-defender-antivirus)  
- [🌐 Step 4: Windows Firewall](#-step-4-windows-firewall)  
- [📦 Step 5: Application & Feature Control](#-step-5-application--feature-control)  
- [🔐 Step 6: Disk Encryption](#-step-6-disk-encryption)  
- [📊 Key Takeaways](#-key-takeaways)  
- [🚀 Next Steps](#-next-steps)  

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

## 📊 Key Takeaways

- Applied **Group Policy** to enforce account & password policies  
- Enabled **Windows Defender Antivirus** for real-time protection  
- Hardened **Windows Firewall** to block inbound threats  
- Reduced attack surface with **SmartScreen + app control**  
- Secured sensitive data with **BitLocker encryption**  

---

## 🚀 Next Steps

- Deploy **Sysmon (Sysinternals)** for advanced logging  
- Practice **log analysis & detection engineering**  
- Document attacker simulations (e.g., **malicious PowerShell detection**)  

---

🔗 This project is part of my **learning path toward becoming a SOC Analyst (Blue Team).**
