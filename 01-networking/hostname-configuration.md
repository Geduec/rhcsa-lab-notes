# Hostname Configuration (RHEL 10 RHCSA Lab)

## Objective

Configure and manage system hostnames using `hostnamectl` and verify name resolution between two virtual machines.

---

## Systems

### Server

* Initial hostname: `localhost` (or default)
* Final hostname: `server.example.com`
* IP: `192.168.26.10`

### Client

* Initial hostname: `localhost` (or default)
* Final hostname: `client.example.com`
* IP: `192.168.26.11`

---

## Steps Performed

### 1. Check current hostname

```bash
hostname
hostnamectl
```

---

### 2. Change hostname (server)

```bash
sudo hostnamectl set-hostname server.example.com
```

---

### 3. Change hostname (client)

```bash
sudo hostnamectl set-hostname client.example.com
```

---

### 4. Apply changes

```bash
exec bash
```

---

### 5. Verify hostname

```bash
hostname
hostnamectl
```

---

## Name Resolution Setup

Both machines were configured in `/etc/hosts`:

```text
192.168.26.10 server.example.com server
192.168.26.11 client.example.com client
```

---

## Verification Tests

### Ping by hostname

From client:

```bash
ping server.example.com
```

From server:

```bash
ping client.example.com
```

---

### Validate resolution

```bash
getent hosts server.example.com
getent hosts client.example.com
```

---

## Key Learnings

* `hostnamectl` is the correct tool to manage hostnames in RHEL 10.
* Hostname changes do not automatically update `/etc/hosts`.
* Name resolution can be handled locally using `/etc/hosts` without DNS.
* Proper hostname configuration is essential for networking and SSH connectivity in Linux environments.

---

## Notes

This setup simulates a basic internal network environment commonly used in RHCSA practice labs.
