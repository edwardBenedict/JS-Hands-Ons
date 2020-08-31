# Hands-on JavaScript Arrays

> Purpose of the this hands-on training is to teach the students JavaScript Arrays.

## Learning Outcomes

> At the end of the this hands-on training, students will be able to use;

- Arrays
- Array `length` Property
- Array Methods

## Outline

- What is an Array?
- Defining an Array
- Defining an Array with `new` Keyword
- Access the Elements of an Array
- Changing an Array Element
- Access the Full Array
- Arrays are Special type of Objects
- Array Properties and Methods

### Part 1 - What is an Array?

- In JavaScript, array is a single variable that is used to store different elements. It is often used when we want to store list of elements and access them by a single variable.

---

### Part 2 - Defining an Array?

Syntax :

```js
var nameOfArray = [item1, item2, ...];
```

Let's give an Array example:

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
```

---

### Part 3 - Defining an Array with `new` Keyword

- You can initialize an array with Array constructor syntax using new keyword.

Syntax :

```js
var arrayName = new Array(element1, element2, element3, ...elementN);
```

```js
var fruitsNewArray = new Array("Pear", "Mango", "Apple");
```

❗ The two examples above do exactly the same. There is no need to use `new Array()`. For **simplicity**, **readability** and **execution speed**, use the first one (the array literal method).

---

### Part 4 - Accessing Elements of an Array

You access an array element with index number.

Syntax :

```js
var element = nameOfArray[indexNumber];
```

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
element = fruitsArray[1];
console.log(element);
// Expected Output : "Mango"
```

❗ Array indexes start with 0.

### Part 5 - Changing an Array Element

You can change an element by giving a new value.

Syntax :

```js
nameOfArray[indexNumber] = "newElement";
```

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
fruitsArray[0] = "Cherry";
console.log(fruitsArray[0]);
// Expected Output : "Cherry"
```

### Part 6 - Accessing Full Array

- You can access the full array with array name.

Syntax :

```js
console.log(nameOfArray);
```

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
console.log(fruitsArray);
// Expected Output : ["Pear", "Mango", "Apple"]
```

### Part 7 - Arrays are Special type of Objects

- The typeof operator in JavaScript returns "object" for arrays.

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
console.log(typeof fruitsArray);
// Expected Output : "object"
```

- How to check if a variable is an array in JavaScript?

Syntax :

```js
Array.isArray(value);
```

```js
Array.isArray([1, 2, 3]);
// Expected Output : true
Array.isArray({ ClarusWay: 99 });
// Expected Output : false
Array.isArray("Clarusway");
// Expected Output : false
Array.isArray(undefined);
// Expected Output : false
```

---

### Part 8 - Array Properties and Methods

- The real strength of JavaScript arrays are the built-in array properties and methods.

- The `length` Property

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
console.log(fruitsArray.length);
// Expected Output : 3
```

- Accessing the Last Array Element

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
lastElement = fruitsArray[fruitsArray.length - 1];
console.log(lastElement);
// Expected Output : "Apple"
```

- The `push()` Method

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
fruitsArray.push("Cherry");
console.log(fruitsArray);
// Expected Output : ["Pear", "Mango", "Apple", "Cherry"]
```

- Also new element can be added to an array using `length` propert

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
fruitsArray[fruitsArray.length] = "Cherry";
console.log(fruitsArray);
// Expected Output : ["Pear", "Mango", "Apple", "Cherry"]
```

- The `toString()` Method

`toString()` method converts an array to a string of (comma separated) array values.

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
stringArray = fruitsArray.toString();
console.log(stringArray);
// Expected Output : "Pear,Mango,Apple"
```

- The `join()` Method

The `join()` method is used to join the elements of an array into a string. The elements of the string will be separated by a specified separator and its default value is a comma(,).

```js
var fruitsArray = ["Pear", "Mango", "Apple"];
joinArray = fruitsArray.join(" | ");
console.log(joinArray);
// Expected Output : "Pear | Mango | Apple"
```

- The `pop()` Method

Remove an item from the end of an array with `pop()` method.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.pop();
console.log(birdsArray);
// Expected Output : ['Albatross', 'Cuckoo']
```

`pop()` returns the remeoved item.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.pop();
// Expected Output : "Falcon"
```

- The `push` Method

Add items to the end of the an array

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.push("Duck");
console.log(birdsArray);
// Expected Output : ["Albatross", "Cuckoo", "Falcon", "Duck"]
```

`push()` returns the new array length.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.push("Duck");
// Expected Output : 4
```

- The `shift()` Method

Remove an item from the beginning of an array

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.shift("");
console.log(birdsArray);
// Expected Output : ["Cuckoo", "Falcon"]
```

`shift()` returns the removed item.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.shift("");
// Expected Output : "Albatross"
```

- The `unshift()` Method

Add items to the beginning of an array.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.unshift("Dock");
console.log(birdsArray);
// Expected Output : ["Dock", "Albatross", "Cuckoo", "Falcon"]
```

`unshift()` returns the new array length.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.unshift("Dock");
// Expected Output : 4
```

- Deleting Elements

Since JavaScript arrays are objects, elements can be deleted by using the JavaScript operator delete.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
delete birdsArray[0];
console.log(birdsArray);
// Expected Output : [empty, "Cuckoo", "Falcon"]
```

❗ Using delete may leave undefined holes in the array. Use `pop()` or `shift()` instead.

- The `splice()` Method

The `splice()` method can be used to add new items to an array.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
birdsArray.splice(2, 0, "Duck", "Swan");
console.log(birdsArray);
// Expected Output : ["Albatross", "Cuckoo", "Duck", "Swan", "Falcon"]
```

First parameter of splice method defines the position where new elements should be added.

Second parameter of splice method defines how many elements should be removed.

Rest of the parameters define the new items to be added.

- The `concat()` Method

The `concat()` method creates a new array by merging (concatenating) existing arrays:

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
let catsArray = ["Persian", "Abyssinian", "Sphynx"];
let petsArray = birdsArray.concat(catsArray);
console.log(petsArray);
// Expected Output : ["Albatross", "Cuckoo", "Falcon", "Persian", "Abyssinian", "Sphynx"]
```

❗ The `concat()` method does not change the existing arrays. It always returns a new array.

The `concat()` method can take any number of array arguments:

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
let catsArray = ["Persian", "Abyssinian", "Sphynx"];
let dogsArray = ["Afador", "Barbet", "Dachsador"];
let petsArray = birdsArray.concat(catsArray, dogsArray);
console.log(petsArray);
// Expected Output : ["Albatross", "Cuckoo", "Falcon", "Persian", "Abyssinian", "Sphynx", "Afador", "Barbet", "Dachsador"]
```

- The `slice()` Method

The `slice()` method slices out a piece of an array into a new array.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon"];
let wildBird = birdsArray.slice(2);
console.log(wildBird);
// Expected Output : ["Falcon"]
```

The `slice()` method can take two arguments like `slice(2, 4)`.

```js
let birdsArray = ["Albatross", "Cuckoo", "Falcon", "Eagle", "Swan"];
let wildBird = birdsArray.slice(2, 4);
console.log(wildBird);
// Expected Output : ["Falcon", "Eagle"]
```
