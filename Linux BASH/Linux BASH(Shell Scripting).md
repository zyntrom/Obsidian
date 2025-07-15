## 📌 **1. Script Basics**

- **Shebang line** (at top of script):  
    `#!/bin/bash`
- **Running a script**:  
```bash
    bash script.sh or ./script.sh (after chmod +x script.sh)
```
- **Comments**:  
    `# This is a comment`

---

## 📦 **2. Variables**

- **Assigning**:  
    `name="Zyn"` (no spaces around =)
- **Accessing**:  
    `echo "$name"`
- **Read from user**:  
    `read varname`

---

## 🔁 **3. Control Structures**

### 👉 If-Else

```bash
if [ condition ]; then   
	code 
elif  condition ; then   
	code 
else   
	code 
fi
```

### 👉 Case

```bash
case $var in   
	pattern1) commands ;;   
	pattern2) commands ;;   
	*) default ;; 
esac
```

### 👉 For Loop

```bash
for var in list; do   
echo "$var" done
```

### 👉 While Loop

```bash
while [ condition ]; do   
# code done
```

### 👉 Until Loop

```bash
until [ condition ]; do   
# code done
```

---

## 🔢 **4. Arithmetic**

```bash
result=$((a + b)) let a=5+3 expr 5 + 3
```

- Increment/Decrement: `((i++))`, `let i+=1`

---

## ⚙️ **5. Functions**

```bash
my_function() {   
	# code 
} 
my_function  # call
```

- Return: `return 0`
- Get function output: `result=$(my_function)`

---

## 📁 **6. File & Directory**

```bash
ls, cd, pwd, mkdir, rm, rmdir cp source dest mv old new touch file.txt
```

---

## 📄 **7. Input / Output**

- **Read**: `read var`
- **Echo**: `echo "Hello"`
- **Print without newline**: `echo -n "Hello"`
- **Redirect output**:
    - Overwrite: `> file.txt`
    - Append: `>> file.txt`
- **Redirect input**: `< input.txt`
- **Pipe**: `command1 | command2`
- **Heredoc**:

```bash
cat << EOF Multiline Text EOF
```

---

## 🧪 **8. Conditions**

- **File tests**:
    - `-e file`: exists
    - `-f file`: regular file
    - `-d dir`: directory
    - `-r file`: readable
    - `-w file`: writable
    - `-x file`: executable
- **String tests**:
    
    - `[ "$a" = "$b" ]`
    - `[ "$a" != "$b" ]`
    - `[ -z "$a" ]`: empty
    - `[ -n "$a" ]`: not empty
- **Number tests**:
    
    - `-eq, -ne, -lt, -le, -gt, -ge`

---

## ⚡ **9. Operators**

- **Logical**: `&&`, `||`, `!`
- **Arithmetic**: `+`, `-`, `*`, `/`, `%`
- **Comparison (inside (( )) )**: , !=, <, >, <=, >=

---

## 🧰 **10. Special Variables**

- `$0`: Script name
- `$1` to `$9`: Positional arguments
- `$@`: All args (individually quoted)
- `$*`: All args (as single word)
- `"$@"`: Best practice
- `$#`: Number of args
- `$$`: PID of script
- `$?`: Exit status of last command
- `$_`: Last argument of previous command

---

## 🗃️ **11. Arrays**

```bash
arr=(apple banana cherry) 
echo "{arr[1]}" 
arr[2]="grape" 
echo "{arr@}"   # all elements 
echo "${#arr@}"  # length
```

---

## 🛠️ **12. Useful Commands**

```bash
basename /path/to/file 
dirname /path/to/file 
date "+%Y-%m-%d" 
sleep 5 clear
```

---

## 🔄 **13. Loops with Command Output**

```bash
for file in $(ls *.txt); do   
	echo "$file" done
```

Or with while-read:

```bash
cat file.txt | while read line; do   
	echo "$line" done
```

---

## 🧵 **14. Exit & Trap**

```bash
exit 0 trap "echo Caught SIGINT" SIGINT
```

---

## 🔐 **15. Permissions & Execution**

```bash
chmod +x script.sh ./script.sh
```