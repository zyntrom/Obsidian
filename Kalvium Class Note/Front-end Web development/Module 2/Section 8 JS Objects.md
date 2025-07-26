### 🧠 **JavaScript Objects — Revision Notes**

#### ✅ What Are Objects?

- Used to store **related data** as **key-value pairs**.
- Think of them like a labeled **dictionary** or a **record**.
- Created using `{}` (curly braces).

```js
const person = {   
	name: 'John',   
	age: 30,   
	city: 'New York' 
};
```

---

#### 🔍 Accessing Values

- Dot notation: `person.name`
- Bracket notation: `person['age']`

---

#### ➕ Adding Properties

```js
person.job = 'Engineer';
```

---

#### ♻️ Updating Properties

```js
person.age = 31;
```

---

#### ❌ Deleting Properties

```js
delete person.city;
```

---

### 🧰 Object Methods You Should Know

|Method|Description|Example|Output|
|---|---|---|---|
|`Object.keys(obj)`|Get array of keys|`Object.keys(person)`|`['name', 'age', 'job']`|
|`Object.values(obj)`|Get array of values|`Object.values(person)`|`['John', 31, 'Engineer']`|
|`Object.entries(obj)`|Get key-value pairs|`Object.entries(person)`|`[['name', 'John'], ['age', 31], ['job', 'Engineer']]`|

---

### 📌 Summary

- Objects use `{}` and store data as **key-value** pairs.
- Access with **dot** or **bracket** notation.
- Add/update/delete properties easily.
- Useful methods: `Object.keys()`, `Object.values()`, `Object.entries()`.