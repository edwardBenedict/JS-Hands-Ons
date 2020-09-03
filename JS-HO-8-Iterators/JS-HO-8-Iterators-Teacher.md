<p><img align="right"
  src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"  width="15px"> Clarusway</p>

# Hands-on JavaScript Iterators

> Purpose of the this hands-on training is to teach the students JavaScript Iterators.

## Outline

- Part 1 - What is Iterators?

- Part 2 - JavaScript Array `forEach()` Method

- Part 3 - JavaScript Array `map()` Method

- Part 4 - JavaScript Array `filter()` Method

- Part 5 - Part 5 - JavaScript Array `reduce()` Method

- Part 6 - JavaScript Array `every()` Method

- Part 7 - JavaScript Array `some()` Method

- Part 8 - JavaScript Array `find()` Method

### Part 1 - What is Iterators?

---

- ES6 (aka ES2015) has introduced new concept in javascript: iterators.
- The Iterator pattern allows clients to effectively loop over a collection of objects.

### Part 2 - JavaScript Array `forEach()` Method

---

- The `forEach()` method executes a provided function once for each array element.

Syntax :

```js
nameOfArray.forEach(callback(element, index, arr), thisValue);
```

```js
<!DOCTYPE html>
<html>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <p>Result: <span id="result"></span></p>
    <button onclick="func()">Click</button>
    <script>
      // JavaScript to illustrate forEach() method
      function func() {
        // Original array
        const items = [8, 13, 19];
        const copy = [];

        items.forEach(function (item) {
          copy.push(item * item);
        });

        document.getElementById("result").innerText = copy;
      }
    </script>
  </body>
</html>
```

### Part 3 - JavaScript Array `map()` Method

---

- The `map()` method creates a new array populated with the results of calling a provided function on every element in the calling array.

Syntax :

```js
nameOfArray.map(function(currentValue, index, arr), thisValue)
```

```js
<!DOCTYPE html>
<html>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <p>Result: <span id="result"></span></p>
    <button onclick="func()">Click</button>
    <script>
      function func() {
        const items = [8, 13, 19];
        const resultOfMap = items.map((x) => x * 3);
        document.getElementById("result").innerText = resultOfMap;
      }
    </script>
  </body>
</html>
```

### Part 4 - JavaScript Array `filter()` Method

---

- The `filter()` method creates a new array with elements that fall under a given criteria from an existing array;

```js
nameOfArray.filter(callback(element, index, arr), thisValue);
```

```js
<!DOCTYPE html>
<html>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <p>Result: <span id="result"></span></p>
    <button onclick="func()">Click</button>
    <script>
      var developers = [
        { name: "Gizem", company: "Google" },
        { name: "Bahar", company: "Clarusway" },
        { name: "Ekrem", company: "Tesla" },
        { name: "Tarık", company: "Amazon" },
      ];

      var CWDevs = developers.filter(function (dev) {
        return dev.company == "Clarusway";
      });
      function func() {
        document.getElementById("result").innerText =
          CWDevs[0].name + " in " + CWDevs[0].company;
        console.log(CWDevs);
      }
    </script>
  </body>
</html>
```

### Part 5 - JavaScript Array `reduce()` Method

---

- **Reduce** is a method that can be difficult to understand especially with all the vague explanations that can be found on the web. There are a lot of benefits to understanding reduce as it is often used in state management (think **Redux**).

```js
nameOfArray.reduce(callback, initialValue);
```

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <p>Result: <span id="result"></span></p>
    <button onclick="func()">Click</button>
    <script>
      const wages = [105.0, 93.0, 78.0];
      const sum = wages.reduce((total, amount) => total + amount);

      function func() {
        document.getElementById("result").innerText = sum;
      }
    </script>
  </body>
</html>
```

### Part 6 - JavaScript Array `every()` Method

- The JavaScript array `every()` method checks whether all the given elements in an array are satisfying the provided condition. It returns true when each given array element satisfying the condition otherwise false.

---

Syntax :

```js
array.every(callback(currentvalue, index, arr), thisArg);
```

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <p>Are numbers greater than 30? : <span id="result"></span></p>
    <button onclick="func()">Click</button>
    <script>
      // JavaScript code for every() method
      function isLargerThan30(element, index, array) {
        return element > 30;
      }

      function func() {
        var arr = [11, 89, 23, 7, 98];

        // Check for positive number
        var value = arr.every(isLargerThan30);
        document.getElementById("result").innerText = value;
      }
    </script>
  </body>
</html>
```

### Part 7 - JavaScript Array `some()` Method

---

- The `some()` method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.

```js
array.some(callback[, thisObject]);
```

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <p>Any number multiple of five? : <span id="result"></span></p>
    <button onclick="func()">Click</button>
    <script>
      const numbersArray = [25, 8, 13, 29];
      const multOfFive = (elmnt) => elmnt % 5 === 0;
      result = numbersArray.some(multOfFive);

      function func() {
        document.getElementById("result").innerText = result;
      }
    </script>
  </body>
</html>
```

### Part 8 - JavaScript Array `find()` Method

---

- The JavaScript `find()` method is a convenient way to find and return the first occurence of an element in an array, under a defined testing function.

```js
array.find(function(currentValue, index, arr),thisValue)
```

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <p>
      First person of greater than 130 number of project:
      <span id="result"></span>
    </p>
    <button onclick="func()">Click</button>
    <script>
      let developers = [
        {
          name: "Naz",
          numberOfProject: 143,
        },
        {
          name: "Talha",
          numberOfProject: 128,
        },
        {
          name: "Yavuz",
          numberOfProject: 151,
        },
      ];
      result = developers.find((devs) => devs.numberOfProject > 130);

      function func() {
        document.getElementById("result").innerText =
          result.name + " " + result.numberOfProject;
      }
    </script>
  </body>
</html>
```
