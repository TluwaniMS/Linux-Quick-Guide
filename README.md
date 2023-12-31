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

# Linux Manual Pages

The manual pages comprise a collection of pages detailing each command accessible on your system, elucidating their functions, operational procedures, and the command line parameters they support.

`man <command_to_look_up>`

# File Manipulation

Making a directory:

`mkdir [options] <Directory>`

Creating a directory with sub-directories:

`mkdir -p main-directory/sub-directory`

`-p` tells mkdir to make parent directories as needed

`mkdir -pv main-directory/sub-directory`

`-v` makes mkdir tell us what it is doing

Removing a directory:

`rmdir [options] <Directory>`

`NB!`

a directory must be empty before it may be removed

Creating a Blank File:

`touch [options] <filename>`

Copying a File or Directory:

`cp [options] <source> <destination>`

Moving a File or Directory:

`mv [options] <source> <destination>`

Removing a File (and non empty Directories);

`rm [options] <file>`

Removing non empty Directories:

`rm -r <directory>`

`NB!`
With the help of the -r flag, which signifies recursive, we can duplicate directories. The recursive feature entails inspecting a directory along with all the files and subdirectories within it. For subdirectories, the process involves delving into them and performing the same action repeatedly.

# VI Text Editor

Vi is a command line text editor.

`vi <file>`

Saving and Exiting a file:

* `ZZ` (Note: capitals) - Save and exit
* `:q!` - discard all changes, since the last save, and exit
* `:w` - save file but don't exit
* `:wq` - again, save and exit

Other ways to view files:

`cat <file>`

# Wildcards

So what are they?:

Wildcards represent a collection of fundamental elements that enable the creation of a pattern defining a group of files or directories.

Here is the basic set of wildcards:

* `*`- represents zero or more characters
* `?` - represents a single character
* `[]` - represents a range of characters

# Grep and Regular Expressions

egrep functions as a software tool that scans a specified dataset and outputs each line that includes a specified pattern. It represents a further development of the grep utility program.

`egrep [command line options] <pattern> [path]`

# Filters

In the realm of the Linux command line, a filter refers to a program that takes in textual data and modifies it in a specific manner. Filters enable the processing of raw data, generated by another program or saved in a file, to present it in a format better aligned with our requirements.

* ### head:

Head is a program that displays the initial lines of its input for a specified number.

`head [-number of lines to print] [path]`

* ### tail:

Tail is a program that outputs the final few lines of its input.

`tail [-number of lines to print] [path]`

* ### sort:
  
Sort will arrange its input in a straightforward and organized manner.

`sort [-options] [path]`

* ### nl:

nl represents number lines.

`nl [-options] [path]`

# Piping and Redirection

Each command line program we execute is inherently linked to three data streams.

* STDIN (0) - Standard input (data fed into the program)
* STDOUT (1) - Standard output (data printed by the program, defaults to the terminal)
* STDERR (2) - Standard error (for error messages, also defaults to the terminal)

Piping and redirection facilitate the connection of these streams between programs and files, enabling the manipulation of data in engaging and practical manners.

* Redirecting to a File:

`<command> > <file-name>`

Saving to an Existing File

If we direct output to a non-existent file, it will be generated automatically. On the other hand, if we save output to an existing file, its contents will be erased before the new output is saved.

Alternatively, we can use the double greater than operator `( >> )` to add the new data to the file.

`<command> >> <file-name>`

* Piping:

Piping refers to the process of transmitting data from one program to another, utilizing the `( | )` operator. This operator functions by directing the output of the left program as the input for the right program.

`e.g`:
`ls | head -3 | tail -1`

####

* zip and unzip

The zip function enables you to condense items into a ZIP archive using the most efficient compression ratio available.

`zip [options] zipfile <folder/file>`
 
* tee

The tee command records the user's input to both the Terminal's output and files.

`command | tee [option] file1`

* sudo

Superuser do, or sudo, executes your command with administrative or root privileges.

`sudo (command)`

* wget

Utilize the wget command for retrieving files from the web via HTTP, HTTPS, or FTP protocols.

`wget [option] [url]`

* curl

The curl command facilitates the transfer of data between servers, utilizing any of the protocols it supports.

`curl [options] [URL...]`

* alias and unalias

The alias directive prompts the shell to substitute one string with another, enabling the creation of a convenient abbreviation for a program, file name, or text.

`alias <alias>=<command>`

To remove a current alias, utilize the 'unalias' command in the following format.:

`unalias [alias_name]`

* apt-get

apt-get is a command-line utility designed for managing Advanced Package Tool (APT) repositories in Debian-based Linux distributions, such as Ubuntu. This tool enables users to oversee software by facilitating tasks such as updating, removing, and installing packages along with their associated dependencies.

`apt-get [options] (command)`

* yum

YUM serves as a software package management tool extensively employed in various Linux distributions.
The term "YUM" is an abbreviation derived from "Yellowdog Updater, Modified".

`yum <command> <packagename>`

* chmod 

The Linux chmod command enables the management of file permissions, empowering users to designate file accessibility, directory searchability, and script execution.

`chmod <options> <permissions> <file name> `
