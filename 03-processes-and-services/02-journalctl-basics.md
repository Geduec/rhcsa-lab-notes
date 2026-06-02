# Log Management with journalctl (RHCSA Lab)

## Objective

Learn how to inspect and troubleshoot system logs using journalctl.

---

## Theory

Systemd stores logs in the system journal.

Logs contain:

* Service events
* Boot messages
* Authentication attempts
* Errors and warnings

The main tool is:

```bash
journalctl
```

---

## Commands

### Display all logs

```bash
journalctl
```

Press:

```text
q or ctrl+c
```

to exit.

---

### Display logs from current boot

```bash
journalctl -b
```

Useful after system startup.

---

### Display logs for a service

```bash
journalctl -u sshd
```

Shows only SSH-related logs.

---

### Show recent entries

```bash
journalctl -u sshd -n 20
```

Displays the last 20 log entries.

---

### Follow logs in real time

```bash
journalctl -f
```

Similar to:

```bash
tail -f
```

---

### Show logs since a specific time

```bash
journalctl --since "1 hour ago"
```

---

### Show logs with priorities

```bash
journalctl -p err
```

Displays error messages only.

---

## Lab Steps

### View current boot logs

```bash
journalctl -b
```

---

### View SSH logs

```bash
journalctl -u sshd
```

---

### Restart SSH

```bash
sudo systemctl restart sshd
```

---

### Verify new log entries

```bash
journalctl -u sshd -n 20
```

---

## Verification

Confirm:

* Logs are accessible.
* Service logs are filtered correctly.
* New events appear after restarting services.

---

## Lessons Learned

* journalctl is the primary logging tool in RHEL.
* Service-specific logs simplify troubleshooting.
* Logs can be filtered by service, time and priority.
* Understanding logs is critical for system administration.

## Issues

* None
