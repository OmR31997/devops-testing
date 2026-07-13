## Introduction to Shell and Environment Setup (DAY_01)

Sell is linux based scripting responsible make task automate as well can write scripts.

A: Applicaions (Utilities) which are responsible to interact with shell.
S: The shell is responsible to interact with kernel.
K: Linux heart is kernel. It inside written kind of programs (C Programs) and which one responsible to operate the linux like new directory creation, manage networking, manage hardware, & software installation etc i.e., the kernel directly inetact with hardware. The Linux kernel was developed by Linus Torvalds in 1991 as a free and open-source operating system kernel.

Shell scripting allows you to automate tasks and manage system operations through command-line interfaces. This section covers the fundamentals of shell environments, basic commands, and essential setup procedures.

## Shell Commands

- echo: To print line statements.
  Example: echo <contents> - echo "Hello Friends"

- mkdir: To create directory.
  Example: mkdir <directoryName> - mkdir tws

- rm -r: To remove directory.
  Example: rm -r <directoryName> - rm -r tws

- rm -rf: To remove directory.
  Example: rm -rf <directoryName> - rm -rf tws

- rm -r <related*name>* - To remove files and directories with the same name.
  Example: rm -r <fileName>\_ - rm -r demo\*
- touch: To create file.
  Example: touch <fileName>.<extensionName> - touch test.txt

- mv: To move or rename files/directories.
  Example: mv <source> <destination> - mv file.txt /tmp/

- ls: To list item.
  Example: ls

- ls -l: To list items in long format (like what the permissions have, sizes, and timestamps).
  Example: ls -l

- vim: To create/edit files.
  Example: vim <filenameName>.<extensionName> - vim test.txt
  Command-1: `i` - To uses for insert (give for write instruction).
  Command-2: `esc` - To exit insert mode and enter command mode.
  Command-3: `enter` - To confirm changes.
  Command-4: `:wq` - To save changes and quit.
  Command-5: `:qa` - To quit without save.

- cat: To display the contents of a file.
  Example: cat <fileName>.<extensionName> - cat test.sh

- which: To locate the executable file associated with a command.
  Example: which <command> - which bash

- Script
  Example:

---

#!/bin/bash

#This is script for TWS

echo "User-1: Hello Dear"

echo "User-2: Hi"

echo "User-1: How are you?"

echo "User-2: I'm fantastic, what about you?"

echo "User-1: I'm well"

---

- chmod: To change file permissions.
  Example: chmod 754 <fileName> - chmod 754 script.sh => -rwxr-xr--
  Uses:
  | N | Bin | Meaning | Permissions |
  | - | --- | --- | --- |
  | 0 | 000 | No permission | --- |
  | 1 | 001 | Execute only | --x |
  | 2 | 010 | Write only | -w- |
  | 3 | 011 | Write + Execute | -wx |
  | 4 | 100 | Read only | r-- |
  | 5 | 101 | Read + Execute | r-x |
  | 6 | 110 | Read + Write | rw- |
  | 7 | 111 | Read + Write + Execute | rwx |

- To run executable file
  Example: ./<fileName> - ./script.sh

## What Is a Shebang?

- When you run a script as an executable file, the operating system needs to know which program should read it. That instruction is usually written on the first line of the file as a shebang, which starts with #! followed by an interpreter path.

## Examples

chmod 755 script.sh

7 (rwx) → User can read, write, execute

5 (r-x) → Group can read, execute

5 (r-x) → Others can read, execute

chmod 644 file.txt

6 (rw-) → User can read, write

4 (r--) → Group can read

4 (r--) → Others can read

chmod 700 secret.sh

7 (rwx) → User full access

0 (---) → Group no access

0 (---) → Others no access

⚙️ Symbolic Mode (Alternative)
Instead of numbers, you can use letters:

chmod u+x file.sh → Add execute permission for user.

chmod g-w file.sh → Remove write permission for group.

chmod o=r file.sh → Set read-only for others.

Set of commands when written with inside a file in programatic way then that called Shell Script. Steave Bourns who one helps to create 'sh' - /bin/sh.
Bourne Again Shell: Comes with improvement 'bash' - /bin/bash
'csh' - C Shell - /bin/csh
'ksh' - Korn Shell - /bin/ksh
'fish' - Friendly Interactive Shell - /usr/bin/fish and more come.

## Requirements

1: Bash
2: Linux Machine
3: Connect - ssh
4: Text Editor (vim, nano, gedit, etc).
5: To sh file something give inside sh scriptind code so you have to put/write `#!/bin/bash`.
6: Sh file have to make executable.

## Steps to connect with AWS

1: Create EC2 instance
2: Connect via terminal
3: SSH into the instance
4: Configure environment variables
5: Install required packages

## Basic Scripting Skills (DAY_02)

## Comment

- Use `#` to add comments in shell scripts
- Everything after `#` on a line is treated as a comment and will not be executed
- Comments help explain the code and make it more readable

## Types of comments

1: Single line comments - The text following `#` is ignored by the shell
Example: # title

2: Multi line comments - Use `:` and `*/` to enclose multiple lines of comments
Example:
:_
This is a multi-line comment
It spans across multiple lines
_/

or

:'
This is another way to create multi-line comments
You can use single quotes instead of double quotes
'

or

<< comment
This is another multi-line comment
It can span multiple lines
comment

# Variable

- The variable is like a container which holds value.

Example-1: Prefixed Variable (file.sh)

---

#!/bin/bash
name="Sameer"
echo "Name is $name and join date is $(date)"

---

Example-2: Using read command (file.sh)

---

#!/bin/bash
echo "Enter the your name: "
read userName

echo "Your name is $userName"

---

Example-3: Using -p option with read (file.sh)

---

#!/bin/bash

read -p "Enter UserName: " userName

echo "You entred $userName"

---

Example-4: Using -p and -s option with read (file.sh) - Check through `cat /etc/passpwd`

---

#!/bin/bash

read -p "Enter User Name: " userName

echo "Your entered $userName"

sudo useradd -m $userName

echo "New user added $userName"

---

# Arguments

- Positional parameters are arguments that are passed to a script when it is run.

Example: Using positional parameters (file.sh) => Check throug `./create-user.sh Sameer Arjun`

---

#!/bin/bash

echo "Entered args are $1 $2 from $0"

---

# Conditional (if ... then ... else ... fi)

- The conditional statement is used to check the condition and based on the condition, it will execute the code.
- Syntax

---

if [ condition ]; then # code to execute if condition is true
fi

---

Example:

#!/bin/bash

echo "Enter your age: "
read age

if [ $age -ge 18 ]; then
echo "You are eligible for voting"
else
echo "You are not eligible for voting"
fi

# Loop

- Loop is used to iterate the code.

# Types of Loop

1: For Loop - The loop which has initialization, conditional, stepup and stepdown as well responsible for iterating the code from initialization to conditional with stepup/stepdown called for loop.
Syntax

---

for(( initialization; conditional; stepup/stepdown ))
do # code to execute
done

---

Example-1:

---

#!/bin/bash

for((num=0; num<=4; num++))
do
mkdir "demo$num"
done

---

Example-2: -

---

#!/bin/bash

for((num=$2; num<=$3; num++))
do
        mkdir "$1$num"
done

---

2: While Loop - The loop which has only condition and responsible for iterating the code until the condition is true called while loop.
Syntax

---

while [ condition ]
do # code to execute
done

---

Example-1:

---

#!/bin/bash

i=0

while [ $i -le 4 ]
do
mkdir "demo$i"
((i++))
done

---

Example-2:

---

#!/bin/bash

read -p "Enter the range: " range
num=1

while [[$num -le $range]]
do
if (( num % 2 == 0))
then
echo $num
fi

        ((num++))

done

---

Example-3:

---

#!/bin/bash

num=0

while [[$num -le 5]]
do
echo "Dam Cool"
num=$num+1
done

---

3: Until Loop - The loop which has condition and responsible for iterating the code until the condition is true called until loop.
Syntax

---

until [ condition ]
do # code to execute
done

---

## Example

read -p "Enter the range: " range
num=1

until [ $num -gt $range ]
do
echo $num
((num++))
done

---

# Function

- The function is like a block of code which is used to perform a specific task.
  Syntax

---

function_name() { # code to execute
}

---

Example-1:

---

#!/bin/bash

function_name() {
echo "Hello World"
}

function_name

---

Example-2:

---

#!/bin/bash

print_range() {
start=$1
end=$2

    while [[ $start -le $end ]]
    do
        echo $start
        ((start++))
    done

}

# Pass the script arguments into the function

print_range $1 $2

---

## System Monitoring (DAY_03)

# Error Handling

- The error handling is used to detect and manage errors that occur during the execution of a script.
- It ensures that the script handles unexpected situations gracefully without crashing unexpectedly.
- Common techniques include checking exit statuses, using conditional statements, and redirecting error messages.

Example:

---

#!/bin/bash

create_directory() {
mkdir demo
}

if ! create_directory; then
echo "The code being executed as the directory already exists"
exit 1
fi
echo "Block of code not executed due to code interruption"

---

# Exit Status

- The exit status (also called return code or exit code) is a value returned by a command to indicate whether it executed successfully or encountered an error.
- In Bash, the exit status of the last executed command is stored in the special variable `$?`.
- A successful execution returns `0`, while any non-zero value indicates an error.

#

## Background Jobs & Process Management

Requirements

- Node App
- Docker

code_clone() {

}

install_requirements() {

}

required_restarts() {

}
