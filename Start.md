---
tags:
  - Linux
margin: "0.3"
---

# 如何使用Linux

---

## 什麼是Linux?

- Linux 是一個作業系統，他的功能是
	1. 管理硬件
	2. 管理軟體
	3. 為用戶提供使用層面

負責提供基本使用層面的是Coreutils。

---

## Linux的用語

在Windows中，大家有資料夾/Folders，C盤/C drive `C:\` 和 檔案/Files

在Linux中，有着自己專業的字眼
- 資料夾叫做Directories
- C drive 的概念是有點不同，叫做Devices，系統的最高層叫Root，而每個device連上的位置叫Mount
- Home folder是`/home/<username>`

---

## Coreutils是什麼來的?

它是一套有着能使用戶們可以對系統進行基本的軟體集。
以下是你們會最常用到的指令:

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

ls 是用來列出(list)現時目錄中的files和directories

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

### `cat`

`cat` stands for con==CAT==enate

it is used to output one or more file's content and turn them into one single output

---

### `cp`

`cp` stands for copy

it copies a file

---

### `rm`

`rm` stands for remove, it means deleting a file.

When used with the `-r` flag, it can delete directories as well.

---

### `mv`

stands for move

it is used to either move a file or directory to another location or rename a file or directory

---

### `mkdir`

stands for makeDirectory

it creates a directory with your specified name

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