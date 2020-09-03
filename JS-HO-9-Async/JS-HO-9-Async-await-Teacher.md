<p>Clarusway<img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"></p>

# Hands-on JavaScript Async/await

> Purpose of the this hands-on training is to teach the students JavaScript async/await.

## Outline

- Part 1 - What is `async/await` function?

- Part 2 - Async Function

- Part 3 - Await

- Part 4 - Error handling

- Part 5 - `asyn/await` Example

### Part 1 - What is `async/await` function?

---

- More recent additions to the JavaScript language are async functions and the await keyword, part of the so-called ECMAScript 2017 JavaScript edition.
- Async/await functions help us even more in allowing us to write completely synchronous-looking code while performing asynchronous tasks behind the scenes.

Syntax :

```js
async function name([param[, param[, ...param]]]) {
   statements
}
```

### Part 2 - Async Function

---

- Let’s start with the async keyword. It can be placed before a function, like this:

```js
async function f() {
  return "Clarusway";
}

f().then(alert);
// Expected Output : alert("Clarusway");
```

### Part 3 - Await

---

Syntax :

```js
// await works only inside async functions
let value = await promise;
```

```js
const getData = async () => {
  var y = await "ClarusWay";
  console.log(y);
};

console.log("Way to ReInvent Yourself!");
getData();
console.log("Choose a New Path!");
/* Expected Ouput :
1;
2;
ClarusWay; */
```

- ⛔ Can’t use await in regular functions.

### Part 4 - Error handling

- If a promise resolves normally, then await promise returns the result. But in the case of a rejection, it throws the error, just as if there were a throw statement at that line.

```js
async function f() {
  try {
    let response = await fetch("/no-user-here");
    let user = await response.json();
  } catch (err) {
    // catches errors both in fetch and response.json
    alert(err);
  }
}

f();
```

### Part 5 - `asyn/await` Example

---

- We will do a basic `async/await` example.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style media="screen">
      table {
        margin: 0 auto;
        border-collapse: collapse;
        border-style: hidden;
      }
      table td {
        padding: 0.5rem;
        border: 5px solid lightblue;
        text-align: center;
      }
      table th {
        padding: 0.5rem;
        border: 5px solid grey;
      }
    </style>
  </head>
  <body>
    <div id="divpart"></div>
    <script>
      let list = "<ol style='font-size: 30px'>";
      async function fetchPosts() {
        try {
          const response = await fetch(
            "https://jsonplaceholder.typicode.com/users"
          );
          const data = await response.json();
          console.log(response);
          data.forEach((i) => {
            list += `<li>${i.name} - Email: ${i.email}</li>`;
            console.log("i", i.name);
          });
          list += "</ol>";
          document.getElementById("divpart").innerHTML = list;
        } catch (err) {
          alert(err);
        }
      }
      fetchPosts();
    </script>
  </body>
</html>
```
