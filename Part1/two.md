# Linux Commands for DevOps – Part 2 (10 Commands)

---

## 11. `ps` – Process Status

**Purpose:**
Displays information about running processes.

```bash
ps
ps -ef
ps aux
```

**Important Options:**

* `-e` → all processes
* `-f` → full format (PPID, UID, etc.)
* `aux` → detailed BSD format

**DevOps Usage:**

* Checking if an application is running
* Identifying high CPU/memory consuming processes
* Finding process IDs (PID)

**Interview Point:**
Each process has a unique PID.
You can combine with `grep`:

```bash
ps -ef | grep nginx
```

**Practice Task:**
Start a background process and find its PID.

---

## 12. `top` – Real-Time Process Monitoring

**Purpose:**
Displays live system resource usage.

```bash
top
```

**What it shows:**

* CPU usage
* Memory usage
* Running processes
* Load average

**DevOps Usage:**

* Performance troubleshooting
* Identifying resource bottlenecks

**Interview Point:**
Load average represents system load over 1, 5, and 15 minutes.

**Practice Task:**
Run a CPU-intensive command and observe changes in `top`.

---

## 13. `df` – Disk Free Space

**Purpose:**
Shows disk space usage.

```bash
df -h
```

**Important Option:**

* `-h` → human readable format

**DevOps Usage:**

* Checking disk space before deployments
* Investigating “No space left on device” errors

**Interview Point:**
`df` shows filesystem-level usage, not individual file sizes.

**Practice Task:**
Check disk usage before and after creating large files.

---

## 14. `du` – Disk Usage

**Purpose:**
Shows size of files and directories.

```bash
du -sh *
du -sh folder_name
```

**Important Options:**

* `-s` → summary
* `-h` → human readable

**DevOps Usage:**

* Finding which folder is consuming space
* Log file analysis

**Interview Point:**
Difference between `df` and `du`:

* `df` → filesystem usage
* `du` → directory/file usage

**Practice Task:**
Find the largest directory inside `/var`.

---

## 15. `free` – Memory Usage

**Purpose:**
Displays memory and swap usage.

```bash
free -h
```

**Columns Explained:**

* total
* used
* free
* available

**DevOps Usage:**

* Checking memory issues
* Monitoring swap usage

**Interview Point:**
“Available” memory is more accurate than “free” memory.

**Practice Task:**
Open multiple applications and observe memory changes.

---

## 16. `systemctl` – Manage Services (Systemd)

**Purpose:**
Controls system services.

```bash
systemctl status nginx
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
systemctl enable nginx
```

**DevOps Usage:**

* Managing application services
* Restarting services after deployment
* Enabling services on boot

**Interview Point:**
`enable` makes service start at boot.
`start` runs it immediately.

**Practice Task:**
Install a service (like nginx) and manage it using `systemctl`.

---

## 17. `find` – Search Files

**Purpose:**
Search for files and directories.

```bash
find / -name file.txt
find /var -type f -name "*.log"
```

**Important Options:**

* `-name` → search by name
* `-type f` → file
* `-type d` → directory
* `-size` → search by size

**DevOps Usage:**

* Finding configuration files
* Locating large files
* Cleaning old logs

**Interview Point:**
`find` can execute commands:

```bash
find . -name "*.log" -delete
```

**Practice Task:**
Find files larger than 100MB.

---

## 18. `tar` – Archive Files

**Purpose:**
Create or extract archives.

```bash
tar -cvf backup.tar folder/
tar -xvf backup.tar
tar -czvf backup.tar.gz folder/
tar -xzvf backup.tar.gz
```

**Important Options:**

* `-c` → create
* `-x` → extract
* `-v` → verbose
* `-f` → file
* `-z` → gzip compression

**DevOps Usage:**

* Creating backups
* Packaging deployments
* Handling release artifacts

**Interview Point:**
`.tar` = archive
`.tar.gz` = compressed archive

**Practice Task:**
Create a compressed backup and extract it.

---

## 19. `scp` – Secure Copy

**Purpose:**
Copy files between servers.

```bash
scp file.txt user@remote_ip:/home/user/
scp -r folder user@remote_ip:/home/user/
```

**DevOps Usage:**

* Transferring build artifacts
* Copying logs from servers
* Manual deployments

**Interview Point:**
Uses SSH protocol for secure transfer.

**Practice Task:**
Set up two VMs and transfer files between them.

---

## 20. `kill` – Terminate Process

**Purpose:**
Stops a running process.

```bash
kill PID
kill -9 PID
```

**Important Signals:**

* `-15` → graceful termination (default)
* `-9` → force kill

**DevOps Usage:**

* Stopping stuck processes
* Killing crashed applications

**Interview Point:**
Always try normal `kill` first before `kill -9`.

**Practice Task:**
Start a background process and terminate it using PID.

---

# Interview Strategy Tip

For DevOps interviews, be ready to:

* Explain real-time scenarios (disk full, service down, high CPU)
* Combine commands (example: `ps -ef | grep java`)
* Explain differences (`df` vs `du`)
* Troubleshoot step-by-step logically


