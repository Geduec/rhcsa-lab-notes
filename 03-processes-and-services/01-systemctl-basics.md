# Service Management with systemctl (RHCSA Lab)

## Objective

Learn how to manage services using systemd and systemctl.

---

## Theory

Systemd is the init system used by RHEL.

PID 1 is:

```bash
systemd
```

Systemd manages:

* Services
* Targets
* Timers
* Boot process

The primary management command is:

```bash
systemctl
```

---

## Commands

### Check service status

```bash
systemctl status sshd
```

Displays:

* Running state
* PID
* Logs
* Startup information

---

### Start a service

```bash
sudo systemctl start sshd
```

Starts the service immediately.

---

### Stop a service

```bash
sudo systemctl stop sshd
```

Stops the service.

---

### Restart a service

```bash
sudo systemctl restart sshd
```

Stops and starts the service.

---

### Reload configuration

```bash
sudo systemctl reload sshd
```

Reloads configuration without restarting.

---

### Enable service at boot

```bash
sudo systemctl enable sshd
```

Service starts automatically after reboot.

---

### Disable service at boot

```bash
sudo systemctl disable sshd
```

Service will not start automatically.

---

### Verify boot status

```bash
systemctl is-enabled sshd
```

Possible output:

```text
enabled
disabled
```

---

### List active services

```bash
systemctl list-units --type=service
```

---

## Lab Steps

### Check SSH service

```bash
systemctl status sshd
```

---

### Restart SSH

```bash
sudo systemctl restart sshd
```

---

### Verify service

```bash
systemctl status sshd
```

---

### Check startup configuration

```bash
systemctl is-enabled sshd
```

---

## Verification

Confirm:

* Service is active.
* Service survives restart.
* Service is enabled at boot.

---

## Lessons learned

* systemd manages system services.
* systemctl is the primary administration tool.
* Services can be controlled without rebooting.
* Enable and start are different operations.

## Issues 

* None 
