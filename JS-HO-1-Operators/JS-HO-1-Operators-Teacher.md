<h2 style="float:right;"><img src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg" width="20px"> Clarusway</h2># Hands-on JavaScript-Operators

> Purpose of the this hands-on training is to teach the students JavaScript Operators.

## Learning Outcomes

> At the end of the this hands-on training, students will be able to use;

- JavaScript Assignment Opeartors
- Adding assignment operator(+)
- Subtraction assignment operator(-)
- Multiplication assignment operator(\*)
- Division assignment operator(/)
- Adding Strings and Numbers
- Remainder assignment operator(%=)
- Exponentiation assignment (\*\*=)
- Logical AND assignment (&&=)
- Logical OR assignment (||=)
- Logical nullish assignment (??=)
- JavaScript Typeof Operator

## Outline

### Part 1 - JavaScript Assignment Opeartors

---

- Define new variables and use assignment operators.

```js
let x = 2;
const y = 3;

console.log(x);
// expected output: 2

console.log((x = y + 1)); // 3 + 1
// expected output: 4

console.log((x = x * y)); // 4 * 3
// expected output: 12
```

Operator : x = y

### Part 2 - Adding assignment operator(`+`)

---

- The addition assignment operator (+=) adds the value of the right operand to a variable and assigns the result to the variable.

```js
let a = 2;
let b = "hello";

console.log((a += 3)); // addition
// expected output: 5

console.log((b += " world")); // concatenation
// expected output: "hello world"
```

Operator : x += y  
Meaning : x = x + y

### Part 3 - Subtraction assignment operator(-)

---

- The subtraction assignment operator (-=) subtracts the value of the right operand from a variable and assigns the result to the variable.

```js
let a = 2;

console.log((a -= 3));
// expected output: -1

console.log((a -= "Hello"));
// expected output: NaN
```

Operator : x -= y  
Meaning : x = x - y

### Part 4 - Multiplication assignment operator(`*`)

---

- The multiplication assignment operator (`_=`) multiplies a variable by the value of the right operand and assigns the result to the variable.

```js
let a = 2;

console.log((a *= 3));
// expected output: 6

console.log((a *= "hello"));
// expected output: NaN
```

Operator : x _= y  
Meaning : x = x _ y

### Part 5 - Division assignment operator(`/`)

---

- The division assignment operator (/=) divides a variable by the value of the right operand and assigns the result to the variable.

```js
let a = 3;

console.log((a /= 2));
// expected output: 1.5

console.log((a /= 0));
// expected output: Infinity

console.log((a /= "hello"));
// expected output: NaN
```

Operator : x /= y  
Meaning : x = x / y

### Part 6 - Adding Strings and Numbers

---

- Adding two numbers, will return the sum, but adding a number and a string will return a string:

```js
var x = 5 + 5;
// expected output: 10

var y = "5" + 5;
// expected output: 55

var z = "Hello" + 5;
// expected output: Hello5
```

&#10071; If you add a number and a string, the result will be a string!

### Part 7 - Remainder assignment operator(%=)

---

- The remainder assignment operator (%=) divides a variable by the value of the right operand and assigns the remainder to the variable.

```js
let a = 3;

console.log((a %= 2));
// expected output: 1

console.log((a %= 0));
// expected output: NaN

console.log((a %= "hello"));
// expected output: NaN
```

Operator : x %= y
Meaning : x = x % y

### Part 8 - Exponentiation assignment (\*\*=)

---

- The exponentiation assignment operator (\*\*=) raises the value of a variable to the power of the right operand.

```js
let a = 3;

console.log((a **= 2));
// expected output: 9

console.log((a **= 0));
// expected output: 1

console.log((a **= "hello"));
// expected output: NaN
```

Operator : x **= y
Meaning : x = x ** y

### Part 9 - Logical AND assignment (&&=)

---

- The logical AND assignment (x &&= y) operator only assigns if x is truthy.

```js
let a = 1;
let b = 0;

a &&= 2;
console.log(a);
// expected output: 2

b &&= 2;
console.log(b);
// expected output: 0
```

Syntax :

```js
expr1 &&= expr2;
```

Using Logical AND Assignment

```js
let x = 0;
let y = 1;

x &&= 0; // 0
x &&= 1; // 0
y &&= 1; // 1
y &&= 0; // 0
```

### Part 10 - Logical OR assignment (||=)

---

- The logical OR assignment (x ||= y) operator only assigns if x is falsy.

```js
const a = { duration: 50, title: "" };

a.duration ||= 10;
console.log(a.duration);
// expected output: 50

a.title ||= "title is empty.";
console.log(a.title);
// expected output: "title is empty"
```

Syntax :

```js
expr1 ||= expr2;
```

```js
x || y;
// returns x when x is truthy
// returns y when x is not truthy
```

- Example : If the "content" element is empty, set the innerHTML to a default value:

```js
document.getElementById("content").innerHTML ||= "<i>No content.</i>";
```

### Part 11 - Logical nullish assignment (??=)

---

- The logical nullish assignment (x ??= y) operator only assigns if x is nullish (null or undefined).

```js
const a = { duration: 50 };

a.duration ??= 10;
console.log(a.duration);
// expected output: 50

a.speed ??= 25;
console.log(a.speed);
// expected output: 25
```

Syntax :

```js
expr1 ??= expr2;
```

- Using logical nullish assignment

```js
function config(options) {
  options.duration ??= 100;
  options.speed ??= 25;
  return options;
}

config({ duration: 125 }); // { duration: 125, speed: 25 }
config({}); // { duration: 100, speed: 25 }
```

### Part 12 - JavaScript Typeof Operator

---

- You can use the typeof operator to find the data type of a JavaScript variable.

Syntax :

```js
typeof variable;
```

```js
typeof "John";
// expected output: "string"

typeof 3.14;
// expected output: "number"

typeof NaN;
// expected output: "number"

typeof false;
// expected output: "boolean"

typeof [1, 2, 3, 4];
// expected output: "object"

typeof { name: "John", age: 34 };
// expected output: "object"

typeof new Date();
// expected output: "object"

typeof function () {};
// expected output: "function"

typeof myCar;
// expected output: "undefined"

typeof null;
// expected output: "object"
```
