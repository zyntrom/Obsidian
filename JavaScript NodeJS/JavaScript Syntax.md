## ✅ 1. **Variable Declaration**

```javascript
let a = 10;    // can be reassigned 
const b = 5;   // constant value 
var c = 15;    // older way, avoid it
```

---

## ✅ 2. **Data Types**

```javascript
let num = 123;            // Number 
let str = "Hello";        // String 
let bool = true;          // Boolean 
let arr = [1, 2, 3];      // Array 
let obj = {a: 1, b: 2};   // Object
```

---

## ✅ 3. **Conditionals**

```javascript
if (a > b) {   // do something 
} 
else if (a == b) {   // do something else 
} 
else {   // fallback 
}
```

---

## ✅ 4. **Loops**

```javascript
for (let i = 0; i < arr.length; i++)
	{   console.log(arr[i]); }  
for (let num of arr) 
	{   console.log(num); // ES6: for-of }  
while (i < 10) 
	{   i++; }
```

---

## ✅ 5. **Functions**

`function add(a, b)` 
	`{   return a + b; }  // Arrow Function const add = (a, b) => a + b;`

---

## ✅ 6. **Arrays Methods**

`arr.push(4);           // add to end` 
`arr.pop();             // remove from end` 
`arr.shift();           // remove from start` 
`arr.unshift(0);        // add to start`  
`arr.includes(2);       // true/false` 
`arr.indexOf(3);        // position` 
`arr.reverse();         // reverse`  
`arr.sort((a,b) => a-b); // ascending sort` 
`arr.map(x => x*2);      // transform array` 
`arr.filter(x => x%2==0);// filter array` 
`arr.reduce((sum, x) => sum + x, 0); // sum`

---

## ✅ 7. **Strings**

`let s = "leetcode";` 
`s.length; s[0];               // character` 
`s.charAt(1);` 
`s.slice(0, 3);      // "lee"` 
`s.substring(0, 3);  // "lee"` 
`s.split('');        // ['l','e','e',...]` 
`s.split('e');       // ['l','', 'tcod']` 
`s.indexOf('e');     // 1`

---

## ✅ 8. **Objects / Hashmaps**

`let map = {   a: 1,   b: 2 };` 
`map["a"];         // 1` 
`map.a;            // 1` 
`map.c = 3;        // add key  for (let key in map)` 
`{   console.log(key, map[key]); }`

---

## ✅ 9. **Set and Map (ES6)**

`let set = new Set([1, 2, 3]);` 
`set.add(4); set.has(2);      // true` 
`set.delete(1);`  
`let map = new Map();` 
`map.set("a", 1);` 
`map.get("a");    // 1` 
`map.has("b");    // false`

---

## ✅ 10. **Classes (used in some OOP problems)**

`class Node {`   
	`constructor(val) {`     
		`this.val = val;`     
		`this.next = null;`   
	`} }`

---

## ✅ 1. **Creating a 2D Array**

`// Example: 3 rows, 4 columns initialized with 0 let matrix = Array.from({ length: 3 }, () => Array(4).fill(0));  // Manual way let matrix = [   [1, 2, 3],   [4, 5, 6],   [7, 8, 9] ];`

---

## ✅ 2. **Accessing Elements**

`console.log(matrix[0][1]); // Row 0, Col 1 => 2 matrix[2][2] = 10;         // Change value at (2,2)`

---

## ✅ 3. **Traversing a 2D Array**

### 🔁 Full traversal (rows and columns):

`for (let i = 0; i < matrix.length; i++) {   for (let j = 0; j < matrix[0].length; j++) {     console.log(matrix[i][j]);   } }`

### 🔁 Row-wise traversal using for-of:

`for (let row of matrix) {   for (let value of row) {     console.log(value);   } }`

---

## ✅ 4. **Printing 2D Array**

`console.log(matrix); // Prints array of arrays  matrix.forEach(row => console.log(row.join(' '))); // Example output: // 1 2 3 // 4 5 6 // 7 8 9`

---

## ✅ 5. **Input for 2D Array on LeetCode**

LeetCode often **provides 2D arrays as arguments**, like:

`var transpose = function(matrix) {   // matrix is already parsed };`

But if you're simulating input manually:

``let input = `1 2 3 4 5 6 7 8 9`;  let matrix = input.split('\n').map(row => row.split(' ').map(Number)); console.log(matrix); // [[1, 2, 3], [4, 5, 6], [7, 8, 9]]``

---

## ✅ 6. **Common Matrix Operations**

### 🔁 Transpose:

`let transpose = matrix[0].map((_, i) => matrix.map(row => row[i]));`

### 🔁 Reverse rows:

`matrix.forEach(row => row.reverse());`

### 🔁 Reverse full matrix:

`matrix.reverse();  // Reverses the order of rows`

---

## ✅ 7. **Diagonal Traversal**

### Primary Diagonal (top-left to bottom-right):

`for (let i = 0; i < matrix.length; i++) {   console.log(matrix[i][i]); }`

### Secondary Diagonal (top-right to bottom-left):

`for (let i = 0; i < matrix.length; i++) {   console.log(matrix[i][matrix.length - 1 - i]); }`

---

## ✅ 8. **Some Built-in 2D Array Tips**

`let flat = matrix.flat(); // Flattens to 1D array let sum = flat.reduce((acc, x) => acc + x, 0); // Sum of all elements`