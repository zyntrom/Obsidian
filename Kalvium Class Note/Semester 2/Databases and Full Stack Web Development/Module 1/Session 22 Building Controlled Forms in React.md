# **1.22 – Building Controlled Forms in React**

---

## **1️⃣ Introduction**

In React, **controlled components** are form inputs (like `<input>`, `<textarea>`, `<select>`) whose values are **fully managed by React state**.  
This means React always knows what is typed, checked, or selected in real time.

**Key concept:**

> React state = Single Source of Truth for all form data.

---

## **2️⃣ Controlled vs Uncontrolled Forms**

|Feature|Controlled Form|Uncontrolled Form|
|---|---|---|
|Data storage|In React state (`useState`)|In the DOM (browser memory)|
|React awareness|React knows every value change|React only knows values on form submit|
|Validation|Easy and real-time|Harder, needs DOM queries|
|Reset / Dynamic control|Simple with `setState`|Requires manual DOM handling|
|Example use|Login forms, dynamic validation|Simple static forms|

---

## **3️⃣ Core Concept – The Single Source of Truth**

Every input’s value is stored in React state.  
React passes that value _back_ to the input via the `value` prop.  
User → `onChange` → Update state → React re-renders → Input shows new value.

**Flow:**

```bash
User types → onChange() fires → setState() updates → React re-renders → input displays latest state

```
---

## **4️⃣ The Three Pillars of Controlled Components**

### **1. State Variable**

Defines and stores the real value.

```js
const [username, setUsername] = useState('');
```

### **2. Value Binding**

Connects the state to the input display.

```js
<input value={username} />
```

### **3. onChange Handler**

Captures user input and updates the state.

```js
<input   value={username}   onChange={(e) => setUsername(e.target.value)} />
```

✅ **All three must exist** — missing any breaks the control chain.

---

## **5️⃣ Example – Live Character Counter**

Demonstrates real-time feedback using controlled inputs.

```js
function TweetBox() {
  const [tweet, setTweet] = useState('');
  const maxLength = 280;
  const remaining = maxLength - tweet.length;

  return (
    <div>
      <textarea
        value={tweet}
        onChange={(e) => setTweet(e.target.value)}
        maxLength={maxLength}
      />
      <p>Characters remaining: {remaining}</p>
      <button disabled={tweet.length === 0}>Post Tweet</button>
    </div>
  );
}
```

**Concepts demonstrated:**

- React knows the exact number of characters typed.
- The button’s state depends on current input.
- No DOM query needed — all managed through React state.

---

## **6️⃣ The Event Object (e)**

When `onChange` fires, React passes an **event object** with details of the change.

Example:

```js
const handleChange = (e) => {
  console.log(e.target.value); // Input value
  console.log(e.target.name);  // Input name
  console.log(e.target.type);  // Input type (text/email/etc)
};

```

**Use case:** Handling multiple inputs using one handler.

`const [formData, setFormData] = useState({ email: '', password: '' });  const handleChange = (e) => {   setFormData({     ...formData,     [e.target.name]: e.target.value,   }); };  // Inputs <input name="email" value={formData.email} onChange={handleChange} /> <input name="password" value={formData.password} onChange={handleChange} />`

This uses **computed property names** (`[e.target.name]`) to dynamically update the correct key.

---

## **7️⃣ Different Input Types in Controlled Components**

|Input Type|Key Property|Example|
|---|---|---|
|**Text input**|`value`|`<input type="text" value={name} onChange={handleChange} />`|
|**Textarea**|`value` (not children like in HTML)|`<textarea value={bio} onChange={handleChange} />`|
|**Select**|`value`|`<select value={country} onChange={handleChange}>...</select>`|
|**Checkbox**|`checked` (not value)|`<input type="checkbox" checked={isChecked} onChange={(e) => setIsChecked(e.target.checked)} />`|

---

## **8️⃣ Common Mistakes and Fixes**

|Mistake|Example|Fix|
|---|---|---|
|Forgetting `onChange` → input becomes read-only|`<input value={name} />`|Add `onChange={(e) => setName(e.target.value)}`|
|Setting event instead of value|`setName(e)`|Use `setName(e.target.value)`|
|Typo in variable names|`username` vs `userName`|Keep consistent naming|
|Using `value` instead of `checked` for checkboxes|`<input value={isChecked} />`|Use `checked={isChecked}`|

---

## **9️⃣ Why Controlled Forms Are Important**

|Benefit|Description|
|---|---|
|**Real-time validation**|Validate inputs as user types (e.g. email format).|
|**Dynamic UI updates**|Enable/disable buttons, show messages instantly.|
|**Form management**|Track if all fields are filled before submit.|
|**Easy reset**|Reset all fields using one state update.|
|**Predictability**|React always knows the exact form data.|

Controlled components = full synchronization between UI and state.

---

## **🔟 Real Example – Login Form**

`function LoginForm() {   const [email, setEmail] = useState('');   const [password, setPassword] = useState('');      const isValid = email.includes('@') && password.length >= 6;    return (     <form>       <input         type="email"         value={email}         onChange={(e) => setEmail(e.target.value)}         placeholder="Email"       />        <input         type="password"         value={password}         onChange={(e) => setPassword(e.target.value)}         placeholder="Password"       />        <button disabled={!isValid}>Login</button>       <p>{!isValid && "Please enter valid email and password (min 6 chars)"}</p>     </form>   ); }`

**Working:**

1. `onChange` triggers on typing.
    
2. State updates instantly.
    
3. React re-renders with new values.
    
4. Validation and UI update in real time.
    

---

## **1️⃣1️⃣ One Handler for Multiple Inputs (Best Practice)**

`const [formData, setFormData] = useState({   name: '',   email: '' });  const handleChange = (e) => {   setFormData({     ...formData,     [e.target.name]: e.target.value,   }); };  return (   <form>     <input name="name" value={formData.name} onChange={handleChange} />     <input name="email" value={formData.email} onChange={handleChange} />   </form> );`

✅ Clean  
✅ Scalable  
✅ Easy for multi-input forms

---

## **1️⃣2️⃣ Summary – Key Takeaways**

|Concept|Summary|
|---|---|
|Controlled Component|Input whose value is managed by React state|
|State variable|Stores the true current value|
|Value binding|`value={stateVariable}` ensures UI sync|
|onChange handler|Updates state when user types|
|Event object|Contains `target.value`, `target.name`, etc.|
|Multiple inputs|Use `name` + dynamic property updates|
|Checkboxes|Use `checked` and `e.target.checked`|
|Validation|Implement directly from state logic|

---

## **1️⃣3️⃣ Quick Checklist (Before Exam)**

-  Do I know what “controlled” means in React?
    
-  Can I create state variables with `useState()`?
    
-  Can I connect `value` and `onChange` correctly?
    
-  Can I handle multiple inputs dynamically?
    
-  Do I know difference between `checked` and `value`?
    
-  Can I explain why controlled components are preferred?
    

---

## **References**

- React Docs: Controlled Components
    
- [React Docs: Forms](https://react.dev/reference/react-dom/components/input)
    
- [useState Hook](https://react.dev/reference/react/useState)