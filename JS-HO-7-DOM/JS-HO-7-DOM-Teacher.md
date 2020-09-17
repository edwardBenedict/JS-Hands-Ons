<h2 style="float:right;"><img src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg" width="20px"> Clarusway</h2>

# Hands-on JavaScript Document Object Model (DOM)

> Purpose of the this hands-on training is to teach the students JavaScript DOM.

## Learning Outcomes

> At the end of the this hands-on training, students will learn;

- How to change the content of HTML elements
- How to change the style (CSS) of HTML elements
- How to react to HTML DOM events
- How to add and remove HTML elements

## Outline

- Part 1 - What is the DOM?

- Part 2 - Selecting Elements

- Part 3 - JavaScript HTML DOM - Changing HTML

- Part 4 - JavaScript HTML DOM - Changing CSS

- Part 5 - Add Events Using the HTML DOM

- Part 6 - Event Listener

- Part 7 - Remove Event Listener (`removeEventListener()`)

### Part 1 - What is the DOM?

- The Document Object Model (DOM) is a programming interface for HTML and XML documents.
- Every element in a document—the document as a whole, the head, tables within the document, table headers, text within the table cells—is part of the document object model for that document, so they can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

```html
<html>
  <head>
    <title>My page</title>
  </head>
  <body>
    <h2>Welcome to my <a href="#">page</a></h2>
    <p>This is the first paragraph.</p>
    <!-- this is the end -->
  </body>
</html>
```

<img alt="The HTML DOM Tree of Objects" src="https://blog.scrapinghub.com/hs-fs/hubfs/tree-7.png?width=564&name=tree-7.png"/> 
<p align="center">The HTML DOM Tree of Objects</p>

### Part 2 - Selecting Elements

|           Object           |                  Property                   |
| :------------------------: | :-----------------------------------------: |
|     `getElementById()`     |          select an element by id.           |
|   `getElementsByName()`    |          select elements by name.           |
|  `getElementsByTagName()`  |       select elements by a tag name.        |
| `getElementsByClassName()` | select elements by one or more class names. |
|     `querySelector()`      |      select elements by CSS selectors.      |

---

> JavaScript `getElementById()` Method

- The getElementById() allows you to select an element by its id.

Syntax :

```js
let element = document.getElementById(id);
```

```html
<html>
  <head>
    <title>JavaScript getElementById() Method</title>
  </head>
  <body>
    <p id="message">A paragraph</p>
    <script>
      const p = document.getElementById("message");
      console.log(p);
    </script>
  </body>
</html>
<!-- Expected Output : <p id="message">A paragraph</p>; -->
```

- If multiple elements share the same id, even though it is not valid, the getElementById() returns still only the first element it encounters.

> JavaScript `getElementsByName()` Method

- Elements on an HTML document can have a name attribute. Unlike the id attribute, multiple element can share the same value of the name attribute.
- To get all elements with a specified name, you use the getElementsByName() method of the document object:

```js
let elements = document.getElementsByName(name);
```

```html
<!DOCTYPE html>
<html>
  <body>
    First Name: <input name="fname" type="text" value="Walter" /><br />
    Second Name: <input name="fname" type="text" value="Edward" />

    <p>
      Click the button to get the tag name of the first element in the document
      that has a name attribute with the value "fname".
    </p>

    <button onclick="myFunction()">Try it</button>

    <p id="demo"></p>

    <script>
      function myFunction() {
        var first = document.getElementsByName("fname")[0].value;
        var second = document.getElementsByName("fname")[1].value;
        document.getElementById("demo").innerHTML = first + " " + second;
      }
    </script>
  </body>
</html>
```

> JavaScript `getElementsByTagName()` Method

- The getElementsByTagName() method accepts a tag name and returns a live HTMLCollection of elements with the matching tag name in the order which they appear in the document.

Syntax :

```js
let elements = document.getElementsByTagName(tagName);
```

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript getElementsByTagName() Demo</title>
  </head>
  <body>
    <h1>Clarusway</h1>
    <h2>ReInvent Yourself.</h2>
    <h1>JavaScript getElementById()</h1>
    <h2>getElementById</h2>
    <h1>JavaScript getElementsByName()</h1>
    <h2>getElementsByName</h2>
    <h1>JavaScript getElementsByTagName()</h1>
    <h2>getElementsByTagName</h2>
    <p>This is paragraph.</p>

    <button id="btnCount">Count h2</button>

    <script>
      let btn = document.getElementById("btnCount");
      btn.addEventListener("click", () => {
        let headings = document.getElementsByTagName("h2");
        alert(`The number of H2 tags: ${headings.length}`);
      });
    </script>
  </body>
</html>
```

> JavaScript `getElementsByClassName()` Method

The `getElementsByClassName()` method returns an object containing all the elements with the specified class names in the document as objects.Each element in the returned object can be accessed by its index. This method can be called upon any individual element to search for its descendant elements with the specified class names.

```js
let elements = document.getElementsByClassName(classNames);
let elements = parentElement.getElementsByClassName(classNames);
```

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM getElementByClassName() Method</title>
    <style>
      h1 {
        color: black;
      }
      body {
        text-align: center;
      }
      button {
        background-color: black;
        color: white;
        width: 300px;
        padding: 10px;
        margin: 10px;
        cursor: pointer;
      }
    </style>
  </head>
  <body>
    <h1>
      <img
        src="https://secure.meetupstatic.com/photos/event/3/1/b/9/600_488352729.jpeg"
        width="20px"
      />
      Clarusway
    </h1>
    <h2>DOM getElementByClassName() Method</h2>
    <div>
      <button onclick="red()" class="black red">
        Click to change to red button</button
      ><br />

      <button onclick="blue()" class="black blue">
        Click to change to blue button</button
      ><br />

      <button onclick="yellow()" class="black yellow">
        Click to change to yellow button</button
      ><br />

      <button onclick="black()">
        Click to change to all buttons to initial state
      </button>
    </div>

    <script>
      function red() {
        document.getElementsByClassName("red")[0].style.backgroundColor = "red";
      }

      function blue() {
        document.getElementsByClassName("blue")[0].style.backgroundColor =
          "blue";
      }

      function yellow() {
        document.getElementsByClassName("yellow")[0].style.backgroundColor =
          "yellow";
      }

      function black() {
        var elements = document.getElementsByClassName("black");
        for (var i = 0; i < elements.length; i++) {
          elements[i].style.backgroundColor = "black";
        }
      }
    </script>
  </body>
</html>
```

> JavaScript `querySelector()` and `querySelectorAll()` Methods

- The querySelector() is a method of the Element interface. The querySelector() allows you to find the first element, which is a descendant of the parent element on which it is invoked, that matches a CSS selector or a group of CSS selectors.

Syntax :

```js
let element = parentNode.querySelector(selector);
```

- Besides the querySelector(), you can use the querySelectorAll() method to find all elements that match a CSS selector or a group of CSS selector:

```js
let elementList = parentNode.querySelectorAll(selector);
```

The following example finds the first h1 element in the document:

```js
let firstHeading = document.querySelector("h1");
```

To select an element based on the value of its Id, you use the Id selector syntax:

```js
let idExm = document.querySelector("#nameOfId");
```

To find the element with a given class attribute, you use the class selector syntax:

```js
let classExm = document.querySelector(".nameOfClass");
```

```html
<!DOCTYPE html>
<html>
<body>

<h1 class="common">Clarusway</h2>
<p class="common">ReInvent Yourself.</p>

<p>Click the button to add a background color to the first element in the document with class="common".</p>

<button onclick="changeBGC()">Change BGC</button>

<script>
function changeBGC() {
  document.querySelector(".common").style.backgroundColor = "lightblue";
}
</script>

</body>
</html>
```

---

### Part 3 - JavaScript HTML DOM - Changing HTML

---

- By using JavaScript, you can change any part of an HTML document.

```html
<!DOCTYPE html>
<html>
<body>
<h1>Clarusway</h2>
<p class="common">ReInvent Yourself.</p>
<p>Click the rsult button to result of <code>document.write()</code>.</p>
<button onclick="result()">Result</button>
<script>
function result() {
  document.write(Date());
}
</script>
</body>
</html>
```

- Never use `document.write()` after the document is loaded. It will overwrite the document.

- The Element property `innerHTML` gets or sets the HTML or XML markup contained within the element.

Syntax:

```js
document.element.innerHTML = newHTML;
```

```html
<!DOCTYPE html>
<html>
<body>
<h1>Clarusway</h2>
<p class="common">ReInvent Yourself.</p>
<p>Click the result button to result</p>
<button onclick="result()">Result</button>
<p id="prg">This text will be changed.</p>
<script>
function result() {
  document.getElementById("prg").innerHTML = "<h1 style='color: red;'>This is new 'h1' text.</h1>";
}
</script>
</body>
</html>
```

- If you need to change the value of an HTML attribute, use this syntax:

```js
document.getElementById(id).attribute = newValue;
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
    <p class="common">ReInvent Yourself.</p>
    <p>Click the result button to result</p>
    <button onclick="result()">Result</button>
    <div id="change"><p>This text will be changed.</p></div>
    <script>
      function result() {
        document.getElementById("change").innerHTML =
          "<img id='image' src='https://cdn.mos.cms.futurecdn.net/EzgdmaCQuT84bgDL4fhXZS.jpg' width='100%'>";
      }
    </script>
  </body>
</html>
```

### Part 4 - JavaScript HTML DOM - Changing CSS

---

- Just as you can use JavaScript to change the HTML in a web page, you can also use it to change CSS styles. The process is very similar.

Syntax :

```js
document.element.style.nameOfProp = newStyle;
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
    <p class="common">ReInvent Yourself.</p>
    <p>Click the result button to result</p>
    <button onclick="result()">Result</button>
    <div id="change"><p>This text will be changed.</p></div>
    <script>
      function result() {
        document.getElementById("change").style.fontSize = "40px";
        document.getElementById("change").style.color =
          "rgba(69, 255, 90, 0.9)";
        document.getElementById("change").style.backgroundColor = "grey";
        document.getElementById("change").style.textAlign = "center";
      }
    </script>
  </body>
</html>
```

### Part 5 - Add Events Using the HTML DOM

- You can add events to HTML using Javascript.

Syntax :

```js
document.element.nameOfEvents = nameOfFunction;
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
    <p class="common">ReInvent Yourself.</p>
    <p>Click the result button to result</p>
    <button id="button">Result</button>
    <div id="change"><p>This text will be changed.</p></div>
    <script>
      document.querySelector("#button").ondblclick = result;
      function result() {
        document.getElementById("change").style.fontSize = "40px";
      }
    </script>
  </body>
</html>
```

### Part 6 - Event Listener

- EventListener is an object that handles an event. It can be passed to `addEventListener()` instead of passing a Function. Any JavaScript object with a handleEvent method can be used as an EventListener.

```js
document.element.addEventListener(event, listener);
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
    <p class="common">ReInvent Yourself.</p>
    <p>Click the result button to result</p>
    <button id="button">Result</button>
    <div><p id="change">This text will be changed.</p></div>
    <script>
      document.getElementById("button").addEventListener("click", function () {
        document.getElementById("change").innerText = "CLARUSWAY";
      });
    </script>
  </body>
</html>
```

- When **passing parameter** values, use an "anonymous function" that calls the specified function with the parameters:

```js
document,
  element.addEventListener("event", function () {
    nameOfFunction(p1, p2);
  });
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
    <p class="common">ReInvent Yourself.</p>
    <p>Click the result button to result</p>
    <button id="button">Result</button>
    <div><p id="change">This text will be changed.</p></div>
    <script>
      document.getElementById("button").addEventListener("click", function () {
        myFunc(7, 8);
      });
      function myFunc(x, y) {
        let multy = x * y;
        document.getElementById("change").innerText = "Result : " + multy;
      }
    </script>
  </body>
</html>

```

### Part 7 - Remove Event Listener (`removeEventListener()`)

---

- The JavaScript `removeEventListener()` method is used to remove an event listener from an element that has been previously attached with the `addEventListener()` method.

Syntax :

```js
document.element.removeEventListener("event", listener);
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
    <p class="common">ReInvent Yourself.</p>
    <div id="box" style="width: 80%; height: 300px; background-color: aqua">
      <p id="change">This box will be changed.</p>
    </div>
    <button id="button" onclick="remEvLis()">removeEventListener</button>
    <script>
      document.getElementById("box").addEventListener("mousemove", func);
      function func() {
        document.getElementById("change").innerHTML =
          "Result : " + Math.random();
      }
      function remEvLis() {
        document.getElementById("box").removeEventListener("mousemove", func);
      }
    </script>
  </body>
</html>

```
