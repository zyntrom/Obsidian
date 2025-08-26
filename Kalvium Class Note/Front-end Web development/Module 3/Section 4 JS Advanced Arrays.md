# JS Advanced Arrays

## 🎯 Learning Objectives

- Understand **map()** for transforming arrays
- Use **filter()** to select elements
- Apply **reduce()** to aggregate data
- Solve real-world data manipulation problems
![[Pasted image 20250826163109.png]]
---

## 🔹 1. map() → Transforming Arrays

- Creates a **new array** by applying a function to each element.
- Does **not** modify the original array.
- Use when you want to **transform data** but keep array structure.

**Example:**

```js
const numbers = [1, 2, 3, 4, 5]; 
const doubled = numbers.map(num => num * 2);  
console.log(doubled); // [2, 4, 6, 8, 10]
```

✅ Transformation belt → Input element goes in → Modified element comes out.

---

## 🔹 2. filter() → Selecting Elements

- Creates a new array with **only elements that pass a condition**.
- Returns elements where the test function = `true`.

**Example:**

```js
const numbers = [1, 2, 3, 4, 5, 6]; 
const evens = numbers.filter(num => num % 2 === 0);  
console.log(evens); // [2, 4, 6]
```

✅ Acts like a **bouncer** → Only allows elements that match the rule.

---

## 🔹 3. reduce() → Aggregating Data

- Reduces an array to a **single value**.
- Takes:
    1. A reducer function `(accumulator, element)`
    2. An initial value

**Example: Sum of numbers**

```js
const numbers = [1, 2, 3, 4, 5]; 
const sum = numbers.reduce((acc, num) => acc + num, 0);  console.log(sum); // 15
```

✅ Like a **cooking pot** → Each element is stirred in until one final dish remains.

---

## 🔹 Real-World Example → Average Grade

```js
const students = [   
	{ name: "Alice", grade: 90 },   
	{ name: "Bob", grade: 80 },   
	{ name: "Charlie", grade: 70 },   
	{ name: "David", grade: 60 } ];  
const totalGrade = students.reduce((acc, student) => 
	acc + student.grade, 0); 
const average = totalGrade / students.length;  console.log(average); // 75
```

---

## 🔹 Interactive Exercises

1. **String lengths**

```js
["hi", "hello"].map(str => str.length); // [2, 5]
```

2. **Numbers > 5**

```js
[3, 7, 2, 9, 5].filter(num => num > 5); // [7, 9]
```

3. **Total price of objects**

```js
[{price: 10}, {price: 20}].reduce((acc, item) => acc + item.price, 0); 
// 30
```

---

## 📝 Summary

- **map()** → Transforms each element → Returns new array
- **filter()** → Selects elements by condition → Returns new array
- **reduce()** → Aggregates all values → Returns single value

✨ With just these 3 methods, you can replace most loops and write cleaner, more expressive code.

```embed
title: "How to use map() filter() reduce() | JavaScript Array Methods Tutorial"
image: "https://i.ytimg.com/vi/PojpwEbOQJg/maxresdefault.jpg"
description: "Most important Array Methods Explained for Beginners | Learn Map, Filter, Reduce in JavaScript with Examples | Use array methods instead of foreach.Become a ..."
url: "https://youtu.be/PojpwEbOQJg"
favicon: ""
aspectRatio: "56.25"
```
