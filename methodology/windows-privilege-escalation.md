---
description: Methodology to Privilege Escalation on Windows
---

# Windows Privilege Escalation

### Understanding Privilege Escalation in Windows

Privilege escalation on Windows is a process whereby a user gains higher-level permissions on the system, often by exploiting system vulnerabilities or misconfigurations. The methodology for achieving this can broadly be categorized into two types: vertical and horizontal escalation.

#### **Vertical Privilege Escalation**

Vertical privilege escalation involves obtaining higher-level privileges, usually from a standard user to an administrator or system-level account.

**Techniques for Vertical Privilege Escalation:**

* **Exploiting System Vulnerabilities:** This includes taking advantage of known software bugs and flaws that can lead to privilege escalation.
* **Misconfigured Permissions:** Sometimes, files, folders, or registry permissions are set incorrectly allowing lower-privileged users to change important settings or files.
* **Token Manipulation:** This involves intercepting or creating access tokens that grant higher privileges.
* **Pass-the-Hash Attack:** Using leaked or captured password hashes to authenticate as a privileged user without the need for the actual password.

#### **Horizontal Privilege Escalation**

Horizontal privilege escalation is when a user extends their privileges to that of a different user who has the same level of privileges.

**Techniques for Horizontal Privilege Escalation:**

* **Guessing or Cracking Passwords:** Trying to gain access to another user's account through password cracking tools.
* **Session Hijacking:** Taking over a user session that is already authenticated with the system.
* **Phishing:** Tricking a user into disclosing their credentials or executing malicious code that exploits their level of access.

### Precautions and Defenses

Ensuring systems are frequently updated, properly configured, and monitored for abnormal activity is crucial to defend against privilege escalation attacks. Use of complex passwords, multi-factor authentication, and privilege auditing can also significantly reduce the risk.

> **Note**: Performing unauthorized privilege escalation on systems that you do not own or do not have explicit permission to test is illegal and unethical. Always obtain proper authorization before conducting any security assessments.
