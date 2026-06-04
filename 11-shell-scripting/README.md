# Shell Scripting Basics

## Introduction

Shell scripting allows you to automate tasks in Linux by writing commands inside a script file.

Shell scripts are commonly used for:

- System Administration
- DevOps Automation
- Server Management
- Monitoring
- Backups
- Deployment Pipelines

---

## What is a Shell?

A shell is a command-line interpreter that allows users to interact with the operating system.

Common shells:

- Bash
- Zsh
- Fish
- Sh

Check current shell:

```bash
echo $SHELL
```

---

## What is a Shell Script?

A shell script is a text file containing Linux commands that are executed sequentially.

Example:

```bash
echo "Hello World"
date
pwd
```

Save as:

```text
script.sh
```

Run:

```bash
bash script.sh
```

---

## Shebang

A shebang tells Linux which interpreter should execute the script.

Example:

```bash
#!/bin/bash
```

or

```bash
#!/usr/bin/env bash
```

Example Script:

```bash
#!/bin/bash

echo "Hello Linux"
```

Make executable:

```bash
chmod +x script.sh
```

Run:

```bash
./script.sh
```

---

## Variables

Create variables:

```bash
name="Piyush"
```

Use variables:

```bash
echo $name
```

or

```bash
echo "$name"
```

---

## User Input

Read user input:

```bash
read name
```

Display value:

```bash
echo $name
```

Example:

```bash
echo "Enter your name:"
read name

echo "Hello $name"
```

---

## Command Line Arguments

Arguments passed to a script.

Example:

```bash
./script.sh Piyush
```

Access argument:

```bash
echo $1
```

Example:

```bash
echo "Hello $1"
```

Special Variables:

```text
$0 → Script name
$1 → First argument
$2 → Second argument
$# → Number of arguments
$@ → All arguments
$$ → Process ID
```

---

## If Statement

```bash
if [ 5 -gt 3 ]
then
    echo "True"
fi
```

---

## If Else

```bash
num=10

if [ $num -gt 5 ]
then
    echo "Greater"
else
    echo "Smaller"
fi
```

---

## Comparison Operators

| Operator | Meaning |
|----------|----------|
| -eq | Equal |
| -ne | Not Equal |
| -gt | Greater Than |
| -lt | Less Than |
| -ge | Greater Than or Equal |
| -le | Less Than or Equal |

Example:

```bash
if [ $a -eq $b ]
then
    echo "Equal"
fi
```

---

## For Loop

```bash
for i in 1 2 3 4 5
do
    echo $i
done
```

Range:

```bash
for i in {1..5}
do
    echo $i
done
```

---

## While Loop

```bash
count=1

while [ $count -le 5 ]
do
    echo $count
    ((count++))
done
```

---

## Functions

Create a function:

```bash
greet() {
    echo "Hello Linux"
}
```

Call function:

```bash
greet
```

---

Function with arguments:

```bash
greet() {
    echo "Hello $1"
}

greet Piyush
```

---

## Exit Status

Every command returns an exit status.

Check status:

```bash
echo $?
```

Common values:

```text
0 → Success
1 → Error
```

---

## Logical Operators

AND:

```bash
if [ $a -gt 5 ] && [ $a -lt 20 ]
then
    echo "Valid"
fi
```

OR:

```bash
if [ $a -eq 5 ] || [ $a -eq 10 ]
then
    echo "Match"
fi
```

---

## Useful Script Example

```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Welcome $name"

echo "Today's date:"
date
```

---

## Best Practices

- Use meaningful variable names
- Add comments when necessary
- Always test scripts before production use
- Use quotes around variables
- Check exit codes when handling errors

---

## Summary

Topics covered:

- Shell
- Shell Scripts
- Shebang
- Variables
- User Input
- Arguments
- If Else
- Loops
- Functions
- Exit Status
- Logical Operators

Shell scripting is one of the most important Linux skills for automation, DevOps, and cloud engineering.
