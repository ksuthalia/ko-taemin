---
title: Shell Code
category: Shell
order: 1
---

 command-line shell
 
 about:
 An operating system like Windows, Linux, or Mac OS is a special kind of program. It controls the computer's processor, hard drive, and network connection, but its most important job is to run other programs.

Since human beings aren't digital, they need an interface to interact with the operating system. The most common one these days is a graphical file explorer, which translates clicks and double-clicks into commands to open files and run programs. Before computers had graphical displays, though, people typed instructions into a program called a command-line shell. Each time a command is entered, the shell runs some other programs, prints their output in human-readable form, and then displays a prompt to signal that it's ready to accept the next command. (Its name comes from the notion that it's the "outer shell" of the computer.)

Typing commands instead of clicking and dragging may seem clumsy at first, but as you will see, once you start spelling out what you want the computer to do, you can combine old commands to create new ones and automate repetitive operations with just a few keystrokes.

The filesystem manages files and directories (or folders). Each is identified by an absolute path that shows how to reach it from the filesystem's root directory: /home/repl is the directory repl in the directory home, while /home/repl/course.txt is a file course.txt in that directory, and / on its own is the root directory.

To find out where you are in the filesystem, run the command pwd (short for "print working directory"). This prints the absolute path of your current working directory, which is where the shell runs commands and looks for files by default.

**How can I identify files and directories?**
pwd tells you where you are. To find out what's there, type ls (which is short for "listing") and press the enter key. On its own, **ls** lists the contents of your current directory (the one displayed by pwd). If you add the names of some files, ls will list them, and if you add the names of directories, it will list their contents. For example, ls /home/repl shows you what's in your starting directory (usually called your home directory).

~~~
$ pwd/home/repl
$ lsbackup  bin  course.txt  people  seasonal
$ cd /home/repl/seasonal
$ pwd
/home/repl/seasonal
$ ls
autumn.csv  spring.csv  summer.csv  winter.csv
$
~~~

**How else can I identify files and directories?**
An absolute path is like a latitude and longitude: it has the same value no matter where you are. A relative path, on the other hand, specifies a location starting from where you are: it's like saying "20 kilometers north".

As examples:

If you are in the directory /home/repl, the relative path seasonal specifies the same directory as the absolute path /home/repl/seasonal.
If you are in the directory /home/repl/seasonal, the relative path winter.csv specifies the same file as the absolute path /home/repl/seasonal/winter.csv.
The shell decides if a path is absolute or relative by looking at its first character: If it begins with /, it is absolute. If it does not begin with /, it is relative.

You are in /home/repl. 
~~~
$ ls seasonal/summer.csv
seasonal/summer.csv
$ pwd
/home/repl
$ ls seasonal
autumn.csv  spring.csv  summer.csv  winter.csv
$ ls people
agarwal.txt
~~~

**How can I move to another directory?**
Just as you can move around in a file browser by double-clicking on folders, you can move around in the filesystem using the command cd (which stands for "change directory").

If you type cd seasonal and then type pwd, the shell will tell you that you are now in /home/repl/seasonal. If you then run ls on its own, it shows you the contents of /home/repl/seasonal, because that's where you are. If you want to get back to your home directory /home/repl, you can use the command cd /home/repl.

~~~
$ pwd/home/repl
$ $ cd /home/repl/seasonal$ pwd
/home/repl/seasonal
$ ls
autumn.csv  spring.csv  summer.csv  winter.csv
~~~


