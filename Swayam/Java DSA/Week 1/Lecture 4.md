## 🔷 What You’ve Learned About Generics in Java

### ✅ 1. **Recap of Basic Generics**

- A **generic class** or **method** allows you to write code that works with **any data type**.
- You define a class like:
```java
    class MyClass<T> {     
	    T obj; 
	}
```
- This is useful for **type safety** and **code reusability**.

---

### ✅ 2. **Why You Can’t Create Generic Arrays**

```java
T[] a = new T[5]; // ❌ Invalid
```

- Because **type `T` is unknown at compile time**, Java doesn’t know how much memory to allocate.
- Workaround:
```java
    T[] a = (T[]) new Object[5]; // ✅ With a type cast
```

---

### ✅ 3. **Static Generic Methods**

- A static method can also be generic:
```java
    public static <T> void gPrint(T data) {     
	    System.out.println(data); 
	}
```
    
- Called without an object:
    
    java
    
    CopyEdit
    
    `gPrint(101); gPrint("Hello"); gPrint(3.14);`
    

---

### ✅ 4. **Generic Methods Inside Generic Classes**

You can define generic methods in a generic class:

java

CopyEdit

`class MyGenericClass<T> {     public <U> void display(U item) {         System.out.println(item);     } }`

---

### ✅ 5. **You Must Use Wrapper Classes for Primitives**

Wrong:

java

CopyEdit

`MyClass<int> obj = new MyClass<>(); // ❌`

Correct:

java

CopyEdit

`MyClass<Integer> obj = new MyClass<>(); // ✅`

---

## 🔷 Generic Classes with **Multiple Type Parameters**

You can define:

java

CopyEdit

`class MyGeneric<T1, T2> {     T1 obj1;     T2 obj2;          MyGeneric(T1 o1, T2 o2) {         obj1 = o1;         obj2 = o2;     }          void print() {         System.out.println(obj1 + ", " + obj2);     } }`

**Usage:**

java

CopyEdit

`MyGeneric<String, Integer> ob1 = new MyGeneric<>("GC", 9); ob1.print();  // Output: GC, 9  MyGeneric<Integer, Double> ob2 = new MyGeneric<>(123, 1.2); ob2.print();  // Output: 123, 1.2`

You can go further:

java

CopyEdit

`class MyTriple<T, U, V> { ... }  // Up to 256 types allowed!`

---

## 🔷 More on Overloaded Generic Methods

java

CopyEdit

`class PairData<T, V> {     T x;     V y;      PairData(T x, V y) {         this.x = x;         this.y = y;     }      T getFirst() { return x; }     V getSecond() { return y; }      void print() {         System.out.println("X: " + x + ", Y: " + y);     } }`

---

## 🔷 Generics with **User-Defined Types**

You can use your own classes like `Student`:

java

CopyEdit

`class Student {     String name;     int[] marks;      Student(String name, int[] marks) {         this.name = name;         this.marks = marks;     }      void printStudent() {         System.out.println(name + " Total: " + Arrays.stream(marks).sum());     } }`

Then use it with generics:

java

CopyEdit

`MyGeneric<String, Student> data = new MyGeneric<>("ID123", new Student("Alice", new int[]{90, 80, 70}));`

---

## ❗ Error When Using Unknown Methods on Type T

java

CopyEdit

`T[] arr;  double avg() {     double sum = 0;     for (T val : arr) {         sum += val.doubleValue(); // ❌ May not compile!     }     return sum / arr.length; }`

- Not all types `T` have `doubleValue()`. Only **Number subclasses** do.
    
- Solution: Use **bounded type parameters**:
    
    java
    
    CopyEdit
    
    `class MyAverage<T extends Number> {     ... }`
    

---

## 🔜 What’s Next?

In the **next lecture**, you'll learn about:

- **Bounded type parameters** (`<T extends Number>`)
    
- **Wildcards** (`<?>`, `<? extends T>`, `<? super T>`)
    
- Advanced use cases to avoid type errors and ensure safe operations
    

---

## 📝 Final Notes

- Java Generics is **compile-time** mechanism: avoids casting, adds safety.
    
- You can use it with:
    
    - Classes
        
    - Methods (static and instance)
        
    - Interfaces
        
    - Constructors
        
- Multiple types? Just list them like `<T, U, V>`.