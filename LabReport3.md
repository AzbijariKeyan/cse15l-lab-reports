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
Here find is going through biomed and looking for a file name "rr74.txt", case insensitive, and printing it out. This will be useful for finding specific named or bad named, files in large directories. Find is recursive here and the dot tells find to search the current directory. `"rr74.txt"` is the file name we are looking for and `-print0` tells find to print out the results.
```
$ find . -type d -empty
./emptybiodir
```
Here find is going through biomed looking for empty directories. This can be useful for finding empty subdirectories in large directories. This command 
will go find adirectory and will check to see if it has any files. If not, it will print nothing. If there are empty directories, then it will print
out the paths of those empty directories. Find is also recursive here and the dot tells find to start in the current directory. `-type d` is telling find to check directories and `-empty` is checking if they are empty.
```
$ find . -mtime -1
./rr74.txt
```
Here find is going through biomed looking for files that have been changed in the past 1 day. I think this is the most useful command. To be able to look 
through a directory as large as biomed and find any files that have been changed in a set amount of time is extremely useful, especially in a team environment. Find is also recursive here and the dot tells find to start in the current directory. 
`-mtime` is the boolean variable that returns true if the file was modified in the last n 24-hour periods. In this case n = 1.

For the plos directory:
```
$ find . -iname "pmed.00204*" -print0
./pmed.0020249.txt./pmed.0020246.txt./pmed.0020247.txt./pmed.0020242.txt
```
Here find is going through plos and looking for files that start with "pmed.00204" and printing them. It is also case insensitive. This is useful for looking through a directory for a specific file or files that were made on accident with the same names or similar names, now you can change these files
to better naming conventions. Find is also recursive here and the dot tells find to start in the current directory.
`"pmed.00204*"` is the file name we are looking for and `-print0` tells find to print out the results.

```
$ find . -type d -empty
./emptyplosdir
```
Here find is going through plos looking for empty directories and printing out the paths of those empty directories. This can be useful for when we just 
cloned a project from GitHub and we want to make sure that all the files were downloaded or that the directories are filled properly. We use this command 
to make sure that the directories are filled with files. Find is also recursive here and the dot tells find to start in the current directory. `-type d` is telling find to check directories and `-empty` is checking if they are empty.

```
$ find . -mtime -1
./pmed002047.txt
```
Here find is going through plos and looking for files that have been changed in the past day. I think this is the most useful commands for files in 
large projects that are being worked on by multiple people. This command will make it incredibly easier to look for files that were changed in a set 
time period ago. Find is also recursive here and the dot tells find to start in the current directory.
`-mtime` is the boolean variable that returns true if the file was modified in the last n 24-hour periods. In this case n = 1.

For the 911report directory:
```
$ find . -iname "chapter-13*" -print0
./chapter-13.4.txt./chapter-13.5.txt./chapter-13.1.txt./chapter-13.2.txt./chapter-13.3.txt
```
Here find is going through 911report and looking for files that start with "chapter-13" and printing the paths of the files. It is again case insensitive, 
so it will be useful for finding files that were not named following good naming conventions. I could have files named "Chapter-13" and "chapter-13" which
would obviously be very confusing. This command allows us to find all files with very similar names so we can change them and make our code easier to 
understand. Find is also recursive here and the dot tells find to start in the current directory. `"chapter-13*"` is the file name we are looking for and `-print0` tells find to print out the results.
```
$ find . -type d -empty
./empty911dir
```
Here find is going through 911report and looking for empty directories. With this command we can find all the directories that are empty. This can be 
useful for when we are done with a project and we have moved some files around to make our project seem cleaner and we have some empty subdirectories
that we need to get rid of. This command will help us find these by printing out the paths of these empty directores.
Find is also recursive here and the dot tells find to start in the current directory. `-type d` is telling find to check directories and `-empty` is checking if they are empty.
```
$find . -mtime -1
./chapter-1.txt./chapter-2.txt
```
Here find is going through 911report and looking for files that have been changed in the past day and printing the paths of those files out. This command
can be very useful for checking if a file has been changed in a set time period. For example, if I `scp` a file to the server, I can use this command to
make sure that it was updated. Or I can check the files that I haven't updated yet. Find is also recursive here and the dot tells find to start in the current directory. `-mtime` is the boolean variable that returns true if the file was modified in the last n 24-hour periods. In this case n = 1.







