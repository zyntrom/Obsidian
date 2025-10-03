# 📒 Notes: Stack Implementation Using Arrays

---

## 🔹 Problem Statement

Implement a **stack** using an **array** that supports the following operations:

- **Push x** → add `x` to the top of the stack
- **Pop** → remove and return the top element
- **Top** → view the top element without removing it

### Constraints

- Maximum stack size: `S`
- Operations on empty stack → **stack underflow**
- Operations on full stack → **stack overflow**

---

## 🔹 Input / Output Format

**Input:**

```
First line: N S  (N = number of operations, S = maximum size) 
Next N lines: operations (push x, pop, top)
```

**Output:**

- For **pop/top** → print the element
    
- If invalid → print `"stack underflow"` or `"stack overflow"`
    

---

### Example 1

**Input:**

`5 3 push 1 push 2 push 3 pop top`

**Output:**

`3 2`

---

### Example 2

**Input:**

`4 2 push 10 push 20 push 30 pop`

**Output:**

`stack overflow 20`

---

### Example 3

**Input:**

`3 5 pop push 1 top`

**Output:**

`stack underflow 1`

---

## 🔹 Problem Solving Approach

1. **Initialize:**
    
    - Empty array of size `S`
        
    - Track **top index** (`-1` when empty)
        
2. **Process Operations:**
    
    - **Push x**
        
        - If top index == S - 1 → `"stack overflow"`
            
        - Else → increment top index and insert x
            
    - **Pop**
        
        - If top index == -1 → `"stack underflow"`
            
        - Else → print element at top and decrement top index
            
    - **Top**
        
        - If top index == -1 → `"stack underflow"`
            
        - Else → print element at top without changing index
            
3. **Output results** of **pop/top** operations
    

---

## 🔹 Code Implementations

### ✅ Python Implementation

`N, S = map(int, input().split()) stack = [] top = -1  for _ in range(N):     command = input().split()          if command[0] == "push":         x = int(command[1])         if top + 1 == S:             print("stack overflow")         else:             stack.append(x)             top += 1     elif command[0] == "pop":         if top == -1:             print("stack underflow")         else:             print(stack.pop())             top -= 1     elif command[0] == "top":         if top == -1:             print("stack underflow")         else:             print(stack[top])`

---

### ✅ Java Implementation

`import java.util.Scanner;  public class StackArray {     public static void main(String[] args) {         Scanner sc = new Scanner(System.in);         int N = sc.nextInt();         int S = sc.nextInt();         sc.nextLine();          int[] stack = new int[S];         int top = -1;          for (int i = 0; i < N; i++) {             String[] command = sc.nextLine().split(" ");             if (command[0].equals("push")) {                 int x = Integer.parseInt(command[1]);                 if (top + 1 == S) {                     System.out.println("stack overflow");                 } else {                     top++;                     stack[top] = x;                 }             } else if (command[0].equals("pop")) {                 if (top == -1) {                     System.out.println("stack underflow");                 } else {                     System.out.println(stack[top]);                     top--;                 }             } else if (command[0].equals("top")) {                 if (top == -1) {                     System.out.println("stack underflow");                 } else {                     System.out.println(stack[top]);                 }             }         }     } }`

---

### ✅ C++ Implementation

`#include <iostream> #include <string> using namespace std;  int main() {     int N, S;     cin >> N >> S;     int* stack = new int[S];     int top = -1;     string command;     getline(cin, command); // consume newline      for (int i = 0; i < N; i++) {         getline(cin, command);         if (command.substr(0,4) == "push") {             int x = stoi(command.substr(5));             if (top + 1 == S) {                 cout << "stack overflow" << endl;             } else {                 top++;                 stack[top] = x;             }         } else if (command == "pop") {             if (top == -1) {                 cout << "stack underflow" << endl;             } else {                 cout << stack[top] << endl;                 top--;             }         } else if (command == "top") {             if (top == -1) {                 cout << "stack underflow" << endl;             } else {                 cout << stack[top] << endl;             }         }     }     delete[] stack;     return 0; }`

---

## 🔹 Key Takeaways

- Implementing stack with arrays is **simple and efficient**.
    
- **Overflow/Underflow** conditions must be handled.
    
- Use a **top index** to track the current top element.
    
- Time Complexity → `O(1)` per operation
    
- Space Complexity → `O(S)`