

# Week 8



# 8.1 DOM Events

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









# 8.2 [Spread Operator](https://www.w3schools.com/react/react_es6_spread.asp) 







# 8.3 React Forms



## React Forms

Just like in HTML, React uses forms to allow users to interact with the web page.

### Adding Forms in React

You add a form with React like any other element:

```jsx
export default function MyForm() {
  return (
    <form>
      <label>
        Enter your name:
        <input type="text" />
      </label>
    </form>
  );
}
```

This will work as normal, the form will submit and the page will refresh.

But this is generally not what we want to happen in React.

We want to prevent this default behavior and let React control the form.

### Handling Forms

Handling forms is about how you handle the data when it changes value or gets submitted.

In HTML, form data is usually handled by the DOM.

In React, form data is usually handled by the components.

When the data is handled by the components, all the data is stored in the component state.

You can control changes by adding event handlers in the `onChange` attribute.

We can use the `useState` Hook to keep track of each inputs value and provide a "single source of truth" for the entire application.

#### Example:

Use the `useState` Hook to manage the input:

````react
import { useState } from "react";

export default function MyForm() {
  const [name, setName] = useState("hello");
  return (
    <form>
      <label>
        Enter your name:
        <input
          type="text"
          value={name}
          onChange={(e) => setName(e.target.value)}
        />
      </label>
    </form>
  );
}
````

### Submitting Forms

You can control the submit action by adding an event handler in the `onSubmit` attribute for the `<form>`

#### Example:

Add a submit button and an event handler in the `onSubmit` attribute:

````react
import { useState } from "react";

export default function MyForm() {
  const [name, setName] = useState("hello");

  function handleSubmit(event) {
    event.preventDefault();
    alert(`The name you entered was: ${name}`);
  }
  return (
    <form onSubmit={handleSubmit}>
      <label>
        Enter your name:
        <input
          type="text"
          value={name}
          onChange={(e) => setName(e.target.value)}
        />
      </label>
      <input type="submit" />
    </form>
  );
}
````

In this code, the form submission is controlled by adding an event handler to the `onSubmit` attribute of the `<form>` element. The `handleSubmit` function, which is set as the event handler, prevents the default form submission behavior (which would normally reload the page) and instead shows an alert with the current value of the `name` state when the form is submitted. This way, you can manage what happens when the user submits the form without reloading the page.



### Multiple Input Fields

You can control the values of more than one input field by adding a `name` attribute to each element.

We will initialize our state with an empty object.

To access the fields in the event handler use the `event.target.name` and `event.target.value` syntax.

To update the state, use square brackets [bracket notation] around the property name.

#### Example:

Write a form with two input fields:

````react
import { useState } from "react";

// Define the MyForm component
export default function MyForm() {
  // Initialize state to hold form input values
  const [inputs, setInputs] = useState({ username: "", age: "" });

  // Handle input changes
  function handleChange(e) {
    // Extract the name and value from the event target (input element)
    const name = e.target.name;
    const value = e.target.value;

    // Update the state with the new value, preserving other form values
    setInputs((preValues) => ({ ...preValues, [name]: value }));
  }

  // Handle form submission
  function handleSubmit(event) {
    // Prevent the default form submission behavior
    event.preventDefault();
    // Display the current form values as a JSON string
    alert(`name: ${inputs.username}\nage: ${inputs.age}`);
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Enter your name:
        <input
          type="text"
          name="username"
          value={inputs.username || ""} //Set value from state or default to empty string
          onChange={handleChange} //Handle changes to update state
        />
      </label>
      <label>
        Enter your age:
        <input
          type="number"
          name="age"
          value={inputs.age || ""}
          onChange={handleChange}
        />
      </label>
      <input type="submit" />
    </form>
  );
}
````

**Note:** We use the same event handler function for both input fields, we could write one event handler for each, but this gives us much cleaner code and is the preferred way in React.

### Textarea

The textarea element in React is slightly different from ordinary HTML.

In HTML the value of a textarea was the text between the start tag `<textarea>` and the end tag `</textarea>`.

````react
<textarea>
  Content of the textarea.
</textarea>
````

In React the value of a textarea is placed in a value attribute. We'll use the `useState` Hook to manage the value of the textarea:

#### Example:

A simple textarea with some content:

````react
import { useState } from "react";

export default function TextArea() {
  const [textarea, setTextarea] = useState(
    "The content of a textarea goes in the value attribute"
  );

  const handleChange = (event) => {
    setTextarea(event.target.value);
  };

  return (
    <form>
      <textarea value={textarea} onChange={handleChange} />
    </form>
  );
}
````

### Select box

A drop down list, or a select box, in React is also a bit different from HTML.

In HTML, the selected value in the drop down list was defined with the `selected` attribute:

````react
<select>
  <option value="Ford">Ford</option>
  <option value="Volvo" selected>Volvo</option>
  <option value="Fiat">Fiat</option>
</select>
````

In React, the selected value is defined with a `value` attribute on the `select` tag:

#### Example:

A simple select box, where the selected value "Volvo" is initialized in the constructor:

````react
import { useState } from "react";

export default function SelectForm() {
  const [myCar, setMyCar] = useState("Volvo");

  const handleChange = (event) => {
    setMyCar(event.target.value);
  };

  return (
    <form>
      <select value={myCar} onChange={handleChange}>
        <option value="Ford">Ford</option>
        <option value="Volvo">Volvo</option>
        <option value="Fiat">Fiat</option>
      </select>
    </form>
  );
}
````

By making these slight changes to `<textarea>` and `<select>`, React is able to handle all input elements in the same way.



Reference: https://www.w3schools.com/react/react_forms.asp

**Please watch the following videos to help you better understand handling form in React**

https://www.youtube.com/watch?v=2bCqpPDRq3s&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=25

https://www.youtube.com/watch?v=5FDDoHI173g&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=26

https://www.youtube.com/watch?v=falMPMOPMAk&list=PLSsAz5wf2lkKm0BG9wUWWSgYWBzDa-dFs&index=27





## Task

### Implementing a Form with React

#### Objective:

Learn how to use React’s state management to handle form inputs, including text fields, textarea, and select elements. You will practice controlling form data and preventing default form submission behavior.

#### Instructions:

1. **Create a New React Component for the Form**

   - In the `src/components` folder, create a file named `UserForm.jsx`.
   - Open `UserForm.jsx` and start by importing `useState` from React.

   ```javascript
   import { useState } from "react";
   
   export default function UserForm() {
     return (
       <form>
         {/* Form elements will go here */}
       </form>
     );
   }
   ```

2. **Add Text Input Fields**

   - Initialize state for the form input values.
   - Add a text input field for capturing the user’s name.

   ```javascript
   import { useState } from "react";
   
   export default function UserForm() {
     // Initialize state to hold form input values
     const [inputs, setInputs] = useState({ name: "", age: "" });
   
     return (
       <form>
         <label>
           Enter your name:
           <input
             type="text"
             name="name"
             value={inputs.name}
             onChange={(e) => setInputs({ ...inputs, name: e.target.value })}
           />
         </label>
       </form>
     );
   }
   ```

3. **Add an Age Input Field**

   - Expand the state to include the age field.
   - Add another input field for the user’s age.

   ```javascript
   import { useState } from "react";
   
   export default function UserForm() {
     // Initialize state to hold form input values
     const [inputs, setInputs] = useState({ name: "", age: "" });
   
     // Handle changes for input fields
     function handleChange(e) {
       const { name, value } = e.target;
       setInputs((prevValues) => ({ ...prevValues, [name]: value }));
     }
   
     return (
       <form>
         <label>
           Enter your name:
           <input
             type="text"
             name="name"
             value={inputs.name}
             onChange={handleChange}
           />
         </label>
         <label>
           Enter your age:
           <input
             type="number"
             name="age"
             value={inputs.age}
             onChange={handleChange}
           />
         </label>
       </form>
     );
   }
   ```

4. **Add a Submit Button and Handle Form Submission**

   - Add a submit button to the form.
   - Implement the `handleSubmit` function to prevent the default form submission and display the form data using an alert.

   ```javascript
   import { useState } from "react";
   
   export default function UserForm() {
     // Initialize state to hold form input values
     const [inputs, setInputs] = useState({ name: "", age: "" });
   
     // Handle changes for input fields
     function handleChange(e) {
       const { name, value } = e.target;
       setInputs((prevValues) => ({ ...prevValues, [name]: value }));
     }
   
     // Handle form submission
     function handleSubmit(event) {
       event.preventDefault();
       alert(`Name: ${inputs.name}\nAge: ${inputs.age}`);
     }
   
     return (
       <form onSubmit={handleSubmit}>
         <label>
           Enter your name:
           <input
             type="text"
             name="name"
             value={inputs.name}
             onChange={handleChange}
           />
         </label>
         <label>
           Enter your age:
           <input
             type="number"
             name="age"
             value={inputs.age}
             onChange={handleChange}
           />
         </label>
         <input type="submit" />
       </form>
     );
   }
   ```

5. **Add a Textarea and Select Element**

   - Expand the form to include a textarea for additional comments and a select box for choosing a car brand.

   ```javascript
   import { useState } from "react";
   
   export default function UserForm() {
     // Initialize state to hold form input values
     const [inputs, setInputs] = useState({ name: "", age: "", comments: "", car: "Ford" });
   
     // Handle changes for input fields
     function handleChange(e) {
       const { name, value } = e.target;
       setInputs((prevValues) => ({ ...prevValues, [name]: value }));
     }
   
     // Handle form submission
     function handleSubmit(event) {
       event.preventDefault();
       alert(`Name: ${inputs.name}\nAge: ${inputs.age}\nComments: ${inputs.comments}\nCar: ${inputs.car}`);
     }
   
     return (
       <form onSubmit={handleSubmit}>
         <label>
           Enter your name:
           <input
             type="text"
             name="name"
             value={inputs.name}
             onChange={handleChange}
           />
         </label>
         <label>
           Enter your age:
           <input
             type="number"
             name="age"
             value={inputs.age}
             onChange={handleChange}
           />
         </label>
         <label>
           Comments:
           <textarea
             name="comments"
             value={inputs.comments}
             onChange={handleChange}
           />
         </label>
         <label>
           Choose your car:
           <select
             name="car"
             value={inputs.car}
             onChange={handleChange}
           >
             <option value="Ford">Ford</option>
             <option value="Volvo">Volvo</option>
             <option value="Fiat">Fiat</option>
           </select>
         </label>
         <input type="submit" />
       </form>
     );
   }
   ```

#### Conclusion:

In this task, you learned how to create and manage a form in React. You used the `useState` hook to control input values and handle form submission, preventing the default page refresh. You also implemented various input types, including text fields, textarea, and select elements, showcasing how React handles different form controls. By following these steps, you should now be comfortable with managing form state and handling user input in a React application.







