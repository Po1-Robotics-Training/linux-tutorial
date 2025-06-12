---
tags:
  - Linux
margin: "0.3"
---

# How to use Linux

---

## What is Linux?

- Linux is an operating system, its main functions are:
	1. managing hardware
	2. managing software
	3. providing a userspace for its users

The software responsible for providing a basic userspace is called Coreutils.

---

## Linux lingo

%% 在Windows中，大家有資料夾/Folders，C盤/C drive `C:\` 和 檔案/Files %%

In Windows, you have folder, a C drive `C:\` and files.

%% 在Linux中，有着自己專業的字眼
- 資料夾叫做Directories
- C drive 的概念是有點不同，叫做Devices，系統的最高層叫Root，而每個device連上的位置叫Mount
- Home folder是`/home/<username>` %%

In Linux, there are more technical terms used:
- folders are called Directories
- The concept of a C drive is different, all connected hardware are called Devies, the highest level of the filesystem is called ==Root==, and the place each storage devices attaches to is called a mount
- And the home folder is `/home/<Username>`

---

## Coreutils does what?

Coreutils provides a suite of binaries for users to operate and control the system.
Here are some of the ones you'll learn in this tutorial:

<split  wrap="2">
::: block

1. ls
2. cd
3. pwd
4. cat
5. cp

:::

::: block

6. rm
7. mv
8. mkdir
9. md5sum
10. touch

:::

::: block

11. echo
:::

</split>

---

## 基本操作

### `ls`

%% ls 是用來列出(list)現時目錄中的files和directories %%

`ls` is used to list out the files and directories in the working directory.

`-l` stands for list form, it turns the output into a more informative list

`-A` stands for all, it allows you to see the hidden files that starts with a dot (.)

`-F` stands for classify, it appends indicators after the file name to show what type of file it is

---

The current directory is `/home/user/Documents`
The contents are file1, file2, .file3, file4

```bash
$ ls
file1  file2  file4
$ ls -l
total 0
-rw-r--r-- 1 user user 0 May  3 12:55 file1
-rw-r--r-- 1 user user 0 May  3 12:55 file2
-rwxr--r-- 1 user user 0 May  3 12:55 file4
$ ls -A
file1  file2  .file3  file4
$ ls -F
file1  file2  file4*
```

```bash
$ ls -lAF
total 0
-rw-r--r-- 1 user user 0 May  3 12:55 file1
-rw-r--r-- 1 user user 0 May  3 12:55 file2
-rw-r--r-- 1 user user 0 May  3 12:55 .file3
-rwxr--r-- 1 user user 0 May  3 12:55 file4*
```

As for why file4 shows up with a star, you'd learn about it in the [[Permission]] section.

---

### `cd`

cd is used for changing directories

When typed without a path, it returns you to your home directory.

For example:

```bash
# This two commands does the same thing, 
# both returning you to your home directory
$ cd ~
$ cd

$ cd / # / stands for root
# change directory to the .local directory in your home
$ cd ~/.local

$ cd .. # Change to upper directory

$ cd . # Change to current directory
```

---

### `pwd`

stands for Print working directory

it shows you the current directory in the file system.

---

The current directory is `/home/user`

```bash
$ pwd
/home/user

$ cd ~/Document
$ pwd
/home/user/Document
```

---

### `cat`

`cat` stands for con==CAT==enate

it is used to output one or more file's content and turn them into one single output

---

Content of file1:

```
Hello World!
```

```bash
$ cat file1
Hello World!
```

---

### `cp`

`cp` stands for copy

it copies a file

Example:

```bash
$ ls
file1
$ cat file1
Hello!

$ cp file1 file2
$ ls
file1 file2
$ cat file2
Hello!
```

---

### `rm`

`rm` stands for remove, it means deleting a file.

When used with the `-r` flag, it can delete directories as well.

```bash 
$ ls 
file1 file2 file3
$ rm file2 file3
$ ls
file1
```

---

### `mv`

stands for move

it is used to either move a file or directory to another location or rename a file or directory.

```bash
$ ls
file1
# using mv to rename a file
$ mv file1 file2
$ ls
file2

# and then moving the file
# to another directory
$ mv file2 ~/Download/
$ ls ~/Download
file2
```

---

### `mkdir`

stands for makeDirectory

it creates a directory with your specified name

```bash
$ pwd
/home/user

$ mkdir ~/Test
$ ls -l
drwxr-xr-x 2 user user 40 May  3 13:50 Test/
```

---

### `md5sum`

this is a checksum function

a checksum is like the DNA of a file, if the contents of two files are the same, their checksums are the same as well.

---

<split even  >
::: block

Contents of file1.txt:

```
Hello World!
```

:::

::: block

Contents of file2.txt:

```
Hello World!
```

:::

::: block

Contents of file3.txt:

```
hello world!
```

:::
</split>

```bash
$ md5sum file1.txt file2.txt file3.txt
8ddd8be4b179a529afa5f2ffae4b9858  file1.txt
8ddd8be4b179a529afa5f2ffae4b9858  file2.txt
c897d1410af8f2c74fba11b1db511e9e  file3.txt
```

Because the contents of file1 and file2 are the same, their checksum are both `8ddd8be4b179a529afa5f2ffae4b9858`

file3's content, though similar, is different, hence it's checksum `c897d1410af8f2c74fba11b1db511e9e` is different from file1 & file2

---

### `touch`

this command is usually used to create a file.

```bash
$ touch file.txt
$ ls
file.txt
```

---

### `echo`

this commands repeats its input

this is similar to a print function in Python

Often used for seeing environment variables or quickly producing inputs for piping.

---

```bash
$ echo "Hello"
Hello
```

You'll learn about some special usage in section [[Pipe and Redirection]]

---