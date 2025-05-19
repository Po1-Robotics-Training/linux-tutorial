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

1. Get the IP address of the domain of the server you're ssh-ing into.
2. Get the name of the user you're logging into.

---

## Syntax

```bash
ssh <name>@<IP/domain>
```

Now that you've successfully logged-in to the server let's see some common problems that you might encounter.

---

## Common Errors

 Sometimes, you might get an error saying that the connection has timed out on Port 22.

You can fix this by specifying which port to connect using the `-P` flag.

---

## Like this

```bash
ssh -p8000 <name>@<IP/domain>
```

---

## Uploading keys

You can facilitate login speed by uploading your key to the server.

```bash
ssh-copy-id -p<port> <name>@<IP/domain>
```