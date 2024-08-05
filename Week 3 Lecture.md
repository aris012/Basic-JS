Typora

A different version of Typora has been uploaded to **Announcement Week 2 resources**, if you have problem installing the previous one, try this one instead.

If you don't have Typora, you can still open lecture materials in **Visual Studio Code**, then click shift+ctrl+v to open preview mode



# Week 2 Review

1. Client-side and server-side development: One major difference between  is where code runs. In client-side development, the code runs on the client's or user's device, In server-side development, the code runs through a server.

2. **3 languages** for Client-side development
   - [**HTML**](https://www.w3schools.com/html/default.asp) to define the content of web pages
   - [**CSS**](https://www.w3schools.com/css/default.asp) to specify the layout of web pages
   - **JavaScript** to program the behavior of web pages

3. Where to write JavaScript code?
   - Browser Console 
   - Browser Sources tab - Snippets
   - Code editor

4. Project File Structure
   - html files
   - styles/ 
   - scripts/
   - images/

5. Naming conventions for project folders and files
   - in lowercase with no space
   - separate words with hyphens, such as `my-file.html`

6. what are the places that we can write/load JavaScript code inside an HTML file? 
   - Inline JavaScript  `onclick` `onmouseover` `onmouseout`  `onchange`  etc
   - Internal JavaScript  
   - External JavaScript 

7. JavaScript comments
   - single line comments   //
   - Multi-line comments:  start with `/*` and end with `*/`. 

8. JavaScript Data Types - Number
   - you can write numbers and standard arithmetic operators to express mathematical operations just like normal math
   - JavaScript Arithmetic Operators:  +    -    *    **    /    %     ++    --  
   - Order of Operations: (...) parentheses, Multiplication (`*`) and division (`/`) ,  addition (`+`) and subtraction (`-`)

9. JavaScript Data Types - String
   - String = text
   - 3 ways to create a string: single quotes, double quotes, back ticks(template strings)
   - Escape characters   \'     \"    \n
   - Template strings:   allow single and double quotes inside a string; allow multiline strings;  provide a easy way to interpolate **variables and expressions** into strings

10. Variables

   - what is variable :  variables = a way to save values
   - how to declare a variable : let   const
   - A variable declared without a value will have the value `undefined`.
   - When to Use var, let, or const?  
     - Always declare variables
     - Use const by default (Only use `let` if you can't use `const`)
     - If we have to change a variable then use let
     - Only use `var` if you MUST support old browsers.


   - Variable Naming Conventions
   - typeof Operator 

11. Booleans

    - Booleans: have 2 values : true, false
    - comparison operators  >    <     >=     <=     ===       !==

12. If-Statements

    - if statement: let us write multiple groups of code, then decide which code to run

    -  if statement syntax
    - logical operators:   &&      ||       ! 
    - Oder of operations    (...) ,  *   /  ,    +    -,     comparison operators,  logical operators
    - Scope:  A scope limits where a variable exists. it helps us avoid naming conflicts. Any variable created inside {...} will only exist inside the {...}. var doesn't follow the rules of scope, so we don't use var anymore




# 3.1 Truthy and Falsy Values

if statement don't just work with Boolean values like true or false, they actually work with any type of value including numbers and strings.

```js
if (5) {
    consol.log('truthy');
}
// output is true 
// we call 5 a truthy value because it behaves just like true
// try to change value to 0 (falsy value)
```

**Falsy values:**

```js
false
0
''
NaN        
undefined
null 

/*
NaN stands for Not a Number. we get NaN if we do some invalid math. for example:
console.log('text'/5);

undefined means something doesn't have a value. for example
let variable1;
console.log(variable1);

null: exists, but was specifically assigned an empty or null value
let user = null;
*/
```





# 3.2 Ternary Operator

- Shortcuts for If-Statements

- A concise way to write conditional statements. 


## Syntax

It takes three operands and has the following syntax:

````js
condition ? expressionIfTrue : expressionIfFalse
````

## Example

Below is an example of using the ternary operator in a JavaScript program. 

Suppose you have a function that determines if a user is eligible for a discount based on their age:

````js
function getDiscountMessage(age) {
  if (age >= 65) {
    return 'You are eligible for a senior discount!';
  } else {
    return 'No discount available for your age group.';
  }
}
````



```javascript
function getDiscountMessage(age) {
  return age >= 65 ? 'You are eligible for a senior discount!' : 'No discount available for your age group.';
}

// Example usage:
const userAge = 70;
console.log(getDiscountMessage(userAge)); // Output: You are eligible for a senior discount!

const anotherUserAge = 30;
console.log(getDiscountMessage(anotherUserAge)); // Output: No discount available for your age group.
```

In this example:
- The ternary operator checks if the `age` is greater than or equal to 65.
- If `true`, it returns `'You are eligible for a senior discount!'`.
- If `false`, it returns `'No discount available for your age group.'`.

This allows you to condense the logic into a single line of code, making it both concise and readable.

## **Another advantage** 

**Another advantage** of Ternary operator over an if statement is that we can save a Ternary operator in a variable

**Using ternary operator**

```javascript
// write code that checks if a person can drive in New Zealand based on their age

const age = 18;
const status = age >= 16 ? 'Can drive in NZ' : 'Cannot drive in NZ';

console.log(status); // Output: Adult
```

In this example:
- The ternary operator evaluates whether `age` is greater than or equal to 18.
- If `true`, it assigns `'Adult'` to the `status` variable.
- If `false`, it assigns `'Minor'` to the `status` variable.

**Using an `if` Statement**

```javascript
const age = 18; 
let status;

if (age >= 16) {
  status = 'Can drive in NZ';
} else {
  status = 'Cannot drive in NZ';
}

console.log(status); // Output: Can drive in NZ
```

In this `if` statement version:
- We declare the `status` variable first.
- We use the `if` statement to determine the value of `status` based on the `age` condition.

## Comparison

- **Ternary Operator**: Allows for a more compact and readable single-line assignment.
- **If Statement**: Requires more lines of code to achieve the same result.

The ternary operator can make your code shorter and cleaner, especially when dealing with simple conditional assignments.



# 3.3 Object	

## why do we need object?

It's hard to store real-world entities without using objects because objects allow us to group related information together in one place. For example, if you want to store information about a car (like its brand, model, and color), doing this without objects would mean using separate variables for each piece of information, making it messy and hard to manage. With objects, you can keep everything related to the car in one structured unit, making your code more organized and easier to work with.

Objects in JavaScript are a fundamental data type used to store collections of data and more complex entities. They allow you to group related data and functions together.

- object let us **group** multiple values together
- object let us **use** multiple values together

## What is an Object?

An object is a collection of key-value pairs (or property-value pair), and the value can be any data type, including other objects or functions.

### Creating an Object

You can create an object using curly braces `{}`. Here's a simple example:

```javascript
let person = {
    name: 'John',
    age: 30,
    job: 'Engineer'
};
```

In this example, `person` is an object with three properties:

- `name` with the value `'John'`
- `age` with the value `30`
- `job` with the value `'Engineer'`

### Accessing Object Properties

You can access the properties of an object using dot notation or bracket notation.

**which one should we use?**

- use dot notation by default
- for properties that don't work with dot notation, use bracket notation 

**Dot Notation:**

```javascript
console.log(person.name); // Output: John
console.log(person.age);  // Output: 30
```

**Bracket Notation:**

```javascript
console.log(person['name']); // Output: John
console.log(person['age']);  // Output: 30
```

### Adding and Modifying Properties

You can add new properties to an object or modify existing ones:

```javascript
person.city = 'New York'; // Adding a new property
person.age = 31;          // Modifying an existing property

console.log(person.city); // Output: New York
console.log(person.age);  // Output: 31
```

### Deleting Properties

You can delete properties from an object using the `delete` operator:

```javascript
delete person.job;

console.log(person.job); // Output: undefined
```

### Methods and **Nested Object:**

- The `address` property below is an nested object containing `street`, `city`, and `country` properties.
- Access nested properties using dot notation, e.g., `person.address.city`.

Objects can also have functions as properties. These functions are called **methods**. Here's an example:

```javascript
let person = {
    name: 'John',
    age: 30,
    job: 'Engineer',
    address: {
        street: '123 Main St',
        city: 'Anytown',
        country: 'USA'
    },
    greet: function() {
        console.log('Hello, my name is ' + this.name);
    }
};

person.greet(); // Output: Hello, my name is John
```

In this example, `greet` is a method of the `person` object that prints a greeting message using the object's `name` property.

When this function is called, it uses the `this` keyword to refer to the `person` object, specifically the `name` property of the object. It prints: `'Hello, my name is John'`.





# 3.4 DOM

## What is the DOM?

The DOM (Document Object Model) is a way to represent the structure of an HTML document in a tree-like format. It allows JavaScript to interact with and manipulate the HTML elements on a webpage.

### Interacting with the DOM using JavaScript

JavaScript can be used to interact with and change the DOM. Let's look at some simple examples.

In the DOM, all HTML elements are defined as **objects**.

The programming interface is the properties and methods of each object.

A **property** is a value that you can get or set (like changing the content of an HTML element).

A **method** is an action you can do (like add or deleting an HTML element).

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DOM</title>
</head>
<body>
  <h1>Hello</h1>
  <p id="demo">This is a paragraph.</p>

  <script>
    document.getElementById("demo").innerHTML = "Hello World!";
  </script>
</body>
</html>
```

In the example above, `getElementById` is a **method**, while `innerHTML` is a **property**.





## 1. Finding HTML Elements

Often, with JavaScript, you want to manipulate HTML elements.

To do so, you have to find the elements first. There are several ways to do this:

- Finding HTML elements by id
- Finding HTML elements by tag name
- Finding HTML elements by class name
- Finding HTML elements by CSS selectors

You can select elements in the DOM using JavaScript. 

```javascript
const element = document.getElementById("intro");  // finds the element with id="intro":
const element = document.getElementsByTagName("p"); //finds all <p> elements:
const element = document.getElementsByClassName("intro"); //returns a list of all elements with class="intro".
const element = document.querySelector("p.intro");//returns the first element that matches a specified CSS selector(s) of an element.
const element = document.querySelectorAll("p.intro"); //returns a list of all <p> elements with class="intro".
```

## 2. JavaScript HTML DOM - Changing HTML

The HTML DOM allows JavaScript to change the content of HTML elements.

```javascript
document.getElementById("p1").innerHTML = "New text!"; //changes the content of a <p> element to "New text!"
document.querySelector('h1').textContent = 'Hello, JavaScript!';

```

## 3. Changing the Value of an Attribute

To change the value of an HTML attribute, use this syntax:

````js
document.getElementById(id).attribute = new value
````

This example changes the value of the src attribute of an `<img>` element:

````js
<!DOCTYPE html>
<html>
<body>

<img id="myImage" src="smiley.gif">

<script>
document.getElementById("myImage").src = "landscape.jpg";
</script>

</body>
</html>

/*
Example explained:

The HTML document above contains an <img> element with id="myImage"
We use the HTML DOM to get the element with id="myImage"
A JavaScript changes the src attribute of that element from "smiley.gif" to "landscape.jpg"
*/
````



## 4. Changing HTML Style

The HTML DOM allows JavaScript to change the style of HTML elements.

To change the style of an HTML element, use this syntax:

````js
document.getElementById(id).style.property = new style
````

For example, to change the color of the `<h1>` text:

```javascript
let heading = document.querySelector('h1');
heading.style.color = 'blue';
```

Now, the text "Hello, JavaScript!" will appear in blue.

## 5. Adding New Elements

You can add new elements to the DOM. For example, to add a new paragraph:

```javascript
let newParagraph = document.createElement('p');
newParagraph.textContent = 'This is a new paragraph added by JavaScript.';
document.body.appendChild(newParagraph);
```

Now, the HTML will have a new paragraph at the end of the body:

```html
<p>This is a new paragraph added by JavaScript.</p>
```

## 6.HTML DOM Element remove()

````js
const element = document.getElementById("demo");  
element.remove();   //Remove an element from the document
````





# 3.5 DOM Events

A JavaScript can be executed when an event occurs, like when a user clicks on an HTML element.

Examples of HTML events:

- When a user clicks the mouse
- When a web page has loaded
- When an image has been loaded
- When the mouse moves over an element
- When an input field is changed
- When an HTML form is submitted
- When a user strokes a key



In JavaScript, you can add event listeners to HTML elements in three main ways:

1. **Inline Event Handlers**:
   - You add the event handler directly in the HTML element using attributes like `onclick`, `onmouseover`, `onchange`, etc.
   - **Example**:
     ```html
     <!-- Assign an onclick event to a button element -->
     <button onclick="alert('Button clicked!')">Click Me</button> 

     <div onmouseover="console.log('Mouse over!')">Hover over me</div>
     <div onmouseout="console.log('Mouse out!')">Hover over me</div>
     <input type="text" onchange="console.log('Input changed!')" />
     <input type="text" oninput="console.log('Input event!')" />
     ```
     ​

2. **DOM Property Event Handlers**:
   - You set event handler properties directly on DOM elements using JavaScript.
   - **Example**:
     ```javascript
     const button = document.getElementById('myButton');
     button.onclick = function() {
         alert('Button clicked!');
     };
     ```
   - **Explanation**: The `onclick` property of the `button` element is assigned a function that will be executed when the button is clicked.

3. **`addEventListener` Method**:
   - You use the `addEventListener` method to attach event listeners to DOM elements. This method allows you to add multiple event listeners to a single element and offers more control over event handling.
   - **Example**:
     ```javascript
     const button = document.getElementById('myButton');
     button.addEventListener('click', function() {
         alert('Button clicked!');
     });
     ```
   - **Explanation**: The `addEventListener` method attaches a function to the `click` event of the `button` element. This method supports additional options like capturing, passive listeners, and more.



Each method has its use cases and can be chosen based on the needs of the application. The `addEventListener` method is generally preferred for its flexibility and ability to attach multiple handlers.

| Event            | Event is fired                                               |
| ---------------- | ------------------------------------------------------------ |
| click            | When you press down and release the primary mouse button. Used to track buttons and clickable elemennts |
| mousemove        | When you move the mouse cursor                               |
| mouseover        | When you move the mouse cursor over an element. It's like the CSS hover state |
| mouseout         | When your mouse cursor moves outside the boundaries of an element |
| dblclick         | When you click twice                                         |
| DOMContentLoaded | When the DOM content is fully loaded                         |
| keydown          | When you press a key on your keyboard                        |
| keyup            | When you release a key on your keyboard                      |
| submit           | When a form is submitted                                     |

https://www.freecodecamp.org/news/dom-events-and-javascript-event-listeners/



# 3.6 Todo Demo 

create function, calling function, finding element, changing element,  creating element, removing element, adding event listener



# 3.7 Array

https://www.w3schools.com/js/js_arrays.asp

An array is a special variable, which can hold more than one value

An array can hold many values under a single name, and you can access the values by referring to an index number.

Syntax:

````js
const array_name = [item1, item2, ...];   
````



### 1. Array Creation and Initialization

Create an array of your favorite fruits and initialize it with at least 5 items.

```javascript
let fruits = ['Apple', 'Banana', 'Cherry', 'Date', 'Elderberry'];
```

- Arrays are used to store multiple values in a single variable.

- The `fruits` array is created and initialized with five fruit names.

  ​

### 2. Accessing Array Elements

Access and log the first and last elements of the `fruits` array.

```javascript
console.log(fruits[0]); // Output: Apple
console.log(fruits[fruits.length - 1]); // Output: Elderberry
```

- Arrays are zero-indexed, meaning the first element is at index `0`.

- `fruits[0]` accesses the first element.

- `fruits[fruits.length - 1]` accesses the last element by using the array's length property.

  ​

### 3. Adding Elements

Add a new fruit to the beginning and end of the `fruits` array.

```javascript
fruits.unshift('Fig'); // Add to the beginning
fruits.push('Grapes'); // Add to the end
```

- `unshift('Fig')` adds 'Fig' to the beginning of the array.

- `push('Grapes')` adds 'Grapes' to the end of the array.

  ​

### 4. Removing Elements

Remove the first and last fruits from the `fruits` array.

```javascript
fruits.shift(); // Remove from the beginning
fruits.pop(); // Remove from the end
```

- `shift()` removes the first element from the array.

- `pop()` removes the last element from the array.

  ​

### 5. Finding Elements

Check if a specific fruit is in the array and find its index.

```javascript
const hasBanana = fruits.includes('Banana'); // Check if 'Banana' is in the array
const indexOfCherry = fruits.indexOf('Cherry'); // Find the index of 'Cherry'
console.log(hasBanana); // Output: true or false
console.log(indexOfCherry); // Output: Index of 'Cherry' or -1 if not found
```

- `includes('Banana')` checks if 'Banana' is in the array and returns `true` or `false`.
- `indexOf('Cherry')` returns the index of 'Cherry' in the array or `-1` if it is not found.



### 6. Iterating Over Arrays

Use a `for` loop and the `forEach` method to log each fruit in the `fruits` array.

```javascript
// Using a for loop
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}

// Using forEach method
fruits.forEach(fruit => console.log(fruit));
```

- A `for` loop iterates through the array by index, logging each fruit.


- **forEach Method**: The `forEach` method is an array method that executes a provided function once for each array element,  logging each fruit.

In this example, the arrow function `fruit => console.log(fruit)` is passed as an argument to the `forEach` method.

```
fruit => console.log(fruit)
```

- **fruit**: fruit is the parameter of the arrow function, representing each element of the `fruits`
- **console.log(fruit)**: This is the body of the arrow function, which logs each fruit to the console.






### Exercise: Array Operations

#### 1. **Array Creation and Initialization**

**Task**: Create an array of your favorite fruits and initialize it with at least 5 items.

**Example**:
```javascript
let fruits = ['Apple', 'Banana', 'Cherry', 'Date', 'Elderberry'];
```

#### 2. **Accessing Array Elements**

**Task**: Access and log the first and last elements of the `fruits` array.

**Example**:
```javascript
console.log(fruits[0]); // Output: Apple
console.log(fruits[fruits.length - 1]); // Output: Elderberry
```

#### 3. **Adding Elements**

Add a new fruit to the beginning and end of the `fruits` array.

```javascript
fruits.unshift('Fig'); // Add to the beginning
fruits.push('Grapes'); // Add to the end
```

#### 4. **Removing Elements**

 Remove the first and last fruits from the `fruits` array.

```javascript
fruits.shift(); // Remove from the beginning
fruits.pop(); // Remove from the end
```

#### 5. **Finding Elements**

 Check if a specific fruit is in the array and find its index.

```javascript
const hasBanana = fruits.includes('Banana'); // Check if 'Banana' is in the array
const indexOfCherry = fruits.indexOf('Cherry'); // Find the index of 'Cherry'
console.log(hasBanana); // Output: true or false
console.log(indexOfCherry); // Output: Index of 'Cherry' or -1 if not found
```

#### 6. **Iterating Over Arrays**

 Use a `for` loop and the `forEach` method to log each fruit in the `fruits` array.

```javascript
// Using a for loop
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}

// Using forEach
fruits.forEach(fruit => console.log(fruit));
```

#### 7. **Transforming Arrays**

Create a new array with the lengths of each fruit's name using the `map` method.

```javascript
const fruitLengths = fruits.map(fruit => fruit.length);
console.log(fruitLengths); // Output: Array of lengths of each fruit name
```

#### 8. **Filtering Arrays**

Filter out fruits with names longer than 5 characters using the `filter` method.

```javascript
const longNamedFruits = fruits.filter(fruit => fruit.length > 5);
console.log(longNamedFruits); // Output: Fruits with names longer than 5 characters
```

#### 9. **Sorting Arrays**

Sort the `fruits` array in alphabetical order and log the sorted array.

```javascript
fruits.sort();
console.log(fruits); // Output: Fruits sorted in alphabetical order
```

#### 10. **Joining Arrays**

Join the elements of the `fruits` array into a single string, separated by commas.

```javascript
const fruitString = fruits.join(', ');
console.log(fruitString); // Output: Fruits joined into a single string separated by commas
```

#### 11. **Combining Arrays**

Combine the `fruits` array with another array of vegetables.

```javascript
const vegetables = ['Carrot', 'Lettuce', 'Spinach'];
const combinedArray = fruits.concat(vegetables);
console.log(combinedArray); // Output: Combined array of fruits and vegetables
```

#### 12. **Finding and Reducing**

Use the `find` method to locate a specific fruit 

```javascript
const foundFruit = fruits.find(fruit => fruit === 'Banana');
console.log(foundFruit); // Output: 'Banana' or undefined if not found
```

we use the `find` method to search through an array for a specific item. Here's a simple explanation:

1. **fruits**: This is an array containing a list of fruit names.
2. **find()**: This method searches through the `fruits` array to find the first element that matches a certain condition.
3. **Arrow Function**: `fruit => fruit === 'Banana'`
   - **fruit**: Represents each element of the `fruits` array as it is checked.
   - **fruit === 'Banana'**: This condition checks if the current `fruit` is equal to `'Banana'`.

In this example, `foundFruit` will be `'Banana'` because that is the first match in the array. If `'Banana'` were not in the array, `foundFruit` would be `undefined`.

The `find` method looks for the first item in the array that meets the condition provided by the arrow function. It returns the item if it is found; otherwise, it returns `undefined`.









# Self Reading Material



##  `for` Loop in JavaScript

A `for` loop is a way to repeat a block of code a certain number of times. It is commonly used when you know in advance how many times you want to execute a statement or a block of statements.

### Basic Structure

The `for` loop has three parts: initialization, condition, and increment/decrement.

```javascript
for (initialization; condition; increment/decrement) {
    // Code to be executed in each iteration
}
```

### Explanation

1. **Initialization**: This sets up a variable to start the loop. It runs once at the beginning of the loop.
2. **Condition**: This is checked before each iteration of the loop. If the condition is true, the loop continues. If the condition is false, the loop stops.
3. **Increment/Decrement**: This updates the variable used in the condition after each iteration of the loop.

### Example

Here’s a simple example that prints numbers from 1 to 5:

```javascript
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

### Breakdown of the Example

1. **Initialization**: `let i = 1;` 
   - This sets up the variable `i` and initializes it to 1.
2. **Condition**: `i <= 5;`
   - Before each iteration, the loop checks if `i` is less than or equal to 5. If true, the loop continues. If false, the loop stops.
3. **Increment**: `i++`
   - After each iteration, `i` is incremented by 1 (`i++` is shorthand for `i = i + 1`).

### Iterations

1. **First Iteration**: `i` is 1, condition is true, `console.log(i)` prints 1, `i` becomes 2.
2. **Second Iteration**: `i` is 2, condition is true, `console.log(i)` prints 2, `i` becomes 3.
3. **Third Iteration**: `i` is 3, condition is true, `console.log(i)` prints 3, `i` becomes 4.
4. **Fourth Iteration**: `i` is 4, condition is true, `console.log(i)` prints 4, `i` becomes 5.
5. **Fifth Iteration**: `i` is 5, condition is true, `console.log(i)` prints 5, `i` becomes 6.
6. **Sixth Iteration**: `i` is 6, condition is false, the loop stops.

### Summary

A `for` loop lets you repeat a block of code a specific number of times. It consists of three parts: initialization (set up a starting value), condition (check if the loop should continue), and increment/decrement (update the value). It’s a useful way to perform repetitive tasks in JavaScript.







## Traditional function and arrow function

### **what is a function?**

- a block of code designed to perform a particular task which is executed when it is called or invoked.

**why do we use functions?** 

- function lets us reuse code

#### Function Syntax

### Traditional Function Syntax

**Syntax**:

````js
function functionName(parameters) {
  ...
}
````

**example**:

````js
function addNumbers(a, b) {
  const sum = a + b;
  return sum;
}

const result = addNumbers(5, 3);
console.log(result); // Output: 8
````

In this example above:

- `addNumbers` is a function that takes two parameters, `a` and `b`.
- It calculates their sum and returns the result.
- The `result` variable stores the return value of the function, which is then logged to the console.




### Arrow Function Syntax

An arrow function is a simpler way to write a function in JavaScript. It uses a special syntax (`=>`) and is often shorter and easier to read.



**Regular Function**:
```javascript
function add(a, b) {
    return a + b;
}
```

**Arrow Function**:
```javascript
const add = (a, b) => {
    return a + b;
}
```

Even shorter if there is only one statement:
```javascript
const add = (a, b) => a + b;
```

### Is it an Anonymous Function?

arrow functions can be anonymous, meaning they don't have a name. However, they can also be assigned to variables or used as arguments to other functions.

**Anonymous Arrow Function Example**:
```javascript
let fruits = ['Apple', 'Banana', 'Cherry', 'Date', 'Elderberry'];
fruits.forEach(fruit => console.log(fruit));
```

In this example, the arrow function `fruit => console.log(fruit)` is passed as an argument to the `forEach` method.

### Key Features of Arrow Functions

1. **Shorter Syntax**: Arrow functions have a concise syntax.
2. **Implicit Return**: If the function body has only one expression, you can omit the `return` keyword.
3. **No `this` Binding**: Arrow functions do not have their own `this` value; they inherit `this` from the surrounding code. This is useful in many cases, especially when dealing with callbacks.

### Summary

- **Arrow Function**: A short and simple way to write functions in JavaScript.
- **Anonymous**: Arrow functions can be anonymous but can also be assigned to variables or used as arguments.
- **Special Syntax**: Uses the `=>` syntax for definition.
- **No Own `this`**: Arrow functions inherit `this` from their surrounding context.
















## Inline attributes 

Inline attributes in HTML are used to include JavaScript code directly within HTML tags. This is often done using event attributes, which are used to define event handler functions that are executed when specific events occur. 

Inline event attributes:

1. **`onclick`**: This attribute is used to execute JavaScript code when an element is clicked.

   ```html
   <button onclick="alert('Button clicked!')">Click Me</button>
   ```

2. **`onmouseover`**: This attribute is used to execute JavaScript code when the mouse pointer is moved over an element.

   ```html
   <div onmouseover="console.log('Mouse over!')">Hover over me</div>
   ```

3. **`onmouseout`**: This attribute is used to execute JavaScript code when the mouse pointer is moved out of an element.

   ```html
   <div onmouseout="console.log('Mouse out!')">Hover over me</div>
   ```

4. **`onchange`**: This attribute is used to execute JavaScript code when the value of an input element is changed.

   ```html
   <input type="text" onchange="console.log('Input changed!')" />
   ```

5. **`oninput`**: This attribute is used to execute JavaScript code when the user inputs something into an input element.

   ```html
   <input type="text" oninput="console.log('Input event!')" />
   ```
   ​


An example combining the `onclick`, `onmouseover`, `onmouseout`, `onchange`, and `oninput` event attributes. 

```html
<!DOCTYPE html>
<html>
<head>
  <title>Inline JavaScript Example</title>
</head>
<body>

  <h1>Inline JavaScript Event Attributes Example</h1>

  <button onclick="alert('Button clicked!')">Click Me</button>

  <div onmouseover="console.log('Mouse over!')" onmouseout="console.log('Mouse out!')" style="width: 200px; height: 100px; background-color: lightblue;">
    Hover over this box
  </div>

  <form>
    <label for="textInput">Text Input:</label>
    <input type="text" id="textInput" onchange="console.log('Input changed!')" oninput="console.log('Input event!')">
  </form>

</body>
</html>
```

In this example:
- When the button is clicked, an alert box will display "Button clicked!".
- When the mouse pointer is moved over the div, "Mouse over!" is logged to the console.
- When the mouse pointer is moved out of the div, "Mouse out!" is logged to the console.
- When text is entered in the input field, "Input event!" is logged to the console each time a character is typed.
- When the input field loses focus (or the form is submitted), "Input changed!" is logged to the console if the input value has changed.



## ES6

ES6, also known as ECMAScript 2015 or ECMAScript 6, is the sixth edition of the ECMAScript standard, which is the scripting language specification that JavaScript adheres to. ES6 introduced several new features and enhancements to the JavaScript language, making it more powerful and easier to use. Here are some of the key features introduced in ES6:

### Key Features of ES6

#### 1. **Let and Const**
- **`let`**: Declares block-scoped variables.
- **`const`**: Declares block-scoped constants.

```javascript
let x = 10;
const y = 20;
```

#### 2. **Arrow Functions**
- Shorter syntax for writing functions and lexically binds `this`.

```javascript
const add = (a, b) => a + b;
```

#### 3. **Template Literals**
- Allows for easier string interpolation and multi-line strings.

```javascript
const name = 'Alice';
const greeting = `Hello, ${name}!`;
```

#### 4. **Destructuring Assignment**
- Allows extracting values from arrays or objects into distinct variables.

```javascript
const [a, b] = [1, 2];
const {name, age} = {name: 'Alice', age: 25};
```

#### 5. **Default Parameters**
- Allows specifying default values for function parameters.

```javascript
function greet(name = 'Guest') {
  return `Hello, ${name}!`;
}
```

#### 6. **Rest and Spread Operators**
- **Rest**: Combines multiple elements into an array.
- **Spread**: Spreads elements of an array or object.

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

const arr = [1, 2, 3];
const newArr = [...arr, 4, 5];
```

#### 7. **Classes**
- Provides a syntactical sugar over JavaScript's prototype-based inheritance.

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    return `Hello, my name is ${this.name}`;
  }
}

const alice = new Person('Alice');
console.log(alice.greet());
```

#### 8. **Modules**
- Allows splitting code into modules and importing/exporting them.

```javascript
// Exporting
export const name = 'Alice';
export function greet() {
  return `Hello, ${name}!`;
}

// Importing
import { name, greet } from './module.js';
```

#### 9. **Promises**
- Provides a way to handle asynchronous operations more gracefully.

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve('Success!'), 1000);
});

promise.then(result => console.log(result));
```

#### 10. **Enhanced Object Literals**
- Allows defining properties and methods in a more concise way.

```javascript
const name = 'Alice';
const person = {
  name,
  greet() {
    return `Hello, my name is ${this.name}`;
  } 
};

//In ES6, if the property name and the variable name are the same, you can use the shorthand syntax.
//name, is shorthand for name: name,
//Method Shorthand:greet(){} is shorthand syntax for defining methods in an object. It is equivalent to writing greet: function() { ... }.
```

#### 
