# 2.1 What is client-side scripting and server-side scripting 

## Reading material 1

As the name suggests, a server is the one who serves.
The client is the one who requests the server to serve.

So when one opens [http://www.youtube.com](https://www.youtube.com/) in Internet Explorer (or any other browser), the browser goes to the Youtube machines on the internet, asking for the content to be displayed. Here, the browser is the client and the Youtube machines which are always running and serving content are the servers.

The one who initiates the request is a client.
The one who serves these requests is a server.

So writing any piece of code that runs on the server machine is a part of server side programming. And writing any piece of code that runs on the client side machine is a part of client side programming.

Some of the languages used for building clients are:

1. HTML + Javascript + CSS
2. C#
3. Java
4. Objective C
5. C/C++
6. Python

And some of the languages used for building servers are:

1. Java
2. PHP
3. Python
4. Ruby
5. JavaScript

Note that there are languages that can be used to write both servers and clients.

## Reading material 2

One major difference between client-side and server-side development is where code runs. In client-side development, the code runs on the client's or user's device. In server-side development, the code runs through a server.

![Difference Between Client Side Scripting and Server Side Scripting - Comparison Summary](https://i0.wp.com/pediaa.com/wp-content/uploads/2018/10/Difference-Between-Client-Side-Scripting-and-Server-Side-Scripting-Comparison-Summary-1.jpg?resize=475%2C507&ssl=1)

## Reading material 2

Client-side and server-side programming are two different approaches to handling the logic and functionality of applications, typically web applications. Here are the key differences between the two:

1. Client-side Programming:
   \- Client-side programming refers to the code that is executed on the user's device (such as a web browser), typically involving technologies like HTML, CSS, and JavaScript.
   \- The client-side code is downloaded from the server to the user's device and executed there.
   \- It is primarily responsible for the user interface and user interactions within the application.
   \- Changes made on the client-side are visible to the user without the need to communicate with the server.
   \- Common tasks performed on the client-side include form validation, dynamic content updates, animations, and handling user input.
2. Server-side Programming:
   \- Server-side programming refers to the code that runs on the server, typically using server-side languages like PHP, Python, Ruby, Java, etc.
   \- The server-side code processes requests from clients, interacts with databases, performs complex calculations, and generates dynamic content.
   \- Server-side code is not visible to users and runs on the server, responding to client requests.
   \- It is responsible for tasks such as authentication, data processing, business logic implementation, and database operations.
   \- Changes made on the server-side affect the data stored on the server and are then sent back to the client for display.

In summary, client-side programming focuses on the user interface and interactions within the user's browser, while server-side programming deals with processing requests, executing business logic, and interacting with databases on the server. Both client-side and server-side programming are essential components of web applications, working together to provide a seamless user experience.



# 2.2 JavaScript Introduction

## why study JavaScript 

JavaScript is one of the **3 languages** all web developers **must** learn:

   1. [**HTML**](https://www.w3schools.com/html/default.asp) to define the content of web pages

   2. [**CSS**](https://www.w3schools.com/css/default.asp) to specify the layout of web pages

   3. **JavaScript** to program the behavior of web pages 

      ​

JavaScript is the world's most popular programming language.

JavaScript is the programming language of the Web.

Canvas -  Module 2 - Fundamental Client-Side Scripting - [JavaScript Basics](https://learn.mywhitecliffe.com/courses/1725/modules/items/89410)

*JavaScript is unique among programming languages because it's the only one deployed on practically all personal computers around the world. All modern web browsers implement JavaScript*

## Commonly Asked Questions

- How do I get JavaScript?
- Where can I download JavaScript?
- Is JavaScript Free?

You don't have to get or download JavaScript. JavaScript is already running in your browser on your computer, on your tablet, and on your smart-phone. JavaScript is free to use for everyone.

## what JavaScript can do

- Listen to events like a mouse click and do something
- Modify the HTML and CSS of your page after the page has loaded
- Make things move around the screen in interesting ways
- Create awesome games that work in the browser
- Communicate data between the server and the browser
- Allow you to interact with a webcam, microphone, and other devices

https://www.w3schools.com/js/js_intro.asp 





# 2.3 JavaScript Data Types

We can use the console to write and run JavaScript.

The Console is a tool in your browser's Developer Tools used for debugging and logging JavaScript code.

Open up your browser, press Command+Option+J (Mac) or **Control+Shift+J** (Windows, Linux, ChromeOS) to open the **Console**

```
alert("Hello");
```



**Sources - Snippets**

you can also write JavaScript code in the **Sources** tab of the browser's Developer Tools

In the Sources tab of the browser's Developer Tools, **Snippets** are small JavaScript files that you can create, save, and run directly in the browser for testing and debugging purposes. They allow you to write and execute custom code snippets without modifying your actual source files.



### **JavaScript has 8 Datatypes**

**String**
**Number**
Bigint
**Boolean**
**Undefined**
Null
Symbol
**Object**

**Examples**:

````js
// Numbers:
let length = 16;
let weight = 7.5;

// Strings:
let color = "Yellow";
let lastName = "Johnson";

// Booleans
let x = true;
let y = false;

// Object:
const person = {firstName:"John", lastName:"Doe"};

// Array object:
const cars = ["Saab", "Volvo", "BMW"];

// Date object:
const date = new Date("2022-03-25");
````

### Number

JavaScript has only one type of number. Numbers can be written with or without decimals.

#### Syntax Rules for Numbers and Math

In JavaScript, you can write numbers and standard arithmetic operators to express mathematical operations just like normal math

JavaScript can handle integers and also handle decimal numbers



#### Order of Operations:

Order of Operations describes the order in which operations are performed in an arithmetic expression.

- (...) When using parentheses, operations inside the parentheses are computed first:
- Multiplication (`*`) and division (`/`) have higher **precedence** than addition (`+`) and subtraction (`-`).
- Operations with the same precedence (like * and /) are computed from left to right:



#### JavaScript Arithmetic Operators

![img](https://miro.medium.com/v2/resize:fit:573/1*DffsXkVfW-cTMnwTxJEZGg.png)

The **addition** operator adds two numbers together.

The **subtraction** operator subtracts two numbers.

The **multiplication** operator multiplies two numbers.

The **division** operator divide two numbers

The **exponential** operator raises the first number to the power of the second number.

The **modulus** operator returns the division remainder.

````js
let x = 11 % 5 // x would equal 1
````

###### Increment

If you want to increment a number by one, you would use the increment operator. A thing to remember is that when placing the operator after the variable will cause the increment to happen the next time the variable is called. If used before the variable, the increment will happen instantly.

````js
//++  Increment
let x = 5
//Using after the variable
x++ // x is still 5
return x // x is 6 now

let y = 7
//Using before the variable
++y // y is 8 now
return y // y is still 8
````

###### Decrement

The same rules as incrementing apply to the decrement operator.

````js
//--  Decrement
let x = 5
//Using after the variable
x-- // x is still 5
return x // x is 4 now

let y = 7
//Using before the variable
--y // y is 6 now
return y // y is still 6
````

https://www.w3schools.com/jsref/jsref_oper_increment.asp

#### Summary

we learned: 

1. Numbers and Math
2. Order of Operations, and Brackets (...)
3. Arithmetic Operators




#### Exercise

![72205522057](C:\Users\elain\AppData\Local\Temp\1722055220571.png)










### String

In JavaScript, a string represents text 

##### Syntax rules for string

A JavaScript string is zero or more **characters** written inside quotes. (characters can be letter, numbers or symbols)

You can use single or double quotes (Strings created with single or double quotes works the same. There is no difference between the two.)

##### String Length

To find the length of a string, use the built-in `length` property:

##### Escape Characters

Because strings must be written within quotes, JavaScript will misunderstand this string

````js
'I'm learning JavaScript'
````

The string will be chopped to 'I'.

To solve this problem, you can use an **backslash escape character**.

The backslash escape character (`\`) turns special characters into string characters:

see more example: https://www.w3schools.com/js/js_strings.asp



##### combine string (also called string concatenation)

````js
'Hello' + 'World'
````

##### Automatic type conversion 

````js
"Hello" + 3  // what will be the result? 
````

##### 3 ways to create a string

````js
'hello' // single quotes
"hello" // double quotes
`hello` // back ticks, we call it template strings
````

Template strings have some special features 

- **Template Strings** allow both single and double quotes inside a string

- **Template Strings** allow multiline strings

- **Interpolation**: Template String provide an easy way to interpolate **variables and expressions** into strings. ( Automatic replacing of variables or expressions with real values is called **string interpolation**.)

  ````js
  let firstName = "John";
  let lastName = "Doe";

  let text = `Welcome ${firstName}, ${lastName}!`;
  ````



##### What should we use to create a string?

1. use '...' by default
2. If we need interpolation, multi-line strings, use ``



##### Summary

1. String = text
2. Use strings and numbers together
3. Three ways to create strings
4. Escape characters   \'      \n
5. Interpolation, multi-line strings

##### Exercise

![72205407405](C:\Users\elain\AppData\Local\Temp\1722054074051.png)

![72205411312](C:\Users\elain\AppData\Local\Temp\1722054113121.png)





# 2.4 JavaScript Where To

## Write JavaScript in a HTML file

we usually put script element at the bottom of the body element because we want the webpage to be created first and then we use js to make it interactive.

for the rest of the course, we are going to run our javascript code using an HTML file

in addition to the script element, we have another way to run js code inside HTML and that's by using an attribute.

````html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <button onclick="alert('Hello there!')">Hello</button>
    <p>
      We can run JavaScript code inside script element and onclick attribute.The code in the script element runs first when the page is loaded. the code in the onclick attribute runs after when we click the button on the
      page.
    </p>
    <script>
      alert("Good job!");
    </script>
  </body>
</html>
````

This **onclick** attribute will run the js code whenever we click this button

#### Questions: 

what are the two places that we can load js code inside an HTML file? 



## External JavaScript

Although Scripts can be placed in the `<body>`, or in the `<head>` section of an HTML page, or in both, but this is not best practice.

Placing scripts in external files has some advantages:

- It separates HTML and code
- It makes HTML and JavaScript easier to read and maintain
- Cached JavaScript files can speed up page loads

Difference between link a  JavaScript file and link a css file 

```html
<link rel="stylesheet" href="styles/style.css">
```

```html
<script src="filename"></script>
```

To add several script files to one page  - use several script tags:

```html
<script src="myScript1.js"></script>
<script src="myScript2.js"></script>
```





## Project File Structure

https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files

When building a website, it's essential to organize your files in a clear and logical way. Here is a common file structure:

![A file structure in macOS finder, showing an images folder with an image in, empty scripts and styles folders, and an index.html file](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files/file-structure.png)

### Explanation

First, create a **project-folder/**: This is the main folder containing all your project files.

Inside this project folder, create an index HTML file and 3 folders to contain images, style files, and script files.

1. **index.html**: This is the main HTML file for your website. It contains the structure and content of your web pages. Think of it as the skeleton of your website.

2. **styles/**: This folder contains all your CSS files. CSS (Cascading Style Sheets) defines the style and layout of your web pages. 

3. **scripts/**: This folder contains all your JavaScript files. JavaScript adds interactivity to your web pages, like responding to user actions and updating the content dynamically.

4. **images/**: This folder contains all your image files, like logos, photos, and icons.

   ​

**Naming conventions:**  Name folders and files completely in lowercase with no spaces. It's also advisable to separate words with hyphens, rather than underscores: `my-file.html` vs. `my_file.html`.

Organizing your project files like this helps you keep everything in its place, making it easier to find and manage your code. It also helps others understand your project structure when they look at your code. 

By separating your HTML, CSS, JavaScript, and images into different folders, you can keep your project neat and organized. This approach makes it easier to maintain and update your website as it grows.





## JavaScript Comments

Comments  - pieces of code that the computer ignores.

https://www.w3schools.com/js/js_comments.asp 

JavaScript comments can be used to explain JavaScript code, and to make it more readable.

JavaScript comments can also be used to prevent execution, when testing alternative code.



Single line comments start with `//`

Multi-line comments start with `/*` and end with `*/`. 

#### Summary:

**Why we use comments?**

1. provide more information for people reading our code
2. commenting out the code
   - don't want to run some code
   - don't want to delete it 

How do we create syntax in HTML and CSS?

````html
<!-- This is a HTML comment  -->
````

````CSS
/* This is a CSS comment, it is the same as a JS multiline comment */
````



## console.log();

`console.log()` displays whatever in the brackets back to the console. 

`console.log()` works for any code we learned so far.

`console.log()` is a function in JavaScript that is used to print or display messages to the console. The console is a tool available in web browsers that helps developers see what's happening in their code.

- **Purpose:** `console.log()` is used to show information, such as the value of a variable, a result of a calculation, or a message for debugging purposes.
- **Usage:** You call `console.log()` and pass the message or value you want to display inside the parentheses.

##### Example

```javascript
let name = "John";
console.log("Hello, " + name); // This will print: Hello, John
console.log(5 + 3); // This will print: 8
console.log("This is a message."); // This will print: This is a message.
```

When the code runs, the messages inside `console.log()` will appear in the console. This helps developers understand what's happening in their code and find errors or check values during development.

#### exercise

![72205917541](C:\Users\elain\AppData\Local\Temp\1722059175413.png)

solution

````html
<!DOCTYPE html>
<html>
  <head>
    <style>
      .add-to-cart-button {
        background-color: yellow;
      }
    
      .buy-now-button {
        background-color: orange;
      }
    </style>
  </head>
  <body>
    <p>Adults Plain Cotton T-shirt</p>
    <p>Price: $7.99</p>

    <!-- I added some extra spaces to make the code easier to read. -->
    <button class="add-to-cart-button" onclick="
      alert('Added');
    ">Add to cart</button>

    <button class="buy-now-button" onclick="
      console.log('Loading...');
      alert('Purchased');
    ">Buy now</button>
  </body>
</html>
````



# 2.5 Variables

Variables are Containers for Storing Data

### Declaring a variable

Creating a variable in JavaScript is called "declaring" a variable.

good practice: declare variables before us and declare all variables at the beginning of a script.

````js
//declare a variable without assigning a value, the variable has no value, means the variable is undefined.
var firstName;
let firstName;
const color
````

In computer programs, variables are often declared without a value. The value can be something that has to be calculated, or something that will be provided later, like user input.

A variable declared without a value will have the value `undefined`.

````js
//declare a variable
let firstName;

//assign a value to the variable
firstName = 'Jack'
````

````js
//assign a value to the variable when you declare it
let carName = "Volvo";
````

### The Assignment Operator

In JavaScript, the equal sign (`=`) is an "assignment" operator, not an "equal to" operator. 

This is different from algebra. The following does not make sense in algebra:

```js
x = x + 5  //assigns the value of x + 5 to x.
```





### Declare variables

- Using `var ` we don't use var anymore in new JaveScript code after 2015
- Using `let`
- Using `const` 

````js
var price = 5; //Only use var if you MUST support old browsers.

//variable price declared with const. value cannot be changed.
const price = 5;

//variable total declared with let. The value total can be changed.
let total = price1 + price2; 


//You cannot re-declare a variable declared with let or const
````

### When to Use var, let, or const?

1. Always declare variables
2. Use const by default (Only use `let` if you can't use `const`)
3. If we have to change a variable then use let
5. Only use `var` if you MUST support old browsers.




### Exercise

![72206733529](C:\Users\elain\AppData\Local\Temp\1722067335292.png)

Solution

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Cart Quantity</title>
  </head>
  <body>
    <p>Cart quantity</p>
    <!-- Button to show the current cart quantity -->
    <button onclick="console.log(`Cart quantity: ${cartQuantity}`);">
      Show Quantity
    </button>

    <!-- Button to increment the cart quantity by 1 -->
    <button
      onclick="cartQuantity++; console.log(`Cart quantity: ${cartQuantity}`);"
    >
      Add to Cart
    </button>

    <!-- Button to increment the cart quantity by 2 -->
    <!-- using template string to insert a value inside a string -->
    <button
      onclick="cartQuantity += 2; console.log(`Cart quantity: ${cartQuantity}`);"
    >
      +2
    </button>

    <!-- Button to increment the cart quantity by 3 -->

    <button
      onclick="cartQuantity += 3; console.log(`Cart quantity: ${cartQuantity}`);"
    >
      +3
    </button>

    <!-- Button to reset the cart quantity to 0 -->
    <button
      onclick="cartQuantity = 0; console.log(`Cart was reset.\nCart quantity: ${cartQuantity}`);"
    >
      Reset Button
    </button>

    <!-- Declare the cartQuantity variable in a script tag -->
    <script>
      let cartQuantity = 0;
    </script>
  </body>
</html>

<!-- You cannot declare the variable let cartQuantity = 0; inside the onclick attribute because the scope of variables declared with let is limited to the block in which they are declared. 
If you declare it inside the onclick attribute, it will only be available within that particular onclick function, and the other onclick functions will not be able to access it.
In this setup, we correctly declare the cartQuantity variable in a <script> tag, which gives it global scope within the context of your HTML file. This allows all onclick functions to access and modify the cartQuantity variable.
-->

```



### Variable Naming Conventions

#### Rules for Naming Variables

1. start with a Letter (a-z or A-Z)
2. can start with _ or $, but not recommended
2. cannot start with a number.
3. can't use special words, such as `let`, `const`, `var`, `if`, `else`, etc.
4. case sensitive

#### Conventions for Naming Variables

1. **Camel Case:** starting with a lowercase letter and capitalizing the first letter of each subsequent word.
   ```javascript
   let firstName;
   let totalPrice;
   ```

2. **Descriptive Names:**Use meaningful and descriptive names that convey the purpose of the variable.
   ```javascript
   let count; // Good
   let c; // Not descriptive
   ```

3. **Avoid Abbreviations:**Avoid using abbreviations or single-letter names, except for common ones like `i` for loop counters.
   ```javascript
   let numberOfItems; // Good
   let numItems; // Okay
   let ni; // Not recommended
   ```

4. **Constants in Uppercase:**Use uppercase letters with underscores to separate words for constants.
   ```javascript
   const MAX_HEIGHT = 100;
   const PI = 3.14;
   ```

5. **No Leading or Trailing Underscores:**
   - Avoid using leading or trailing underscores in variable names, as they are typically used for private variables in some coding standards.
   ```javascript
   let _privateVariable; // Not recommended
   let privateVariable; // Recommended
   ```

6. **Avoid Starting with a Dollar Sign:**
   - Generally, avoid starting variable names with a dollar sign unless you're using it for a specific purpose, like jQuery objects.
   ```javascript
   let $myElement = $('#element'); // Common in jQuery
   let $price; // Not commonly used otherwise
   ```






### Shortcuts for Re-assigning variables

````js
let cartQuantity = 0
cartQuantity = cartQuantity + 2 //increase cartQuantity by 2
cartQuantity += 2 //shortcut

cartQuantity = cartQuantity + 1
cartQuantity += 1 //increase cartQuantity by 1
cartQuantity++  //shortcut
````

````js
// variable re-assignment shortcuts

+= 2    // variable = variable + 2
-= 2    // variable = variable - 2
*= 2    // variable = variable * 2
/= 2    // variable = variable / 2
++    // variable = variable + 1
--    // variable = variable - 1

````



### The typeof Operator

The **typeof** operator returns the **data type** of a JavaScript variable.

````js
const message = 'hello';
console.log(typeof message);

let cartQuantity = 2;
conslole.log(typeof cartQuantity);
````



### Summary

1. variables = a way to save values
2. re-assign a variable
3. created the cart quantity feature
4. shortcuts for re-assigning a variable
5. naming conventions and best practices
6. 3 ways to create a variable: let const var 


### Exercises

![72207045043](C:\Users\elain\AppData\Local\Temp\1722070450434.png)

![72207049056](C:\Users\elain\AppData\Local\Temp\1722070490566.png)

![72207054340](C:\Users\elain\AppData\Local\Temp\1722070543401.png)

![72207062542](C:\Users\elain\AppData\Local\Temp\1722070625428.png)



# 2.6 Booleans and If-Statements

## Booleans

What are booleans?**

Booleans are another type of value 

There are only 2 boolean values: true, false

**What's the purpose of boolean values?**

A boolean value represents whether something is ture or false

````js
console.log(3 < 5);
console.log(3 > 5);
````



**Syntax rules for booleans**

````
// use true instead of 'true'
console.log(typeof 'true') //string
````

**Comparison Operators**

````js
>   //greater than
<   //less than
>=  //greater than or equal to 
<=  //less than or equal to
=== //equal to 
!== //not equal to   
````

- **=== (strict equality), !== (strict inequality):** Check both value and type. 


- **== (loose equality), != (loose inequality):** Checks only the value. values are not equal, performing type conversion if necessary

  ​

````js
console.log(5 === '5.00')
console.log(5 == '5.00')
````

**Oder of operations**

````js
//1. (...)
//2.  * /
//3. +  -
//4. Comparison operators

console.log(3 > 5 - 5);
````



## If-Statements

if statement 

- let us writ multiple groups of code
- then decide which code to run

````js
if (true) {
    console.log('hello');
} else {
   console.log('else'); 
}
````

Practical example:

write some code to check if someone is old enough to drive

````
const age = 30;
if ( age >= 16) {
    console.log('You can drive');
} else {
    console.log('You can not drive');
}
````



## Syntax

The **if** statement specifies a block of code to be executed if a condition is true:

````js
if (condition) {
  // block of code to be executed if the condition is true
}
````

The **else** statement specifies a block of code to be executed if the condition is false:

````js
if (condition) {
  // block of code to be executed if the condition is true
} else {
  // block of code to be executed if the condition is false
}
````

The **else if** statement specifies a new condition if the first condition is false:

````js
if (condition1) {
  // block of code to be executed if condition1 is true
} else if (condition2) {
  // block of code to be executed if the condition1 is false and condition2 is true
} else {
  // block of code to be executed if the condition1 is false and condition2 is false
}

//else if optional 
````



**Exercise**

build a simple version of rock, paper, scissors game

**Strategy for JavaScript**

1. Think about what steps we need
2. Convert those steps into code

**Steps** (Algorithm: a set of steps to complete a task or to solve a problem)

when we click a button:

1. computer randomly selects a move
2. compare the moves to get the result
3. display the result in a popup



Math.random() generates a random number between 0 and 1

````html
<button onclick = "
console.log(Math.random()); ">Rock</button>
````

![72207388938](C:\Users\elain\AppData\Local\Temp\1722073889380.png)

## logical operators

Logical operators are used to determine the logic between variables or values.

Given that `x = 6` and `y = 3`, the table below explains the logical operators:

![72207416595](C:\Users\elain\AppData\Local\Temp\1722074165953.png)

````js
console.log(true && true);
console.log(true && false);
console.log(true || false);
console.log(!true);
````



**Oder of operations**

```js
//1. (...)
//2.  * /
//3. +  -
//4. Comparison operators
//5. logical operators
```



## Scope

If statements have a special feature. they create something called a scope.

**A scope limits where a variable exists.**

Any variable we create inside {...} will only exists inside the {...}, we cannot use the variable outside the {...}. This is called a scope

scopes are a feature of many programming languages and they help us avoid naming conflicts. if we didn't have scope and we have hundreds or even thousands of lines of code we would quickly start to run out of variable names.

so by creating a new scope, all variable names inside the scope only exists between the curly brackets and it won't affect anything outside. 

**So scopes help us avoid naming conflicts**

**Any variable created inside {...} will only exist inside the {...}**

So to access a variable outside the if statement, we have to create the variable outside the if statement.

var doesn't follow the rules of scope, so we don't use var anymore

## Truthy and Falsy Values

if statement don't just work with Boolean values like true or false, they actually work with any type of value including numbers and strings.

````js
if (5) {
    consol.log('truthy');
}
// true 
// we call 5 a truthy value because it behaves just like true
// try to change value to 0 (falsy value)
````

**Falsy values:**

````js
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
````



**why do we use truthy and falsy values?**

we use it as a shortcut 

````js
let cartQuantity = 5;
if (cartQuantity) {
   console.log('cart has products');;
    }
````

truthy and falsy values also work with logical operators. for example

````js
console.log(!0);  // true
````



## Ternary Operator 

Shortcuts for If-Statements

````js
true ? 'truthy' : 'falsy'

//shortcut for 
if (true) { 
    'truthy';
} else {
    'falsy';
} 
````

The advantage of Ternary operator over an if statement is that we can save a 

Ternary operator in a variable

````js
const result = 0 ? 'truthy' : 'falsy'; 
console.log(result);
//0 can be any thruthy or falsy value

//shortcut for
let result;

if (condition) { 
    result = 'truthy';
} else {
    result = 'falsy';
} 
````



## Summary

1. Boolean values  represents whether something is true or false
2. use if statements to make decisions in our code
3. comparison operators(>, <, >=, <=, ===, !==) and logical operators(&&, ||, !)
4. Algorithms, and created simple version of Rock Paper Scissors
5. Truthy and Falsy values
6. Ternary operator (shortcut for if-statement )

![72209234587](C:\Users\elain\AppData\Local\Temp\1722092345875.png)

![72209253787](C:\Users\elain\AppData\Local\Temp\1722092537870.png)

![72209270198](C:\Users\elain\AppData\Local\Temp\1722092701989.png)

![72209276692](C:\Users\elain\AppData\Local\Temp\1722092766924.png)



# 2.7 Functions

### **what is a function?** 

- a block of code designed to perform a particular task which is executed when it is called or invoked.

**why do we use functions?** 

- function lets us reuse code

### Syntax

````js
// this code creates a function named sayHello, it doesn't run the code inside
function sayHello() {
    console.log('Hello, world!');
}

function greet(name) {
    console.log(`Hello, ${name}!`);
}

//calling/running/executing the function
greet('Jack');
````



A JavaScript function is defined with the `function` keyword, followed by a **name**, followed by parentheses **()**.

Rules for function names: 

1. can't use special words
2. can't start with a number
3. can't use special characters except $ _
4. Best practice = use camelCase

The parentheses may include parameter names separated by commas:
**(parameter1, parameter2, ...)**

The code to be executed, by the function, is placed inside curly brackets: **{}**



### Use functions to improve the code of Rock, Paper, Scissors

if we move pick computer Move code into a function, computerMove variable is no longer available inside onclick attribute, why? how to solve it? 

Function creates scope

Scope Review:

- A scope limits where a variable exists. 
- Any variable we create inside {...} will only exists inside the {...}, we cannot use the variable outside the {...}. This is called a scope
- variable created outside {...} is global scope variable and can be accessed elsewhere



functions let us reuse code and they make our code a lot cleaner by removing all the duplication that we have. Another benefit is that if we want to update our code for picking a computer move, we don't need to update it in three places

**So, functions also makes our code easier to update**



### Return statement

- let us get a value out of a function

update the code the code of Rock, Paper, Scissors using return statement? 

**which solution is better?** 

Global variable vs Return statement

Return statement is preferred over using a global variable. that's because scope can help use prevent naming conflicts. so all the variables inside the function {...} will not conflict with anything outside the scope

**Best practice:**

Keep variables inside a scope (if we can)



### Parameter

Return = gets a value out of a function

Parameter = puts a value into a function

- Function **parameters** are listed inside the parentheses () in the function definition.

- Function **arguments** are the **values** received by the function when it is invoked.

- Inside the function, the arguments (the parameters) behave as local variables.
- A function can have more than one parameter

````js
function calculateTax(cost) {
    console.log(cost * 0.1)
}

//calling the function and passing a value to the function
calculateTax(200)

//function with 2 parameters
function calculateTax2(cost, taxPercent) {
    console.log(cost * taxPercent)
}

calculateTax2(200, 0.2)
calculateTax(500) // if we don't give the second parameter, it will get the value undefined

//set default value for a parameter
function calculateTax3(cost, taxPercent = 0.1) {
    console.log(cost * taxPercent)
}
````

Parameter names follow same rules as variable names

Rules for Parameter names: 

1. can't use special words
2. can't start with a number
3. can't use special characters except $ _
4. Best practice = use camelCase




### summary

1. functions = let us reuse code
2. return = get a value out of a function
3. parameters = put values into a function
4. improved the code for rock, paper, scissors






# 2.8 Objects

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
- for properties that don't work, use bracket notation 

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

**Summary**: Objects are essential for organizing and structuring data in JavaScript, allowing you to represent real-world entities and their behaviors effectively.



### Exercise

modify Rock-Paper-Scissors game to add score and reset button







## Math Object

The `Math` object in JavaScript is a built-in object that provides properties and methods for mathematical constants and functions. Unlike other objects, you do not need to create a `Math` object, as it is automatically available.

### Properties of the Math Object

The `Math` object includes several mathematical constants. such as:

- `Math.PI`: Represents the value of π (Pi), approximately 3.14159.

### Methods of the Math Object

The `Math` object includes various methods for performing mathematical operations. Here are some commonly used methods:

- **Rounding Methods:**
  - `Math.round(x)`: Rounds `x` to the nearest integer.
  - `Math.ceil(x)`: Rounds `x` up to the next largest integer.
  - `Math.floor(x)`: Rounds `x` down to the next smallest integer.
- **Arithmetic and Calculations:**
  - `Math.sqrt(x)`: Returns the square root of `x`.
  - `Math.pow(base, exponent)`: Returns `base` raised to the power of `exponent`.
  - `Math.abs(x)`: Returns the absolute value of `x`.
- **Random Number Generation:**
  - `Math.random()`: Returns a pseudo-random number between 0 (inclusive) and 1 (exclusive).



# 2.9 DOM 

## What is the DOM?

The DOM (Document Object Model) is a way to represent the structure of an HTML document in a tree-like format. It allows JavaScript to interact with and manipulate the HTML elements on a webpage.

### Interacting with the DOM using JavaScript

JavaScript can be used to interact with and change the DOM. Let's look at some simple examples.

In the DOM, all HTML elements are defined as **objects**.

The programming interface is the properties and methods of each object.

A **property** is a value that you can get or set (like changing the content of an HTML element).

A **method** is an action you can do (like add or deleting an HTML element).

````html
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
````

In the example above, `getElementById` is a **method**, while `innerHTML` is a **property**.





#### 1. Selecting Elements

You can select elements in the DOM using JavaScript. For example, to select the `<h1>` tag, you can use:

```javascript
let heading = document.querySelector('h1');
console.log(heading); // This will log the <h1> element to the console
```

#### 2. Changing Text

You can change the text inside an element. For example, to change the text of the `<h1>`:

```javascript
let heading = document.querySelector('h1');
heading.textContent = 'Hello, JavaScript!';
```

Now, the `<h1>` in the HTML will be:

```html
<h1>Hello, JavaScript!</h1>
```

#### 3. Changing Styles

You can also change the styles of an element. For example, to change the color of the `<h1>` text:

```javascript
let heading = document.querySelector('h1');
heading.style.color = 'blue';
```

Now, the text "Hello, JavaScript!" will appear in blue.

#### 4. Adding New Elements

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

### Summary

- The DOM represents the HTML of a webpage as a tree structure.
- JavaScript can be used to select, change, and add elements in the DOM.
- This allows you to dynamically change the content and appearance of a webpage.

By understanding the DOM, you can create interactive and dynamic web pages using JavaScript.



## Most commonly used DOM properties and methods

The DOM (Document Object Model) provides a wide range of properties and methods for interacting with and manipulating web documents. Here are some of the  ones:

### Common Properties of the DOM:

1. **document**
   - Represents the entire HTML or XML document.
   - Example: `document.title` gives the title of the document.

2. **element.innerHTML**
   - Gets or sets the HTML or XML markup contained within an element.
   - Example: `element.innerHTML = '<p>New content</p>'`.

3. **element.textContent**
   - Gets or sets the text content of an element and its descendants.
   - Example: `element.textContent = 'New text content'`.

4. **element.style**
   - Provides access to the inline styles of an element.
   - Example: `element.style.color = 'blue'`.

5. **element.attributes**
   - Returns a live collection of all attributes of the element.
   - Example: `element.attributes['class'].value`.

6. **element.children**
   - Returns a live HTMLCollection of the child elements of the element.
   - Example: `element.children[0]`.

### Common Methods of the DOM:

1. **document.getElementById(id)**
   - Returns the element with the specified ID.
   - Example: `document.getElementById('myElement')`.

2. **document.getElementsByClassName(className)**
   - Returns a live HTMLCollection of all elements with the specified class name.
   - Example: `document.getElementsByClassName('myClass')`.

3. **document.getElementsByTagName(tagName)**
   - Returns a live HTMLCollection of all elements with the specified tag name.
   - Example: `document.getElementsByTagName('div')`.

4. **document.querySelector(selector)**
   - Returns the first element that matches the specified CSS selector.
   - Example: `document.querySelector('.myClass')`.

5. **document.querySelectorAll(selector)**
   - Returns a static NodeList of all elements that match the specified CSS selector.
   - Example: `document.querySelectorAll('.myClass')`.

6. **element.appendChild(child)**
   - Adds a new child node to an element as the last child node.
   - Example: `parentElement.appendChild(newElement)`.

7. **element.removeChild(child)**
   - Removes a child node from the element.
   - Example: `parentElement.removeChild(childElement)`.

8. **element.replaceChild(newChild, oldChild)**
   - Replaces a child node within the element with another one.
   - Example: `parentElement.replaceChild(newElement, oldElement)`.

9. **element.setAttribute(name, value)**
   - Adds a new attribute or changes the value of an existing attribute on the element.
   - Example: `element.setAttribute('class', 'newClass')`.

10. **element.getAttribute(name)**
   - Returns the value of the specified attribute on the element.
   - Example: `element.getAttribute('class')`.

11. **element.removeAttribute(name)**
    - Removes the specified attribute from the element.
    - Example: `element.removeAttribute('class')`.

12. **element.addEventListener(type, listener)**
    - Attaches an event handler to the element.
    - Example: `element.addEventListener('click', function() { alert('Clicked!'); })`.

13. **element.removeEventListener(type, listener)**
    - Removes an event handler from the element.
    - Example: `element.removeEventListener('click', clickHandlerFunction)`.

### Summary:

These properties and methods are essential for interacting with and manipulating web documents through the DOM. They provide a way to access elements, change their content, style them, handle events, and modify their structure dynamically.



























































































for loop

while loop, break , continue

when do we need to return a value?

what is Anonymous Function?

Understanding Events in JavaScript

DOM

DOM - todo list input demo 

**DOM** - changing element style

simple event handler

canvas - module. w3s

![72199389488](C:\Users\elain\AppData\Local\Temp\1721993894887.png)



# Other Reading materials

## Math object

The `Math` object in JavaScript is a built-in object that has properties and methods for mathematical constants and functions. It’s not a function object and cannot be instantiated. Instead, it provides a variety of static methods and properties that you can use for mathematical operations.

### Commonly Used Methods

1. **Math.abs()**: Returns the absolute value of a number.
   ```javascript
   Math.abs(-5);  // 5
   ```

2. **Math.ceil()**: Rounds a number up to the next largest integer.
   ```javascript
   Math.ceil(4.2);  // 5
   ```

3. **Math.floor()**: Rounds a number down to the next smallest integer.
   ```javascript
   Math.floor(4.9);  // 4
   ```

4. **Math.round()**: Rounds a number to the nearest integer.
   ```javascript
   Math.round(4.5);  // 5
   Math.round(4.4);  // 4
   ```

5. **Math.max()**: Returns the largest of zero or more numbers.
   ```javascript
   Math.max(1, 3, 2);  // 3
   ```

6. **Math.min()**: Returns the smallest of zero or more numbers.
   ```javascript
   Math.min(1, 3, 2);  // 1
   ```

7. **Math.pow()**: Returns base raised to the power of exponent.
   ```javascript
   Math.pow(2, 3);  // 8
   ```

8. **Math.sqrt()**: Returns the positive square root of a number.
   ```javascript
   Math.sqrt(16);  // 4
   ```

9. **Math.random()**: Returns a pseudo-random number between 0 (inclusive) and 1 (exclusive).
   ```javascript
   Math.random();  // e.g., 0.123456789
   ```

10. **Math.trunc()**: Returns the integer part of a number by removing any fractional digits.
   ```javascript
   Math.trunc(4.9);  // 4
   ```

### Mathematical Constants

1. **Math.PI**: The ratio of the circumference of a circle to its diameter (approximately 3.14159).
   ```javascript
   Math.PI;  // 3.141592653589793
   ```

2. **Math.E**: Euler's number (approximately 2.718).
   ```javascript
   Math.E;  // 2.718281828459045
   ```

### Examples

1. **Calculating the area of a circle:**
   ```javascript
   let radius = 5;
   let area = Math.PI * Math.pow(radius, 2);
   console.log(area);  // 78.53981633974483
   ```

2. **Generating a random integer between two values (inclusive):**
   ```javascript
   function getRandomInt(min, max) {
       min = Math.ceil(min);
       max = Math.floor(max);
       return Math.floor(Math.random() * (max - min + 1)) + min;
   }
   console.log(getRandomInt(1, 10));  // e.g., 7
   ```

3. **Finding the maximum value in an array:**
   ```javascript
   let numbers = [1, 2, 3, 4, 5];
   let max = Math.max(...numbers);
   console.log(max);  // 5
   ```

The `Math` object is extremely useful for a wide range of mathematical operations and is a fundamental part of JavaScript programming.

##  remainder (or modulus) operator

In JavaScript, the `%` operator is known as the remainder (or modulus) operator. It returns the remainder of a division operation. Specifically, it takes two operands and divides the first operand by the second, then returns the remainder of that division.

Here is the basic syntax:

```javascript
result = dividend % divisor;
```

Where `dividend` is the number to be divided, and `divisor` is the number by which `dividend` is divided.

### Examples

1. Basic Usage:
   ```javascript
   let remainder = 10 % 3;  // remainder is 1, because 10 divided by 3 is 3 with a remainder of 1
   console.log(remainder);  // Output: 1
   ```

2. Even or Odd Check:
   The `%` operator is often used to check if a number is even or odd.
   ```javascript
   let number = 15;
   if (number % 2 === 0) {
       console.log('Even');
   } else {
       console.log('Odd');  // Output: Odd
   }
   ```

3. Looping with a Fixed Interval:
   The `%` operator can be useful in loops when you want to perform an action at fixed intervals.
   ```javascript
   for (let i = 1; i <= 10; i++) {
       if (i % 3 === 0) {
           console.log(i + ' is divisible by 3');
       }
   }
   // Output:
   // 3 is divisible by 3
   // 6 is divisible by 3
   // 9 is divisible by 3
   ```


### Important Points

- The `%` operator only works with integers. If you use floating-point numbers, the result may not be as expected.








## Why Do We Need Functions in JavaScript?

Functions in JavaScript are essential for several reasons. They help you organize your code, make it reusable, and make your programs easier to understand and maintain. Here’s a simple explanation for your students:

**1. Reusability:**

Functions allow you to write a piece of code once and reuse it as many times as needed. This helps you avoid writing the same code multiple times, which can save a lot of effort and reduce errors.

**Example:**

```javascript
function greet(name) {
    console.log("Hello, " + name + "!");
}

greet("Alice"); // Outputs: Hello, Alice!
greet("Bob");   // Outputs: Hello, Bob!
greet("Charlie"); // Outputs: Hello, Charlie!
```

In this example, the `greet` function is defined once but can be called with different names to greet different people.

**2. Organization:**

Functions help organize your code into smaller, manageable pieces. Each function can perform a specific task, making your code easier to read and understand.

**Example:**

```javascript
function calculateArea(width, height) {
    return width * height;
}

let area = calculateArea(5, 10);
console.log("The area is: " + area);
```

Here, the `calculateArea` function performs a specific task (calculating the area), making the main part of the code (the `let area` and `console.log` lines) simpler and more readable.

**3. Avoiding Repetition:**

Functions help you avoid repeating code. Instead of writing the same code in multiple places, you write a function and call it wherever needed.

**Example:**

```javascript
function showWelcomeMessage() {
    console.log("Welcome to our website!");
}

// Call the function wherever you need the welcome message
showWelcomeMessage();
showWelcomeMessage();
showWelcomeMessage();
```

By using the `showWelcomeMessage` function, you avoid repeating the same console.log statement multiple times.

**4. Abstraction:**

Functions help you hide complex details and provide a simple interface for using that functionality. This makes it easier to work with and maintain your code.

**Example:**

```javascript
function calculateDistance(speed, time) {
    return speed * time;
}

let distance = calculateDistance(60, 2); // 60 km/h for 2 hours
console.log("The distance traveled is: " + distance + " km");
```

You don’t need to worry about how the distance is calculated each time you want to find the distance; you just call the `calculateDistance` function with the appropriate values.

### Summary

- **Reusability**: Write code once and reuse it.
- **Organization**: Break your code into smaller, manageable pieces.
- **Avoiding Repetition**: Prevent writing the same code multiple times.
- **Abstraction**: Hide complex details and provide a simple interface.

By using functions, you can make your JavaScript code more efficient, organized, and easier to understand and maintain.



## What is an Anonymous Function?

An anonymous function in JavaScript is a function that does not have a name. Unlike regular functions that you define and give a specific name, anonymous functions are typically used for short-term tasks or as arguments to other functions.

**Example of a Regular Function:**

```javascript
function sayHello() {
    console.log("Hello!");
}

sayHello(); // Outputs: Hello!
```

**Example of an Anonymous Function:**

```javascript
const sayHello = function() {
    console.log("Hello!");
};

sayHello(); // Outputs: Hello!
```

In this example, the anonymous function is assigned to the variable `sayHello`, so we can call it just like a regular function.

### When to Use Anonymous Functions

Anonymous functions are often used in situations where you need to pass a function as an argument to another function, or where the function is only used once and doesn’t need a specific name. Here are some common cases:

#### 1. **Event Handlers**

When you want to run some code in response to an event, like a button click, you can use an anonymous function.

```javascript
document.getElementById("myButton").addEventListener("click", function() {
    console.log("Button was clicked!");
});
```

Here, the function inside `addEventListener` is anonymous. It runs when the button is clicked but doesn’t need a name because it’s not used anywhere else.

#### 2. **Array Methods**

Methods like `forEach`, `map`, and `filter` often use anonymous functions to perform operations on each item in an array.

```javascript
let numbers = [1, 2, 3, 4];
let doubled = numbers.map(function(number) {
    return number * 2;
});

console.log(doubled); // Outputs: [2, 4, 6, 8]
```

In this example, the anonymous function inside `map` doubles each number in the array.

#### 3. **Immediately Invoked Function Expressions (IIFE)**

Sometimes you need a function that runs immediately after it’s defined. This is useful for creating a separate scope for variables.

```javascript
(function() {
    let message = "This runs immediately!";
    console.log(message);
})();
```

The anonymous function here runs right away because of the `()` at the end.

### Summary

- **Anonymous Functions**: Functions without a name, often used for short-term tasks.
- **Common Uses**:
  - **Event Handlers**: Code that runs in response to events like clicks.
  - **Array Methods**: Operations on each item in an array (e.g., `map`, `forEach`).
  - **IIFE**: Functions that run immediately for creating a separate variable scope.

Anonymous functions are useful when you need a function for a specific task that doesn’t require naming or reuse elsewhere in your code. They help keep your code concise and focused on the task at hand.





## Understanding Events in JavaScript

**What is an Event?**

An event is something that happens on a web page. It could be something that the user does, like clicking a button, typing in a text box, or moving the mouse. It could also be something that happens automatically, like when a page finishes loading.

**Examples of Events:**

- **Click**: When a user clicks on a button or link.
- **Mouseover**: When a user moves the mouse pointer over an element.
- **Keypress**: When a user presses a key on the keyboard.
- **Load**: When the web page or an image finishes loading.

**How to Use Events in JavaScript:**

To make your web page interactive, you can write JavaScript code that responds to these events. This is called "event handling."

**Example: Changing Text on a Button Click**

Let's say you have a button on your web page, and you want to change the text inside a `div` when the button is clicked. Here's how you can do it:

1. **HTML**: Create a button and a `div`.

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Event Example</title>
       <script src="script.js" defer></script>
   </head>
   <body>
       <button id="myButton">Click Me!</button>
       <div id="myDiv">Original Text</div>
   </body>
   </html>
   ```

2. **JavaScript**: Write the code to handle the button click event.

   ```javascript
   // script.js
   document.getElementById("myButton").addEventListener("click", function() {
       document.getElementById("myDiv").innerText = "Text changed by JavaScript!";
   });
   ```

**Explanation:**

1. **HTML**: 
   - The `<button>` element has an `id` of `myButton`.
   - The `<div>` element has an `id` of `myDiv`.

2. **JavaScript**: 
   - `document.getElementById("myButton")`: Finds the button element in the HTML.
   - `.addEventListener("click", function() { ... })`: Adds an event listener to the button, listening for a "click" event. When the button is clicked, the function inside the curly braces `{ ... }` runs.
   - `document.getElementById("myDiv").innerText = "Text changed by JavaScript!"`: Changes the text inside the `div` to "Text changed by JavaScript!"

**Why Use Events?**

Events make your web pages interactive. They allow you to create a dynamic user experience where the content and behavior of the page can change in response to user actions or other occurrences.

### Summary

- An **event** is something that happens on a web page (like a click, mouse movement, or key press).
- **Event handling** is writing JavaScript code that responds to these events.
- Use **addEventListener** to set up event handlers that run specific code when an event occurs.
