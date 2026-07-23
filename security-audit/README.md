
# 🔐 Security Audit

This section presents the security audit performed on the Linux system.  
The objective was to analyze users, privileges, network exposure, running services, and file permissions in order to understand potential security risks and improve system security awareness.

---

## User Enumeration

### Command

```bash
cat /etc/passwd
```

### Purpose

This command lists all user accounts configured on the Linux system.

It provides information about existing users, system accounts, and service accounts.

### Cybersecurity relevance

User enumeration is an important step during system reconnaissance.

Analyzing user accounts helps identify:
- unnecessary accounts
- suspicious users
- weak account management practices
- potential privilege escalation targets

---

## Privilege Analysis

### Command

```bash
sudo -l
```

### Purpose

This command checks which commands the current user is allowed to execute with administrator privileges.

### Cybersecurity relevance

Privilege management is a critical aspect of cybersecurity.

Incorrect sudo permissions can allow unauthorized users to perform administrative actions and may lead to privilege escalation vulnerabilities.

---

## Network Service Enumeration

### Command

```bash
ss -tulnp
```

### Purpose

This command displays active network connections and listening services running on the system.

It helps identify:
- open ports
- active network services
- processes using network connections

### Cybersecurity relevance

Open ports and unnecessary services increase the attack surface of a system.

Security professionals analyze exposed services to identify potential vulnerabilities and reduce unnecessary risks.

---

## Running Services Analysis

### Command

```bash
systemctl list-units --type=service --state=running
```

### Purpose

This command lists all currently running services managed by systemd.

### Cybersecurity relevance

Analyzing active services helps security analysts:
- understand the system configuration
- detect unnecessary applications
- identify possible attack vectors

Disabling unnecessary services is an important step in system hardening.

---

## SUID Files Detection

### Command

```bash
find / -perm -4000 2>/dev/null
```

### Purpose

This command searches the filesystem for files with the SUID permission enabled.

SUID allows a program to run with the privileges of its file owner.

### Cybersecurity relevance

Misconfigured SUID binaries can create security risks.

Identifying these files during a security audit helps detect possible privilege escalation paths and insecure file permissions.

---

# 🧠 Skills Acquired

Through this security audit, I developed practical skills in:

- Linux system security analysis
- User enumeration
- Privilege and permission management
- Network service enumeration
- Attack surface analysis
- Basic vulnerability identification
- Linux command-line administration
- Cybersecurity documentation

---

# 🎯 Conclusion

This security audit helped me understand how Linux systems can be analyzed from a cybersecurity perspective.

I learned how to collect information about a system, evaluate user privileges, identify exposed services, and detect configurations that could represent security weaknesses.

These concepts are fundamental in cybersecurity fields such as penetration testing, vulnerability assessment, SOC analysis, and system hardening.
