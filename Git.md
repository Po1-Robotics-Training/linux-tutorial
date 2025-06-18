---
tags:
  - Git
---

# What is Git?

---

## Git is a distributed version control system

It tracks versions of files, maintains branching and many more!

---

## How to use git?

Git has many sub commands, they are all useful in their own unique ways.

In this short tutorial, only the essentials commands and functions of git would be demonstrated.

---

# Before staring

## Lets learn the terms

---

## 1. Head and commits

---

Head/Main means the first commit of the repository.

A commit is each submitted change on a branch.

---

## Example graph

```mermaid
gitGraph:
	commit id: "First commit"
	commit id: "Second commit"
	commit
```

^f72366

---

Each commit comes with its own unique hash.

![[Git#^f72366]]

---

The first two commits are committed with comments.

![[Git#^f72366]]

---

Comments are not a must but it is generally advised to have.

![[Git#^f72366]]

---

## 2. Branches

---

## Example graph 2

```mermaid
gitGraph:
	commit
	commit
	branch new_feature
	commit
	commit
	checkout main
	branch another_feature
	commit
```

^3970a7

---

![[Git#^3970a7]]

As you can see three branches are present.

- main
- new_feature
- another_feature

---

![[Git#^3970a7]]

Both branch `new_feature` and `another_branch` are forked from the `main` branch, inheriting every file from `main`.

---

## 3. Merging

---

![[Git#^3970a7]]

The new features implemented in those 2 branches only exists on their own branch.

So what would we do when we want the `main` branch to have those feature updates?

---

### We merge them together

---

## Example graph 3

```mermaid
gitGraph:
	commit
	commit
	branch new_feature
	commit
	commit
	checkout main
	branch another_feature
	commit
	checkout main
	merge new_feature
	merge another_feature
```

^957b53

---

![[Git#^957b53]]

Now, the `main` branch has the features added `new_feature` and `another_feature`.