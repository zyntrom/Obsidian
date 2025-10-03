# 🌐 6.6 React Router: Dynamic Routes & URL Parameters

---

## 🔹 Overview

- **Dynamic Routes:** Routes with parameters in the URL, allowing **multiple similar pages with a single route**
- **URL Parameters:** Changeable parts of the URL that components can read and use to display content
- Common use cases: **User profiles, product pages, blog posts**

---

## 🔹 Why Dynamic Routes?

|Benefit|Explanation|
|---|---|
|Flexibility|Handle many similar pages with one route|
|Efficiency|No need to define separate routes for each page|
|Maintainability|Easier updates & management|
|User Experience|Seamless browsing with dynamic content|

---

## 🔹 Defining Dynamic Routes

- Use **colon `:`** followed by parameter name in `path`

**Example: Product Page**

```js
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import Product from './Product';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/product/:id" element={<Product />} />
      </Routes>
    </BrowserRouter>
  );
}

```

- `/product/:id` matches `/product/123`, `/product/456`, etc.
- `:id` is a **dynamic segment** of the URL

---

## 🔹 Extracting URL Parameters

- Use the **`useParams` hook** from `react-router-dom`

```js
import { useParams } from 'react-router-dom';

function Product() {
  const { id } = useParams();

  return (
    <div>
      <h2>Product Details</h2>
      <p>Product ID: {id}</p>
    </div>
  );
}

```
- `useParams()` returns an object containing **all route parameters**
- Example: URL `/product/456` → `{ id: "456" }`

---

## 🔹 Using URL Parameters for Dynamic Content

- Fetch data or render content based on the parameter

```js
import { useState, useEffect } from 'react';
import { useParams } from 'react-router-dom';

function Product() {
  const { id } = useParams();
  const [product, setProduct] = useState(null);

  useEffect(() => {
    fetch(`https://api.example.com/products/${id}`)
      .then(res => res.json())
      .then(data => setProduct(data));
  }, [id]);

  if (!product) return <p>Loading...</p>;

  return (
    <div>
      <h2>{product.name}</h2>
      <p>{product.description}</p>
      <p>Price: ${product.price}</p>
    </div>
  );
}

```

- URL parameter controls **which data is fetched and displayed**

---

## 🔹 Real-World Example: User Profiles

```js
function UserProfile() {
  const { userId } = useParams();
  const [user, setUser] = useState(null);

  useEffect(() => {
    fetch(`https://api.example.com/users/${userId}`)
      .then(res => res.json())
      .then(data => setUser(data));
  }, [userId]);

  if (!user) return <p>Loading...</p>;

  return (
    <div>
      <h2>{user.name}</h2>
      <p>Email: {user.email}</p>
      <p>Bio: {user.bio}</p>
    </div>
  );
}

```

- URL `/users/101` → displays profile for **user 101**
    

---

## 🔹 Common Pitfalls

|Mistake|Fix|
|---|---|
|Missing colon (`/product/id`)|Use `/product/:id`|
|Name mismatch|Parameter names in `path` must match `useParams`|
|Invalid/non-existent IDs|Handle missing data gracefully|
```embed
title: "Fetching"
image: "data:image/svg+xml;base64,PHN2ZyBjbGFzcz0ibGRzLW1pY3Jvc29mdCIgd2lkdGg9IjgwcHgiICBoZWlnaHQ9IjgwcHgiICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxMDAgMTAwIiBwcmVzZXJ2ZUFzcGVjdFJhdGlvPSJ4TWlkWU1pZCI+PGcgdHJhbnNmb3JtPSJyb3RhdGUoMCkiPjxjaXJjbGUgY3g9IjgxLjczNDEzMzYxMTY0OTQxIiBjeT0iNzQuMzUwNDU3MTYwMzQ4ODIiIGZpbGw9IiNlMTViNjQiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM0MC4wMDEgNDkuOTk5OSA1MCkiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49IjBzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9Ijc0LjM1MDQ1NzE2MDM0ODgyIiBjeT0iODEuNzM0MTMzNjExNjQ5NDEiIGZpbGw9IiNmNDdlNjAiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM0OC4zNTIgNTAuMDAwMSA1MC4wMDAxKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMDYyNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iNjUuMzA3MzM3Mjk0NjAzNiIgY3k9Ijg2Ljk1NTE4MTMwMDQ1MTQ3IiBmaWxsPSIjZjhiMjZhIiByPSI1IiB0cmFuc2Zvcm09InJvdGF0ZSgzNTQuMjM2IDUwIDUwKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMTI1cyI+PC9hbmltYXRlVHJhbnNmb3JtPgo8L2NpcmNsZT48Y2lyY2xlIGN4PSI1NS4yMjEwNDc2ODg4MDIwNyIgY3k9Ijg5LjY1Nzc5NDQ1NDk1MjQxIiBmaWxsPSIjYWJiZDgxIiByPSI1IiB0cmFuc2Zvcm09InJvdGF0ZSgzNTcuOTU4IDUwLjAwMDIgNTAuMDAwMikiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49Ii0wLjE4NzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9IjQ0Ljc3ODk1MjMxMTE5NzkzIiBjeT0iODkuNjU3Nzk0NDU0OTUyNDEiIGZpbGw9IiM4NDliODciIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDM1OS43NiA1MC4wMDY0IDUwLjAwNjQpIj4KICA8YW5pbWF0ZVRyYW5zZm9ybSBhdHRyaWJ1dGVOYW1lPSJ0cmFuc2Zvcm0iIHR5cGU9InJvdGF0ZSIgY2FsY01vZGU9InNwbGluZSIgdmFsdWVzPSIwIDUwIDUwOzM2MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiIGJlZ2luPSItMC4yNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iMzQuNjkyNjYyNzA1Mzk2NDE1IiBjeT0iODYuOTU1MTgxMzAwNDUxNDciIGZpbGw9IiNlMTViNjQiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDAuMTgzNTUyIDUwIDUwKSI+CiAgPGFuaW1hdGVUcmFuc2Zvcm0gYXR0cmlidXRlTmFtZT0idHJhbnNmb3JtIiB0eXBlPSJyb3RhdGUiIGNhbGNNb2RlPSJzcGxpbmUiIHZhbHVlcz0iMCA1MCA1MDszNjAgNTAgNTAiIHRpbWVzPSIwOzEiIGtleVNwbGluZXM9IjAuNSAwIDAuNSAxIiByZXBlYXRDb3VudD0iaW5kZWZpbml0ZSIgZHVyPSIxLjVzIiBiZWdpbj0iLTAuMzEyNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT4KPC9jaXJjbGU+PGNpcmNsZSBjeD0iMjUuNjQ5NTQyODM5NjUxMTc2IiBjeT0iODEuNzM0MTMzNjExNjQ5NDEiIGZpbGw9IiNmNDdlNjAiIHI9IjUiIHRyYW5zZm9ybT0icm90YXRlKDEuODY0NTcgNTAgNTApIj4KICA8YW5pbWF0ZVRyYW5zZm9ybSBhdHRyaWJ1dGVOYW1lPSJ0cmFuc2Zvcm0iIHR5cGU9InJvdGF0ZSIgY2FsY01vZGU9InNwbGluZSIgdmFsdWVzPSIwIDUwIDUwOzM2MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiIGJlZ2luPSItMC4zNzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxjaXJjbGUgY3g9IjE4LjI2NTg2NjM4ODM1MDYiIGN5PSI3NC4zNTA0NTcxNjAzNDg4NCIgZmlsbD0iI2Y4YjI2YSIgcj0iNSIgdHJhbnNmb3JtPSJyb3RhdGUoNS40NTEyNiA1MCA1MCkiPgogIDxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MzYwIDUwIDUwIiB0aW1lcz0iMDsxIiBrZXlTcGxpbmVzPSIwLjUgMCAwLjUgMSIgcmVwZWF0Q291bnQ9ImluZGVmaW5pdGUiIGR1cj0iMS41cyIgYmVnaW49Ii0wLjQzNzVzIj48L2FuaW1hdGVUcmFuc2Zvcm0+CjwvY2lyY2xlPjxhbmltYXRlVHJhbnNmb3JtIGF0dHJpYnV0ZU5hbWU9InRyYW5zZm9ybSIgdHlwZT0icm90YXRlIiBjYWxjTW9kZT0ic3BsaW5lIiB2YWx1ZXM9IjAgNTAgNTA7MCA1MCA1MCIgdGltZXM9IjA7MSIga2V5U3BsaW5lcz0iMC41IDAgMC41IDEiIHJlcGVhdENvdW50PSJpbmRlZmluaXRlIiBkdXI9IjEuNXMiPjwvYW5pbWF0ZVRyYW5zZm9ybT48L2c+PC9zdmc+"
description: "Fetching https://youtu.be/rb1GWqCJid4"
url: "https://youtu.be/rb1GWqCJid4"
favicon: ""
```

---

✅ **Key Takeaways**

- Dynamic routes allow **flexible, reusable route definitions**
- `useParams()` lets you **access URL parameters**
- Combine with **API calls or state** to render dynamic content
- Essential for **SPAs with user-specific or product-specific pages**