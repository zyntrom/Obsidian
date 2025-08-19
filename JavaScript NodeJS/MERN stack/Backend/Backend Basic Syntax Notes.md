## Required Node Packages

- To initialize the folder for npm 

```bash
npm init
```

- For the server to work install Nodemon globally

```bash
npm install -g nodemon
```

- To install express JS

```bash
npm install express
```

## Basic Express JS Server

```js
const express= require("express"); //importing express 
const app= express(); //creating an instance for the server
const PORT = 5000; //The port number in which the server runs

app.use(express.json()); //middleware to parse raw json to  

app.get("/",(req,res)=>{
res.send("Hello from backend");
});

app.listen(PORT,()=>{
	console.log("The Server is running...");
	
})
```
