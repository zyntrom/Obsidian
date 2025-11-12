# **1.7 — Modules and File System**

---

## **1️⃣ Concept Overview**

Modern backend development is based on **modularity** — dividing code into reusable, independent files (modules).  
This lesson covers:

- **Modules** (code reusability and organization)
- **CommonJS system** (`module.exports` and `require`)
- **Node.js fs module** (File System interaction)
- **Promise-based file operations** (`fs.promises`)
- **Practical integration of modules and file operations**

---

## **2️⃣ What Are Modules?**

### **Definition**

A **module** is an independent file that contains reusable code — functions, variables, or classes — that can be imported and used in other files.

### **Purpose**

- Promotes **code reusability**
- Simplifies **organization**
- Reduces **code duplication**
- Makes debugging and maintenance easier

### **Real-world analogy**

Instead of writing everything in one file (`server.js`), separate logic into multiple modules:

- `server.js` → main logic
- `utils.js` → helper functions
- `db.js` → database configuration
- `routes.js` → routes and endpoints

---

## **3️⃣ CommonJS Module System (Node.js Default)**

Node.js uses **CommonJS** as its native module system.

Two main keywords:

|Keyword|Purpose|Description|
|---|---|---|
|`module.exports`|Export|Defines what code (function, object, etc.) is made available for import.|
|`require()`|Import|Loads exported code from another file or Node.js core module.|

---

## **4️⃣ Exporting in Node.js**

### **(A) Exporting a Single Function**

When a file contains one main function or feature.

```js
// utils.js
const greet = (name) => {
  return `Hello, ${name}! Welcome to the world of modules.`;
};

// Exporting the function
module.exports = greet;

```
> ✅ Anything assigned to `module.exports` is what other files will receive when they `require()` this file.

---

### **(B) Exporting Multiple Functions / Objects**

When multiple related functions exist.

```js
// utils.js
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;

module.exports = {
  add,
  subtract,
};

```

> Here, `module.exports` contains an **object** with both functions.

---

## **5️⃣ Importing Modules with require()**

### **(A) Importing a Single Function**

When the module exports one thing (like a function).

```js
// server.js
const greetFunction = require('./utils.js');
console.log(greetFunction('Architect'));

```

Output:

`Hello, Architect! Welcome to the world of modules.`

---

### **(B) Importing an Object (Multiple Exports)**

`// server.js const mathUtils = require('./utils.js'); console.log(mathUtils.add(5, 3)); // 8  // OR destructure directly const { add, subtract } = require('./utils.js'); console.log(subtract(10, 4)); // 6`

---

### **Key Points**

- Always include `./` when importing **local** files.
    
    - ✅ `require('./utils.js')`
        
    - ❌ `require('utils')` (this looks for a package in node_modules)
        
- `require()` executes the module once and **caches** it — efficient reuse.
    

---

## **6️⃣ Benefits of Modularity**

|Benefit|Description|
|---|---|
|**Organization**|Keeps project clean and structured.|
|**Reusability**|Write once, use anywhere.|
|**Maintainability**|Isolated modules make debugging easier.|
|**Collaboration**|Multiple developers can work on separate files safely.|

---

## **7️⃣ Node.js File System Module (fs)**

### **Definition**

The **fs (File System)** module allows Node.js to interact with the computer’s file system — to read, write, delete, or modify files and directories.

---

### **Versions**

|Type|Syntax Style|Status|
|---|---|---|
|**fs (callback-based)**|Uses callbacks|Older style|
|**fs.promises**|Uses Promises|✅ Modern and works with `async/await`|

> Always prefer `fs.promises` for modern Node.js code.

---

## **8️⃣ Reading Files Using fs.promises**

### **Setup**

Create a file `data.txt`:

`This is a secret message from the file system!`

Now create `server.js`:

`// server.js const fs = require('fs').promises; // Import the Promise-based fs  async function readFileContent() {   try {     const data = await fs.readFile('data.txt', 'utf8'); // Read as text     console.log("File content:", data);   } catch (error) {     console.error("Error reading the file:", error);   } }  readFileContent();`

### **Explanation**

|Function|Description|
|---|---|
|`fs.readFile(path, encoding)`|Reads file content. Returns a Promise.|
|`utf8`|Decodes binary data into readable text.|
|`await`|Waits until the file is read before continuing.|

**Output:**

`File content: This is a secret message from the file system!`

---

## **9️⃣ Combining Modules + File System (Practical Integration)**

Goal: Build a modular server that reads a message from a text file and serves it over HTTP.

---

### **Step 1: Create greeting.txt**

`Hello from a modular server!`

---

### **Step 2: utils.js**

`const fs = require('fs').promises;  // Exported async function that reads greeting from file async function getGreeting() {   try {     const message = await fs.readFile('greeting.txt', 'utf8');     return message;   } catch (error) {     console.error("Error reading greeting:", error);   } }  module.exports = { getGreeting };`

---

### **Step 3: server.js**

`const http = require('http'); const { getGreeting } = require('./utils.js');  const server = http.createServer(async (req, res) => {   const greeting = await getGreeting(); // Read message from file   res.writeHead(200, { 'Content-Type': 'text/plain' });   res.end(greeting); });  server.listen(3000, () => {   console.log('Server running on http://localhost:3000'); });`

**Output (on visiting browser):**

`Hello from a modular server!`

---

## **🔟 Assignment: Reading and Parsing JSON**

### **Task**

- Create `data.json` with structured data.
    
- Use `fs.promises.readFile()` to read it.
    
- Convert text to an object using `JSON.parse()`.
    

**Example:**

`const fs = require('fs').promises;  async function readJSON() {   const data = await fs.readFile('data.json', 'utf8');   const parsed = JSON.parse(data);   console.log(parsed); }  readJSON();`

**data.json**

`{   "name": "Kalvium",   "course": "Full Stack Web Development" }`

**Output**

`{ name: 'Kalvium', course: 'Full Stack Web Development' }`

---

## **1️⃣1️⃣ Key Concepts Recap**

|Concept|Definition|
|---|---|
|**Modularity**|Organizing code into small, reusable parts (modules).|
|**CommonJS**|Node.js’s module system using `module.exports` and `require()`.|
|**module.exports**|Defines what a file makes available for import.|
|**require()**|Imports code from another module or core library.|
|**fs Module**|Node.js core module for file operations.|
|**fs.promises**|Modern, async/await-based version of fs.|
|**fs.readFile()**|Reads the contents of a file asynchronously.|
|**JSON.parse()**|Converts JSON text into a JavaScript object.|

---

## **1️⃣2️⃣ New Terms & Keywords**

|Keyword|Meaning|
|---|---|
|**Module**|Independent file containing reusable code.|
|**CommonJS**|Node.js’s native module format.|
|**module.exports**|Object used to export code from a module.|
|**require()**|Function used to import code into another file.|
|**fs (File System)**|Node.js core module for interacting with files.|
|**fs.promises**|Promise-based file system API for async/await use.|
|**fs.readFile()**|Reads data from a file asynchronously.|
|**JSON.parse()**|Parses JSON-formatted text into an object.|
|**Async/Await**|Modern syntax for handling Promises cleanly.|

---

## **1️⃣3️⃣ Summary**

✅ **Modules** let you split logic into reusable, organized files.  
✅ **CommonJS system** powers imports/exports with `module.exports` and `require()`.  
✅ **fs module** allows Node.js to access and manipulate the file system.  
✅ **fs.promises** provides modern async/await support for non-blocking I/O.  
✅ Reading and parsing files (including `.json`) is essential in backend systems.  
✅ Combining modules and fs enables real-world, data-driven backend logic.