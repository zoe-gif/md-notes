---
title: Github Commit
date: 2022-06-28
update: 2022-06-28
categories:
- CS
tags: CMD
description: 
---

### Locate directory

- `cd\` to upper level
- `cd ~\folder`
- `cd "folder with space"`
- `c:` to change the drive
- `cd /d C:\Windows`: `/d` to change drive and directory at the same time

### Make and check direcotry

- `mkdir D:\folder\"folder name with sapce"` to create
- `dir` to view content

### Rename file

- `ren folder to new-folder-name`
- `ren file.extension to new-file-name.extension`

### Copy, delete and move file

- `copy location\filename.extension newlocation\newname.extension`
- `xcopy /s /i location\filename.extension newlocation\newname.extension`
    - to copy folder including content
- `move "<source_dir>" "<destination_dir>"`
- `del folder`: delete all files from folder
- `del abc*.md`: delete all with md extension that start with abc
- `del *.*`: delete all
- `rd folder`: delete folder

### Create and write txt

~~~
$ echo "this is a test" > test.txt
$ cat test.txt
this is a text
~~~

### Help and manual

- `man [keyword]`