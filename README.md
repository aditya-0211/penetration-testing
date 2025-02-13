# Penetration Test Report: The Masked DJ  

## Project Overview  
RAS Security conducted a comprehensive **penetration test** of **The Masked DJ's** network and IT assets from **November 12, 2024, to December 7, 2024**. The goal was to identify **vulnerabilities** that could be exploited to gain unauthorized access and potentially **reveal the Masked DJ's real identity**.  

## Key Findings  
- **Vulnerable SMBv1 service** on BOOKINGS-PC (192.168.65.129) allowed initial access via **EternalBlue exploit (CVE-2017-0143)**  
- **Unsecured Active Directory backups** found on a network share, including the **sensitive ntds.dit file**  
- **Weak user credentials** and **poor password policies**  
- **Plaintext KeePass database password** stored on IT Admin's desktop  
- **AWS S3 bucket containing images** revealing the Masked DJ’s identity was accessible via exposed credentials  
- **Domain Controller vulnerable** to **pass-the-hash attacks**  

## Critical Vulnerabilities  
- **High:** SMBv1 vulnerability (**CVE-2017-0143**) on multiple systems  
- **High:** Unsecured storage of sensitive **Active Directory backups**  
- **High:** Weak password policies and **easily crackable credentials**  
- **Medium:** Plaintext storage of **sensitive passwords**  
- **Medium:** Exposed **AWS credentials** and S3 bucket misconfigurations  

## Exploitation Path  
1. **Gained initial access** to BOOKINGS-PC via **EternalBlue exploit**  
2. **Extracted and cracked password hashes** from **unsecured AD backups**  
3. Used cracked credentials to **access IT Admin’s desktop via RDP**  
4. Found **plaintext KeePass password**, revealing **webserver credentials**  
5. **Accessed Linux webserver** and retrieved **AWS S3 bucket contents**  
6. Discovered images **revealing Masked DJ’s identity as "Professor Shivers"**  
7. Demonstrated potential for **full domain compromise** via **pass-the-hash attack on the Domain Controller**  

## Key Recommendations  
- **Upgrade operating systems** and **disable SMBv1 protocol**  
- Implement **proper encryption and access controls** for sensitive backups  
- Enforce **strong password policies** and modern authentication protocols  
- **Avoid storing plaintext credentials** on systems  
- Implement **network segmentation** and **firewall rules**  
- Secure AWS environments with **proper access controls and key rotation**  
- Conduct **regular vulnerability assessments** and **security awareness training**  

## Conclusion  
The **penetration test** revealed **significant vulnerabilities** in **The Masked DJ's IT environment**, which could be exploited to **compromise systems** and **expose sensitive information**. By **implementing the recommended security measures**, the organization can **substantially improve its security posture** and **protect the Masked DJ's identity**.  
