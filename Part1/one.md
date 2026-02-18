# Linux Commands for DevOps – Part 1 (10 Commands)

---

## 1. `pwd` – Print Working Directory

**Purpose:**
Displays the current directory path.

```bash
pwd
```

**Why it matters in DevOps:**
When working on servers, containers, or CI/CD pipelines, you must always know your current location before executing commands.

**Interview Point:**
`pwd` shows the absolute path from the root directory `/`.

**Practice Task:**
Navigate to different directories using `cd` and verify your location with `pwd`.

---

## 2. `ls` – List Directory Contents

**Purpose:**
Lists files and directories.

```bash
ls
ls -l
ls -a
ls -lh
```

**Important Options:**

* `-l` → long listing format (permissions, owner, size)
* `-a` → shows hidden files
* `-h` → human readable sizes
* `-t` → sort by time
* `-r` → reverse order

**DevOps Usage:**

* Checking log files
* Verifying deployments
* Viewing configuration files

**Interview Point:**
Hidden files start with `.` (example: `.bashrc`).

**Practice Task:**
List all files including hidden ones and sort them by size.

---

## 3. `cd` – Change Directory

**Purpose:**
Move between directories.

```bash
cd /var/log
cd ..
cd ~
cd -
```

**Important Shortcuts:**

* `cd ..` → one level up
* `cd ~` → home directory
* `cd -` → previous directory

**DevOps Usage:**
Used constantly while navigating logs, configs, and application directories.

**Interview Point:**
`cd -` switches between last two directories.

**Practice Task:**
Move between `/etc`, `/var`, and your home directory using shortcuts only.

---

## 4. `mkdir` – Create Directory

**Purpose:**
Create new directories.

```bash
mkdir test
mkdir -p project/app/config
```

**Important Option:**

* `-p` → creates parent directories if they do not exist

**DevOps Usage:**

* Creating project structures
* Log directories
* Deployment folders

**Interview Point:**
Without `-p`, parent directories must already exist.

**Practice Task:**
Create a nested directory structure in one command.

---

## 5. `rm` – Remove Files or Directories

**Purpose:**
Delete files or directories.

```bash
rm file.txt
rm -r folder
rm -rf folder
```

**Important Options:**

* `-r` → recursive (for directories)
* `-f` → force delete (no confirmation)

**DevOps Warning:**
`rm -rf /` is destructive. Always double-check path before executing.

**Interview Point:**
There is no recycle bin in Linux.

**Practice Task:**
Create a directory and safely delete it.

---

## 6. `cp` – Copy Files and Directories

**Purpose:**
Copy files or folders.

```bash
cp file1.txt file2.txt
cp -r dir1 dir2
```

**Important Option:**

* `-r` → recursive copy for directories
* `-p` → preserve permissions

**DevOps Usage:**

* Backing up config files
* Copying build artifacts
* Preparing deployments

**Interview Point:**
Permissions are not preserved unless `-p` is used.

**Practice Task:**
Copy a directory and verify permissions.

---

## 7. `mv` – Move or Rename Files

**Purpose:**
Move files or rename them.

```bash
mv old.txt new.txt
mv file.txt /tmp/
```

**DevOps Usage:**

* Renaming logs
* Archiving files
* Moving builds to deployment directories

**Interview Point:**
`mv` does not duplicate; it relocates the file.

**Practice Task:**
Rename a file and move it to another directory.

---

## 8. `cat` – View File Content

**Purpose:**
Display file content.

```bash
cat file.txt
```

**DevOps Usage:**

* Viewing configuration files
* Reading logs
* Debugging errors

**Interview Tip:**
`cat` is good for small files only. For large files use `less`.

**Practice Task:**
Create a sample file and display its content.

---

## 9. `grep` – Search Text in Files

**Purpose:**
Search for patterns inside files.

```bash
grep "error" app.log
grep -i "failed" app.log
grep -r "port" /etc/
```

**Important Options:**

* `-i` → case insensitive
* `-r` → recursive search
* `-n` → show line numbers
* `-v` → exclude matching lines

**DevOps Usage:**

* Searching logs for errors
* Checking configuration values
* Monitoring application failures

**Interview Point:**
`grep` uses regular expressions.

**Practice Task:**
Search for a keyword inside `/var/log`.

---

## 10. `chmod` – Change File Permissions

**Purpose:**
Modify file permissions.

```bash
chmod 755 script.sh
chmod +x script.sh
```

**Permission Structure:**

* Owner
* Group
* Others

**Numeric Representation:**

* 4 → Read
* 2 → Write
* 1 → Execute

Example:

* 7 = 4+2+1 (rwx)
* 5 = 4+1 (r-x)

**DevOps Usage:**

* Making scripts executable
* Securing configuration files
* Controlling access in servers

**Interview Point:**
`chmod 777` gives full access to everyone (not recommended in production).

**Practice Task:**
Create a script file and make it executable.

---

# How to Practice Effectively

1. Create a folder named `devops_practice`.
2. Perform all commands inside it.
3. Break things intentionally and fix them.
4. Practice combining commands (example: `grep` with `cat`).
5. Try these on a Linux VM or cloud instance.


