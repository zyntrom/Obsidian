# 📘 Generic Programming: Bounded Type Parameters in Java

---

## 🔹 Recap: Why Use Bounded Types?

In previous lectures, generic classes and methods were defined using type parameters like:

```java
class MyClass<T> { 
	... 
}
```

However, this allows **any type**, which can cause **type errors** if we try to use methods not available to all objects.

Example Problem:

```java
T[] a; double sum = 0; 
for (int i = 0; i < a.length; i++) {     
	sum += a[i].doubleValue(); 
	// ❌ Error! T might not have doubleValue() 
}
```

**Solution:** Use bounded type parameters.

---

## ✅ What Are Bounded Type Parameters?

A **bounded type parameter** restricts the types that can be used as arguments.

### 🔸 Syntax:

```java
<T extends ClassName>
```

This ensures that T must be **ClassName or a subclass**.

---

### ✅ Example 1: Bounded by `Number`

```java
class Average<T extends Number> {     
	T[] a;      
	Average(T[] a) {         
		this.a = a;     }      
	double average() {         
		double sum = 0;         
		for (int i = 0; i < a.length; i++) {             
			sum += a[i].doubleValue();  
			// ✅ Allowed because T extends Number         
		}         
	return sum / a.length;     
	} 
}
```

### 🧪 Usage:

```java
Integer[] i = {1, 2, 3, 4, 5}; 
Average<Integer> ai = new Average<>(i); 
System.out.println("Average: " + ai.average());
```

---

## ❌ Trying With Non-Number Types

```java
String[] s = {"A", "B", "C"}; 
Average<String> as = new Average<>(s); // ❌ Compile-time error!
```

Because `String` doesn't extend `Number`, it cannot be used.

---

## 📘 Type Hierarchy (for reference)

Java wrapper classes for primitives all extend `Number`:
- `Integer`, `Double`, `Float`, `Short`, `Long`, `Byte` → extend `Number`
- `String` does **not**

Thus:

```java
Average<Integer> ✅ Average<Double>  ✅ Average<String>  ❌
```

---

## 🔄 Comparing Two Objects With Bounded Types

To compare two objects using generics:

```java
class Compare<T extends Number> {     
	T x, y;      
	Compare(T x, T y) {        
		this.x = x;         
		this.y = y;     
	}      
	boolean areEqual() {         
		return x.doubleValue() == y.doubleValue();     
	} 
}
```

### 💡 Why `doubleValue()`?

Because all subclasses of `Number` have:

- `intValue()`
- `doubleValue()`
- `floatValue()`, etc.

---

## 🔷 Key Points

- Bounded type parameters **allow access** to superclass methods (like `doubleValue()` from `Number`).
- It **restricts usage** to only certain types, improving type safety.
- Java does **not support multiple bounds with classes**, but it does with interfaces:
```java
<T extends Number & Comparable<T>>  ✅
```

---

## 📌 Conclusion

Bounded generics:

- Solve the problem of calling specific methods on generic types.
- Provide **compile-time safety**.
- Are used widely in real-world Java code (e.g., in `Collections`, `Comparable`, etc.)

---

## 🧠 Coming Up Next

In the next lecture:

- **Wildcards in Generics**
- `<?>`, `<? extends T>`, `<? super T>` – usage, benefits, and limitations.