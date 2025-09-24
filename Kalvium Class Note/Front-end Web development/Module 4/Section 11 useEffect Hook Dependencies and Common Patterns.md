# ⚛️ React `useEffect` Hook: Dependencies & Common Patterns

## 🎯 Learning Objectives

- Understand what the **dependency array** in `useEffect` is for.
- Learn how it improves **performance & control**.
- Explore **common patterns** (data fetching, subscriptions).
- Recognize and **avoid common mistakes**.

---

## 1️⃣ What is the Dependency Array?

The **dependency array** is the second argument in `useEffect`.

```js
useEffect(() => {   
	// Side effect logic 
}, [/* dependencies */]);
```

### 🔹 How it works:

- **Empty `[]`** → Runs **only once**, after initial mount.
- **With dependencies `[x, y]`** → Runs whenever **x or y changes**.
- **No array** → Runs **after every render** (⚠️ often inefficient).

👉 Think of it like watering a plant: you don’t water it all the time, only when the soil is dry (dependencies change).

---

## 2️⃣ Why Use a Dependency Array?

- ✅ **Better performance** → avoids running unnecessarily.
- ✅ **Avoids infinite loops** → prevents repeated execution.
- ✅ **Controls side effects** → ensures actions happen at the right time.

---

## 3️⃣ Examples of Dependency Array Usage

### a) Empty Dependency Array

```js
useEffect(() => {   
	console.log("Component mounted"); 
}, []);
```

- Runs **once** when component first loads.
- Great for **initial setup** (fetch once, start a connection, etc.).

---

### b) With Values (State or Props)

```js
function Greeting({ name }) {   
	const [message, setMessage] = useState("");    
	useEffect(() => {     
		setMessage(`Hello, ${name}!`);   
	}, [name]); // Runs only when 'name' changes    return <p>{message}</p>; }
```

- Runs whenever **name** changes.
- Avoids re-running when `name` stays the same.
- Prevents unnecessary renders and loops.

⚠️ Without `[name]`, effect would run **after every render** → wasteful or buggy.

---

## 4️⃣ Common Patterns

### a) **Data Fetching**

```js
useEffect(() => {   
	async function fetchProducts() {     
		const res = await fetch(`https://api.example.com/products?category=${categoryId}`);     
		const data = await res.json();     
		setProducts(data);   }    fetchProducts(); }, [categoryId]); // runs when categoryId changes
```

- Fetches products only when **categoryId** changes.
    
- Prevents unnecessary API calls.
    

---

### b) **Subscriptions (WebSockets, Firebase, etc.)**

`function ChatRoom({ roomId }) {   const [messages, setMessages] = useState([]);    useEffect(() => {     const subscription = chatService.subscribeToMessages(       roomId,       message => setMessages(prev => [...prev, message])     );      return () => {       subscription.unsubscribe();     };   }, [roomId]);    return (     <ul>       {messages.map(msg => (         <li key={msg.id}>{msg.text}</li>       ))}     </ul>   ); }`

- Subscribes when `roomId` changes.
    
- **Cleanup** unsubscribes old room to prevent memory leaks.
    
- Ensures we only listen to the correct chat room.
    

---

## 5️⃣ Common Mistakes & Fixes

|❌ Mistake|⚠️ Problem|✅ Fix|
|---|---|---|
|Missing dependencies|Uses outdated (stale) data|Add all values effect depends on|
|Too many dependencies|Runs too often, slows down|Only include what’s necessary|
|No dependency array|Effect runs after every render|Add `[]` or proper deps|
|Infinite loops|Effect updates state → triggers rerender → effect again|Use correct dependency control|

---

## 🎯 Summary

- Dependency array = **controls when useEffect runs**.
    
- **Empty `[]`** → run once on mount.
    
- **With values `[x]`** → run only when `x` changes.
    
- **No array** → runs after every render.
    
- **Common patterns** → API fetch, subscriptions, conditional updates.
    
- **Best practice** → include only true dependencies to avoid stale data & infinite loops.