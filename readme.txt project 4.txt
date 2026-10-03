# Cyber Security Project 4 – System Vulnerability Checklist

**Student:** Aditya Chaturvedi  
**Project:** Cyber Security Project 4  
**Role:** Cybersecurity Analyst / Blue Team  
**Batch:** 2026

## 1. Project Overview

This project focuses on performing a basic defensive security audit of a primary computer. The objective is to identify common security gaps, document the findings, perform applicable remediation, and verify that the system has been hardened.

The audit follows four major areas:

1. Identity and Password Security
2. Software Updates and Patch Management
3. Human/User and Physical Security
4. Network and Endpoint Security

## 2. Objectives

- Check password and MFA security.
- Check software and operating-system update status.
- Identify unnecessary or unauthorized applications.
- Review administrator accounts and privileges.
- Check Windows Firewall status.
- Check disk-encryption status.
- Document security findings and their risk.
- Apply appropriate remediation.
- Capture evidence and perform final verification.

## 3. Audit Environment

| Item | Details |
|---|---|
| Operating System | Windows PC |
| Audit Type | Defensive vulnerability audit |
| Auditor | Aditya Chaturvedi |
| Project | Cyber Security Project 4 |
| Audit Date | 03 October 2026 |

> **Important:** The findings in this repository must be updated with the actual results from the audited computer. Do not claim that a control is enabled unless it was actually checked.

## 4. Checklist

### Step 1 – Identity Front Door

#### Passwords
- Check whether important accounts use strong and unique passwords.
- Prefer long passphrases.
- Avoid reusing passwords.

#### Multi-Factor Authentication
- Check MFA on important accounts.
- Prefer phishing-resistant authentication/passkeys where available.

**Evidence:** Add screenshots to `screenshots/`.

---

### Step 2 – Software Decay and Patch Management

Check:

- Windows Update status.
- Pending security updates.
- Browser/application update status.
- Antivirus/security update status.
- Unapproved or unnecessary applications (Shadow IT).

For Windows, use:

```powershell
Get-WUList
```

If this command is unavailable, use:

**Settings → Windows Update → Check for updates**

Also review:

**Settings → Apps → Installed apps**

**Evidence:** Add update and installed-application screenshots.

---

### Step 3 – Human Perimeter

Check:

- Administrator accounts.
- Unnecessary/guest accounts.
- Excessive privileges.
- Automatic screen locking.
- Physical security.
- Unknown USB devices.
- Awareness of social-engineering risks.

To check local administrators:

```powershell
Get-LocalGroupMember Administrators
```

**Evidence:** Add the administrator-account and relevant settings screenshots.

---

### Step 4 – Network and Endpoint Hygiene

#### Firewall

Run:

```powershell
Get-NetFirewallProfile
```

Check whether the required firewall profiles are enabled.

#### Disk Encryption

Run:

```powershell
Get-BitLockerVolume
```

Record the encryption/protection status.

**Evidence:** Add PowerShell screenshots to `screenshots/`.

---

## 5. Risk Categorization

Findings can be categorized as:

| Risk | Meaning |
|---|---|
| Critical | Immediate and serious security exposure |
| High | Significant weakness requiring prompt attention |
| Medium | Security weakness that should be addressed |
| Low | Minor issue or low-impact weakness |

Risk should be assigned based on the actual finding and its impact. Do not assign Critical/High simply to make the report look serious.

## 6. Findings

Use this table after performing the audit:

| ID | Security Area | Finding | Risk | Status |
|---|---|---|---|---|
| F-01 | Passwords | [Enter actual result] | [Risk] | [Open/Fixed] |
| F-02 | MFA | [Enter actual result] | [Risk] | [Open/Fixed] |
| F-03 | Updates | [Enter actual result] | [Risk] | [Open/Fixed] |
| F-04 | Admin Accounts | [Enter actual result] | [Risk] | [Open/Fixed] |
| F-05 | Firewall | [Enter actual result] | [Risk] | [Open/Fixed] |
| F-06 | Encryption | [Enter actual result] | [Risk] | [Open/Fixed] |
| F-07 | Shadow IT | [Enter actual result] | [Risk] | [Open/Fixed] |
| F-08 | Physical Security | [Enter actual result] | [Risk] | [Open/Fixed] |

## 7. Remediation

Record only actions that were actually performed.

Examples:

- Installed pending security updates.
- Removed an unnecessary application.
- Enabled MFA.
- Corrected unnecessary administrator access.
- Enabled a required security control.
- Verified firewall configuration.
- Verified disk encryption.

## 8. Verification

After remediation, repeat the relevant checks and add final screenshots.

Example format:

| Check | Before | Action | After |
|---|---|---|---|
| Windows Update | [Result] | [Action] | [Result] |
| Firewall | [Result] | [Action] | [Result] |
| Encryption | [Result] | [Action] | [Result] |
| Admin Accounts | [Result] | [Action] | [Result] |

## 9. Evidence

Store screenshots in:

```text
screenshots/
```

Recommended filenames:

```text
01-windows-update.png
02-mfa.png
03-admin-accounts.png
04-firewall.png
05-bitlocker.png
06-installed-apps.png
07-final-verification.png
```

## 10. Conclusion

The system was audited using a four-step defensive security checklist covering identity, software updates, human/user security, and network/endpoint hygiene. Findings were documented, applicable remediation was performed, and the final system state was verified using evidence.

## 11. Repository Structure

```text
Cyber-Security-Project-4/
│
├── README.md
├── Vulnerability_Report.md
├── commands.txt
└── screenshots/
    ├── 01-windows-update.png
    ├── 02-mfa.png
    ├── 03-admin-accounts.png
    ├── 04-firewall.png
    ├── 05-bitlocker.png
    ├── 06-installed-apps.png
    └── 07-final-verification.png
```

## 12. Disclaimer

This is a defensive audit project. Testing should be performed only on a computer and accounts that you own or are authorized to assess. Do not upload passwords, API keys, private keys, tokens, or other sensitive information to the repository.
