---
tags:
  - Linux
margin: "0.3"
---

# 如何使用Linux

---

## Linux是什麽

- Linux是一個操作系統，其主要功能有
	1. 硬件管理
	2. 軟件管理
	3. 提供使用者空間（userspace）

Coreutils 是提供基礎使用者空間（userspace）的軟件。

---

## Linux 術語

在Windows系統中，我們使用 /folders 來稱作資料夾，而C盤和C:/來稱作系統所在的硬盤，檔案稱作/Files。

在Linux系統當中擁有更加多的術語，比如：
- 資料夾（folders）稱作Directories
- Linux當中的C盤亦有所不同，所有與系統鏈接的硬件都被稱作 Devices，而在系統檔案系統中最頂級的被稱爲 Root（可以理解為C:/）。Linux系統當中，每一個與系統鏈接的儲存裝置（硬盤）被稱爲 mount。
- Linux當中的 home folder 的位置在 `/home/<Username>`

---

## Coreutils 是用來做什麽的?

Coreutils 提供了一系列的已編譯代碼給予用戶，用以運作以及控制操作系統。
以下是其中將會在教學中學到的 Coreutils。

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

## 基本用法

### `ls`

`ls` 用來列出所有在當前目錄（directory）中的檔案以及在這個目錄下的其他目錄

`-l` 代表 List ，以列表形式輸出

`-A` 代表 All ，輸出所有文件，包括已隱藏文件（'.'作爲開頭的文件）

`-F` 代表 classify ， 在文件名后插入副檔名，顯示文件格式

---

在以下情況中，我們所在的 Directory 是 `/home/user/Documents`。
而其中内容則是 file1, file2, .file3, file4。

在以下實例當中我們可以更直觀的看到 ls 的使用方法。

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

至於爲什麽 file4 後面有一個星號（ * ），我們將在 [[Permission]] 的部分中學到。 

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