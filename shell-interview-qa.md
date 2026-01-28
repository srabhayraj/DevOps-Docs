# 🐚 Shell Scripting – Interview Notes & Project-Based Q&A

This repository contains **commonly asked Shell Scripting interview questions**, **basic Linux commands**, and **real DevOps project-based explanations**.

---

## 📌 Commonly Used Linux Shell Commands (Basics Only)

> Focused on **daily usage** and **interview basics** (not advanced/debug-only commands)

| Command | Description |
|------|-----------|
| `ls` | List files and directories |
| `cp` | Copy files or directories |
| `mv` | Move or rename files |
| `mkdir` | Create directories |
| `touch` | Create empty files |
| `vim` | Edit files |
| `grep` | Search text patterns |
| `df -h` | Disk usage (human readable) |
| `free -m` | Memory usage in MB |
| `nproc` | Number of CPU cores |

---

## 📌 List All Running Processes

```bash
ps -ef
```

### Print Only Process IDs (PID)

```bash
ps -ef | awk '{print $2}'
```

---

## 📌 Print Only Errors From a Remote Log File

```bash
curl <remote-log-file-url> | grep -i error
```

---

## 📌 Shell Script: Print Numbers Divisible by 3 and 5 but NOT 15

### Logic
- Loop from **1 to 100**
- Divisible by **3**
- Divisible by **5**
- **NOT divisible by 15**

> Script available in `shell-chaos` repository

---

## 📌 Count Number of Letter "S" in `mississippi`

```bash
echo "mississippi" | grep -o "s" | wc -l
```

> Script available in `shell-chaos` repository

---

## 📌 How to Debug a Shell Script

```bash
set -x
```

✔ Enables debug mode  
✔ Prints each command before execution

---

## 📌 What is Crontab in Linux?

`crontab` is used to **schedule commands or scripts** to run automatically at a specified time.

### Example: Run script daily at 2 AM

```bash
0 2 * * * /home/ubuntu/script.sh
```

---

## 📌 Open a File in Read-Only Mode

```bash
vim -R test.txt
```

---

## 📌 Difference Between Soft Link and Hard Link

### 🔹 Hard Link
- Points directly to the inode
- Survives even if original file is deleted
- Cannot span file systems
- Cannot link directories

```bash
ln file1 file2
```

### 🔹 Soft Link (Symbolic Link)
- Acts like a shortcut
- Breaks if original file is deleted
- Can span file systems
- Used for aliases (e.g., `python -> python3`)

```bash
ln -s file1 file2
```

---

## 📌 Difference Between `break` and `continue`

| Statement | Behavior |
|--------|---------|
| `break` | Stops the loop completely |
| `continue` | Skips current iteration and moves to next |

---

## 📌 Disadvantages of Shell Scripting

- Each command spawns a new process
- Limited error handling
- Weak data structures
- Slower execution compared to compiled languages
- Difficult to maintain large scripts

---

## 📌 Types of Loops in Shell Script

| Loop | Use Case |
|----|---------|
| `for` | Fixed number of iterations |
| `while` | Condition-based loop |
| `until` | Runs until condition becomes true |

---

## 📌 Is Bash Dynamically or Statically Typed?

✔ **Dynamically Typed**

```bash
x=5
x="string"
```

No type declaration required.

---

## 📌 Networking Troubleshooting Utilities

### 🔹 traceroute
- Shows hops from source to destination
- Requires sudo

```bash
sudo traceroute google.com
```

### 🔹 tracepath
- Similar to traceroute
- No sudo required

```bash
tracepath google.com
```

---

## 📌 Sort Names in a File

```bash
sort names.txt
```

---

## 📌 Managing Huge Log Files

✔ Use `logrotate`

Features:
- Rotate logs
- Compress old logs
- Delete logs after a defined period

---

# 🚀 Shell Scripting – Project-Based Interview Questions

---

## 1️⃣ What shell scripting projects have you worked on?

**Answer:**
- AWS resource usage monitoring using AWS CLI (S3, EC2, IAM, Lambda)
- GitHub repository audit script to list users with **read-only access**

---

## 2️⃣ How did you automate AWS resource monitoring?

**Answer:**
- Used AWS CLI inside shell scripts
- Collected resource details
- Automated execution using cron
- Logged output for auditing

---

## 3️⃣ What is cron and how did you use it?

**Answer:**
Cron is a Linux scheduler for automating tasks.

```bash
0 2 * * * /home/ubuntu/aws_usage.sh >> /home/ubuntu/aws_cron.log 2>&1
```

---

## 4️⃣ Why use `>>` and `2>&1`?

- `>>` appends logs
- `2>&1` redirects errors to log file

✔ Helps debug cron jobs

---

## 5️⃣ What is `set -x`?

Enables debug mode by printing commands before execution.

---

## 6️⃣ How did you handle AWS authentication?

- Used `aws configure`
- Relied on IAM roles / credentials
- Followed AWS security best practices

---

## 7️⃣ What is `jq` and why was it required?

- Command-line JSON parser
- Used to extract fields from AWS CLI and GitHub API responses

---

## 8️⃣ How did GitHub read-only access script work?

- Used `curl` to call GitHub API
- Filtered users with `pull` permission using `jq`

---

## 9️⃣ How did you secure GitHub tokens?

- Stored tokens as environment variables
- Avoided hardcoding credentials

---

## 🔟 Error Handling in Scripts

- Checked empty outputs
- Validated input arguments
- Printed user-friendly messages

---

## 1️⃣1️⃣ Possible Improvements

- Argument validation
- Timestamped logs
- Slack/Email alerts
- Modular functions
- Dockerization

---

## 1️⃣2️⃣ Why is Shell Scripting Important in DevOps?

- Automation
- CI/CD pipelines
- System administration
- Cloud operations
- Tool integration

---

## 🎯 Interview Tip (IMPORTANT)

**Question:**  
_Do you have hands-on experience?_

**Answer:**  
Yes, I implemented shell automation projects involving AWS resource tracking, cron scheduling, logging, GitHub API integration, and permission auditing.
