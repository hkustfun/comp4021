# COMP4021 Internet Computing

## HTML (Hypertext Markup Language)
HTML is the standard markup language for creating web pages.
An HTML document starts with a `<!DOCTYPE html>` declaration, followed by `<html>`, `<head>`, and `<body>` tags.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Page Title</title>
</head>
<body>
  <!-- Content goes here -->
</body>
</html>
```

### Common Tags

- **Headings**: `<h1>` to `<h6>`
  ```html
  <h1>Main Heading</h1>
  <h2>Subheading</h2>
  ```
- **Paragraph**: `<p>`
  ```html
  <p>This is a paragraph.</p>
  ```
- **Links**: `<a href="URL">`
  ```html
  <a href="https://example.com">Visit Example.com</a>
  ```
- **Images**: `<img src="image.jpg" alt="Description">`
  ```html
  <img src="path/to/image.jpg" alt="An image description">
  ```
- **Lists**:
  - **Ordered List**: `<ol>`, `<li>`
    ```html
    <ol>
      <li>First item</li>
      <li>Second item</li>
    </ol>
    ```
  - **Unordered List**: `<ul>`, `<li>`
    ```html
    <ul>
      <li>Bullet item</li>
      <li>Another item</li>
    </ul>
    ```
- **Tables**:
  ```html
  <table>
    <thead>
      <tr>
        <th>Header 1</th>
        <th>Header 2</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
      </tr>
    </tbody>
  </table>
  ```

### Forms

Forms are used to collect user input.

```html
<form action="/submit" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="user_name">
  <input type="submit" value="Submit">
</form>
```

## CSS (Cascading Style Sheets)

CSS describes how HTML elements are to be displayed.

### Basic Usage

- **Inline Style**: Using the `style` attribute within HTML tags.
  ```html
  <p style="color:blue;">Blue text</p>
  ```
- **Internal Stylesheet**: Placed inside `<style>` tags within the `<head>`.
  ```html
  <style>
    p { color: blue; }
  </style>
  ```
- **External Stylesheet**: Using a separate `.css` file linked via `<link>`.
  ```html
  <head>
    <link rel="stylesheet" href="styles.css">
  </head>
  ```

### Selectors

- **Element Selector**: Selects all elements of a given type.
  ```css
  p {
    font-size: 16px;
  }
  ```
- **ID Selector**: Selects an element with a specific `id`.
  ```css
  #unique-element {
    background-color: yellow;
  }
  ```
  ```html
  <div id="unique-element"></div>
  ```
- **Class Selector**: Selects elements with a specific `class`.
  ```css
  .highlight {
    color: red;
  }
  ```
  ```html
  <span class="highlight">Important</span>
  ```

### Common Properties

- **Color and Background**
  ```css
  color: blue;
  background-color: lightgray;
  ```
- **Font**
  ```css
  font-family: Arial, sans-serif;
  font-size: 14px;
  font-weight: bold;
  ```
- **Text Alignment**
  ```css
  text-align: center;
  ```
- **Margin and Padding**
  ```css
  margin: 10px;
  padding: 20px;
  ```
- **Border**
  ```css
  border: 1px solid black;
  border-radius: 5px;
  ```

### Box Model

- Consists of `margin`, `border`, `padding`, and `content`.

## JavaScript

JavaScript is a scripting language for creating dynamic web content.

### Including JavaScript in HTML

- **Inline Script**
  ```html
  <script>
    alert('Hello, World!');
  </script>
  ```
- **External Script**
  ```html
  <script src="script.js"></script>
  ```

### Variables

- Declare variables using `var`, `let`, or `const`.
  ```javascript
  let name = 'Alice';
  const PI = 3.1415;
  ```

### Functions

- Define a function:
  ```javascript
  function greet(name) {
    return 'Hello, ' + name + '!';
  }
  ```
- Using an anonymous function:
  ```javascript
  let greet = function(name) {
    return 'Hello, ' + name + '!';
  };
  ```

### Events

- Add event listeners to elements.
  ```html
  <button onclick="alert('Button clicked!')">Click Me</button>
  ```

### DOM Manipulation

- Access elements:
  ```javascript
  let element = document.getElementById('my-id');
  let elements = document.getElementsByClassName('my-class');
  ```
- Modify content:
  ```javascript
  element.innerHTML = 'New Content';
  ```
- Change styles:
  ```javascript
  element.style.color = 'blue';
  ```

## The Document Object Model (DOM)

The DOM represents the page so that programs can change the document structure, style, and content.

### DOM Access Methods

- **By ID**
  ```javascript
  let element = document.getElementById('unique-id');
  ```
- **By Class Name**
  ```javascript
  let elements = document.getElementsByClassName('class-name');
  ```
- **By Tag Name**
  ```javascript
  let elements = document.getElementsByTagName('div');
  ```
- **Query Selectors**
  ```javascript
  let element = document.querySelector('.my-class');
  let elements = document.querySelectorAll('div.my-class');
  ```

### Manipulating the DOM

- **Create Elements**
  ```javascript
  let newDiv = document.createElement('div');
  ```
- **Append Elements**
  ```javascript
  parentElement.appendChild(newDiv);
  ```
- **Remove Elements**
  ```javascript
  parentElement.removeChild(childElement);
  ```

## jQuery

jQuery is a fast, small, and feature-rich JavaScript library that simplifies HTML document traversal and manipulation.

### Selecting Elements

- **By Tag**
  ```javascript
  $('p').hide(); // Hides all <p> elements
  ```
- **By ID**
  ```javascript
  $('#my-id').show(); // Shows the element with id="my-id"
  ```
- **By Class**
  ```javascript
  $('.my-class').css('color', 'red');
  ```

### Event Handling

```javascript
$('#my-button').on('click', function() {
  alert('Button clicked!');
});
```

### AJAX with jQuery

```javascript
$.ajax({
  url: 'data.json',
  method: 'GET',
  success: function(data) {
    console.log(data);
  }
});
```

## AJAX (Asynchronous JavaScript and XML)

AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes.

### Fetch API

- **GET Request**
  ```javascript
  fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data));
  ```
- **POST Request**
  ```javascript
  fetch('https://api.example.com/data', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({ key: 'value' })
  })
  .then(response => response.json())
  .then(data => console.log(data));
  ```

## JSON (JavaScript Object Notation)

JSON is a lightweight data-interchange format.

### Example JSON

```json
{
  "name": "Alice",
  "age": 30,
  "isMember": true
}
```

### Parsing JSON in JavaScript

```javascript
let jsonData = '{"name": "Alice", "age": 30}';
let obj = JSON.parse(jsonData);
console.log(obj.name); // "Alice"
```

### Stringify JavaScript Object to JSON

```javascript
let obj = { name: 'Alice', age: 30 };
let jsonString = JSON.stringify(obj);
```

## Node.js and Express

Node.js is a JavaScript runtime built on Chrome's V8 engine. Express is a minimal and flexible Node.js web application framework.

### Setting Up an Express Server

1. Install Express:
   ```bash
   npm install express
   ```
2. Basic Server Setup:
   ```javascript
   const express = require('express');
   const app = express();

   app.get('/', (req, res) => {
     res.send('Hello World!');
   });

   app.listen(3000, () => {
     console.log('Server is running on port 3000');
   });
   ```

### Middleware

Middleware functions have access to the request and response objects.

```javascript
app.use((req, res, next) => {
  console.log('Middleware executed');
  next();
});
```

### Serving Static Files

```javascript
app.use(express.static('public'));
```

## WebSocket and Socket.IO

WebSocket provides full-duplex communication channels over a single TCP connection.

### Using Socket.IO

- **Server Side**

  ```javascript
  const io = require('socket.io')(server);

  io.on('connection', (socket) => {
    console.log('a user connected');

    socket.on('chat message', (msg) => {
      io.emit('chat message', msg);
    });

    socket.on('disconnect', () => {
      console.log('user disconnected');
    });
  });
  ```

- **Client Side**

  ```html
  <script src="/socket.io/socket.io.js"></script>
  <script>
    var socket = io();
    socket.on('chat message', function(msg){
      console.log('message: ' + msg);
    });
  </script>
  ```

## RESTful APIs

RESTful APIs are designed around resources.

### HTTP Methods

- **GET**: Retrieve a resource.
- **POST**: Create a new resource.
- **PUT**: Update a resource.
- **DELETE**: Delete a resource.

### Example with Express

```javascript
app.get('/users', (req, res) => {
  // Return list of users
});

app.post('/users', (req, res) => {
  // Create a new user
});

app.put('/users/:id', (req, res) => {
  // Update user with id
});

app.delete('/users/:id', (req, res) => {
  // Delete user with id
});
```

## Sessions and Cookies

### Cookies

- Set a cookie:
  ```javascript
  res.cookie('name', 'value', { maxAge: 900000, httpOnly: true });
  ```
- Read a cookie:
  ```javascript
  let name = req.cookies['name'];
  ```

### Sessions

- Using `express-session` middleware:
  ```javascript
  const session = require('express-session');
  app.use(session({
    secret: 'secret-key',
    resave: false,
    saveUninitialized: true
  }));
  ```
- Set session variable:
  ```javascript
  req.session.userId = user.id;
  ```
- Access session variable:
  ```javascript
  let userId = req.session.userId;
  ```

## Authentication with JWT (JSON Web Tokens)

### Generating a Token

```javascript
const jwt = require('jsonwebtoken');
let token = jwt.sign({ id: user.id }, 'secret-key', { expiresIn: '1h' });
```

### Verifying a Token

```javascript
jwt.verify(token, 'secret-key', (err, decoded) => {
  if (err) {
    // Token invalid
  } else {
    // Token valid
    console.log(decoded.id);
  }
});
```

## HTML Forms

- **Form with GET method**

  ```html
  <form action="/search" method="get">
    <input type="text" name="query">
    <input type="submit" value="Search">
  </form>
  ```

- **Form with POST method**

  ```html
  <form action="/submit" method="post">
    <input type="text" name="name">
    <input type="submit" value="Submit">
  </form>
  ```

## Template Engines (EJS)

EJS allows you to generate HTML markup with plain JavaScript.

### Basic Usage

- **Render an EJS Template**

  ```javascript
  res.render('index', { title: 'My Page', message: 'Hello there!' });
  ```

- **EJS Template: index.ejs**

  ```ejs
  <h1><%= title %></h1>
  <p><%= message %></p>
  ```

### Loops and Conditions

- **Loop**

  ```ejs
  <% items.forEach(function(item){ %>
    <li><%= item %></li>
  <% }); %>
  ```

- **Condition**

  ```ejs
  <% if(user) { %>
    <h2>Welcome, <%= user.name %></h2>
  <% } else { %>
    <a href="/login">Login</a>
  <% } %>
  ```

## CSS Animations

### Basic Animation

```css
@keyframes slidein {
  from { transform: translateX(0%); }
  to { transform: translateX(100%); }
}

.element {
  animation-name: slidein;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}
```

## SVG (Scalable Vector Graphics)

SVG is used to define vector-based graphics for the Web.

### Basic SVG Example

```html
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green"
  stroke-width="4" fill="yellow" />
</svg>
```

## Canvas

Canvas is an HTML element used to draw graphics on a web page.

### Drawing on Canvas

- **HTML**

  ```html
  <canvas id="myCanvas" width="200" height="100"></canvas>
  ```

- **JavaScript**

  ```javascript
  let c = document.getElementById("myCanvas");
  let ctx = c.getContext("2d");
  ctx.fillStyle = "#FF0000";
  ctx.fillRect(0, 0, 150, 75);
  ```

## Timers in JavaScript

### setTimeout and setInterval

- **setTimeout**

  ```javascript
  setTimeout(function() {
    alert('Delayed message');
  }, 2000); // Executes after 2 seconds
  ```

- **setInterval**

  ```javascript
  setInterval(function() {
    console.log('Repeating message');
  }, 1000); // Executes every 1 second
  ```

## Modules in JavaScript

### Exporting and Importing Modules

- **Exporting**

  ```javascript
  // In file module.js
  module.exports = function () {
    // Module code
  };
  ```

- **Importing**

  ```javascript
  const myModule = require('./module');
  myModule();
  ```

## Error Handling

### Try...Catch

```javascript
try {
  // Code that may throw an error
} catch (error) {
  console.error(error.message);
}
```

## Promises

### Creating a Promise

```javascript
let myPromise = new Promise(function(resolve, reject) {
  // Asynchronous code
  if (/* success */) resolve('Success!');
  else reject('Failure!');
});
```

### Using Promises

```javascript
myPromise
  .then(function(value) {
    // Success
  })
  .catch(function(error) {
    // Failure
  });
```

## Async/Await

Simplifies working with promises in asynchronous code.

```javascript
async function myAsyncFunction() {
  try {
    let result = await myPromise();
    console.log(result);
  } catch (error) {
    console.error(error);
  }
}
```

# Short Examples

- **HTML Link Opening in New Tab**

  ```html
  <a href="https://example.com" target="_blank">Visit Example.com</a>
  ```

- **CSS Centering an Element**

  ```css
  .center {
    margin: auto;
    width: 50%;
    text-align: center;
  }
  ```

- **JavaScript Event Listener**

  ```javascript
  document.getElementById('myButton').addEventListener('click', function() {
    alert('Button clicked!');
  });
  ```

- **Express Route Handling**

  ```javascript
  app.get('/user/:id', function(req, res) {
    res.send('User ID: ' + req.params.id);
  });
  ```

- **EJS Iteration**

  ```ejs
  <ul>
    <% for(let i=0; i<items.length; i++) { %>
      <li><%= items[i] %></li>
    <% } %>
  </ul>
  ```
