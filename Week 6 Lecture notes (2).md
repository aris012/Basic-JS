# 6.1 Review: JSX

## What is JSX?

JSX stands for JavaScript XML.

JSX allows us to write HTML in React.

With JSX you can write expressions inside curly braces `{ }`.

The expression can be a React variable, or property, or any other valid JavaScript expression

````react
export default function Hello() {
  const name = "John";
  return <h1>Hello, {name}!</h1>;
}
````







## One Top Level Element

The HTML code must be wrapped in *ONE* top level element.

So if you like to write *two* paragraphs, you must put them inside a parent element, like a `div` element.

````REACT
//Wrap two paragraphs inside one DIV element
export default function Hello() {
  return (
    <div>
      <p>Hello there!</p>
      <p>Greeting from Hello component!</p>
    </div>
  );
}
````

Alternatively, you can use a "fragment" to wrap multiple lines. This will prevent unnecessarily adding extra nodes to the DOM.

A fragment looks like an empty HTML tag: `<></>`.

````REACT
//Wrap two paragraphs inside a fragment
export default function Hello() {
  return (
    <>
      <p>Hello there!</p>
      <p>Greeting from Hello component!</p>
    </>
  );
}

````



## Elements Must be Closed

````REACT
//Close empty elements with />
//JSX will throw an error if the HTML is not properly closed.
const myElement = <input type="text" />;
````







# 6.2 Review: React Router

## **Navigate through different pages** 



Routing allows the user to **navigate through different pages of your app without refreshing the whole page.**

With the help of routing, you can create a single-page application (SPA) that allows users to navigate through different pages of your web app without refreshing the whole page and improve the overall user experience by making your application faster, more responsive, and more dynamic.



### **1: Installing React Router**

````react
npm install react-router-dom
````



### **2: Adding React Router**

To make React Router available anywhere in your app. we need to import `BrowserRouter` from `react-router-dom`.

 wrap the root component with `BrowserRouter`.



### 3. **Creating Multiple Components** for your pages

Create four separate components for your pages under **pages** directory.



#### 4. **Define routes**

Create all our routes in App.jsx. 

To define the routes, we need **Routes** and **Route**. Import both components from react-router-dom and use them to route the components. The syntax for defining the routes is as follows:

```
<Routes>
   <Route path="/" element={<Home />} />
   <Route path="/course" element={<Courses />} />
   <Route path="/live" element={<Live />} />
   <Route path="/contact" element={<Contact />} />
</Routes>
```

**<Routes>-** The <Routes> component is used to define the different routes that are available in your application. Each individual route is defined using a <Route> component.

**<Route>-** The <Route> component takes in a path prop, which is a string that defines the URL path that the route should match.

- **path-** The path prop defines the route path. 

- **element-** The component prop defines the React component to render when the route path matches the current URL.



#### 5. **Link to Navigate to Components**

Use the **<Link>** component of react-router-dom to create clickable links that change the URL of the browser and render a different component based on the new URL.

This component takes in a **to** prop, which is a string that defines the URL path that the link should navigate to, and when the user clicks on a <Link> component, the URL of the browser will change to the path specified in the to prop. The appropriate component associated with that route will be rendered. 

In our example, we have defined a route with a path prop of ‘/contact’, therefore we can create a <Link> component with a **to** prop of ‘/contact’ to allow the user to navigate to the contact page. The same procedure goes for all of the components to navigate through the different pages. 

We will now use <Link> to navigate to different pages based on the routes and pathnames we have defined in the App component

Reference : https://www.guvi.in/blog/how-to-setup-react-router-v6-tutorial/







# 6.3 Styling React Using CSS

Three common ways to style components and UI elements with CSS:

- Inline styling
- CSS stylesheets
- CSS Modules

### How to Style React Components with Inline Styling

Every JSX element has a `style` property you can add to its opening tag. This means you can add inline styling to JSX in a React component like in traditional HTML.

The primary difference is that you must specify inline styles as objects. In this object, the keys are the CSS properties written in ***camelCase*,** and the values are **strings** corresponding to valid CSS values.

And because the stylings have to be an object, you have to add them inside **two curly braces** if you're passing them directly to the element:

````react
<h1 style={{ textAlign: 'center', marginTop: '2rem', color: '#F43596' }}>
  Hello
</h1>
````

The **first set of curly braces `{}`** tells JSX to treat the content inside as a JavaScript expression.

The **second set of curly braces `{}`** is used to create the JavaScript object that represents the styles.



You can define the same styles as a separate object and pass it into the `style` property:

```jsx
export default function Home() {
  const myStyles = {
    textAlign: "center",
    marginTop: "2rem",
    color: "#F43596",
    backgroundColor: "lightblue",
  };

  return (
    <main>
      <h1 style={myStyles}>Hello</h1>
    </main>
  );
}

```



### How to Use CSS Stylesheets in React

Using external stylesheets is a common styling approach in React because it's straightforward.

All you need to do is create a CSS file, define your styles in it, and then import the stylesheet into your React component.

But you import the stylesheet using the `import` keyword and then specify the relative path of the stylesheet, not with the `link` tag as you do in HTML.

````react
import 'relative-path-to-css-file.css'
````



Create a new file called "Home.css" and insert some CSS code in it as below:

````css
h1 {
  text-align: center;
  margin-top: 2rem;
  color: #f43596;
  background-color: lightblue;
}
/*
In internal CSS, property names are written in kebab-case (e.g., text-align, margin-top, background-color), words are separated by hyphens; 
Values are provided directly without quotation marks.
Each property-value pair is separated by a semicolon ;, not commas.
*/
````

Import the stylesheet in your Home component:

````react
import "./Home.css";

export default function Home() {
  return (
    <main>
      <h1>Hello</h1>
    </main>
  );
}
````

 Import the Header component in `src/App.jsx` and render the component to see the result.



#### **Advantages**

- **Familiarity**: If you’re accustomed to traditional CSS, this method is straightforward and easy to start with.
- **Separation of Concerns**: Keeping styles in separate files helps maintain a clear separation between component logic and styling.
- **Maintainability**: External stylesheets can be easier to manage and update, especially in larger projects.



#### **Disadvantages**

**Global Scope and Conflicts**

- **Issue**: Styles defined in external CSS files are global by default, which means they apply to the entire application. This can lead to unintended style conflicts and overrides if different components or pages use the same class names.
- **Solution**: To mitigate this, use unique class names or consider CSS Modules to scope styles to individual components.

**Limited Component Encapsulation**

- **Issue**: External CSS does not naturally encapsulate styles within components. As a result, styles are not tied to specific components, which can make it harder to track where styles are coming from or to refactor components.
- **Solution**: CSS-in-JS libraries or CSS Modules provide better encapsulation by associating styles directly with components.







## **Use `NavLink` in Your Component**

 `NavLink` automatically applies the `active` class to the currently active link:

````css
.active {
  background-color: aquamarine;
}
````

````react
import { NavLink } from "react-router-dom";
import "./Navbar.css";

export default function Navbar() {
  return (
    <nav>
      <ul>
        <li>
          <NavLink to="/">Home</NavLink>
        </li>
        <li>
          <NavLink to="/products">Products</NavLink>
        </li>
        <li>
          <NavLink to="/about">About</NavLink>
        </li>
        <li>
          <NavLink to="/contact">Contact</NavLink>
        </li>
      </ul>
    </nav>
  );
}
````

**CSS**: The `.active` class is automatically applied to the `NavLink` that matches the current route. This class is used in your CSS to style the active link.









# 6.4 Destructuring

Destructuring is one of the features in JavaScript, that gives the ability to write clean and readable code.

## What is Object Destructuring?

Object destructuring is a syntax of JavaScript that helps in the extraction of properties from an object and assigns it to variables in a single, concise statement. This reduces code to a great extent and makes it easier for your code to be understood and maintained.

Instead of writing multiple lines to extract values from an object, you can do it on one line with destructuring:



````react
// Without destructuring
const user = { name: 'John Doe', age: 30, occupation: 'Web Developer' };
const name = user.name;
const age = user.age;
const occupation = user.occupation;

// With destructuring
const { name, age, occupation } = user;

````

It’s not only shorter, but it also conveys the clear intention that you’re extracting specific properties from an object.









# 6.5 Rendering Lists

## JavaScript Array map()

`map()` creates a new array from calling a function for every array element.

`map()` does not execute the function for empty elements.

`map()` does not change the original array.

````js
const numbers = [65, 44, 12, 4];
const newArr = numbers.map(myFunction) //Multiply all the values in an array with 10:

function myFunction(num) {
  return num * 10;
}
````

#### Syntax

*array*.map(*function(currentValue, index, arr), thisValue*)

#### Parameters

|                |                                                        |
| -------------- | ------------------------------------------------------ |
| Parameter      | Description                                            |
| *function()*   | Required. A function to be run for each array element. |
| *currentValue* | Required. The value of the current element.            |
| *index*        | Optional. The index of the current element.            |
| *arr*          | Optional. The array of the current element.            |

#### Return Value

|          |                                                   |
| -------- | ------------------------------------------------- |
| Type     | Description                                       |
| An array | The results of a function for each array element. |





## Rendering Lists in React

You will often want to display multiple similar components from a collection of data. You can use the [JavaScript array methods](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array#) to manipulate an array of data. On this page, you’ll use [`filter()`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) and [`map()`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map) with React to filter and transform your array of data into an array of components.





### Render components from an array using JavaScript’s `map()`

Add the following array of names to your `HomePage` component:

````jsx
import Header from "./Header";

export default function HomePage() {
  const names = ["Ada Lovelace", "Grace Hopper", "Margaret Hamilton"];

  return (
    <div>
      <Header title="Hello React" />
    </div>
  );
}
````

You can then use the `array.map()` method to iterate over the array and use an **arrow function** to map a name to a list item:

````jsx
import Header from "./Header";

export default function HomePage() {
  const names = ["Ada Lovelace", "Grace Hopper", "Margaret Hamilton"];

  return (
    <div>
      <Header title="Hello React" />
      <ul>
        {names.map((name) => (
          <li>{name}</li>
        ))}
      </ul>
    </div>
  );
}
````

Notice how you've used curly braces to weave in and out of "JavaScript" and "JSX" land.

If you run this code, React will give us a warning about a missing `key` prop. This is because React needs something to uniquely identify items in an array so it knows which elements to update in the DOM.

You can use the names for now since they are currently unique, but it's recommended to use something guaranteed to be unique, like an item ID.

````jsx
import Header from "./Header";

export default function HomePage() {
  const names = ["Ada Lovelace", "Grace Hopper", "Margaret Hamilton"];

  return (
    <div>
      <Header title="Hello React" />
      <ul>
        {names.map((name) => (
          <li key={name}>{name}</li>
        ))}
      </ul>
    </div>
  );
}
````

In this code above, we are creating an array `names` with three values. We then use the `map()` function to iterate over each item in the array and return a new array of `<li>` elements with the item's value as its content.

We also provide a `key` prop to the `<li>` elements to help React keep track of each item's identity in the array.

Finally, we render the resulting array of`<li>` elements inside a `<ul>` element to display the items on the page.





### Render only specific components using JavaScript’s `filter()`

 Let's modify the example to include an `age` property for each person in the array and then filter the list based on age.



Here's how you can update your `HomePage` component to filter and display only those who are 30 years old or older:

````REACT
Header from "./Header";

export default function HomePage() {
  const people = [
    { name: "Ada Lovelace", age: 36 },
    { name: "Grace Hopper", age: 85 },
    { name: "Margaret Hamilton", age: 34 },
    { name: "Alan Turing", age: 41 }
  ];

  // Filter the people to include only those who are 30 years old or older
  const filteredPeople = people.filter((person) => person.age >= 40);

  return (
    <div>
      <Header title="Hello React" />
      <ul>
        {filteredPeople.map((person) => (
          <li key={person.name}>
            {person.name} - {person.age} years old
          </li>
        ))}
      </ul>
    </div>
  );
}
````

**Explanation**:

1. **Array of Objects**:
   - The `people` array now contains objects where each object has a `name` and `age` property.
2. **Filtering by Age**:
   - We use the `filter()` method to create a new array, `filteredPeople`, that includes only the people who are 30 years old or older (`age >= 30`).
3. **Rendering the Filtered List**:
   - The `filteredPeople` array is then passed to the `map()` function, which generates the list items `<li>`, displaying each person's name and age.
4. **Using the `key` Prop**:
   - As before, the `name` is used as the `key` prop to uniquely identify each list item.



This code will render a list that only displays people who are 30 years old or older:

By incorporating an age filter, you can further customize the data being displayed in your React components based on specific criteria.







# 6.6 Conditional Rendering

Your components will often need to display different things depending on different conditions. In React, you can conditionally render JSX using JavaScript syntax like `if` statements, `&&`, and `? :` operators.

### What is Conditional Rendering?

React's concept of conditional rendering enables you to display or hide items depending on specific circumstances. It is frequently employed to manage user interactions, such as presenting a popup when a button is pressed or displaying various content depending on the user's authentication state. You may dynamically adjust the user interface and offer a more individualized experience by using conditional rendering.

### Implementing Conditional Rendering

There are numerous ways to achieve conditional rendering in React. Each technique has its own syntax and usage cases. Let's study the most popular techniques:

- **The if/else Statement:** React's if/else statement functions similarly to JavaScript's treatment of circumstances. React will alter the user interface in accordance with elements created using JavaScript operators like if and else.

example:

````react
 export default function ExampleComponent ({ isLoggedIn }) {
  if (isLoggedIn) {
   return <h1>Welcome, User!</h1>;
  } else {
   return <h1>Please log in to continue.</h1>;
  }
 };
````

The isLoggedIn prop is sent to the ExampleComponent component so it may determine whether the user is logged in. According to the isLoggedIn value, it employs an if/else statement to render the headings "Welcome, User!" if true and "Please log in to continue" if false. In React, conditional rendering is a standard technique.



- **The Ternary Operator:** Another often used technique for conditional rendering in React is the ternary operator. It enables simpler conditionally rendering of items.

````react
export default function ExampleComponent({ isLoggedIn }) {
  return isLoggedIn ? (
    <h1>Welcome, User!</h1>
  ) : (
    <h1>Please log in to continue.</h1>
  );
}
````

**Explanation**:

- **Component Declaration**: The `ExampleComponent` is a functional component that receives `isLoggedIn` as a prop.
- **Conditional Rendering**: The ternary operator `isLoggedIn ? ... : ...` is used to render different `<h1>` elements based on whether `isLoggedIn` is true or false.
- **Export**: The component is exported as the default export, which allows it to be imported and used in other files.

This is a concise and effective way to handle conditional rendering in React.





















# 6.7 React naming conventions 

**Component Name**

Component name should be in `PascalCase`.

**For example,** `MyComponent`, `MyChildComponent` etc.

------

**Attributes**

Attribute name's should be `camelCase`.

**For example,** `className`, `onClick` etc.

------

**Inline styles**

Inline styles should be `camelCase`.

**For example,** `<div style={{color: 'blue', backgroundColor: 'black', border: '1px solid', borderRadius:'4px'}}>My Text</div>` etc.

------

**Variable Names**

Variable names can be `camelCase` (Good practice), `PascalCase` (Avoidable), `lowercase`, can also contain `number` and `special characters`.

**For example,** `state = {variable:true, Variable:true, variableName:true}` etc.

------

**Class Name**

Class names can be anything `camelCase`, `PascalCase`, `lowercase`, can also contain `number` and `special characters`, because after all it is a **string**.

**For example,** `className="myClass MyClass My_Class my-class"` etc.
