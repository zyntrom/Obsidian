# 🌡️ Temperature State Message Program

## 📘 Topic: Control Structures – Conditional Logic

**Course:** Problem Solving Using Programming | SPE 2025  
**Concept:** Use `if`, `elif`, and `else` statements to check value ranges and print appropriate messages.

---

## 🧠 Concept Summary

### 🔹 What You Learn

- Taking integer input from user
- Checking multiple ranges using conditional logic
- Printing different outputs based on temperature

### 🔹 Conditional Logic in Programming

- Helps the program _make decisions_
- `if`, `elif`, `else` are used to handle multiple conditions
- First matching condition gets executed

---

## 🔢 Temperature Ranges & Messages

|Temperature Range (°C)|Weather Message|
|---|---|
|temperature <= 0|❄️ Freezing Cold|
|1 <= temperature <= 15|🧥 Cold|
|16 <= temperature <= 25|😊 Pleasant|
|26 <= temperature <= 35|😓 Warm|
|temperature > 35|🔥 Hot|

---

## 🧪 Step-by-Step Breakdown

### ✅ Step 1: Read Input

- Ask user for temperature input
- Use integer (you can later modify to float)

**Python**  
temperature = int(input("Enter the temperature in Celsius: "))

**C++**  :
```c++
include <iostream>  
using namespace std;  
int main() {  
    int temperature;  
    cout << "Enter the temperature in Celsius: ";  
    cin >> temperature;  
    return 0;  
}
```

---

### ✅ Step 2: Use Conditionals

Check each temperature range using `if`, `elif`, and `else`.

---

## 💻 Final Program

### 🐍 Python Version

```python
temperature = int(input("Enter the temperature in Celsius: "))  
if temperature <= 0:  
    print("❄️ It's Freezing Cold!")  
elif temperature <= 15:  
    print("🧥 It's Cold!")  
elif temperature <= 25:  
    print("😊 It's Pleasant!")  
elif temperature <= 35:  
    print("😓 It's Warm!")  
else:  
    print("🔥 It's Hot!")
```

---

### 💠 C++ Version

```c++
include <iostream>  
using namespace std;  
int main() {  
    int temperature;  
    cout << "Enter the temperature in Celsius: ";  
    cin >> temperature;  
    if (temperature <= 0) {  
        cout << "❄️ It's Freezing Cold!" << endl;  
    } else if (temperature <= 15) {  
        cout << "🧥 It's Cold!" << endl;  
    } else if (temperature <= 25) {  
        cout << "😊 It's Pleasant!" << endl;  
    } else if (temperature <= 35) {  
        cout << "😓 It's Warm!" << endl;  
    } else {  
        cout << "🔥 It's Hot!" << endl;  
    }  
    return 0;  
}
```

---

## 🎯 Key Tips

- Start with the most specific conditions first
- Don't forget to use `else` to catch all other cases
- Maintain proper indentation for readability
- You can replace `int` with `float` if you want decimal input