# JavaScript – Fetch & Axios

## 🎯 Learning Objectives

- Understand what an **API** is and how it works.
- Use the **Fetch API** to make GET requests.
- Handle **JSON responses & errors** with Fetch.
- Use **Axios** for simpler and more powerful API requests.
- Practice fetching and displaying **real data** in JavaScript.

---

## 🔹 1. What is an API?

- **API (Application Programming Interface)** → allows one program to talk to another.
- Analogy: **Ordering food online** → you send a request, restaurant sends back food (data).
- In JS → APIs let your app fetch, send, and update data from servers.

---

## 🔹 2. Fetch API (Built-in)

### Syntax Example:

```js
fetch("https://jsonplaceholder.typicode.com/posts/1")   
.then(response => response.json())   
.then(data => {     console.log("Post Title:", data.title);   })   .catch(error => {     console.error("Error fetching data:", error);   });
```

### Explanation:

- `fetch(url)` → sends GET request.
- `response.json()` → parses response into JS object.
- `.then(data => …)` → works with actual data.
- `.catch(error => …)` → handles errors.

---

## 🔹 3. Fetching Multiple Items

```js
fetch("https://jsonplaceholder.typicode.com/posts")   
.then(response => response.json())   
.then(posts => {     posts.forEach(post => {       
	console.log(post.title);     
	});   
});
```

- Useful for lists → **blog posts, products, users, etc.**

---

## 🔹 4. Axios (3rd-Party Library)

- Axios simplifies API requests.
- Automatically parses JSON.
- Works in older browsers.
- Easier to send headers or post data.

### Include Axios

```js
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
```

### Example

```js
axios.get("https://jsonplaceholder.typicode.com/posts/1")   .then(response => {     console.log("Post Title:", response.data.title);   })   
.catch(error => {     console.error("Error fetching with Axios:", error);   });
```

**Key Difference**:

- Axios → data inside `response.data`.
- Fetch → need `response.json()`.

---

## 🔹 5. Real-world Example: User List

```js
fetch("https://jsonplaceholder.typicode.com/users")   
.then(response => response.json())   
.then(users => {     users.forEach(user => {  
		console.log(`${user.name} - ${user.email}`);     
	});   
});
```

👉 Use cases: **team members, students, customers, etc.**

---

## 🔹 6. Common API Request Types

- **GET** → fetch data.
- **POST** → send new data.
- **PUT/PATCH** → update existing data.
- **DELETE** → remove data.

_(Both Fetch & Axios support all request types.)_

---

## 🔹 7. Interactive Exercises

1. Use **Fetch** → get users from `https://jsonplaceholder.typicode.com/users` and log all usernames.
2. Use **Axios** → fetch a post by ID and print the title.
3. Use **Fetch** → handle an error (wrong URL) and log a custom error message.
4. **Bonus** → Create a search bar that fetches posts containing a keyword.

---

## 🔹 8. Summary

- APIs let JS **talk to servers** → fetch & send data.
- **Fetch API** → built-in, returns Promises.
- **Axios** → simplifies API work, automatically parses JSON.
- Both allow **GET, POST, PUT, DELETE** requests.
- Useful for **dynamic, real-world applications**.

---

## 🔹 9. Useful Resources

- MDN – Fetch API
- [Axios GitHub](https://github.com/axios/axios?utm_source=chatgpt.com)
- [JSONPlaceholder test API](https://jsonplaceholder.typicode.com/?utm_source=chatgpt.com)
```embed
title: "API Tutorial - Fetch Data with Axios - (Example in React)"
image: "https://i.ytimg.com/vi/bMRrSqWFKqM/maxresdefault.jpg"
description: "Tutorial on how to make API calls to fetch data using axios. I'm using React in this example, but you'll know how to use axios anywhere 👍.Hope it helps! Fee..."
url: "https://youtu.be/bMRrSqWFKqM"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "Learn Fetch API In 6 Minutes"
image: "https://i.ytimg.com/vi/cuEtnrL9-H0/maxresdefault.jpg"
description: "Accessing data from an API is one of the most common things you will do in web development, and the way to access APIs is with fetch. Fetch is function built..."
url: "https://youtu.be/cuEtnrL9-H0"
favicon: ""
aspectRatio: "56.25"
```
