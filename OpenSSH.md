---
tags:
  - Linux
  - Linux/ssh
  - Linux/Server
---
# OpenSSH

---

OpenSSH is a package that allows one to remotely connect to a server that has the SSH [[Daemon]] enabled.

---

## How to use it

Firstly, you'd have to get the IP address or the domain of the server you're ssh-ing into.

Then, you have to know the name of the login user.

---

### Syntax

```bash
ssh <name>@<IP/domain>
```

Sometimes, you might get an error saying that the connection has timed out on Port 22