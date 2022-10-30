# Lab Report 3
***
I chose:
```
  find -iname
  find . -type d -empty
  find . -mtime -1
```

For the biomed directory:
```
$ find . -iname "rr74.txt" -print0
./rr74.txt
```
Here find is going through biomed and looking for a file name "rr74.txt", case insenitive, and printing it out. This will be useful for finding specific 
files in large directories.
```
$ find . -type d -empty
./emptybiodir
```
Here find is going through biomed looking for empty directories. This can be useful for finding empty subdirectories in large directories. 
```
$ find . -mtime -1
./rr74.txt
```
Here find is going through biomed looking for files that have been changed in the past 1 day. I think this is the most useful command. To be able to look 
through a directory as large as biomed and find any files that have been changed in a set amount of time is extremely useful, especially in a team environment.

For the plos directory:
```
$ find . -iname "pmed.00204*" -print0
./pmed.0020249.txt./pmed.0020246.txt./pmed.0020247.txt./pmed.0020242.txt
```
Here find is going through plos and looking for files that start with "pmed.00204" and printing them.

```
$ find . -type d -empty
./emptyplosdir
```
Here find is going through plos looking for empty directories.

```
$ find . -mtime -1
./pmed002047.txt
```
Here find is going through plos and looking for files that have been changed in the past day.

For the 911report directory:
```
$ find . -iname "chapter-13*" -print0
./chapter-13.4.txt./chapter-13.5.txt./chapter-13.1.txt./chapter-13.2.txt./chapter-13.3.txt
```
Here find is going through 911report and looking for files that start with "chapter-13" and printing them.
```
$ find . -type d -empty
./empty911dir
```
Here find is going through 911report and looking for empty directories.
```
$find . -mtime -1
./chapter-1.txt./chapter-2.txt
```
Here find is going through 911report and looking for files that have been changed in the past day.







