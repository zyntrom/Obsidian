# **1.23 — Client-Side Form Validation and Error Handling (React)**

---

## **1️⃣ Introduction**

Client-side validation ensures **user input is checked instantly in the browser** before submission.  
It improves usability, reduces server requests, and makes forms responsive and accessible.

> ⚠️ **Note:** Client-side validation improves user experience but **does not replace server-side validation** (which ensures security).

---

## **2️⃣ Why Client-Side Validation Matters**

|Advantage|Description|
|---|---|
|**Instant feedback**|Errors appear as user types — no reloads.|
|**Better UX**|Prevents frustration from failed submissions.|
|**Reduced server load**|Invalid data never reaches backend.|
|**Accessibility**|Screen readers can announce validation errors in real-time.|

---

## **3️⃣ The Validation Workflow**

```bash
User types → Event triggers → Validation runs → Error state updates → UI re-renders → Button enables/disables
```
✅ **Goal:** Keep data valid _before_ it’s submitted.

---

## **4️⃣ Building Blocks of Client-Side Validation**

### **(1) State Management — Track everything**

We need to track:

- Input values
- Error messages
- Form validity

```js
const [username, setUsername] = useState('');
const [usernameError, setUsernameError] = useState('');
const [isFormValid, setIsFormValid] = useState(false);
```

---

### **(2) Validation Logic — Define the rules**

Each input has validation criteria.  
Example rules:

```js
if (value.trim() === '') {
  setError('This field is required.');
} else if (value.length < 6) {
  setError('Must be at least 6 characters.');
} else if (value.length > 20) {
  setError('Cannot exceed 20 characters.');
} else if (!/\d/.test(value)) {
  setError('Must contain at least one number.');
} else {
  setError(''); // ✅ Valid input
}

```

---

### **(3) useEffect — Trigger validation automatically**

`useEffect()` re-runs when input values change, automatically validating the form in real-time.

```js
useEffect(() => {
  let hasErrors = false;

  if (username.trim() === '') {
    setUsernameError('Username is required.');
    hasErrors = true;
  } else if (username.length < 3) {
    setUsernameError('Username must be at least 3 characters.');
    hasErrors = true;
  } else {
    setUsernameError('');
  }

  if (age === '' || age === 0) {
    setAgeError('Age is required.');
    hasErrors = true;
  } else if (age < 18) {
    setAgeError('You must be 18 or older.');
    hasErrors = true;
  } else {
    setAgeError('');
  }

  setIsFormValid(!hasErrors); // Only valid if no errors
}, [username, age]); // Dependencies

```

✅ Dependencies array ensures the validation re-runs when any input changes.

---

### **(4) Conditional Rendering — Show errors only when needed**

Render messages dynamically:

```js
{usernameError && <p className="error">{usernameError}</p>}
```

Apply dynamic class names to highlight invalid fields:

```js
<input
  className={usernameError ? 'input-error' : ''}
  value={username}
  onChange={(e) => setUsername(e.target.value)}
/>
```

---

### **(5) Button State — Disable until valid**

```js
<button type="submit" disabled={!isFormValid}>
  Sign Up
</button>

```

✅ Prevents invalid form submission.

---

## **5️⃣ Accessibility in Form Validation**

Use **ARIA attributes** so screen readers can interpret errors correctly:

```js
<input
  type="text"
  id="username"
  aria-invalid={usernameError ? "true" : "false"}
  aria-describedby={usernameError ? "username-error" : undefined}
/>

{usernameError && (
  <p id="username-error" className="error">{usernameError}</p>
)}
```

|Attribute|Purpose|
|---|---|
|`aria-invalid`|Marks input as invalid when true|
|`aria-describedby`|Links input with its error message|

---

## **6️⃣ Common Validation Rules**

|Rule|Check|Example Error Message|
|---|---|---|
|**Required**|`value.trim() === ''`|"This field is required."|
|**Min length**|`value.length < minLength`|"Must be at least X characters."|
|**Max length**|`value.length > maxLength`|"Cannot exceed X characters."|
|**Number range**|`value < min||
|**Contains character**|`!value.includes(char)`|"Must contain X."|
|**Regex pattern**|`!/pattern/.test(value)`|"Invalid format."|

---

## **7️⃣ Example — Username Validator**

Reusable function for validating multiple rules:

```js
function validateUsername(username) {
  if (username.trim() === '') return 'Username cannot be empty.';
  if (username.length < 3) return 'Username must be at least 3 characters.';
  if (username.length > 15) return 'Username cannot exceed 15 characters.';
  if (!/^[a-zA-Z0-9_]+$/.test(username))
    return 'Username can only contain letters, numbers, and underscores.';
  return ''; // ✅ Valid input
}

```

Used in component:

```js
useEffect(() => {
  const error = validateUsername(username);
  setUsernameError(error);
  setIsFormValid(error === '');
}, [username]);
```

---

## **8️⃣ Validation Strategies**

|Strategy|Description|Best Use|
|---|---|---|
|**Validate on Change**|Validate after every keystroke|Real-time forms|
|**Validate on Blur**|Validate when input loses focus|Less intrusive|
|**Hybrid**|Validate only after user touches input once|Professional UX|

**Hybrid Example:**

```js
const [touched, setTouched] = useState(false);

useEffect(() => {
  if (touched) validateField(value);
}, [value, touched]);

<input
  onBlur={() => setTouched(true)}
  onChange={(e) => setValue(e.target.value)}
/>
```

---

## **9️⃣ Putting It All Together – Validated Login Form**

```js
function LoginForm() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [emailError, setEmailError] = useState('');
  const [passwordError, setPasswordError] = useState('');
  const [isFormValid, setIsFormValid] = useState(false);

  useEffect(() => {
    const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    let valid = true;

    if (!emailPattern.test(email)) {
      setEmailError('Invalid email format.');
      valid = false;
    } else setEmailError('');

    if (password.length < 6) {
      setPasswordError('Password must be at least 6 characters.');
      valid = false;
    } else setPasswordError('');

    setIsFormValid(valid);
  }, [email, password]);

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!isFormValid) return;
    alert('Form submitted!');
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="email"
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        aria-invalid={!!emailError}
        aria-describedby="email-error"
        placeholder="Email"
      />
      {emailError && <p id="email-error">{emailError}</p>}

      <input
        type="password"
        value={password}
        onChange={(e) => setPassword(e.target.value)}
        aria-invalid={!!passwordError}
        aria-describedby="password-error"
        placeholder="Password"
      />
      {passwordError && <p id="password-error">{passwordError}</p>}

      <button disabled={!isFormValid}>Login</button>
    </form>
  );
}

```

✅ Features:

- Real-time validation
- Clear error messages
- Accessible inputs
- Button disabled until valid

---

## **🔟 Common Mistakes and Fixes**

|Mistake|Cause|Fix|
|---|---|---|
|Not clearing old errors|Forgot to reset when valid|Always set `setError('')` when input becomes valid|
|Missing dependencies in `useEffect`|Only some fields trigger validation|Include **all** validated fields|
|Treating empty input as invalid format|Order of checks wrong|Check “empty” first, then pattern|
|Page reload on submit|No `preventDefault()`|Always use `e.preventDefault()`|
|Hardcoded button enable|No link to validity state|Use `disabled={!isFormValid}`|

---

## **1️⃣1️⃣ Cheat Sheet – Quick Reference**

```js
// State setup
const [value, setValue] = useState('');
const [error, setError] = useState('');
const [isValid, setIsValid] = useState(false);

// Validation logic
useEffect(() => {
  if (value === '') setError('Required field');
  else if (value.length < 3) setError('Too short');
  else setError('');
  setIsValid(error === '');
}, [value]);

// Conditional rendering
{error && <p className="error">{error}</p>}

// Accessibility
<input
  aria-invalid={!!error}
  aria-describedby={error ? "error-id" : undefined}
/>

// Button
<button disabled={!isValid}>Submit</button>

```
---

## **1️⃣2️⃣ Summary – Key Takeaways**

|Concept|Description|
|---|---|
|**Validation Goal**|Catch errors before submission|
|**State variables**|Track values, errors, validity|
|**useEffect**|Runs validation automatically|
|**Conditional Rendering**|Shows/hides messages dynamically|
|**Button Control**|Prevents invalid submissions|
|**Accessibility**|Use `aria-invalid` and `aria-describedby`|
|**Hybrid Validation**|Combines best of real-time + blur strategies|

---

## **1️⃣3️⃣ References**

- React Docs: [Forms](https://react.dev/reference/react-dom/components/input)
- React Docs: [useEffect Hook](https://react.dev/reference/react/useEffect)
- W3C: [Accessible Form Validation Techniques](https://www.w3.org/WAI/tutorials/forms/validation/)