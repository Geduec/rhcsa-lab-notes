# Common Linux Command Options

## Objective

Provide a quick reference for the most commonly used command options in RHCSA studies.

---

## Option Types

### Short Options

```bash
ls -l
```

### Long Options

```bash
ls --all
```

---

## Common Options

| Option | Meaning | Example |
|----------|----------|----------|
| -l | Long format | ls -l |
| -a | Show hidden files | ls -a |
| -h | Human readable | ls -lh |
| -r | Recursive | cp -r dir backup |
| -R | Recursive (capital version used by some commands) | chmod -R 770 dir |
| -f | File / Force (depends on command) | rm -f file |
| -v | Verbose | cp -v file backup |
| -p | Port / Create parents (depends on command) | ssh -p 2222 host |
| -i | Ignore case / Identity file (depends on command) | grep -i error |
| -n | Number of lines | journalctl -n 20 |
| -u | User or Unit | journalctl -u sshd |
| -b | Current boot | journalctl -b |
| -z | gzip compression | tar -czf backup.tar.gz |