# Process Management (RHCSA Lab)

## Objective

Learn how to inspect, identify, monitor and terminate processes in RHEL 10.

---

## Theory

A process is a running instance of a program.

Every process has:

* PID (Process ID)
* User owner
* CPU usage
* Memory usage
* State (running, sleeping, stopped, etc.)

Linux uses processes for everything, including services, shells and user applications.

---

## Commands

### Display all running processes

```bash
ps aux
```

Explanation:

* `a` → show processes for all users
* `u` → display detailed information
* `x` → include processes not attached to a terminal

---

### Display process tree

```bash
pstree
```

Shows parent-child relationships between processes.

Example:

```text
systemd─┬─NetworkManager
        ├─sshd
        └─bash
```

---

### Search for a process

```bash
ps aux | grep sshd
```

Searches for processes containing "sshd".

---

### Display PID directly

```bash
pgrep sshd
```

Returns only the process ID.

---

### Show detailed process information

```bash
ps -fp <PID>
```

Example:

```bash
ps -fp 1234
```

---

### Create a test process

```bash
sleep 300
```

Creates a process that waits for 300 seconds.

---

### Stop a process gracefully

```bash
kill <PID>
```

Example:

```bash
kill 1234
```

Sends SIGTERM (signal 15).

---

### Force terminate a process

```bash
kill -9 <PID>
```

Example:

```bash
kill -9 1234
```

Sends SIGKILL (signal 9).

Use only when normal termination fails.

---

## Lab Steps

### Create a process

```bash
sleep 300
```

Open another terminal.

---

### Find the process

```bash
ps aux | grep sleep
```

or

```bash
pgrep sleep
```

---

### Display process details

```bash
ps -fp <PID>
```

---

### Terminate the process

```bash
kill <PID>
```

Verify:

```bash
ps aux | grep sleep
```

---

## Verification

Confirm that:

* Process appears in ps output.
* PID can be found using pgrep.
* Process terminates successfully.

---

## Lessons Learned

* Every running program is a process.
* Processes are identified by PID.
* SIGTERM should be used before SIGKILL.
* pgrep is faster than filtering ps output.

## Issues 

* None
