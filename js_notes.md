# Javascript Notes

## Defining Variables

- let: Variable is limited to block {}
```js
let x = 5;
```
- const: Variable is constant throughout code
```js
const y = 10;
```
- var: Older way to declare variables

## Arrow Functions

- Way to define functions
```js
// Normal Javascript
export default function DoSomething () {
    // logic
}

// Arrow Functions
export const DoSomething = () => {
    // logic
}

// Example React Component
const MyComponent = () => {
    return <div> </div>
}
```

## Anonymous Functions

- A function that doesnt have a name 
```js
<button
    onClick = {() => {
        console.log("Hello World");
    }}
></button>
```

## Ternary Operators

- Ternary operators are shorthand for if/else statements

```js
let age = 16;
// Set name to Pedro if age > 10
let name = age > 10 && "Pedro";

// Set name to Pedro if not age > 10
let name = age > 10 || "Pedro";

// Let name = Pedro if age > 10 else Jack
let name = age > 10 ? "Pedro" : "Jack";

// React example
const Component = () => {
    return age > 10 ? <div> Pedro </div> : <div> Jack </div>
}
```

## Objects

- Destucturing objects
```js
const Person = {
    name: "Pedro",
    age: 20;
    isMarried: false;
};

// destructuring
const {name, age, isMarried} = person;
```

- Spread operator
```js
const person = {
    name = "Pedro",
    age = 20,
    isMarried = false;
};

const person2 = {...person, name: "Jack"};
```

```js
const names = ["Pedro", "Jack", "Jessica"];
const names2 = [...names, "Joel"];
```

## .Map and .Filter

- Map
```js
let names = ["Pedro", "Jack", "Jessica"];

names.map((name) => {
    console.log(name);
});

names.map((name) => {
    return name + "1";
});

names.map((name) => {
    return <h1> {name} </h1>;
});
```

- Filter
```js
names.filter((name) => {
    return name !== "Pedro";
});
```

## Promises

- Used when communicating with an API
- Used to handle data that you are requesting
- Speed of API requests is not instant

```js
const event = new Promise((resolve, reject) => {
    var name = "Pedro";
    if (name == "Pedro") {
        resolve(name);
    } else {
        reject("Name was not Pedro");
    }
});
```

- Promise is a class
- .then is called if resolved
- .catch is called if rejected

```js
event.then((name) => {
    console.log(name);
}) .catch((err) => {
    console.log(err);
}) .finally(() => {
    console.log("Promise finished");
});
```

```js
// Promises real example
const axios = require("axios");
const data = axios.get("https.//cat-fact...);
data
    .then((res) => {
        console.log(res.data);
    }) .catch((err) => {
        console.log(err);
    }) .finally(() => {
        console.log("Promise resolved");
    });
```

## Async Await
- Uses syntax to do the same thing as promises
- An asynchronous function is a function that allows for operations that take time to complete. 

```js
const axios = require("axios");

const fetchData = async() => {
    try{
        const data = await axios.get("https.//cat-fact...");
        console.log(data);
    } catch (err) {
        console.log(err);
    } finally {
        console.log("Hello");
    }
}

fetchData();
```