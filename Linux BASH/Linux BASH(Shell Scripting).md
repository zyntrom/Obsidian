# 🐚 Bash Scripting Full Guide

---

## 1. 🧠 What is Bash?

- Bash (Bourne Again SHell) is a Unix shell and scripting language.
- Used for: automation, file management, system control.

---

## 2. 📄 Basic Structure of a Bash Script

```bash
#!/bin/bash      # Shebang: defines the interpreter 
# This is a comment  
echo "Hello, World"   # Print to terminal
```

### ✨ Making a Script Executable

```bash
chmod +x script.sh    # Make script executable 
./script.sh           # Run the script
```

---

## 3. 📦 Variables

```bash
name="ZynTrom" 
echo "Hello $name"         # Use variable echo "Hello ${name}"       
# Safe syntax
```

### 🔢 Arithmetic

```bash
a=5 
b=3 
echo $((a + b))     # 8 
((a++))             # increment 
let "c = a * b"     # using let
```

---

## 4. 📥 Input / Output

`read name echo "You entered: $name"  read -p "Enter your age: " age`

---

## 5. 🧪 Conditionals

bash

CopyEdit

`if [ $age -ge 18 ]; then     echo "Adult" elif [ $age -gt 12 ]; then     echo "Teen" else     echo "Child" fi`

### ✅ Comparison Operators

#### Numbers

- `-eq` (equal), `-ne` (not equal)
    
- `-lt` (less), `-le` (less or equal)
    
- `-gt` (greater), `-ge` (greater or equal)
    

#### Strings

- `=` (equal), `!=` (not equal)
    
- `-z` (empty), `-n` (not empty)
    

#### Files

- `-e` (exists), `-f` (regular file), `-d` (directory)
    
- `-r`, `-w`, `-x` (read/write/execute permission)
    

---

## 6. 🔁 Loops

### For Loop

bash

CopyEdit

`for i in 1 2 3; do     echo $i done`

### C-style For Loop

bash

CopyEdit

`for ((i = 0; i < 5; i++)); do     echo $i done`

### While Loop

bash

CopyEdit

`count=1 while [ $count -le 5 ]; do     echo $count     ((count++)) done`

### Until Loop

bash

CopyEdit

`count=1 until [ $count -gt 5 ]; do     echo $count     ((count++)) done`

---

## 7. 🧰 Functions

bash

CopyEdit

`greet() {     echo "Hello, $1" }  greet "ZynTrom"`

---

## 8. 📂 File Handling

### Write and Append

bash

CopyEdit

`echo "Hello" > file.txt       # Overwrite echo "Another line" >> file.txt  # Append`

### Read Line-by-Line

bash

CopyEdit

`while read line; do     echo "$line" done < file.txt`

### Check File

bash

CopyEdit

`if [ -f file.txt ]; then     echo "Exists and is a file" fi`

---

## 9. 🧵 Command Line Arguments

bash

CopyEdit

`echo "Script name: $0" echo "1st arg: $1" echo "2nd arg: $2" echo "All args: $@" echo "Arg count: $#"`

Run:

bash

CopyEdit

`./myscript.sh hello world`

---

## 10. 🧨 Error Handling

bash

CopyEdit

`command || echo "Failed" command && echo "Succeeded"  set -e     # Exit on first error set -u     # Exit if using undefined variables`

---

## 11. 🧮 String Operations

bash

CopyEdit

`str="Hello World" echo "${str:0:5}"       # Substring echo "${#str}"          # Length echo "${str/World/Unix}" # Replace`

---

## 12. ⏳ Timing and Sleep

bash

CopyEdit

`sleep 5                # Wait 5 seconds date                   # Current date/time`

---

## 13. 🧹 Useful Commands in Scripts

|Command|Use|
|---|---|
|`basename`|Get filename from path|
|`dirname`|Get directory from path|
|`cut`|Extract parts of lines|
|`awk`|Advanced text processing|
|`sed`|Stream editor (replace text)|
|`grep`|Search pattern in text|
|`head`, `tail`|Start/end of file|

---

## 14. 📦 Arrays

bash

CopyEdit

`arr=(one two three) echo ${arr[0]}         # one echo ${arr[@]}         # all echo ${#arr[@]}        # length  arr+=(four)            # append`

---

## 15. 🧭 Loops with Arrays

bash

CopyEdit

`for item in "${arr[@]}"; do     echo $item done`

---

## 16. 🗂️ File and Directory Operations

bash

CopyEdit

`mkdir new_folder touch file.txt rm file.txt rm -r folder/ mv a.txt b.txt cp a.txt b.txt`

---

## 17. 🧩 Cron Jobs (Automate Scripts)

Edit crontab:

bash

CopyEdit

`crontab -e`

Example: Run every day at 9 AM

bash

CopyEdit

`0 9 * * * /path/to/script.sh`

---

## 18. 📊 Real Script Examples

### ✔️ Backup Script

bash

CopyEdit

`#!/bin/bash tar -czf backup-$(date +%F).tar.gz /home/user`

### ✔️ Batch Rename `.txt` to `.bak`

bash

CopyEdit

`for file in *.txt; do     mv "$file" "${file%.txt}.bak" done`

---

## 19. 📛 Exit Codes

bash

CopyEdit

`exit 0      # success exit 1      # error`

Check exit code:

bash

CopyEdit

`echo $?`

---

## 20. 🔁 Include Other Scripts

bash

CopyEdit

`source other_script.sh . other_script.sh`

---

## ✅ Tips

- Use `#!/bin/bash` at the top.
    
- Quote variables: `"$var"` to prevent word splitting.
    
- Always test your script with `bash -x script.sh` for debug.