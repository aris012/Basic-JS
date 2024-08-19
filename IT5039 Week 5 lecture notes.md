

# React 

StackOverflow survey: [Web frameworks and technologies](https://survey.stackoverflow.co/2023/#web-frameworks-and-technologies)

[Google trends](https://trends.google.com/trends/explore?date=all&geo=NZ&q=react,angular,vue,django&hl=en-NZ)

React is the most popular web technology





# 5.1 Introduction To React



1. **History and Evolution of Web Development**:

   - Traditional websites used SSR(server side rendering), where the server rendered the entire web page.
   - React uses CSR(client side rendering), loading a single page initially and updating sections dynamically without full page reloads.
   - This leads to better performance and a dynamic user experience.

   

2. **What is React?**:

   https://react.dev/ 

   - An open-source JavaScript library, not a framework.

   - Handles the view layer of applications, focusing on building user interfaces.

   - Enables creation of large-scale web applications that update data without reloading the page.

     

3. **Why Use React?**:

   - Developed and maintained by Facebook, ensuring long-term support and updates.

   - JSX syntax allows mixing JavaScript with HTML, simplifying the development process.

   - High demand skill for front-end developer roles, compatible with various back-end technologies.

   - Facilitates mobile app development through React Native.

     

4. **Component-Based Architecture**:

   - React apps are built using reusable components.
   - Example: An Instagram post composed of components like image, like button, share button, etc.
   - Components can be reused across different parts of an application or multiple projects.



# 5.2 Installing Required Tools for React Development

Visual Studio Code (VS Code), Node.js, Google Chrome.

**1. Installing Visual Studio Code (VS Code):**

**2. Installing Node.js:**

- **Why Node.js?**
  - Node.js is necessary for creating and running React projects.
- **Download and Install:**
  - Go to Google, search for "Node.js."
  - Click the first link, download the LTS version (e.g., 20.16.0).
  - **Mac:**
    - Open the downloaded file, run the installation wizard.
    - Enter your password if prompted, and follow the instructions to complete the installation.
  - **Windows:**
    - Open the downloaded file, run the installation wizard.
    - Follow the prompts to complete the installation.
- **Verify Installation:**
  - Open Terminal (Mac) or Command Prompt (Windows).
  - Type `node --version` and press Enter.
  - If the version number is displayed, Node.js is installed correctly.

**3. Installing Google Chrome:**

- **Why Google Chrome?**
  - Google Chrome has a robust developer console, which is very useful for inspecting and debugging React applications.
- **Download and Install:**
  - Go to Google, search for "Google Chrome."
  - Click the download link and follow the instructions to install it.





#  5.3 Create a React project using CDN

Creating a React project using a CDN is a straightforward way to get started with React without needing a build tool or package manager. 



### Step 1: Create an HTML File

1. **Create a new HTML file** (e.g., `index.html`).

2. **Add the following code** to include React and ReactDOM via CDN and set up a basic HTML structure:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>

    <!-- Include React library from CDN -->
    <script
      crossorigin
      src="https://unpkg.com/react@18/umd/react.development.js"
    ></script>

    <!-- Include ReactDOM library from CDN -->
    <script
      crossorigin
      src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
    ></script>

    <!-- Include Babel for transforming JSX into JavaScript -->
    <script
      type="text/javascript"
      src="https://unpkg.com/babel-standalone@6/babel.js"
    ></script>
  </head>
  <body>
    <!-- The root element where React will render the component -->
    <div id="root"></div>

    <!-- Your React code goes here -->
    <script type="text/babel">
      // Define a simple React component

      function MyComponent() {
        return (
          <div>
            <h1>Hello React</h1>
          </div>
        );
      }

      // Render the MyComponent to the DOM inside the element with id 'root'
      ReactDOM.render(<MyComponent />, document.getElementById("root"));
    </script>
  </body>
</html>
```



### Step 2: Explanation of Code

- **React and ReactDOM Scripts**:
  - These `<script>` tags include the React and ReactDOM libraries from a CDN. 

- **Babel Script**:
  - This `<script>` tag includes Babel, which allows you to use JSX syntax in your code. Babel will transpile JSX into standard JavaScript.

- **Root Element**:
  - The `<div id="root"></div>` element is where your React application will be rendered.

- **React Code**:
  - Inside the `<script type="text/babel">` tag, you define your React components and render them. In this example, the `App` component is a simple function component that returns an `<h1>` element. `ReactDOM.render` is used to render this component into the `root` element in the HTML.



### Step 3: Open the HTML File

1. **Save the HTML file**.

2. **Open the HTML file in a web browser**. You should see "Hello, React!" rendered on the page.

   

This method is great for quick prototyping and learning, but for larger projects or production applications, it is recommended a build tool like Create React App or Vite.







![image-20240818181147326](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240818181147326.png)





# 5.4 Creating React App Using Vite

`npm create vite@latest`  `npm create react`

### Why creating React App Using Vite

**Creating React app using a CDN** involves directly including React and ReactDOM libraries via script tags in an HTML file. This approach is straightforward and ideal for quickly getting started with React, especially for small projects, learning purposes, or simple prototypes. It allows developers to write React code directly in the HTML file without the need for complex build tools or package managers. 

**However,** this method has limitations, especially for larger or more complex applications. It lacks advanced features and optimizations necessary for production environments, such as efficient code management, performance improvements, and better development workflows.

**This is where Vite comes in.**  Vite offers a more robust solution for building React applications, providing better performance, advanced features, and a more streamlined development process.







### Create and run your first React app using Vite

Vite is a modern build tool that offers fast development and build times. It’s known for its speed and simplicity, especially for React projects. 

Follow the instructions in the activities below step by step to create and run your first React app using Vite

**1. Preparing the Environment:**

- **Creating a Folder:**
  - Optional step: Create a new folder on the desktop to contain your React project.
  - Example folder name: `my-project`.

**2. Using VS Code to Create a React App:**

- **Opening the Folder in VS Code:**
  - Open VS Code.
  - Open the newly created folder (`my-react-project`) in VS Code.
- **Opening the Terminal:**
  - In VS Code, go to the terminal bar and click on "New Terminal."
  - This opens the terminal in the project folder location.

**3. Creating a React App with Vite:**

- **Command to Create a React App:**
  - In the terminal, type `npm create vite@latest`
- **Installation Steps:**
  - After running the command, Vite will prompt you to confirm the installation.
  - Enter `Y` (Yes) to proceed.
  - Specify the project name ( you can name it **my-react-app**) and select the framework (`React`).
  - Choose JavaScript.

**4. Setting Up the Project:**

- **Changing Directory:**
  - Navigate to your project directory: `cd my-react-app` (replace `my-react-app` with your project name).  (It's important to navigate to your project directory using`cd my-react-app` )
- **Installing Dependencies:**
  - Run `npm install` to install all dependencies listed in the `package.json` file.

**5. Running the React App:**

- **Starting the Development Server:**
  - Run `npm run dev` to start the development server.
  - Vite will host the React app on a local server.
- **Accessing the App:**
  - Vite will provide a URL (e.g., `http://localhost:5173/`).
  - Open the URL in your browser to see your running React app.
  - The default page will show Vite and React logos, a heading, and a counter.

**6. Managing the Development Server:**

- **Stopping the Server:**
  - To stop the server, go to the terminal and press `Ctrl+C` (both Mac and Windows).
- **Restarting the Server:**
  - To restart, run `npm run dev` again and refresh the browser.



### Code Cleanup

1. **Delete Unnecessary Files**:

   - clean up the `main.css` file.
   - Delete the `App.css` file.
   - Delete the file under `assets` folder within the `src` folder.
   - Delete the `public` folder.

2. **Simplify `main.jsx`**:

   - Clean up the code in `main.jsx` to match the following structure:

   ````react
   import { StrictMode } from 'react'
   import { createRoot } from 'react-dom/client'
   import App from './App.jsx'
   import "./index.css";
   
   
   createRoot(document.getElementById('root')).render(
     <StrictMode>
       <App />
     </StrictMode>,
   )
   ````

3. **Simplify `App.jsx`**:

   - Clean up the code in `App.jsx` to match the following structure:

   ````react
   function App() {
     return <div>Hello World!</div>;
   }
   
   export default App;
   ````

After completing these steps, the project should be clean and ready for the next phase.





### [Choosing Between “Create React App” and “Vite” for Your React Project](https://medium.com/@oguzkaganbati/choosing-between-create-react-app-and-vite-for-your-react-project-5a06a6370a11)









# 5.5 React Components



## **What are React Components?**

React Components are the building block of React Application. They are the reusable code blocks containing logics and and UI elements. They are JavaScript functions and return JSX. Components make the task of building UI much easier. 

A UI is broken down into multiple individual pieces called components. You can work on components independently and then merge them all into a parent component which will be your final UI. 

Components promote efficiency and scalability in web development by allowing developers to compose, combine, and customize them as needed.

You can see in the below image we have broken down the UI of GeeksforGeeks’s homepage into individual components. 

![React components](https://media.geeksforgeeks.org/wp-content/uploads/20230804155419/gfgdrawio-(1).jpg)



If you think of components as **LEGO bricks**, you can take these individual bricks and combine them together to form larger structures. If you need to update a piece of the UI, you can update the specific component or brick.

![Example of a Media Component made up of 3 smaller components: image, text, and button](https://nextjs.org/_next/image?url=%2Flearn%2Flight%2Flearn-components.png&w=3840&q=75)

This modularity allows your code to be more maintainable as it grows because you can add, update, and delete components without touching the rest of our application.

Components in React return a piece of JSX code that tells what should be rendered on the screen.

**Types of Components in React**
In React, we mainly have two types of components:

- Functional Components

- Class based Components




### Creating React Components with Traditional Functions

In React, a **functional component** is simply a JavaScript function that returns JSX. Functional components are preferred for their simplicity and ease of use. You can create a React component using a traditional JavaScript function as shown below:

```jsx
export default function Greeting() {
  return <h1>Hello, world!</h1>;
}
```

In this example, the `Greeting` component is a function that returns a simple JSX element. When this component is used, it will render an `h1` tag with the text "Hello, world!".

### Creating React Components with Arrow Functions

You can also create functional components using **arrow functions**, a more modern syntax in JavaScript. Arrow functions are often shorter and can be more concise, especially when the component logic is simple:

```jsx
const Greeting = () => {
  return <h1>Hello, world!</h1>;
};
export default Greeting; //The export default should be placed after the declaration of the arrow function
```



### Which Approach Will We Use?

**Types of Components in React**
In React, we mainly have two types of components:

- Functional Components

- Class based Components

we will primarily use **traditional functions** to create components. This approach aligns well with foundational JavaScript concepts, making it easier to understand for those new to React. As you become more comfortable with React, you'll be able to explore and use arrow functions in your projects. But for now, we'll focus on traditional function syntax to ensure a solid understanding.

 Since the React community is moving towards using functional components more, we will be focusing on **Functional Components**







### JSX



- **JSX (JavaScript XML)** is a syntax extension for JavaScript that allows you to write HTML-like code directly within your JavaScript files. 
- It’s a key feature of React, making the code more intuitive and easier to understand by closely resembling the structure of the final user interface. 
- With JSX, you can seamlessly combine JavaScript logic with HTML-like elements, enabling you to create dynamic and interactive UIs. 
- Although JSX looks like HTML, it is ultimately compiled into regular JavaScript by tools like Babel, which then converts the JSX into `React.createElement()` calls. This makes it easier to build and manage complex user interfaces in a clear and structured way.

### JSX Example with Variable

````react
export default function Welcome() { // JavaScript
  const userName = 'Tracy'; // JavaScript

  return ( // JSX
    <div> // JSX
      <h1>Hello, {userName}!</h1> // JSX with JavaScript expression
      <p>Welcome to learning React with JSX.</p> // JSX
    </div> // JSX
  ); // JSX
}
````

**Explanation**:

- JSX Parts
  - `return (` - This begins the JSX code that will be returned by the component.
  - `<div>` - This is a JSX element representing a container for other elements.
  - `<h1>Hello, {userName}!</h1>` - This JSX element contains both HTML-like content and a JavaScript expression (`{userName}`) that dynamically inserts the value of `userName` into the heading.
  - `<p>Welcome to learning React with JSX.</p>` - This is a JSX element representing a paragraph of text.
  - `</div>` - This closes the JSX `<div>` element.
  - `);` - This ends the JSX code and completes the return statement.

In summary, JSX allows you to write HTML-like syntax within your JavaScript code, and the JavaScript parts handle logic, imports, and exports. The combination of both makes it easier to create dynamic and interactive user interfaces in React.



React Components: https://www.geeksforgeeks.org/reactjs-components/  

**Please watch the following videos to learn how to create React Components**

https://www.youtube.com/watch?v=d5ooYpXioqE&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=5 





# 5.6 React Props



### What is props?

In React, “**props**” (short for “properties”) are a mechanism for passing data from a parent component to a child component. Props allow you to customize and configure child components by providing them with values or functions.



1. **Passing Data**: Props are used to pass data from a parent component to a child component. They are passed as attributes to the child component when it is declared in the parent component’s JSX.

````jsx
// Parent component
function ParentComponent() {
    const message = "Hello from parent!";
    return <ChildComponent greeting={message} />;
}

// Child component
function ChildComponent(props) {
    return <p>{props.greeting}</p>;
}
````



2. **Immutable**: Props are immutable, meaning that once they are set by the parent, they cannot be changed by the child component. The child component can use props for rendering, but it should not modify them.

   

Props play a fundamental role in React’s component-based architecture, enabling the creation of flexible and reusable components that can adapt to different data and scenarios. They facilitate the flow of information between components, supporting a hierarchical and modular structure in React applications.

**Please watch the following videos to learn What are Props in React, How to destructuring Props and immutability of Props**

https://www.youtube.com/watch?v=SV0fSOIKAZQ&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=9

https://www.youtube.com/watch?v=n5WWqx8a4tg&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=10

https://www.youtube.com/watch?v=axkeWqPr9-8&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=11







# 5.7 Destructuring

**Destructuring** is a feature in JavaScript that allows you to unpack values from arrays or properties from objects into distinct variables. This syntax makes it easier to extract and work with individual elements or properties without needing to reference the array or object repeatedly.

### Destructuring Arrays:

You can extract values from an array and assign them to variables in a single line:
```javascript
const fruits = ["apple", "banana", "cherry"];
const [first, second, third] = fruits;

console.log(first); // Output: apple
console.log(second); // Output: banana
console.log(third); // Output: cherry
```

### Destructuring Objects:

You can extract properties from an object and assign them to variables with the same name as the properties:
```javascript
const person = { name: "John", age: 30, city: "New York" };
const { name, age, city } = person;

console.log(name); // Output: John
console.log(age); // Output: 30
console.log(city); // Output: New York
```

### Key Benefits:
- **Simplifies Code**: Makes your code cleaner and more concise by reducing the need for multiple lines of variable assignment.
- **Flexibility**: You can extract only the values or properties you need, ignoring the rest.



# 5.8 Styling React Using CSS



### Styling React Using CSS

Styling plays a vital role in creating visually appealing and user-friendly web applications. When it comes to React applications, there are numerous ways to style components and UI elements with CSS. In this lesson, we will have a look at three common ways:

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

If you want to handle **conditional CSS with inline styling** in React, you can use a combination of the `useState` hook and ternary operator:

````react
import { useState } from "react";

export default function ConditionalInlineStyling() {
  const [isActive, setIsActive] = useState(true);

  const buttonStyle = {
    margin: "0 auto",
    backgroundColor: isActive ? "green" : "gray",
    cursor: isActive ? "pointer" : "not-allowed",
    color: "white",
    padding: "0.6rem 1.2rem",
    border: "none",
  };

  return (
    <div style={{ textAlign: "center", marginTop: "2rem" }}>
      <button style={buttonStyle}>{isActive ? "Active" : "Inactive"}</button>
    </div>
  );
}
````

**Code explanation:** 

**Importing `useState`**: The code imports the `useState` hook from React, which is used to create and manage a piece of state within the component.

**State Initialization**: The component has a state variable called `isActive`, initialized to `true`. This state controls whether the button appears "Active" or "Inactive." The `setIsActive` function is available to change this state, but it’s not used directly in the given code.

**Styling the Button**: A `buttonStyle` object defines the CSS styles for the button. The styles change depending on the `isActive` state:

- If `isActive` is `true`, the button has a green background, a "pointer" cursor, and is labeled "Active."
- If `isActive` is `false`, the button has a gray background, a "not-allowed" cursor, and is labeled "Inactive."

**Rendering the Button**: The component returns a `div` that centers the button on the page. The button is styled with the `buttonStyle` object, and its text changes based on the `isActive` state.

If you change the `true` value to `false` , the button will appear in the "Inactive" state:



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



The advantage of using traditional stylesheets to style React components is that it's easy to start with, and the only learning curve is how you import it into a component.

### How to Use CSS Modules for Component-Specific Styling

CSS Modules offer a powerful solution for writing component-specific styles in React. They let you scope styles to individual components, thereby letting you **avoid naming conflicts** and simplifying style maintenance.

To use CSS modules in React, create a file with the `.module.css` extension. For example, `styles.module.css`. You then need to import the file into your component with the `import` keyword and a name you want, for example, `styles` or `classes`, followed by the relative path of the CSS modules file:

````react
import styles from 'relative-path-to-css-modules-file.module.css';
````

The name you choose is now an object, the keys are the classes in the CSS modules file and the values are the respective properties in the class.

To use a class from the CSS modules file, you scope the choice import name (`styles` or `classes`) to a class name. For example `<div className={styles.container}>`.

Let modify the example code we used above 

Create a new file called "Home.module.css" and insert CSS code in it:

````css
.header {
  text-align: center;
  margin-top: 2rem;
  color: #f43596;
  background-color: lightblue;
}
````

Import the stylesheet in your Home component: 

````react
import styles from "./Home.module.css";

export default function Home() {
  return (
    <main>
      <h1 className={styles.header}>Hello</h1>
    </main>
  );
}
````

In this example, we import an external CSS module file called `Home.module.css` and assign it to the `styles` object. The `styles` object contains mappings of CSS class names to unique generated class names specific to the component.

CSS Modules aim to solve the global scope and reusability issues of pure CSS. They allow you to write modular stylesheets, where class names are scoped to specific components.



Reference:

https://www.w3schools.com/react/react_css.asp

https://www.freecodecamp.org/news/how-to-style-react-components/

https://www.freecodecamp.org/news/how-to-style-a-react-app/ 

**Please watch the following videos to help you better understand different ways to style React Components**

https://www.youtube.com/watch?v=tZHPk4DWsxY&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=33

https://www.youtube.com/watch?v=tZry5Rlne3I&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=34

https://www.youtube.com/watch?v=avrYe4CkOB4&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=35







# 5.9 Rendering Lists

- How to render components from an array using JavaScript’s `map()`
- How to render only specific components using JavaScript’s `filter()`
- When and why to use React keys

We will often want to display multiple similar components from a collection of data. You can use the [JavaScript array methods](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array#) to manipulate an array of data. On this page, you’ll use [`filter()`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) and [`map()`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map) with React to filter and transform your array of data into an array of components.



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



reference: https://nextjs.org/learn/react-foundations/displaying-data-with-props 

**Please read React document below to learn more about Rendering data from array and filtering arrays of items** 

https://react.dev/learn/rendering-lists#rendering-data-from-arrays 

https://blog.stackademic.com/efficient-data-rendering-with-the-map-function-in-react-7da9078aa32



**Please watch the following videos to help you understand better**

https://www.youtube.com/watch?v=KU-I2M9Jm68&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=12

https://www.youtube.com/watch?v=bq56o84gZyQ&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=13

https://www.youtube.com/watch?v=KBGUaQAg2Fc&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=14

https://www.youtube.com/watch?v=8AY4siDB3ow&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=15
