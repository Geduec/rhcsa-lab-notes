# SSH Key Authentication (RHEL 10 RHCSA Lab)

## Objective

Configure passwordless SSH authentication between client and server using SSH key pairs.

---

## Environment

* Client: client.example.com
* Server: server.example.com
* User: student

---

## Steps

### 1. Verify SSH service on server

```bash id="sshdoc2"
sudo systemctl status sshd
```

Enable if needed:

```bash id="sshdoc3"
sudo systemctl enable --now sshd
```

---

### 2. Generate SSH key (client)

```bash id="sshdoc4"
ssh-keygen
```

---

### 3. Copy public key to server

```bash id="sshdoc5"
ssh-copy-id student@server.example.com
```

---

### 4. Test SSH connection

```bash id="sshdoc6"
ssh student@server.example.com
```

---

## Verification

* Login works without password
* User is `student`
* Host is `server.example.com`

![SSH Key Authentication](./img/ssh%20ping%20and%20key.png)

---

## Lessons Learned

* SSH key authentication improves security and automation.
* Public key is stored in `~/.ssh/authorized_keys` on server.
* Password authentication is no longer required after setup.

## Issues

* None

