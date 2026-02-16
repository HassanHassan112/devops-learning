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

- ---

## Task 2: File System Navigation

This section covers directory navigation, file creation, file management, and viewing system files.

---

### Navigate to System Logs

**Command:**
```bash
cd /var/log
ls -lah
pwd
```

**Explanation:**
- `cd /var/log` → Change directory to system log folder
- `ls -lah` → List files with detailed info (permissions, size, owner)
- `pwd` → Confirm current working directory

Observed many system logs owned by root and system services.

---

### Create and Manage Files

**Commands Used:**
```bash
cd ~/devops-learning
touch test.txt
mkdir -p projects/demo
```

**Explanation:**
- `touch test.txt` → Create empty file
- `mkdir -p projects/demo` → Create nested directories

---

### Copy, Move and Delete Files

Initially attempted:

```bash
mv projects/demo/test.txt projects/demo/backup.txt
```

Received error:
```
No such file or directory
```

Reason:
The file had not yet been copied into the directory.

Correct sequence:

```bash
cp test.txt projects/demo/
mv projects/demo/test.txt projects/demo/backup.txt
rm projects/demo/backup.txt
```

**Explanation:**
- `cp` copies file
- `mv` renames/moves file
- `rm` removes file

---

### View System Files

**Commands:**
```bash
cat /etc/passwd
head -n 20 /etc/services
```

**Explanation:**
- `/etc/passwd` → Contains system user account information
- `head -n 20` → Displays first 20 lines of a file

Observed:
Many system service accounts (e.g., _sshd, _www, _postgres, etc.)

---

## What I Learned

- Always verify file location before moving it.
- Errors like "No such file or directory" usually indicate incorrect path or missing file.
- File operations follow a logical flow: create → copy → move → delete.
- System files like `/etc/passwd` are important for user management.
- Careful reading of error messages is critical in DevOps work.

---

## Task 3: Permissions and Ownership

Linux controls access to files using permissions and ownership.

---

### View File Permissions

Command:
```bash
ls -l permissions.txt
```

Example output:
```
-rw-r--r-- permissions.txt
```

Explanation:
- Owner can read and write
- Group can read
- Others can read

---

### Change Permissions

Command:
```bash
chmod 600 permissions.txt
```

Result:
```
-rw-------
```

Explanation:
Only owner can read and write.

---

Command:
```bash
chmod 644 permissions.txt
```

Result:
```
-rw-r--r--
```

Explanation:
Owner can read/write, others read-only.

---

### Make File Executable

Command:
```bash
chmod +x permissions.txt
```

Result:
```
-rwxr-xr-x
```

Explanation:
File is now executable.

---

### Check System File Permissions

Command:
```bash
ls -l /etc/passwd
```

Observed:
Owned by root, cannot be modified by normal users.

---

## What I Learned

- Linux uses permissions to control file access.
- chmod modifies file permissions.
- ls -l shows permissions and ownership.
- Root owns critical system files.
- Permissions are essential for system security.
