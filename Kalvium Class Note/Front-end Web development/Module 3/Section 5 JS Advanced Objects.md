# JS Advanced Objects

## 🎯 Learning Objectives

- Understand **prototypes** and the **prototype chain**
- Learn **prototypal inheritance** for sharing behavior
- Use built-in **Object methods** for manipulation
- Apply these concepts to reuse and organize code

---

## 🔹 1. Prototype Chain → How Objects Inherit

- Every object has a hidden link → **`[[Prototype]]`** (or `__proto__`).
- If property/method not found → JS looks **up the chain** until `null`.
- Prototype = **backup plan**.

**Example:**

```js
const animal = {   
	speak: function() {     
		return "I can make a sound";   
	} 
};  
const dog = Object.create(animal); 
dog.bark = function() {   
	return "Woof!"; 
};  
console.log(dog.bark());   // "Woof!" 
console.log(dog.speak());  // "I can make a sound"
```

👉 `dog` doesn’t have `speak`, so JS checks `animal` (its prototype).

---

## 🔹 2. Prototypal Inheritance → Sharing Behavior

- Objects can inherit using:
    - `Object.create(protoObj)`
    - Constructor functions + `prototype`
- Prevents duplication → methods shared via prototype.

**Example with Constructor Function:**

```js
function Person(name) {   
	this.name = name; 
}  
Person.prototype.sayHello = function() {   
	return `Hello, I'm ${this.name}`; 
};  
const alice = new Person("Alice"); 
console.log(alice.sayHello()); // "Hello, I'm Alice"
```

👉 `sayHello` lives on `Person.prototype`, shared by all `Person` objects.

---

## 🔹 3. Useful Object Methods

- `Object.keys(obj)` → array of keys

```js
const user = { name: "Leo", age: 21 }; 
console.log(Object.keys(user)); // ["name", "age"]
```

- `Object.values(obj)` → array of values

```js
console.log(Object.values(user)); // ["Leo", 21]
```

- `Object.entries(obj)` → array of `[key, value]` pairs

```js
console.log(Object.entries(user)); // [["name", "Leo"], ["age", 21]]
```
- `Object.assign(target, ...sources)` → copy/merge properties

```js
const extra = { city: "Delhi" }; 
const updatedUser = Object.assign({}, user, extra); console.log(updatedUser); // { name: "Leo", age: 21, city: "Delhi" }
```

---

## 🔹 4. Real-World Example → User Profiles with Inheritance

```js
const user = {   
	login: function() {     
		return `${this.name} has logged in`;   
	} 
};  
const admin = Object.create(user); 
admin.name = "Admin"; 
admin.accessLevel = "super";  
console.log(admin.login()); // "Admin has logged in"
```

👉 `admin` inherits `login` from `user` but adds extra properties.

---

## 🔹 5. Interactive Exercises

1. **Car & Electric Car**

```js
const car = { 
	drive: () => "Car is driving" 
}; 
const electricCar = Object.create(car); 
electricCar.charge = () => "Battery charging";
```

2. **List object keys**

```js
Object.keys({ name: "Sara", role: "Student" }); // ["name", "role"]
```

3. **Book constructor**

```js
function Book(title) {   
	this.title = title; 
} 
Book.prototype.describe = function() {   
	return `Title: ${this.title}`; 
};
```

---

## 📝 Summary

- **Prototypes** = hidden links that form inheritance chains.
- **Prototype Inheritance** → objects share methods without duplication.
- **Object methods** (`keys`, `values`, `entries`, `assign`) → inspect & manipulate objects easily.
- Mastering these = **deeper control** over JS object system.

```embed
title: "Learn JavaScript OBJECTS in 7 minutes! 🧍"
image: "https://i.ytimg.com/vi/lo7o91qLzxc/maxresdefault.jpg"
description: "#JavaScript #tutorial #course // object = A collection of related properties and/or methods//                Can represent real world objects (people, produc..."
url: "https://youtu.be/lo7o91qLzxc"
favicon: ""
aspectRatio: "56.25"
```
