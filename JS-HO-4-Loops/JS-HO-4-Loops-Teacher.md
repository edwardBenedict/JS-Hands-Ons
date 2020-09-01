<h2 style="float:right;"><img src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg" width="20px"> Clarusway</h2>

# Hands-on JavaScript Loops

> Purpose of the this hands-on training is to teach the students JavaScript Loops.

## Learning Outcomes

> At the end of the this hands-on training, students will be able to use;

- What is Loops?
- `for` Loops
- `while` Loops
- `do ... while` Loops
- `for ... in` Loops
- `for ... of` Loops

### Part 1 - What is Loops?

---

- JavaScript Loops offer a quick and easy way to do something _repeatedly_. If you want to run the same code over and over again, you can use **Loops**.

```js
console.log("ClarusWay");
console.log("ClarusWay");
console.log("ClarusWay");
console.log("ClarusWay");
console.log("ClarusWay");
console.log("ClarusWay");
console.log("ClarusWay");
console.log("ClarusWay");
// Expected Output : 8 Clarusway
```

### Part 2 - `for` Loops

---

- A `for` loop repeats until a specified condition evaluates to `false`. The JavaScript `for` loop is similar to the Java and C for loop.
- The javascript `for` statement consists of three expressions and a statement.

Syntax :

```js
for (initialExpression; conditionExpression; incrementExpression) {
  repeatedStatement;
}
```

```js
for (let i = 0; i < 8; i++) {
  // Runs 8 times, with values of step 0 through 7.
  console.log("ClarusWay");
} // Expected Output : 8 ClarusWay
```

### Part 3 - `for ... in` Loops

---

- The `for ... in` loop is a special type of a loop that iterates over the properties of an object, or the elements of an array.

Syntax :

```js
for (variable in object) {
  repeatedStatement;
}
```

```js
var birdsArray = ["Falcon", "Eagle", "Swan", "Duck", "Albatross"];

for (var i in birdsArray) {
  console.log(birdsArray[i]);
}
/* Expected Output :
Falson
Eagle
Swan
Duck
Albattross */
```

### Part 4 - `for ... of` Loops

---

- **ES6** introduces a new `for ... of` loop which allows us to iterate over arrays or other iterable objects (e.g. strings) very easily. Also, the code inside the loop is executed for each element of the iterable object.

Syntax :

```js
for (variable of object) {
  repeatedStatement;
}
```

```js
// Iterating over array
let birdsArray = ["Falcon", "Eagle", "Swan", "Duck", "Albatross"];

for (let bird of birdsArray) {
  console.log(bird);
}
/* Expected Output :
Falson
Eagle
Swan
Duck
Albattross */

// Iterating over string
let cw = "Clarusway";

for (let char of cw) {
  console.log(char);
}
/* Expected Output : 
C 
l 
a
r
u
s
w
a
y    */
```

### Part 5 - `while` Statement

---

- The `while` loop starts by evaluating the condition. If the condition is `true`, the statement(s) is/are executed. If the condition is `false`, the statement(s) is/are not executed. After that, `while` loop ends.

Syntax :

```js
while (condition) {
  repeatedStatement;
}
```

```js
let n = 1;
let x = 1;
while (n <= 8) {
  x *= n;
  n++;
}
console.log(n - 1 + "! = " + x + ".");
// Expected Output : "8! = 40320."
```

### Part 6 - `do ... while` Statement

---

The `do...while` loop is closely related to `while` loop. But in the `do ... while` loop, the condition is checked at the end of the loop. Because of that the statement will executed at least once before check the condition.

Syntax :

```js
do {
  repeatedStatement;
} while (condition);
```

```js
var i = 0;
do {
  i = i + 1;
  console.log(i + ". loop.");
} while (i < 5);

/*
Expected Output:
1. loop.
2. loop.
3. loop.
4. loop.
5. loop.
*/
```

---
