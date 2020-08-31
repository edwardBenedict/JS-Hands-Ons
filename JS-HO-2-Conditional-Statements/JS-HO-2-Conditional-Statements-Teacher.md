# Hands-on JavaScript Conditional Statements

> Purpose of the this hands-on training is to teach the students JavaScript Conditional Statements.

## Learning Outcomes

> At the end of the this hands-on training, students will be able to use;

- `if` Statement
- `else` Statement
- `else if` Statement
- `switch` Statement.

### Part 1 - `if` Statement

- The if statement executes a statement if a specified condition is true.

Syntax :

```js
if (condition) {
  statement;
}
```

```js
age = 13;
if (age < 16) {
  message = "You can not drive a car!";
  console.log(message);
}
// expected output: "You can not drive a car!"
```

---

### Part 2 - `if .. else` Statement

The if statement executes a statement if a specified condition is true. If the condition is false, another statement can be executed.

Syntax :

```js
if (condition) {
  firstStatement;
} else {
  secondStatement;
}
```

```js
let age = 5;
if (age > 6) {
  message = "You can ride bike!";
} else {
  message = "You can not ride bike.";
}
console.log(message);
// expected output: "You can not ride bike!"
```

---

### Part 3 - `if .. else if .. else` Statement

- Multiple if...else statements can be nested to create an else if clause. Note that there is no elseif or elif (in one word) keyword in JavaScript.

Syntax :

```js
if (firstCondition)
  firstStatement
else if (secondCondition)
  secondStatement
else if (thirdCondition)
  thirdStatement
...
else
  lastStatement
```

```js
let age = 19;
if (age > 18) {
  message = "You can drive car!";
} else if (age > 6) {
  message = "You can ride bike!";
} else {
  message = "You can not ride bike!";
}
console.log(message);
// expected output: "You can drive car!"
```

---

### Part 4 - `switch` Statement

- The switch statement evaluates an expression, matching the expression's value to a case clause, and executes statements associated with that case, as well as statements in cases that follow the matching case.
- A default clause; if provided, this clause is executed if the value of expression doesn't match any of the case clauses.

```js
 switch (expression) {
  case firstValue:
    //statement of expression matches firstValue
    break;
  case secondValue:
    //statement of expression matches secondValue
    break;
  ...
  case nthValue:
    //statement of expression matches nthValue
    break;
  default:
    //Statements executed when none of
    //the values match the value of the expression
    break;
}

```

```js
expr = "Bananas";

switch (expr) {
  case "Oranges":
    console.log("Oranges are orange.");
    break;
  case "Apples":
    console.log("Apples are red.");
    break;
  case "Bananas":
  case "Mangoes":
    console.log("Bananas and Mangoes are yellow.");
    break;
  case "Pears":
    console.log("Pears are green");
    break;
  default:
    console.log("Sorry, we do not know color of " + expr + ".");
}
// expected output : "Bananas and Mangoes are yellow."
```

---
