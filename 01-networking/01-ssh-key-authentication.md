# SSH Key Authentication (RHEL 10 RHCSA Lab)

## Objective

Configure passwordless SSH authentication between client and server using SSH key pairs.

---

## Environment

* Client: client.example.com
* Server: server.example.com
* User: student

---

## SSH Authentication Methods

SSH connections require:

1. A destination host (hostname or IP address).
2. A valid user account on the remote system.
3. An authentication method.

Common connection examples:

```bash
ssh student@server.example.com
```

Connect using hostname.

```bash
ssh student@192.168.26.10
```

Connect using IP address.

```bash
ssh 192.168.26.10
```

Uses the current local username.

SSH supports two common authentication methods:

- Password Authentication
- Public Key Authentication (SSH Keys)


---

## Steps

### 1. Verify SSH service on server

```bash"
sudo systemctl status sshd
```

Enable if needed:

```bash"
sudo systemctl enable --now sshd
```

---

### 2. Generate SSH key (client)

```bash"
ssh-keygen
```

---

### 3. Copy public key to server

```bash"
ssh-copy-id student@server.example.com
```

---

### 4. Test SSH connection

```bash"
ssh student@server.example.com
```

---

### 5. Verify SSH Sessions

Display connected users:

```bash
who
```

Display active SSH connections:

```bash
ss -tnp | grep sshd
```

View SSH service logs:

```bash
journalctl -u sshd
```

---

## Verification

* Login works without password
* User is `student`
* Host is `server.example.com`

![SSH Key Authentication](./img/ssh%20ping%20and%20key.png)

---

## Lessons Learned

* SSH connections require a destination host, specified by hostname or IP address.
* Hostnames are resolved using DNS or `/etc/hosts`.
* Public key authentication improves security and automation.
* Public keys are stored in `~/.ssh/authorized_keys` on the server.
* Private keys remain on the client and must never be shared.
* SSH key authentication removes the need to enter a password for each connection.

## Issues

* None