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

2. rm
3. mv
4. mkdir
5. md5sum
6. touch

:::

::: block

7. echo
:::

</split>

---

## 基本操作

### `ls`

ls 是用來列出(list)現時目錄中的files和directories

-l stands for list form, it turns the output into a more informative list

-A stands for all, it allows you to see the hidden files that starts with a dot (.)

-F stands for classify, it appends indicators after the file name to show what type of file it is

---

### `cd`

cd is used for changing directories

When typed without a path, it returns you to your home directory.

For example:

```bash
# This two commands does the same thing, both returning you to your home directory
cd ~
cd

cd / # / stands for root
# change directory to the .local directory in your home
cd ~/.local

cd .. # Change to upper directory

cd . # Change to current directory
```

---

### `pwd`

### `cat`

### `cp`

### `rm`