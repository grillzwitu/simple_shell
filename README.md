# <a href="url"><img src="https://cdn4.iconfinder.com/data/icons/icocentre-free-icons/170/f-command_256-512.png" align="middle" width="100" height="100"></a>   Simple_shell


## Table of Contents
* [Description](#description)
* [File Structure](#file-structure)
* [Requirements](#requirements)
* [Installation](#installation)
* [Usage](#usage)
* [Example of Use](#example-of-use)
* [Bugs](#bugs)
* [Authors](#authors)
* [License](#license)

## Description
Simple_shell is a basic command line interpreter, or shell. This shell includes the basic functionality of a traditional Unix-like command line user interface. 
Standard functions and system calls employed in simple_shell include:
   `access, execve, exit, fork, free, fstat, fflush, getline, malloc, perror, signal, stat, wait, write.`

## File Structure
* [AUTHORS](AUTHORS) - List of contributors to this repository
* [man_1_simple_shell](man_1_simple_shell) - Manual page for the simple_shell
* [shell.h](shell.h) - program header file
* [builtins.c](builtins.c) - major builtin functions
  * `check_for_builtins` - checks to see if the user's command matches a builtin
  * `new_exit` - exits the shell with the option of a specified status
  * `_env` - prints the shell's environment variables to the standard output
  * `new_setenv` - initializes a new environment variable, or modifies an existing one
  * `new_unsetenv` - removes an environment variable
* [builtins2.c](builtins2.c) - helper functions for the builtins
  * `add_key` - creates a new environment variable
  * `find_key` - finds an environment variable in the environment array
  * `add_value` - creates a new environment variable string
  * `_atoi` - converts a string into a non-negative integer
* [environment.c](environment.c) - functions related to the environment
  * `make_env` - creates the shell's environment from the parent process
  * `free_env` - frees the shell's environment
* [errors.c](errors.c) - functions related to printing errors
  * `print_error` - prints an error message to the standard error
  * `_puts2` - prints a string to the standard error
  * `_uitoa` - converts an unsigned integer to a string
* [memory_manager.c](memory_manager.c) - memory allocation functions
  * `_realloc` - a custom realloc function for arrays of pointers
* [new_strtok.c](new_strtok.c) - custom strtok and helper functions
  * `check_match` - checks if a character matches any in a string
  * `new_strtok` - a custom strtok for the shell
* [path.c](path.c) - functions related to executing commands
  * `path_execute` - executes a command in the PATH
  * `find_path` - finds the PATH environment variable
  * `check_for_path` - checks if the command is in the PATH
  * `execute_cwd` - executes a command with an absolute path
  * `check_for_dir` - checks if the command contains an absolute path
* [simple_shell.c](simple_shell.c) - essential functions to the shell
  * `main` - the main function of the program
  * `sig_handler` - handles SIGINT
* [strfunc.c](strfunc.c) - functions related to string manipulation
  * `_puts` - writes a string to standard output
  * `_strdup` - duplicates a string
  * `_strcmpr` - compares two strings
  * `_strcat` - concatenates two strings with a `/` in the middle
  * `_strlen` - calculates the length of a string
* [tokenize.c](tokenize.c) - tokenizing function
  * `tokenize` - creates an array of tokens from a buffer with a specified delimiter

## Requirements

simple_shell is designed to run in the `Ubuntu 14.04 LTS` linux environment and to be compiled using the GNU compiler collection v. `gcc 4.8.4` with flags`-Wall, -Werror, -Wextra, and -pedantic.`

## Installation

   - Clone this repository.
   - Change directories into the repository: `cd simple_shell`
   - Compile: `gcc -Wall -Werror -Wextra -pedantic *.c -o hsh`
   - Run the shell in interactive mode: `./hsh`
   - Or run the shell in non-interactive mode: example `echo "pwd" | ./hsh`

## Usage

The simple_shell is designed to execute commands in a similar manner to sh, however with more limited functionality. The development of this shell is ongoing. The below features will be checked as they become available (see man page for complete information on usage):

### Features
- [x] uses the PATH
- [x] implements builtins
- [x] handles command line arguments
- [x] custom strtok function
- [x] uses exit status
- [x] handles comments (#)
- [x] handles **;**
- [x] shell continues upon Crtl+C (**^C**)
- [ ] custom getline type function
- [ ] handles **&&** and **||**
- [ ] aliases
- [ ] variable replacement


### Builtins

- [x] exit
- [x] env
- [x] setenv
- [x] unsetenv
- [ ] cd
- [ ] help
- [ ] history

## Example of Use
Run the executable in your terminal after compiling:
```
$ ./hsh
($) ls -l
total 80
-rw-r--r-- 1 root root   118 Apr 14 15:51 AUTHORS
-rw-r--r-- 1 root root  5750 Apr 14 16:11 README.md
-rw-r--r-- 1 root root  3024 Apr 14 03:52 builtins.c
-rw-r--r-- 1 root root  2518 Apr 14 03:52 builtins2.c
-rw-r--r-- 1 root root   788 Apr 14 03:52 environment.c
-rw-r--r-- 1 root root  1320 Apr 14 03:52 errors.c
-rwxr-xr-x 1 root root 18923 Apr 14 16:13 hsh
-rw-r--r-- 1 root root  2451 Apr 14 16:06 man_1_simple_shell
-rw-r--r-- 1 root root   530 Apr 14 03:52 memory_manager.c
-rw-r--r-- 1 root root  1357 Apr 14 03:52 new_strtok.c
-rw-r--r-- 1 root root  3630 Apr 14 03:52 path.c
-rw-r--r-- 1 root root  1817 Apr 14 04:13 shell.h
-rw-r--r-- 1 root root  1459 Apr 14 15:49 simple_shell.c
-rw-r--r-- 1 root root  2298 Apr 14 03:52 strfunc.c
-rw-r--r-- 1 root root   754 Apr 14 03:52 tokenize.c
($)
```
## Bugs
At this time, there are no known bugs.

## Authors
Taremowei Appah  
Bezawit Kifle

## License
simple_shell is open source and free to use without restrictions or permissions.