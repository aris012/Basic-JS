# Week 5 Lab session exercises



# Task 1 Install Node.js  

### Install Node.js (Windows & Mac)

Before creating and running your first React app using Vite, you need to install Node.js on your computer. Node.js provides the runtime environment necessary to run JavaScript outside of a browser and comes with NPM (Node Package Manager), which you'll use to manage your project dependencies.

#### For Windows Users:

1. **Download Node.js:**
   - Go to the official Node.js website: [https://nodejs.org](https://nodejs.org).
   - You'll see two versions available:
     - **LTS (Long Term Support):** Recommended for most users.
     - **Current:** Latest features but may be less stable.
   - Click on the **LTS** version to download the Windows installer (`.msi` file).

2. **Install Node.js:**
   - Open the downloaded `.msi` installer file.
   - Follow the installation wizard:
     - Accept the terms and conditions.
     - Choose the installation path (default is recommended).
     - Ensure the option to install NPM is checked.
   - Click "Next" and then "Install."
   - Wait for the installation to complete.

3. **Verify Installation:**
   - Open Command Prompt:
     - Press `Win + R`, type `cmd`, and press `Enter`.
   - In the terminal, type `node -v` and press `Enter` to check the Node.js version.
   - Type `npm -v` and press `Enter` to check the NPM version.
   - If both commands return a version number, Node.js and NPM are successfully installed.

#### For Mac Users:

1. **Download Node.js:**
   - Visit the official Node.js website: [https://nodejs.org](https://nodejs.org).
   - You'll see two versions:
     - **LTS (Long Term Support):** Recommended for most users.
     - **Current:** Latest features but may be less stable.
   - Click on the **LTS** version to download the macOS installer (`.pkg` file).

2. **Install Node.js:**
   - Open the downloaded `.pkg` installer file.
   - Follow the prompts in the installer:
     - Agree to the license agreement.
     - Choose the installation location (default is recommended).
   - Click "Continue" and then "Install."
   - The installation process may take a few minutes.

3. **Verify Installation:**
   - Open Terminal:
     - Press `Cmd + Space`, type `Terminal`, and press `Enter`.
   - In the terminal, type `node -v` and press `Enter` to check the Node.js version.
   - Type `npm -v` and press `Enter` to check the NPM version.
   - If both commands return a version number, Node.js and NPM are successfully installed.

With Node.js and NPM installed, you're ready to create and run your first React app using Vite!





# Task 2 Create React app using Vite

## Create and run your first React app using Vite

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





# Task 3: Code Cleanup

1. **Delete Unnecessary Files**:

   - Delete the `main.css` file.
   - Delete the `App.css` file.
   - Delete the `public` folder.

2. **Simplify `main.jsx`**:

   - Clean up the code in `main.jsx` to match the following structure:

   ````react
   import { StrictMode } from 'react'
   import { createRoot } from 'react-dom/client'
   import App from './App.jsx'
   
   
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

After completing these steps, your project should be clean and ready for the next phase.









# React Components

In the previous lesson page, you learned about creating a React app using Vite and how react app works.

In this lesson page, you will explore Components from the React Library. 

**What are React Components?**
React Components are the building block of React Application. They are the reusable code blocks containing logics and and UI elements. They have the same purpose as JavaScript functions and return JSX. Components make the task of building UI much easier. 

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

In our lessons, we will primarily use **traditional functions** to create components. This approach aligns well with foundational JavaScript concepts, making it easier to understand for those new to React. As you become more comfortable with React, you'll be able to explore and use arrow functions in your projects. But for now, we'll focus on traditional function syntax to ensure a solid understanding.

As we discussed above, functional components are just JavaScript functions that returns JSX, making our code easier to read and write. With Hooks, these components can also handle state and side effects, just like class-based components but with less complexity. This means our apps will run faster and be easier to test and debug. Since the React community is moving towards using functional components more, focusing on them will keep our code modern and up-to-date.

### JSX

We introduced JSX in a previous lesson; let’s refresh our memory before jumping into writing components.

**JSX (JavaScript XML)** is a syntax extension for JavaScript that allows you to write HTML-like code directly within your JavaScript files. It’s a key feature of React, making the code more intuitive and easier to understand by closely resembling the structure of the final user interface. With JSX, you can seamlessly combine JavaScript logic with HTML-like elements, enabling you to create dynamic and interactive UIs. Although JSX looks like HTML, it is ultimately compiled into regular JavaScript by tools like Babel, which then converts the JSX into `React.createElement()` calls. This makes it easier to build and manage complex user interfaces in a clear and structured way.

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



# Task 4  Create component 

## Create your first React component and nested component.

In our previous lesson, you have setup Your React Environment Using Vite. Now follow the instructions below to create your first React component and nested component.

#### **Create a Header Component**

1. **Open Your Project in a Code Editor**
   - Open **`my-react-app`** in your preferred code editor.
2. **Create a Header Component**:

- In the `src` directory, create a new folder `components` .

- In the new folder `components` , create a new file named `Header.jsx`.

- Add the following code to `Header.jsx`: 

  ```jsx
  function Header() {
    return <h1>Header from React Header Component.</h1>;
  }
  export default Header;
  ```

  In the code above, you defined the component as a function and exported the component.

3. **Render the Header Component**:

- Open `src/App.jsx` and import the Header component:

  ```jsx
  import Header from "./components/Header";
  ```

- Replace the existing JSX inside the `App` component with the `Header` component:

  ```jsx
  function App() {
    return (
      <div>
        <Header />
      </div>
    );
  }
  
  export default App;
  ```

4. **Run and Check Your App**:

- Save all files and check your browser. You should see "Header from React Header Component." displayed on the screen.

  

#### Nesting Components

5. **Create a HomePage Component**:

- In the `components` directory, create a new file named `HomePage.jsx`.

- Add the following code to `HomePage.jsx`:

  ```jsx
  import Header from './Header';
  
  function HomePage() {
    return (
      <div>
        <Header />
      </div>
    );
  }
  export default HomePage;
  ```

6. **Render the HomePage Component**:

- Open `src/App.jsx` and import the `HomePage` component:

  ```jsx
  import HomePage from "./components/HomePage";
  ```

- Replace the existing JSX inside the `App` component with the `HomePage` component:

  ```jsx
  function App() {
    return (
      <div>
        <HomePage />
      </div>
    );
  }
  
  export default App;
  ```

7. **Check the Nested Components**:

- Save all files and check your browser. The `Header` component should still be visible as it is now nested inside the `HomePage` component.

  

#### Expand the Component Tree

8. **Create Additional Components**:

- Create `Footer.jsx` with the following content:

  ```jsx
  function Footer() {
    return <footer>Footer Content</footer>;
  }
  export default Footer;
  ```

- Update `HomePage.jsx` to include the `Footer`:

  ```jsx
  import Header from './Header';
  import Footer from './Footer';
  
  function HomePage() {
    return (
      <div>
        <Header />
        <Footer />
      </div>
    );
  }
  export default HomePage;
  ```

9. **Final Check**:

- Save all files and verify the changes in your browser. You should see both the `Header` and `Footer` components displayed.

Now you have learnt how to create, nest, and render components using the React framework with a Vite setup.



# React Router

 

## React Router

React Router is a crucial tool for building dynamic, single-page applications in React. It provides a seamless way to manage navigation, routing, and user interactions within your web application. In this lesson, we will explore the fundamentals of React Router, its core features, and how to implement routing in your React applications.

### What is React Router?

React Router is a popular library for managing client-side routing in React applications. It allows you to create complex, multi-page web applications that feel like traditional websites while still being single-page applications (SPAs) under the hood. With React Router, you can define and manage routes, enabling users to navigate through different views of your application without having to request a new HTML page from the server.

### Key Concepts

Before diving into the implementation, let’s understand some essential concepts:

1. Route: A route is a mapping between a URL and a component. When a user visits a specific URL, React Router renders the corresponding component.
2. Router: The router is the top-level component that provides the routing infrastructure. In React Router, we typically use `BrowserRouter` for web applications 
3. Nested Routes: React Router allows you to nest routes, creating a hierarchy of components. This is especially useful for layout structures.
4. Link: The `Link` component enables navigation by creating anchor-like elements that maintain the application's state.





## `BrowserRouter`, `Routes`, `Route`, and `Link` 

In React, `BrowserRouter`, `Routes`, `Route`, and `Link` are all components provided by the `react-router-dom` library. Together, they enable client-side routing, allowing your React application to handle navigation between different views or pages without reloading the entire page. 

**BrowserRouter**:

- Think of `BrowserRouter` as the manager of your app's navigation. It keeps track of the current URL and decides what to show on the screen based on that URL.

**Routes**:

- `Routes` is like a map that tells your app which page or view to display for each specific URL. It looks at the current URL and matches it with one of the possible pages you've set up.

**Route**:

- Each `Route` is a specific rule in that map. It says, "When the URL is this, show that page." So, if your URL is `/about`, the `Route` will know to display the "About" page.

**Link**:

- `Link` is like a button or link you click to go to a different page in your app. Unlike regular links on websites, clicking a `Link` doesn't reload the entire page. Instead, it just changes what the app shows based on the new URL.

  

### Implementation

To use React Router in your project, you need to follow these steps:

1. Installation: Begin by installing React Router using npm:

   ````react
   npm install react-router-dom
   ````

**2.  Set-Up**: Open main.jsx and wrap the App component with it:

````react
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import App from "./App.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </StrictMode>
);
````

3. **Creating the Navbar**: create a Navbar.jsx file in your src/components folder and add the following code:

````react
import { Link } from "react-router-dom";

export default function Navbar() {
  return (
    <nav>
      <ul>
        <li>
          <Link to="/">Home</Link>
        </li>
        <li>
          <Link to="/about">About</Link>
        </li>
        <li>
          <Link to="/contact">Contact</Link>
        </li>
      </ul>
    </nav>
  );
}
````

In the above code, we’ve imported `Link` from `react-router-dom`, to enable navigation to different sections of the web app.

When you click on a `Link`, it triggers a navigation event.

The `to` prop specifies the path you want to navigate to. For example, `to="/"` navigates to the home page, `to="/about"` navigates to the about page, and `to="/contact"` navigates to the contact page.

4. **Create the Pages**: 
   - **Navigate to the `src` Folder:**
     Under the `src` folder, create a new folder called `pages`.
   - **Create Page Files:**
     Inside the `pages` folder, create three files: `Home.jsx`, `About.jsx`, and `Contact.jsx`.
   - **Create React Components:**
     Within each of these files (`Home.jsx`, `About.jsx`, and `Contact.jsx`), create the corresponding React components.
   - **Import Navbar:**
     Import the `Navbar` component into each of these newly created page components.

````react
 //Home.jsx
import Navbar from "../components/Navbar";

export default function Home() {
  return (
    <div>
      <Navbar />
      <h1>Home</h1>
    </div>
  );
}
````

````react
 //About.jsx
import Navbar from "../components/Navbar";

export default function About() {
  return (
    <div>
      <Navbar />
      <h1>About</h1>
    </div>
  );
}
````

````react
 //Contact.jsx
import Navbar from "../components/Navbar";

export default function Contact() {
  return (
    <div>
      <Navbar />
      <h1>Contact</h1>
    </div>
  );
}
````

5. **Create the routes in App.js**: Open `App.js` and import `Routes`, `Route`, from react-router-dom.
   Import `Home`, `About`, and `Contact` components as well.

````react
 //App.jsx
 import { Route, Routes } from 'react-router-dom';
 import Home from './pages/Home';
 import About from './pages/About';
 import Contact from './pages/Contact';

 function App() {
   return (
     <div>

     </div>
   );
 }

 export default App;
````

Inside the div element, add the following:

````react
<Routes>
   <Route path='/' element={<Home/>} />
   <Route path='/about' element={<About/>} />
   <Route path='/contact' element={<Contact/>} />
</Routes>
````

- The `Route` elements are wrapped inside `Routes`.
- `path` represents the URL path to the component it represents.
- `element` describes the component that the path points to.

7. **Run the Application**: When the app runs, the navbar links will dynamically navigate you to its corresponding page.

### Conclusion

React Router is a powerful tool for managing client-side routing in your React applications. It allows you to create seamless, dynamic user experiences by handling navigation, route parameters, nested routes, and more. By following the steps outlined in this article, you can get started with React Router and build highly interactive and user-friendly single-page applications.

Reference:  https://luqmanshaban.medium.com/react-router-a-step-by-step-guide-4c5ec964d2e9 



# Task 5

In this task, you'll create a simple React website with navigation through four different pages using React Router. Follow the instructions below and ensure attention to the key points for a smooth implementation.

#### Steps & Key Points

1. **Project Setup:**

   - Start by opening your existing React project that you set up with Vite.

   - Install React Router DOM using `npm install react-router-dom`.

     - **Open Terminal:**

       - Launch your terminal or command prompt.

       **Navigate to Project Directory:**

       - Use `cd path/to/your/project ` to go to your project folder. 

       **Install React Router DOM:**

       - Run this command to add React Router DOM to your project:

         ```
         npm install react-router-dom
         ```

       - This installs the package and updates your `package.json` with `react-router-dom` as a dependency.

2. **Routing Configuration:**

   - In `main.jsx`, wrap your `<App />` component with `BrowserRouter` to enable routing across your application. This step is crucial to activate React Router.

3. **Create Navbar Component:**

   - Build a `Navbar.jsx` component under a `components` folder.
   - Use the `Link` component from `react-router-dom` instead of `<a>` tags to create navigation links for seamless page transitions without refreshing.

4. **Create Page Components:**

   - create a new folder called `pages` if you haven't already
   - Inside a `pages` folder, create four files: `Home.jsx`, `About.jsx`, `Contact.jsx`, and `Services.jsx`.
   - Each file should export a React component that includes the `Navbar` and a heading corresponding to the page name. Remember to import the `Navbar` in each of these components for consistent navigation.

5. **Set Up Routes:**

   - Define routes in `App.jsx` using `Routes` and `Route` components from `react-router-dom`.
   - Ensure that each route path (`/`, `/about`, `/contact`, `/services`) matches its respective component (`Home`, `About`, `Contact`, `Services`). Verify that the paths in your `Route` components align with the `Link` paths in `Navbar.jsx`.

6. **Run and Test:**

   - Use `npm run dev` to start your application.
   - Test the navigation by clicking on the links in the `Navbar` to ensure each page renders correctly.