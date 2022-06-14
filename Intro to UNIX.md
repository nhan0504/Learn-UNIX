- [Types of UNIX](#types-of-unix)
- [The UNIX operating system](#the-unix-operating-system)
  - [The kernel](#the-kernel)
  - [The shell](#the-shell)
- [Files and processes](#files-and-processes)
  - [Running background process](#running-background-process)
- [Directory structure](#directory-structure)
- [File system security](#file-system-security)
  - [File access rights](#file-access-rights)
  - [Directory access rights](#directory-access-rights)
  - [Change access rights](#change-access-rights)
- [UNIX variables](#unix-variables)
  - [Environment variable](#environment-variable)
  - [Shell variable](#shell-variable)
  - [Using and setting variables](#using-and-setting-variables)
   
**Resource:**
[A beginners guide to UNIX and Linux operating system](http://www.ee.surrey.ac.uk/Teaching/Unix/index.html "UNIX tutorial")
- An operating system developed in the 1960s and still under development
- Multi-user, multi-tasking

# Types of UNIX
- Many different versions of UNIX
- Most popular one: GNU/Linux, Sun Solaris, and MacOS X

# The UNIX operating system
- Made up of three main parts: The kernel, the shell, and the programs
## The kernel
- The hub of the operating system: Allocates time and memory to programs, handles filestore and communication in response to system calls
## The shell
- Acts as an interface between user and the kernel
- The shell is a command line interpreter (CLI) -> Interpret user command and arranged them to be carried out. The command are programs
- User can use different shells on the same machine
- History: The shell keeps a list of command user typed in

> ### How shell and kernel work together
> 1. Supposed user type `rm myfile`   
> 2. The shell search through the filestore for the file containing program `rm` and request the kernel (through system calls) to execute the program `rm` on `myfile`   
> 3. When the process `rm myfile` finished, the shell return the prompt waiting for more command

# Files and processes
- Everything in UNIX is either a file or a process
- **Process:** An executing program identified by a unique PID (Process identifier)
- **File:** A collection of data created by users or runninf compiler
## Running background process
- `<command> &`: Run command in the background and return a job number and PID (Eg: [1] 83) -> Notify when the background process has finished
- To put a running process into background:
  - ctrl + z: Suspend the process running
  - `bg`: Put the process into background
- A process running, bacgrounded or susdpended will entered a list with job number (`jobs` will show the list)
- To restart (foreground) a suspended process, type `fg <job number>`

# Directory structure
- All the files are grouped together in the directory structure
- The root is written as `/`
- The `/home` directory is a particualr user directory (The first place that occurs after logging into a UNIX System)
- `home` directory can be referred to as `~` 
  - Eg: `ls ~/mydirector`: list everything in mydirectory wherever you currently are in the file system

# File system security
- Type `ls -l` to get long listing format of files and directory
- The long listing format will be similair to this: `-rwxrwxrwx 1 nhan0504 abby2003 3453 Jan 14 14:24 test.txt`
  - `-rwxrwxrwx`: Access right (Read, write, and execute). The first 3 letters are the owner access rights. The second 3 letters are group access rights. The last 3 letter are everyone else access rights. There will be `d` in place of `-`if this is a directory
  - `nhan0504`: Owner
  - `abby2003`: Group
  - `3453`: Size of the file or directory
  - `Jan 14 14:24`: Date of creation
  - `test.txt`: Date of creation
- The access right is a string containing symbols: d, r, w, x, -, and ocasionally s/S
- The meanings of the symbols depend on whether it is a file or a directory
## File access rights
- `r` or `-`: Read permission or no read permission (The permission to read or copy a file)
- `w` or `-`: Write permission or no write permission (The permission to change a file) 
-  `x` or `-`: Execute permission or no execute permission (The permission to execute a file)

## Directory access rights
- `r`: Permission to list the files in the directory
- `w`: Permission to delete files or move files into directory
- `x`: Permission to access files in the directory (Eg: Read file if you have read access on that file)
## Change access rights
- Only owner of a file can change the access rights using `chmod`   
  
|Symbol| Meaning             |
|:----:|---------------------|
| `u`  | user                |
| `g`  | group               |
| `o`  | other               |
| `a`  | all                 |
| `r`  | read                |
| `w`  | write               |
| `x`  | execute             |
| `+`  | add permission      |
| `-`  | take away permission|

Eg: `chmod og-rw test.txt`: Take away read and write permission from group and other people

# UNIX variables
- Variables are a way of passing information from the shell to a program
- There are 2 categories of variable in UNIX: Environment variable and shell variable
## Environment variable
- Naming convention: Have UPPER CASE name
- Have farther reaching significant compares to shell variable
- To see the value of an environment variable, type `echo $<variable>`
- Some environment variable:
  - USER: Your login name
  - HOME: Path name of home directory
  - HOST: Name of the computer you are using
  - 
## Shell variable
- Naming convention: Have lower case name
- Apply only to the current instance of the shell and are used to set short-term working conditions
- Some example:
  - cwd: The current working directory
  - prompt: The text string used to prompt for command
## Using and setting variables
- At login, the C shell first read **.cshrc** followed by **.login**
  - **.login** set conditions for the session and perform login actions
  - **.cshrc** set conditions and perform actions specific to the shell and each time a new shell is opened (each invocation) 

> Set ENVIRONMENT variables in the **.login**   
> Set shell variables in **.cshrc**

- Example1: Setting the history buffer to 100
  - The change only applied to the currrent shell
  - To permanently change the buffer size -> Set th size in **.cshrc**
    - `nedit ~/.cshrc`: Open **.cshrc**
    - Add `set history = 100` after the list of command
    - `source .cshrc`: Force the shell to reread **.cshrc** to update new changes
- Example2: Setting the path for a program so you can run it anywhere in the directory
  - The specific path to run the units program: ~/units174/bin/units 
  - `set path = ($path ~/units174/bin)`: set ~/units174/bin to a path
  - `units`: Run the program from any directory
