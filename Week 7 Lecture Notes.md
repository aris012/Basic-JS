# Week 7



# 7.1 Rendering Lists



## Rendering Lists

### **In this lesson, you will learn**:

- How to render components from an array using JavaScript’s [`map()`](https://www.w3schools.com/jsref/jsref_map.asp)  
- How to render only specific components using JavaScript’s [`filter()`](https://www.w3schools.com/jsref/jsref_filter.asp)
- When and why to use React keys

You will often want to display multiple similar components from a collection of data. You can use the [JavaScript array methods](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array#) to manipulate an array of data. In this lesson, you’ll use [`filter()`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) and [`map()`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map) with React to filter and transform your array of data into an array of components.



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



## Task 

### Rendering Components from Arrays Using `map()` and `filter()`

#### Objectives:

- Learn how to render components from an array using JavaScript’s `map()`
- Learn how to render only specific components using JavaScript’s `filter()`
- Understand when and why to use React keys

#### Instructions:

##### Step 1: Setup Your Project

1. **Open Your Project:**

   - Open your React project in your preferred code editor.

2. **Create a List Component:**

   - In the `src` directory, you have already created a new folder named `components `in previous lesson.
   - In the `components` folder, create a new file named `List.jsx`.

3. **Add the List Component Code:**

   - Add the following code to `List.jsx`:

   ```jsx
   export default function List() {
     const people = [
             'Creola Katherine Johnson: mathematician',
             'Mario José Molina-Pasquel Henríquez: chemist',
             'Mohammad Abdus Salam: physicist',
             'Percy Lavon Julian: chemist',
             'Subrahmanyan Chandrasekhar: astrophysicist'
           ];
       
       
     const listItems = people.map((person, index) =>
       <li key={index}>{person}</li>
     );
     return <ul>{listItems}</ul>;
   }
   ```

   - This code moves the data into an array and maps each item in the array to a list item (`<li>`), adding a unique key using the `index` of the array.

4. **Render the List Component:**

   - Open `src/App.jsx` and import the `List` component:

   ```jsx
   import List from "./components/List";
   ```

   - Replace the existing JSX inside the `App` component with the `List` component:

   ```jsx
   function App() {
     return (
       <div>
         <List />
       </div>
     );
   }
   
   export default App;
   ```

5. **Run and Check Your App:**

   - Save all files and check your browser. You should see the list of names displayed.

##### Step 2: Filtering the List

1. **Update the Data Structure:**

   - Modify the `people` array in `List.jsx` to be an array of objects:

   ```jsx
   const people = [
     { name: 'Creola Katherine Johnson', profession: 'mathematician' },
     { name: 'Mario José Molina-Pasquel Henríquez', profession: 'chemist' },
     { name: 'Mohammad Abdus Salam', profession: 'physicist' },
     { name: 'Percy Lavon Julian', profession: 'chemist' },
     { name: 'Subrahmanyan Chandrasekhar', profession: 'astrophysicist' }
   ];
   ```

2. **Filter and Map the Data:**

   - Use `filter()` to show only the chemists and `map()` to create list items:
   - Try to complete the activity on your own first; if you encounter any difficulties, refer to the solution below for guidance

   ```jsx
   export default function List() {
     const chemists = people.filter(person => person.profession === 'chemist');
     const listItems = chemists.map((person, index) =>
       <li key={index}>{person.name}: {person.profession}</li>
     );
     return <ul>{listItems}</ul>;
   }
   ```

3. **Run and Check Your App:**

   - Save all files and check your browser. You should see only the chemists displayed.

##### Step 3: Using Unique Keys

1. **Update List Component to Use Unique Keys:**

   - Change the `people` array to include unique IDs:

   ```jsx
   const people = [
     { id: 1, name: 'Creola Katherine Johnson', profession: 'mathematician' },
     { id: 2, name: 'Mario José Molina-Pasquel Henríquez', profession: 'chemist' },
     { id: 3, name: 'Mohammad Abdus Salam', profession: 'physicist' },
     { id: 4, name: 'Percy Lavon Julian', profession: 'chemist' },
     { id: 5, name: 'Subrahmanyan Chandrasekhar', profession: 'astrophysicist' }
   ];
   ```

2. **Use IDs as Keys:**

   - Update the `List` component to use `id` as the key:

   ```jsx
   export default function List() {
     const chemists = people.filter(person => person.profession === 'chemist');
     const listItems = chemists.map(person =>
       <li key={person.id}>{person.name}: {person.profession}</li>
     );
     return <ul>{listItems}</ul>;
   }
   ```

3. **Run and Check Your App:**

   - Save all files and check your browser. The warning about unique keys should be gone.

##### Conclusion:

By completing this activity, you have learned how to:

- Render components from an array using `map()`.
- Filter arrays using `filter()` to render only specific components.
- Use unique keys in React components to avoid warnings and ensure efficient rendering.

This practice enhances your ability to manage and display dynamic data in React applications, a common requirement in real-world projects.







# 7.2 Conditional Rendering

## Conditional Rendering

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





reference: https://www.scholarhat.com/tutorial/react/conditional-rendering-in-react-creating-dynamic-user-interfaces

**Please read React document below to learn more about conditional rendering**

 https://react.dev/learn/conditional-rendering

**Please watch the following videos to help you better understand conditional rendering**

https://www.youtube.com/watch?v=tz7pURTCrCc&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=16 

https://www.youtube.com/watch?v=beWzxkM6wQw&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=17

https://www.youtube.com/watch?v=WWT9etP2BRo&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=18

https://www.youtube.com/watch?v=1vi8JKN8LDg&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=19

https://www.youtube.com/watch?v=wl8-JKNNPnc&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=20



## Task

### **Building and Displaying a Fruit List with Conditional Rendering**

Before starting, here's the list of fruits you'll be working with:

````react
  const fruits = [
    { name: "Apple", price: 10, emoji: "🍎"},
    { name: "Mango", price: 7, emoji: "🥭"},
    { name: "Watermelon", price: 10, emoji: "🍉"},
    { name: "Orange", price: 3, emoji: "🍊"},
    { name: "Pineapple", price: 4, emoji: "🍍"},
  ];
````

In this activity, you'll create two React components: `Fruit` and `Fruits`. You'll use these components to display a list of fruits and conditionally render them based on their price.

#### **Step 1: Create the `Fruit` Component**

1. **Create a new file**: In your `src/components` folder, create a file named `Fruit.jsx`.

2. **Define the `Fruit` component**: In `Fruit.jsx`

   This component accepts `name`, `price`, `emoji`, and `soldout` as props.

   It displays the fruit's emoji, name, and price.

````react
export default function Fruit({ name, price, emoji, soldout }) {
  return (
    <li>
      {emoji}{name}-${price}
    </li>
  );
}
````

#### **Step 2: Create the `Fruits` Component**

1. **Create a new file**: In your `src/components` folder, create a file named `Fruits.jsx`.

2. **Define the `Fruits` component**: In `Fruits.jsx`, write code to finish following task

   imports the `Fruit` component.

   defines a list of fruits.

   Use the `map` function to render a `Fruit` component for each fruit in the list, passing the necessary props to each `Fruit` component.

   In **`App.jsx`**, Import and use the `Fruits` component.

````react
import Fruit from "./Fruit";

export default function Fruits() {
  const fruits = [
    { name: "Apple", price: 10, emoji: "🍎"},
    { name: "Mango", price: 7, emoji: "🥭"},
    { name: "Watermelon", price: 10, emoji: "🍉"},
    { name: "Orange", price: 3, emoji: "🍊"},
    { name: "Pineapple", price: 4, emoji: "🍍"},
  ];
  return (
    <div>
      <ul>
        {fruits.map((fruit) => {
          return (
            <Fruit
              key={fruit.name}
              name={fruit.name}
              price={fruit.price}
              emoji={fruit.emoji}
            />
          );
        })}
      </ul>
    </div>
  );
}
````



#### **Step 3:  Only Display Fruits Below $5 Using Conditional Rendering **

**Filter the fruits:** In the `Fruits` component, modify the code to only display fruits with a price less than 5.

Note: In some situations, you won’t want to render anything at all. For example, say you don’t want to show fruit item that is under $5. A component must return something. In this case, you can return `null`:

Using an `if` statement:

`````react
export default function Fruit({ name, price, emoji }) {
  if (price >= 5) {
    return null; // Don't render anything if the price is 5 or more
  }

  return (
    <li>
      {emoji} {name} - ${price}
    </li>
  );
}
`````

Using a Ternary Operator:

`````react
export default function Fruit({ name, price, emoji }) {
  return (
    price < 5 ? (
      <li>
        {emoji} {name} - ${price}
      </li>
    ) : null
  );
}
`````

You should see only the fruits under $5 displayed.

Another way to display fruits under $5 is to handle filtering in the `Fruits` component and avoid rendering unnecessary components, you can filter the list of fruits before mapping them to `Fruit` components. 



Note: The ternary operator `price < 5 ? ... : ...` is pure JavaScript. It's used here to conditionally decide what to return. If the `price` is less than 5, it will return the JSX inside the parentheses; otherwise, it will return `null`. `price < 5` is treated as a regular JavaScript expression, which does not require `{}`. The curly braces are needed only when embedding JavaScript within JSX tags.







# 7.3 Responding to Events



## Responding to Events

React lets you add *event handlers* to your JSX. Event handlers are your own functions that will be triggered in response to interactions like clicking, hovering, focusing form inputs, and so on.

### You will learn

- Different ways to write an event handler
- How to pass event handling logic from a parent component

### React Events

Just like HTML DOM events, React can perform actions based on user events.

React has the same events as HTML: click, change, mouseover etc.

### Adding Events

React events are written in camelCase syntax:

`onClick` instead of `onclick`.

React event handlers are written inside curly braces:

`onClick={shoot}` instead of `onclick="shoot()"`.

To add an event handler, you will first define a function and then pass it as a prop to the appropriate JSX tag. For example, here is a button that doesn’t do anything yet:

````react
export default function Button() {
  return (
    <button>
      I don't do anything
    </button>
  );
}
````

You can make it show a message when a user clicks by following these three steps:

1. Declare a function called `handleClick` *inside* your `Button` component.
2. Implement the logic inside that function (use `alert` to show the message).
3. Add `onClick={handleClick}` to the `<button>` JSX.

`````react
export default function Button() {
  function handleClick() {
    alert('You clicked me!');
  }

  return (
    <button onClick={handleClick}>
      Click me
    </button>
  );
}
`````

You defined the `handleClick` function and then passed it as a prop to `<button>`.  `handleClick` is an **event handler.** Event handler functions:

- Are usually defined *inside* your components.
- Have names that start with `handle`, followed by the name of the event.

By convention, it is common to name event handlers as `handle` followed by the event name. You’ll often see `onClick={handleClick}`, `onMouseEnter={handleMouseEnter}`, and so on.

Alternatively, you can define an event handler inline in the JSX:

````react
<button onClick={function handleClick() {
  alert('You clicked me!');
}}>
````

Or, more concisely, using an arrow function:

````react
<button onClick={() => {
  alert('You clicked me!');
}}>
````

All of these styles are equivalent. Inline event handlers are convenient for short functions.



### Passing Arguments

To pass an argument to an event handler, use an arrow function.

**Example**:

Send "Goal!" as a parameter to the `shoot` function, using arrow function:

````react
export default function Football() {
  function shoot(a) {
    alert(a);
  }

  return <button onClick={() => shoot("Goal!")}>Take the shot!</button>;
}

````

**Passing Arguments:**

- You want to pass an argument (`"Goal!"`) to the `shoot` function when the button is clicked. If you were to write `shoot("Goal!")` directly inside the `onClick` handler, the function would be called immediately when the component renders, not when the button is clicked.
- To prevent this immediate execution, you use an arrow function: `() => shoot("Goal!")`. This creates a new function that React will call when the `onClick` event occurs, and inside that function, the `shoot` function is then called with the `"Goal!"` argument.



### React Event Object

Event handlers have access to the React event that triggered the function.





If you don't need to pass any additional arguments to your function and just want to pass the event object, you can simply reference the function directly without wrapping it in an arrow function. React will automatically pass the event object as the first argument to the function.

```react
export default function Football() {
  function shoot(event) {
    alert(`Button clicked! Event type: ${event.type}`);
  }

  return <button onClick={shoot}>Take the shot!</button>;
}
```



To pass an event to a function in React, you can do so by including the event object as an argument in your function. When you use an event handler like `onClick`, React automatically passes the event object to the handler function.

In our example the event is the "click" event.

**Example**:

Arrow Function: Sending the event object manually:

````react
export default function Football() {
  function shoot(a, event) {
    alert(event.type);
    /*
    'b' represents the React event that triggered the function,
    in this case the 'click' event
    */
  }

  return (
    <button onClick={(event) => shoot("Goal!", event)}>Take the shot!</button>
  );
}
````

#### Breakdown

1. **Function Definition:**
   - `function shoot(a, event)` defines a normal function named `shoot` that takes two parameters: `a` and `event`.
2. **Button Click Handler:**
   - `<button onClick={(event) => shoot("Goal!", event)}>` uses an arrow function to handle the `onClick` event.
   - The arrow function `(event) => shoot("Goal!", event)` calls the `shoot` function, passing `"Goal!"` as the first argument and the `event` object as the second argument.
3. **Event Handling:**
   - When the button is clicked, the arrow function captures the `event` and passes it to the `shoot` function along with the string `"Goal!"`.
   - The `shoot` function then displays an alert showing both the string `"Goal!"` and the event type.

#### Why Use This Approach?

- **Flexibility:** This method allows you to pass additional parameters to the function while still receiving the event object.
- **Readability:** Using an arrow function in the `onClick` attribute makes it clear that you are passing additional arguments along with the event.



Reference: 

 https://www.w3schools.com/react/react_events.asp 

https://react.dev/learn/responding-to-events

**Please watch the following videos to help you better understand Event Handling in React**

https://www.youtube.com/watch?v=sq4kXuZhZH8&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=21





## Task

### Created a `LightSwitch` component with an `onClick` event handler to toggle the page background color

1. Create a New File for the LightSwitch Component

In the `components` folder, create a file named `LightSwitch.jsx`.

2. Define the LightSwitch Component

````react
export default function LightSwitch() {

  return (
    <button>
      Toggle the lights
    </button>
  );
}
````

3. Update `App.jsx`

In **`App.jsx`**, Import and use the `LightSwitch` component.

````react
import LightSwitch from "./components/LightSwitch";

function App() {
  return (
    <div>
      <LightSwitch />
    </div>
  );
}

export default App;
````

4. create `handleClick` function to switch the page background between white and black in `LightSwitch` component.

````react
  function handleClick() {
    let bodyStyle = document.body.style;
    if (bodyStyle.backgroundColor === 'black') {
      bodyStyle.backgroundColor = 'white';
    } else {
      bodyStyle.backgroundColor = 'black';
    }
  }
````

5. Add an `onClick` event to the button element in the `LightSwitch` component so that when the button is clicked, it toggles the page background color between white and black.

````react
export default function LightSwitch() {
    
  function handleClick() {
    let bodyStyle = document.body.style;
    if (bodyStyle.backgroundColor === 'black') {
      bodyStyle.backgroundColor = 'white';
    } else {
      bodyStyle.backgroundColor = 'black';
    }
  }

  return (
    <button onClick={handleClick}>
      Toggle the lights
    </button>
  );
}
````

In this task, you created a `LightSwitch` component with an `onClick` event handler to toggle the page background color. You also updated the `App` component to use the new `LightSwitch` component.









# 7.4  Managing State in React

## Managing State in React

Hooks were added to React in version 16.8.

Hooks allow function components to have access to state and other React features. Because of this, class components are generally no longer needed.

### useState Hook

The React `useState` Hook allows us to track state in a function component.

State generally refers to data or properties that need to be tracking in an application.

**Import `useState`**

To use the `useState` Hook, we first need to `import` at the top of component.

````react
import { useState } from "react";
````

Notice that we are destructuring `useState` from `react` as it is a named export. 

To learn more about destructuring, check out the link below:

https://www.w3schools.com/react/react_es6_destructuring.asp

**Initialize `useState`**

We initialize our state by calling `useState` in our function component.

`useState` accepts an initial state and returns two values:

- The current state.
- A function that updates the state.

**Example:**

Initialize state at the top of the function component.

````react
import { useState } from "react";

function FavoriteColor() {
  const [color, setColor] = useState("");
}
````

Notice that again, we are destructuring the returned values from `useState`.

The first value, `color`, is our current state.

The second value, `setColor`, is the function that is used to update our state. 

**Note**: These names are variables that can be named anything you would like.

Lastly, we set the initial state to an empty string: `useState("")`



### Read State

We can now include our state anywhere in our component.

**Example**:

Use the state variable in the rendered component.

````react
import { useState } from "react";

export default function FavoriteColor() {
  const [color, setColor] = useState("red");

  return <h1>My favorite color is {color}!</h1>;
}
````

### Update State

To update our state, we use our state updater function.

**Example**:

Use a button to update the state:

````react
import { useState } from "react";

export default function FavoriteColor() {
  const [color, setColor] = useState("red");

  return (
    <>
      <h1>My favorite color is {color}!</h1>
      <button
        onClick={() => {
          setColor("Blue");
        }}
      >
        Blue
      </button>
    </>
  );
}
````

In this  `FavoriteColor` component, the `useState` hook is used to manage the state of a `color` variable, initially set to "red". The component renders a heading that displays the current favorite color and a button labeled "Blue". When the button is clicked, the `onClick` event handler updates the `color` state to "Blue" using the `setColor` function. This change triggers a re-render, updating the heading to reflect the new favorite color. This demonstrates how state management and event handling work together in React to dynamically update the UI based on user interactions.



### What Can State Hold

The `useState` Hook can be used to keep track of strings, numbers, booleans, arrays, objects, and any combination of these!

We could create multiple state Hooks to track individual values.

````react
import { useState } from "react";

export default function Car() {
  const [brand, setBrand] = useState("Ford");
  const [model, setModel] = useState("Mustang");
  const [year, setYear] = useState("1964");
  const [color, setColor] = useState("red");

  return (
    <>
      <h1>My {brand}!!</h1>
      <p>
        It is a {color} {model} from {year}.
      </p>
    </>
  );
}
````

Or, we can just use one state and include an object instead!

````react
import { useState } from "react";

export default function Car() {
  const [car, setCar] = useState({
    brand: "Ford",
    model: "Mustang",
    year: "1964",
    color: "red",
  });

  return (
    <>
      <h1>My {car.brand}</h1>
      <p>
        It is a {car.color} {car.model} from {car.year}.
      </p>
    </>
  );
}

//Since we are now tracking a single object, we need to reference that object and then the property of that object when rendering the component. (Ex: car.brand)
````





### Updating Objects and Arrays in State

When state is updated, the entire state gets overwritten.

What if we only want to update the color of our car?

If we only called `setCar({color: "blue"})`, this would remove the brand, model, and year from our state.

We can use the **JavaScript spread operator** to help us.

````react
import { useState } from "react";

export default function Car() {
  const [car, setCar] = useState({
    brand: "Ford",
    model: "Mustang",
    year: "1964",
    color: "red",
  });

  function updateColor() {
    setCar((previouseState) => {
      return { ...previouseState, color: "Blue" };
    });
  }

  return (
    <>
      <h1>My {car.brand}!!</h1>
      <p>
        It is a {car.color} {car.model} from {car.year}.
      </p>
      <button onClick={updateColor}>Update Color</button>
    </>
  );
}
````

In this React component, `Car`, the `useState` hook is used to manage the state of a car object, which includes properties like brand, model, year, and color. Initially, the car is set with a default state: a red Ford Mustang from 1964. The `updateColor` function, which is called when the "Update Color" button is clicked, updates the car's color to blue. It uses the spread operator (`...`) within the functional update form of `setCar` to create a new car object with the updated color while preserving the existing properties. This ensures that only the `color` property is modified, and the rest of the car's details remain unchanged.



**`prevState`**: Represents the current state object of `car` before the update. It is a parameter in the state updater **updateColor** function that represents the current state of the component before any updates are applied. 

You can name the parameter whatever you like, as long as it is descriptive. For example, you might call it `currentState`, `prevCarState`, or simply `state`. The important thing is that the name should clearly convey that it represents the current state before the update.



reference:

https://www.w3schools.com/react/react_usestate.asp 

**Please watch the following videos to help you better understand useState Hook in React**

https://www.youtube.com/watch?v=VT9qU5uIKyE&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=22 

https://www.youtube.com/watch?v=esBzjVl9b0k&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=23





## Task

###  **Implementing a Counter in a Shopping Cart Application**

**Objective:** Learn how to use the `useState` hook to manage state in a React component by building a counter for a shopping cart item.

Try to write the code by following the instructions first. Only refer to the provided code if you are confused or struggling. This approach will help you develop problem-solving skills and gain a deeper understanding of the concepts.

**Instructions:**

1. **Create a New Component**

   *Instruction:* Start by defining a basic React component structure for `ItemCounter`. Initially, create a simple UI with a heading, a paragraph displaying a static quantity of 0, and two buttons labeled "Increase" and "Decrease". This will help you set up the component before adding functionality.

   - **Create a File for Your Component:**

     - In the `src/components` folder, create a file named `ItemCounter.jsx`.

   - **Define the ItemCounter Component:**

     - Open `ItemCounter.jsx` and write the following code:

     ````react
     export default function ItemCounter() {
       return (
         <div>
           <h2>Item Quantity</h2>
           <p>Quantity: 0</p>
           <button>Increase</button>
           <button>Decrease</button>
         </div>
       );
     }
     ````

     

2. **Import to App.jsx**

   *Instruction:* Integrate the `ItemCounter` component into your main application to make it visible. This step involves importing the `ItemCounter` component and rendering it within the `App` component.

   - **Import ItemCounter:**

     - In `App.jsx`, add the following code:

     ````react
     import ItemCounter from "./components/ItemCounter";
     
     function App() {
       return (
         <div>
           <ItemCounter />
         </div>
       );
     }
     
     export default App;
     ````

     

3. **Add State Management**

   *Instruction:* Introduce state management using the `useState` hook. This allows the component to manage and display the quantity dynamically. Implement the state initialization and use it to update the quantity displayed in the paragraph.

   - **Modify ItemCounter to Use State:**

     - Update `ItemCounter.jsx` to the following:

     ````react
     import { useState } from "react";
     
     export default function ItemCounter() {
       // Initialise State
       const [count, setCount] = useState(0);
     
       return (
         <div>
           <h2>Item Quantity</h2>
           <p>Quantity: {count}</p>
           <button>Increase</button>
           <button>Decrease</button>
         </div>
       );
     }
     ````

     

4. **Implement Event Handlers**

   *Instruction:* Add event handlers to manage state changes when the buttons are clicked. Define functions to increment and decrement the count, and link these functions to the buttons using the `onClick` event handler.

    In this final step, you add the logic to update the state based on button clicks. The `increment` function increases the count by 1, while the `decrement` function decreases the count by 1 but ensures it does not go below 0. Connect these functions to the respective buttons to make the quantity interactive.

   - **Update ItemCounter with Event Handlers:**

     - Modify `ItemCounter.jsx` to the following:

     ````react
     import { useState } from "react";
     
     export default function ItemCounter() {
       // Initialize State
       const [count, setCount] = useState(0);
     
       // Create traditional Function to Update State
       function increment() {
       setCount(prevCount => prevCount + 1);
     }
       // Create arrow Function to Update State
       const decrement = () => {
       setCount(prevCount => (prevCount > 0 ? prevCount - 1 : 0));
     }
     
       return (
         <div>
           <h2>Item Quantity</h2>
           <p>Quantity: {count}</p>
           <button onClick={increment}>Increase</button>
           <button onClick={decrement}>Decrease</button>
         </div>
       );
     }
     ````

     

   Congratulations on completing this task!

   In this exercise, you learned how to utilize the `useState` hook to manage and update state within a React component. You created a basic counter component for a shopping cart application, integrated it into your main app, and added functionality to dynamically adjust the item quantity. By using event handlers and state management, you enhanced the interactivity of your component, allowing users to increase or decrease the quantity of items.

   These skills are fundamental in building interactive user interfaces with React. Understanding how to manage state and respond to user actions will help you develop more complex and engaging applications. Keep practicing these concepts to solidify your knowledge and build more advanced features in your projects.



