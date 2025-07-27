## 🔹 **Topic: Generic Classes in Java**

### 📌 **Purpose of the Lecture**

- To understand **how to define and use generic classes** in Java.
- A continuation of previous lectures on **generic methods**.
- To **eliminate code duplication** by writing one class that can operate on multiple data types (e.g., `Integer`, `Float`, `String`, or even user-defined types like `Student`).

---

## 📘 **1. What is a Generic Class?**

- A **generic class** is one that can **handle any type of data** instead of being fixed to a specific type (e.g., only `int` or `float`).
- Allows a class to work with **different data types** using **type parameters** (e.g., `<T>`, `<T1, T2>`).

---

## 📗 **2. Basic Concept Without Generics**

- For different types like `int`, `float`, or `String`, we need to write **separate classes**:
    - `SpecificArrayInt`
    - `SpecificArrayFloat`
    - `SpecificArrayString`
- These classes:
    - Declare and initialize arrays of a specific type.
    - Include methods to print and reverse the array.
    - Use a **driver class (main method)** to demonstrate functionality.
- This leads to **code duplication** and poor scalability.

---

## 📙 **3. Generic Class Syntax**

```java
class Generic<T> {     
	T x;      
	Generic(T x) {         
		this.x = x;     
	}      
	void printData() {         
		System.out.println(x);     
	} 
}
```

- `<T>` is a **type parameter** representing any object type (not primitives).
- `x` can be of any type (`String`, `Integer`, `Double`, etc.).
- Methods inside the class can also use `T`.

---

## 📕 **4. Using the Generic Class**

### Example in `main()`:

```java
Generic<String> g1 = new Generic<>("Java"); 
g1.printData();// Output:Java  
Generic<Integer> g2 = new Generic<>(123); 
g2.printData(); // Output: 123  
Generic<Double> g3 = new Generic<>(45.6); 
g3.printData(); // Output: 45.6
```

---

## 📘 **5. Generic Class with Arrays**

### Problem:

- Earlier, we used generic classes with **single values**.
- Now, extend it to work with **arrays of any type**.

### Class Structure:

`class GenericArray<T> {     T[] arr;      GenericArray(T[] arr) {         this.arr = arr;     }      void printData() {         for (T elem : arr) {             System.out.print(elem + " ");         }     }      void reverseArray() {         for (int i = 0; i < arr.length / 2; i++) {             T temp = arr[i];             arr[i] = arr[arr.length - 1 - i];             arr[arr.length - 1 - i] = temp;         }     } }`

### Usage:

java

CopyEdit

`Integer[] intArr = {1, 2, 3}; GenericArray<Integer> gInt = new GenericArray<>(intArr);  String[] strArr = {"apple", "banana", "cherry"}; GenericArray<String> gStr = new GenericArray<>(strArr);  gInt.printData(); gStr.reverseArray();`

⚠️ **Note:** Must use wrapper classes (like `Integer`, `Double`) instead of primitives (`int`, `double`) due to Java generics type erasure.

---

## 📙 **6. Using Generics with User-Defined Types**

### Example:

java

CopyEdit

`class Student {     String name;     float marks;      Student(String name, float marks) {         this.name = name;         this.marks = marks;     }      public String toString() {         return name + ": " + marks;     } }  Generic<Student> gStu = new Generic<>(new Student("Alice", 85.5f)); gStu.printData(); // Output: Alice: 85.5`

✅ This proves that **generic classes work for user-defined types** too, not just built-in data types.

---

## 🧠 **Key Takeaways**

- Generic classes provide **flexibility and reusability**.
    
- Eliminate redundant code.
    
- Can work with **arrays** and **user-defined types**.
    
- Must use **object types** (e.g., `Integer` not `int`).
    
- Follow standard syntax: `class ClassName<T> {}` and use `T` throughout the class.
    

---

## 🔜 **Next Steps (Upcoming Lecture Topics)**

- Advanced topics in generics, such as:
    
    - **Bounded types**
        
    - **Wildcards (`?`)**
        
    - **Generic interfaces**
        
    - **Generic constraints**