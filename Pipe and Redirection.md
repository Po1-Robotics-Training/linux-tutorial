---
tags:
  - Linux
  - Linux/Pipe
  - Linux/Redirection
---

# Pipe and Redirection

---

### Before learning about redirecting

#### First you need to know what are streams

---

## A stream is simply where the command outputs its data

---

### Commonly there are 3 streams

Stream 0, Stream 1 and Stream 2

---

#### Stream 1 is for normal outputs

Or in other words, outputs that aren't errors.

---

#### Stream 2 is for error outputs

For example, a command encountered a failure during its runtime.

Depending on how the programmer chooses, the command might exit immediately and throw the error.

Or it could continue despite having errors to not disrupt the work flow.

---

#### Stream 0 is for ==inputs==

Every process takes in their inputs in Stream 0.

---

## What are pipes?

Pipes  `|` are used to send the outputs of one command to another.

