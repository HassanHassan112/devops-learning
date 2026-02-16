# File System Notes

## Task 1: Environment Setup

These commands were used to verify my terminal environment and system information.

---

### uname

**Command:**
```bash
uname
```

**Output:**
```
Darwin
```

**Explanation:**
Shows the operating system name. On macOS, the OS is called Darwin, which is the Unix-based foundation of macOS.

---

### uname -a

**Command:**
```bash
uname -a
```

**Output:**
```
Darwin MacBook-Air.local 21.6.0 Darwin Kernel Version 21.6.0: Mon Jun 24 00:56:10 PDT 2024; root:xnu-8020.240.18.709.2~1/RELEASE_X86_64 x86_64
```

**Explanation:**
Displays detailed system information including:
- Operating system name
- Hostname
- Kernel version
- System architecture

This command is useful for troubleshooting and verifying system configuration.

---

### whoami

**Command:**
```bash
whoami
```

**Output:**
```
macbook
```

**Explanation:**
Displays the currently logged-in user. This is important for understanding permissions and ownership of files.

---

### pwd

**Command:**
```bash
pwd
```

**Output:**
```
/Users/macbook/devops-learning
```

**Explanation:**
Shows the present working directory. This helps identify where you are in the file system.

---

## Summary / What I Learned

- macOS uses Darwin, which is a Unix-based system similar to Linux.
- The terminal allows full control over system navigation and management.
- `uname` helps identify the system and kernel version.
- `whoami` confirms the current user.
- `pwd` confirms the current working directory.
- These commands are essential for system administration and DevOps workflows.
