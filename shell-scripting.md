## What is Shell Scripting? (Learning Perspective)
Shell scripting is writing a series of Linux commands in a file to automate tasks.

Shell acts as:
Interface between user and OS kernel

Most common shell:
Bash (Bourne Again Shell)

👉 DevOps engineers use shell scripts for automation, monitoring, deployments, and troubleshooting.

## Why Shell Scripting is Important in DevOps
- Automates repetitive tasks
- Used in CI/CD pipelines
- Server maintenance & monitoring
- Backup and cleanup jobs
- Faster incident response

👉 Shell scripting is mandatory for DevOps roles.

## Basic Structure of a Shell Script
```
#!/bin/bash
# This is a sample shell script

echo "Hello DevOps"
```

Key Points:
- #!/bin/bash → Shebang (interpreter path)
- .sh → Script extension
- chmod +x script.sh → Make executable
- ./script.sh → Run script

## Variables in Shell
```
name="Abhay"
echo "My name is $name"
```

- No space around =
- Use $ to access variable

## User Input
```
read username
echo "Welcome $username"
```

Used for dynamic scripts.

## Conditional Statements (VERY IMPORTANT)
```
if–else
if [ $a -gt $b ]; then
  echo "a is greater"
else
  echo "b is greater"
fi
```

Operators:
- -eq equal
- -ne not equal
- -gt greater than
- -lt less than

👉 Most common interview topic

## Loops
```
for loop
for i in 1 2 3
do
  echo $i
done

while loop
while [ $count -lt 5 ]
do
  echo $count
  ((count++))
done
```

Used for:
- Iteration
- Automation
- Batch operations

## Functions
```
my_function() {
  echo "This is a function"
}
my_function
```

- Reusable logic
- Clean code

## Command-Line Arguments
```
echo "First argument is $1"
```

Used heavily in:
- CI/CD
- Production scripts

## File & Directory Operations

Common commands:
- ls, pwd, cd
- cp, mv, rm
- touch, mkdir
- cat, less, grep, awk, sed
  
👉 grep & awk are very valuable

## Real-World DevOps Use Cases
- Server health checks
- Log analysis
- Cleanup old files
- Deploy application scripts
- Backup automation
  
## Shell Scripting Skills used in ny work experience
- Linux automation
- Conditional logic
- Loops & functions
- Production-ready scripting
- CI/CD compatibility

## Interview Questions (Direct)

Q1: Why shell scripting in DevOps?\
A: To automate server tasks, CI/CD jobs, and reduce manual errors.

Q2: Difference between sh and bash?\
A: Bash is more powerful and feature-rich.

Q3: How do you debug shell scripts?\
A: Using set -x, echo, and step-by-step execution.

Q4: How do you make a script executable?\
A: chmod +x script.sh

🔑 Key Takeaways
- Shell scripting = automation backbone
- Used in CI/CD & production
