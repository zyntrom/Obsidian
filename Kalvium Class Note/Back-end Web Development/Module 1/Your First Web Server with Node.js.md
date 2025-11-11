# ✅ **1. Introduction: What You Are Building**

A Node.js **web server** is a program that:

- Listens for incoming HTTP requests.
- Processes those requests.
- Sends back HTTP responses.

Node provides the **http** core module for creating servers. No installation is required.

---

# ✅ **2. Importing the http Module**

### **Code**

```js
const http = require('http');
```

### **Explanation**

- `require('http')` loads Node’s built-in HTTP functionalities.
- The `http` object provides methods such as:
    - `createServer()`
    - `request()`
    - `get()`

---

# ✅ **3. Creating the Server**

### **Code**

```js
const server = http.createServer((req, res) => { });
```

### **Explanation**

`http.createServer()` does two things:

1. **Creates a server instance**.
2. **Accepts a callback function** that runs every time a request arrives.

The callback receives **two arguments**:

- `req` (request object)
- `res` (response object)

This function defines how the server responds to any incoming request.

---

# ✅ **4. The Request Object (`req`)**

`req` contains complete details about the incoming HTTP request.

Important properties:

- `req.url`  
    Path requested by the client (example: `/`, `/about`).
- `req.method`  
    HTTP method: GET, POST, PUT, DELETE.
- `req.headers`  
    Metadata sent by the client (browser type, content type, etc.).
- `req` may also contain:
    - Request body (for POST/PUT)
    - Query parameters

For this simple server, we do not use `req` deeply, but in real applications it determines the route and logic.

---

# ✅ **5. The Response Object (`res`)**

`res` provides methods to send data back to the client.

Main methods:

### **1. res.writeHead(statusCode, headers)**

Sets:

- HTTP status code
- Response headers

Example:

```js
res.writeHead(200, { 'Content-Type': 'text/plain' });
```

### **2. res.end(body)**

- Writes response body.
    
- Finalizes and sends the response.  
    Once `res.end()` runs, the response is finished.

Example:

```js
res.end('Hello, World!');
```

---

# ✅ **6. Writing the Complete Response**

### **Code**

```js
const server = http.createServer((req, res) => {   
	res.writeHead(200, { 'Content-Type': 'text/plain' });
	res.end('Hello, World!'); 
});
```

### **Explanation**

- Status code **200** means "OK" (successful request).
- `'Content-Type': 'text/plain'` tells the browser we're sending plain text.
- `'Hello, World!'` is the actual response body.

---

# ✅ **7. Listening on a Port**

### **Code**

```js
server.listen(3000, () => {   
	console.log(`Server running at http://localhost:3000/`); 
});
```

### **Explanation**

- `server.listen(PORT)` tells the server to start listening for requests.
- Port **3000** is commonly used for local development.
- The callback runs once the server starts successfully.
- As long as the server is running, your terminal will not exit.  
    (This is expected; it's waiting for incoming requests.)

---

# ✅ **8. Full server.js Example (Minimal HTTP Server)**

```js
const http = require('http');  
const server = http.createServer((req, res) => {   
	res.writeHead(200, { 'Content-Type': 'text/plain' });
	res.end('Hello, World!'); 
});  
server.listen(3000, () => { 
	console.log(`Server running at http://localhost:3000/`); 
});
```

---

# ✅ **9. Running the Server**

Commands:

```bash
node server.js
```

Open browser and go to:

```
http://localhost:3000
```

Output:

`Hello, World!`

Stop server:

`Ctrl + C`

---

# ✅ **10. Assignment Answers (req and res Explanation)**

### **req (Request Object)**

- Represents the incoming HTTP request.
    
- Contains details like:
    
    - URL path (`req.url`)
        
    - HTTP method (`req.method`)
        
    - Headers (`req.headers`)
        
    - Body data (for POST/PUT)
        
- Used to determine what the client is asking for.
    

### **res (Response Object)**

- Represents the outgoing HTTP response.
    
- Contains methods to build and send the reply.
    
- Main methods:
    
    - `res.writeHead()` to set status code and headers.
        
    - `res.end()` to send the body and finish the response.
        
- Used to control exactly what is returned to the client.