## ✅ 1. **Variable Declaration**

js

CopyEdit

`let a = 10;    // can be reassigned` 
`const b = 5;   // constant value` 
`var c = 15;    // older way, avoid it`

---

## ✅ 2. **Data Types**

js

CopyEdit

`let num = 123;            // Number let str = "Hello";        // String let bool = true;          // Boolean let arr = [1, 2, 3];      // Array let obj = {a: 1, b: 2};   // Object`

---

## ✅ 3. **Conditionals**

js

CopyEdit

`if (a > b) {   // do something }` 
`else if (a == b) {   // do something else }` 
`else {   // fallback }`

---

## ✅ 4. **Loops**

js

CopyEdit

`for (let i = 0; i < arr.length; i++)`
	`{   console.log(arr[i]); }`  
`for (let num of arr)` 
	`{   console.log(num); // ES6: for-of }`  
`while (i < 10)` 
	`{   i++; }`

---

## ✅ 5. **Functions**

js

CopyEdit

`function add(a, b)` 
	`{   return a + b; }  // Arrow Function const add = (a, b) => a + b;`

---

## ✅ 6. **Arrays Methods**

js

CopyEdit

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

js

CopyEdit

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

js

CopyEdit

`let map = {   a: 1,   b: 2 };` 
`map["a"];         // 1` 
`map.a;            // 1` 
`map.c = 3;        // add key  for (let key in map)` 
`{   console.log(key, map[key]); }`

---

## ✅ 9. **Set and Map (ES6)**

js

CopyEdit

`let set = new Set([1, 2, 3]);` 
`set.add(4); set.has(2);      // true` 
`set.delete(1);`  
`let map = new Map();` 
`map.set("a", 1);` 
`map.get("a");    // 1` 
`map.has("b");    // false`

---

## ✅ 10. **Classes (used in some OOP problems)**

js

CopyEdit

`class Node {`   
	`constructor(val) {`     
		`this.val = val;`     
		`this.next = null;`   
	`} }`

---

## ✅ 11. **Common LeetCode Patterns**

### Two pointers:

js

CopyEdit

`let left = 0, right = arr.length - 1;` 
`while (left < right) {`   
	`// logic   left++;   right--;` 
`}`

### Binary Search:

js

CopyEdit

`let l = 0, r = arr.length - 1; 
while (l <= r) {   let mid = Math.floor((l + r) / 2);   if (arr[mid] === target) return mid;   else if (arr[mid] < target) l = mid + 1;   else r = mid - 1; }`