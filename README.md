# Linux-Quick-Guide

# About:

I established this repository to chronicle my learning process with the Bash command line interface (terminal) on Unix/Linux.

## What is a command line interface?


A command line interface is a form of user interaction with a computer program, relying on the input of text lines, commonly referred to as command-lines.
Unlike graphical interfaces that rely on mouse navigation, a command line interface is based on text input and immediate execution of instructions. It presents users with a textual user interface where commands are entered, executed, and responses displayed on the screen.

If you want to find out which shell you're using, you can utilize the `echo` command to reveal a system variable `$SHELL` that indicates your current shell.

```echo $SHELL```

# Basic Navigation:

* `pwd  (Print Working Directory)`:

The instruction accomplishes precisely that, informing you of your current or active directory.

* `ls (list):`
  
Lists what’s in our current location

* `ls [options] [location]`

* `ls -l`:

The presence of `-l` implies that we will be performing a lengthy listing.

* `ls Desktop`:

List contents in the Desktop directory

## Paths:

A path serves as a way to reach a specific file or directory within the system.

Two kinds of paths can be utilized: absolute and relative. Absolute paths define the location (file or directory) with respect to the root directory. They are identifiable by the initial forward slash (/).

On the other hand, relative paths indicate a location (file or directory) in relation to the current position in the system. They do not start with a slash.

* `~ (tilde)`:

This serves as a quick path to your home directory.
`e.g`

if your home directory is located at /home/username, you can access the Documents directory using the path /home/username/Documents or simply ~/Documents.

* `. (dot)`:

This refers to your present directory. 

`e.g`

it could be denoted as ./Documents, indicating a directory or content within your current location.

* `.. (dotdot)`:

This refers to the parent directory. You can utilize this multiple times within a path to navigate upward in the hierarchy.

# How to move around the system:

* `cd (change directory)`:

move to another directory.

* `cd [location]`:
  
The path is indicated as the location and can be either absolute or relative in nature.

`Note:`

Executing the command cd without any parameters will consistently return you to your home directory.

## 

# About Linux files

To begin our understanding of Linux, it's crucial to recognize that in this operating system, all components are essentially treated as files. This encompasses various elements such as text files, directories, keyboards (solely for system input), monitors (exclusively for system output), and more.

# Important things to note:

Linux operates as a system without specific file extensions. Typically, a file extension consists of 2 to 4 characters following a period at the end of a file, indicating its file type. 

Some common extensions include:

* `file.exe` - representing an executable file or program.
* `file.txt` - denoting a plain text file.
* `file.png`, `file.gif`, `file.jpg` - indicating an image file.

In different operating systems like Windows, the extension holds significance as the system relies on it to identify the file type. In contrast, Linux disregards the extension and inspects the file content to ascertain its file type.

`Note`: Linux is Case Sensitive

### Spaces in names:
When you mention files with names containing spaces, it's necessary to enclose the names in quotation marks.

### Hidden Files and Directories:
If a file or directory starts with a . (period), it is regarded as hidden.

Listing hidden files:
ls -a
