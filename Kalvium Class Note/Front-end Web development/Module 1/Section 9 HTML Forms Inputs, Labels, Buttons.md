## 🧠 Learning Outcomes

By the end of this, you should be able to:

- Understand what an HTML form does.
- Use `<input>` fields for collecting various kinds of data.
- Associate `<label>` tags with inputs for better usability.
- Add buttons to trigger actions like submit, reset, or custom JavaScript.
- Build complete, interactive forms!

---

## 🧾 1. What is an HTML Form?

- An HTML form is like a **questionnaire** inside a web page.
- It collects user input like names, emails, passwords, etc.
- Form data is typically sent to a **server** for processing.

### 🔧 Basic Structure

`<form>   <!-- form fields go here --> </form>`

---

## 🧩 2. Input Types — “Data Collectors”

The `<input>` tag is used to **collect** information.

### 🔑 Common Types

|Type|Purpose|
|---|---|
|`text`|Regular text (e.g., name)|
|`password`|Hidden/masked text (e.g., password)|
|`email`|Validates email format|
|`number`|Numeric input with spinner UI|
|`checkbox`|Allows multiple selections|
|`radio`|Only one selection in a group|
|`file`|File upload|
|`submit`|Submits the form|

### ✅ Example

`<form>   <input type="text" name="username">   <input type="email" name="email">   <input type="submit" value="Submit"> </form>`

---

## 🏷️ 3. Labels — “The Form’s Guideposts”

The `<label>` element **describes** what each input field is for.

### 🔗 Important: Use `for` and `id`

`<label for="email">Email:</label> <input type="email" id="email" name="email">`

- `for="email"` links the label to `<input id="email">`
- Clicking the label focuses the corresponding input

---

## 🔘 4. Buttons — “Trigger the Action”

There are **3 types** of buttons in HTML forms:

|Button Type|Purpose|
|---|---|
|`submit`|Sends form data to server|
|`reset`|Clears all input fields|
|`button`|Used with JavaScript (no default action)|

### 🧪 Example with Buttons

`<form>`   
`<input type="text" name="name">`   
`<input type="submit" value="Submit">`   
`<input type="reset" value="Reset">`   
`<button type="button" onclick="alert('Hello!')">Click Me</button>` 
`</form>`

---

## 🧱 5. Full Example: A Basic Form

`<form>   <label for="name">Name:</label><br>`   
`<input type="text" id="name" name="name"><br><br>`    
`<label for="email">Email:</label><br>`  
`<input type="email" id="email" name="email"><br><br>`    
`<label for="password">Password:</label><br>`   
`<input type="password" id="password" name="password"><br><br>`    
`<input type="submit" value="Register">` 
`</form>`

---

## 📌 Summary

|Element|Use|
|---|---|
|`<form>`|Main container for form elements|
|`<input>`|Collects different kinds of user data|
|`<label>`|Describes each input field|
|`<button>`|Triggers submit/reset or custom JS|
