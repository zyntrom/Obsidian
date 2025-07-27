# 📘 Java Generic Programming - Generic Methods

## 📌 Introduction to Generic Programming

- **Generic programming** allows methods/classes to work with any data type.
- It enhances **code reusability**, **flexibility**, and **type safety**.
- Java supports this via **Generics**.
- Generic methods can operate on **any data type** — e.g., `int`, `float`, `String`, or user-defined types.

---

## 🧠 Why Generic Methods?

- In traditional Java, you'd write:
    - `void swap(int x, int y)`
    - `void swap(float x, float y)`
    - `void swap(String x, String y)`
- Same logic needs multiple versions for each type ⇒ **code duplication**.
- With generics: **write once, use for all types**.

---

## 🧱 Structure of a Generic Method

**Syntax:**

```java
public <T> void methodName(T param) {     
	// use param 
}
```

### Components:

- `public`: Access specifier.
- `<T>`: Type parameter (template), can be any identifier like T, U, V.
- `void`: Return type (can also be T).
- `methodName(T param)`: Parameter of generic type.

---

## ✅ Simple Example of Generic Method

**Print any type:**

```java
class Demo {     public <T> void genericPrint(T data) { 
	System.out.println(data);     
}     
public static void main(String[] args) {         
	Demo obj = new Demo();         
	obj.genericPrint(100);         // Integer
	obj.genericPrint("Hello");     // String         
	obj.genericPrint(45.67);       // Double     
	} 
}
```

**Output:**

```
100 Hello 45.67
```

---

## 🔄 Swap Method Using Generics

```java
public class GenericSwap {     
	public static <T> void swap(T x, T y) {         
		T temp = x;         
		x = y;         
		y = temp;         
		System.out.println("x = " + x + ", y = " + y);     
}      
public static void main(String[] args) {         
	Integer a = 99, b = 66;         
	swap(a, b);  // Works with Integer          
	String p = "Alice", q = "Bob";        
	swap(p, q);  // Works with String          
	Double d1 = 2.3, d2 = 4.5;         
	swap(d1, d2); // Works with Double     
	} 
}
```

> ⚠ Note: In Java, primitives like `int`, `float` need to be wrapped using wrapper classes (e.g., `Integer`, `Float`) when used in generic methods.

---

## 🧑‍💻 Generic Method with User-Defined Class

```java
class Person {     
	String name;     
	Person(String name) {         
		this.name = name;     
	}      
	public String toString() {        
		 return name;     
	} 
}  
public class SwapTest {     
	public static <T> void swap(T x, T y) {         
		T temp = x;         
		x = y;         
		y = temp;         
		System.out.println("x = " + x + ", y = " + y);     
}      
public static void main(String[] args) {         
	Person p1 = new Person("Alen");         
	Person p2 = new Person("John");         
	swap(p1, p2);     
	} 
}
```

---

## 🔁 Static Generic Methods

- Static methods can also be generic:

```java
public class StaticGeneric {     
	public static <T> void print(T value) {  
		System.out.println("Value: " + value);     
	}      
	public static void main(String[] args) {         
		print(123);         
		print("Static call");     
	} 
}
```

---

## 📥 Parameter Passing in Generic Methods

- Generic methods can also accept **variable number of parameters** (varargs).

### Ways:

1. **Using Array**
2. **Using Ellipses (`...`)**
3. **Using `Object` type**

---

## 1️⃣ Using Array
```java
public class VarArgArray {     
	public static void show(int[] values) {         
		for (int v : values)             
			System.out.print(v + " ");         
		System.out.println();     
	}      
	public static void main(String[] args) {         
		int[] a = {1, 3, 5, 7};         
		int[] b = {2, 4};         
		int[] c = {};         
		show(a); 
		show(b); 
		show(c);     
	} 
}
```

---

## 2️⃣ Using Ellipses (`...`)

```java
public class VarArgEllipsis {     
	public static void show(int... values) {         
		for (int v : values)             
			System.out.print(v + " ");         
		System.out.println();     
	}      
	public static void main(String[] args) {         
		show(1, 3, 5, 7);         
		show(10, 20);         
		show(); // no arguments     
	} 
}
```

> ✅ Cleaner and more flexible than array method.

---

## 3️⃣ Using `Object...` for Generic Type & Number

```java
public class VarArgObject {     
	public static void show(Object... values) {         
		for (Object v : values)             
			System.out.print(v + " ");         
		System.out.println();     
	}      
	public static void main(String[] args) {         
		show(1, "Hi", 3.14, true);         
		show("Single");         
		show();     
	} 
}
```

> 🔁 Accepts any number of arguments of any type (Integer, String, Float, Boolean, etc.)

---

## 🔍 Summary

|Concept|Description|
|---|---|
|Generic Method|Works for any data type|
|Syntax|`<T> void method(T arg)`|
|Type Parameters|`<T>`, `<U>`, `<K, V>` etc.|
|Static Generic Method|Allowed|
|Method Overloading|Compatible with generics|
|Varargs Support|Arrays, `...`, `Object...`|
|Wrapper Classes Needed|For `int`, `float`, etc.|

---

## 📚 Practice Tips

- Always use **wrapper classes** (e.g., `Integer` not `int`) in generics.
- `Object...` gives maximum flexibility for any type/number.
- Combine **generics + varargs** for powerful reusable APIs.
- Use descriptive type parameters (`<T>`, `<K, V>`) in real-world projects.