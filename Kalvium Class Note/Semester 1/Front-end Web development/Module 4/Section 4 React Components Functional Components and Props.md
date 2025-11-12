# React Components: Functional Components & Props

## Learning Objectives

- Understand what functional components are and why they matter
- Learn how to build your own components
- Understand props and how to pass data with them
- Use props to create dynamic, reusable components

---

## What Are Functional Components?

- **Definition**: JavaScript functions that return **JSX**.
- **JSX**: HTML-like syntax used inside JavaScript to build UI.
- **Purpose**: React uses functional components as **building blocks** for interfaces.

**Example**  
```js
function Welcome() {  
  return <h1>Hello, Kalvian!</h1>;  
}
```

- Usage: `<Welcome />`
- Effect: Each time you use `<Welcome />`, it renders **"Hello, Kalvian!"**.

---

## Why Use Functional Components?

- **Reusable**: Use the same UI block in multiple places.
- **Maintainable**: Update code once → reflects everywhere.
- **Readable**: Cleaner, simpler code.
- **Testable**: Easy to test each component separately.

---

## How to Create a Functional Component

- Write a **function** that returns JSX.
- Example:

```js
function Welcome() {  
  return <h1>Hello, Kalvian!</h1>;  
}
```
- Think of it as a **personal stamp** you can place anywhere in your app.

---

## What Are Props?

- **Props**: Short for _properties_.
- Used to **pass data into a component**.
- Help **customize** and **reuse** components easily.
- Props are received as an **object** inside the component.

**Example**

```js
function Greeting(props) {  
  return <h1>Hello, {props.name}!</h1>;  
}
```

```js
function App() {  
  return <Greeting name="Kalvian" />;  
}
```
### Breakdown

- `props` is an **object** containing all values passed to the component.
- `props.name` → accesses the `name` prop.
- `<Greeting name="Kalvian" />` → passes `"Kalvian"` as a value.
- Analogy: **Props are like order slips**. Component reads them and gives a customized output.

---

## Making Components Dynamic with Props

- Props make components **dynamic and reusable** by allowing different data each time.

	**Example: ProfileCard`**

```js
function ProfileCard(props) {  
  return (  
    <>  
      <img src={props.avatar} alt={props.name} />  
      <h2>{props.name}</h2>  
      <p>{props.bio}</p>  
    </>  
  );  
}

function App() {  
  return (  
    <>  
      <ProfileCard  
        name="John Doe"  
        avatar="[https://example.com/john.jpg](https://example.com/john.jpg)"  
        bio="Software Engineer"  
      />  
      <ProfileCard  
        name="Jane Smith"  
        avatar="[https://example.com/jane.jpg](https://example.com/jane.jpg)"  
        bio="Web Developer"  
      />  
    </>  
  );  
}

```
### Breakdown

- `ProfileCard` accepts **3 props**: `name`, `avatar`, `bio`.
- Each time `<ProfileCard />` is used → different values can be passed.
- Analogy: Component is like a **blank ID card**. Props fill in the **details** (name, photo, bio).

```embed
title: "ReactJS Tutorial - 5 - Functional Components"
image: "https://i.ytimg.com/vi/Cla1WwguArA/maxresdefault.jpg"
description: "📘 Courses - https://learn.codevolution.dev/💖 Support UPI - https://support.codevolution.dev/💖 Support PayPal - https://www.paypal.me/Codevolution💾 Github..."
url: "https://youtu.be/Cla1WwguArA"
favicon: ""
aspectRatio: "56.25"
```

```embed
title: "ReactJS Tutorial - 9 - Props"
image: "https://i.ytimg.com/vi/m7OWXtbiXX8/maxresdefault.jpg"
description: "📘 Courses - https://learn.codevolution.dev/💖 Support UPI - https://support.codevolution.dev/💖 Support PayPal - https://www.paypal.me/Codevolution💾 Github..."
url: "https://youtu.be/m7OWXtbiXX8"
favicon: ""
aspectRatio: "56.25"
```

---

## Summary

- **Functional Components**: JavaScript functions that return JSX → building reusable UI blocks.
- **Benefits**: Reusable, maintainable, readable, testable.
- **Creating Components**: Define a function that returns JSX.
- **Props**: Objects used to pass data into components → customize & reuse them.
- **Dynamic Components with Props**: Components display different content based on props → like blank forms filled with unique data.