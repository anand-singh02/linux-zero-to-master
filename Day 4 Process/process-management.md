# Linux Process Management ⚙️

## Introduction

A **process** is a running instance of a program in Linux. Process management allows users and administrators to monitor, control, and manage system processes.

Linux provides several commands to view running processes, manage background tasks, and control system resource usage.

---

# 1. ps (Process Status)

The `ps` command displays information about currently running processes.

Example:

```bash
ps
```

Display all processes:

```bash
ps -e
```

Display detailed information:

```bash
ps -ef
```

Example Output:

```
UID   PID  PPID  CMD
root    1     0  systemd
anand 2034  1500 bash
```

Explanation:

* **PID** → Process ID
* **PPID** → Parent Process ID
* **CMD** → Command running

---

# 2. top

The `top` command shows real-time system processes and resource usage.

Example:

```bash
top
```

It displays:

* CPU usage
* Memory usage
* Running processes
* System load

Press **q** to exit.

---

# 3. htop

`htop` is an interactive and improved version of `top`.

Example:

```bash
htop
```

Features:

* Colorful interface
* Interactive process control
* Scrollable process list

Install `htop`:

```bash
sudo apt install htop
```

---

# 4. kill

The `kill` command terminates a process using its Process ID (PID).

Example:

```bash
kill 1234
```

Force terminate a process:

```bash
kill -9 1234
```

---

# 5. jobs

The `jobs` command shows background jobs running in the current terminal.

Example:

```bash
jobs
```

Example Output:

```
[1]+ Running   sleep 100 &
```

Explanation:

* `[1]` → Job number
* `Running` → Job status
* `sleep 100` → Command running

---

# 6. bg (Background)

The `bg` command resumes a paused job in the background.

Example:

```bash
bg %1
```

Explanation:

* `%1` refers to **job number 1**

Result:

The process continues running in the background.

---

# 7. fg (Foreground)

The `fg` command brings a background process to the foreground.

Example:

```bash
fg %1
```

Result:

The process will run in the terminal until it completes.

---

# 8. nohup

The `nohup` command runs a process that continues running even after the terminal is closed.

Example:

```bash
nohup python script.py &
```

Output Example:

```
nohup: ignoring input and appending output to 'nohup.out'
```

Explanation:

* Process continues running even after logout
* Output is stored in `nohup.out`

---

# 9. nice

The `nice` command starts a process with a specified priority.

Example:

```bash
nice -n 10 python script.py
```

Explanation:

* `-n 10` sets a lower priority for the process.
* Higher number → lower priority.

Priority Range:

```
-20  (Highest Priority)
  0  (Default Priority)
 19  (Lowest Priority)
```

---

# Summary

Linux process management commands allow users to monitor and control running programs efficiently.

Common commands include:

* `ps` → view processes
* `top` / `htop` → monitor system resources
* `kill` → terminate processes
* `jobs` → view background jobs
* `bg` / `fg` → manage background and foreground tasks
* `nohup` → run processes after logout
* `nice` → control process priority

These commands are essential for Linux administrators and DevOps engineers.

---

# Author

Anand Singh
B.Tech Graduate | Learning Linux for Cloud and DevOps
