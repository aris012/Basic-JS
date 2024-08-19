# Dicee Challenge 

### **Step 1 - Create an External Javascript File**

Create a new Javascript file called index.js and link to it from the index.html file.



### **Step 2 - Add Dice Images**

In the Dicee project, there is a folder called images, add the images of dice6.png as the source to both of the <img> elements.



### Step 3 - Create a Random Number

Inside index.js, create a new variable called `randomNumber1` then set the value of this variable to a random number between 1 and 6. Test it out in the console to make sure it works as expected.



### Step 4 - Change the <img> to a Random Dice

Use the random number you created in the last step to pick out a random dice image between dice**1**.png to dice **6**.png then place this image inside the left <img> element.

Hint: You will need to use what you've learnt about the DOM and the method setAttribute() to achieve this. [HTML DOM Element setAttribute()](https://www.w3schools.com/jsref/met_element_setattribute.asp)



### Step 5 - Change both <img> Elements

Do the same for the right hand side image element.



### Step 6 - Change the Title to Display a Winner

Change the text in the h1, (which currently says Refresh Me) to show which user won or if there was a draw depending on the dice values of player 1 (left) and player 2 (right).

<img src="https://img-c.udemycdn.com/redactor/raw/2018-11-03_02-51-14-87553d9e0d570eab7ab9cb19af24f242.gif" alt="img" style="zoom: 50%;" />





# Apply user interface design principles and user accessibility principles 



## 1. **Semantic HTML Structure**

- **Use Semantic Elements:** Replace `<div>` elements with more meaningful semantic elements 

  ```html
  <header>
    <h1>Refresh Me</h1>
  </header>
  
  <main class="container">
    <section class="dice">
      <h2>Player 1</h2>
      <img class="img1" src="images/dice6.png" alt="Dice showing 6" />
    </section>
  
    <section class="dice">
      <h2>Player 2</h2>
      <img class="img2" src="images/dice6.png" alt="Dice showing 6" />
    </section>
  </main>
  
  <footer>
    <p>www 🎲 Whitecliffe 🎲 ac.nz</p>
  </footer>
  ```

**Principle:** **Clarity and Structure**

**Description:**

- Semantic HTML elements like `<header>`, `<main>`, `<section>`, and `<footer>` should be used to give structure and meaning to the content. This enhances readability and makes it easier for assistive technologies (e.g., screen readers) to interpret the page's content.

## 2. **Accessibility Enhancements**

- **Alt Attributes:** Ensure all images have descriptive `alt` attributes.

  ```html
  <img class="img1" src="images/dice6.png" alt="Dice showing 6" />
  ```

  Alt attributes should be added to the dice images, providing text descriptions of the images. This ensures that users who rely on screen readers or those with slow internet connections can understand what the images represent.

- **Color Contrast:** Ensure sufficient color contrast between text and background. Use tools like [WebAIM's Contrast Checker](https://webaim.org/resources/contrastchecker/) to validate.

- **Font Size and Readability:** Use legible font sizes and consider users with visual impairments.

## 3. **Responsive Design**

- **Viewport Meta Tag:** Add the viewport meta tag for responsive scaling on mobile devices.

  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  ```

- **Flexible Layouts:** Use CSS Flexbox or Grid to create flexible layouts that adapt to various screen sizes.

  ```css
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  @media (min-width: 600px) {
    .container {
      flex-direction: row;
      justify-content: space-around;
    }
  }
  ```

## 4. **Interactive Elements**

- **Refresh Functionality:** Since the heading says "Refresh Me," consider adding a button that allows users to roll the dice without refreshing the entire page.

  ```html
  <button class="rollButton">Roll Dice</button>
  ```

  Ensuring that all interactive elements (like buttons) are accessible via keyboard is crucial for users who cannot use a mouse. This involves focus management and the ability to navigate through elements using keyboard keys (e.g., Tab, Enter).

  **Example:** The addition of a `button` element for rolling the dice should be focusable and triggerable via keyboard, improving accessibility for users with physical impairments.

  #####  **Adding Outline on Focus (for Accessibility)**

  To ensure better accessibility, you can add an outline when the button is focused (e.g., when navigated via keyboard):

  ````css
  .rollButton:focus {
    outline: 2px solid #2ecc71; /* Green solid outline on focus */
    outline-offset: 3px;
  }
  ````

  

- **ARIA Labels:** For interactive elements like buttons, ensure they have appropriate ARIA labels if necessary.  [Accessibility Labels](https://www.w3schools.com/accessibility/accessibility_labels.php)

- **Description**: The `aria-label` attribute provides an accessible name for elements that do not have a visible text label. It allows developers to define a custom label that assistive technologies, such as screen readers, can announce to users, ensuring that they understand the purpose or function of an element.

  ```html
  <button id="rollButton" aria-label="Roll the dice">Roll Dice</button>
  ```





# Rock-Paper-Scissors



![image-20240811233252183](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240811233252183.png)



![image-20240811234220956](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240811234220956.png)





## Strategy for JavaScript:

1. Think about what steps we need
2. Convert those steps into code

**Algorithm**:
when we click a button:

1. Computer randomly selects a move
2. Compare the moves to get the result
3. Display the result in a popup



## 1. Using inline JavaScript - onclick attribute

**Issues**:

Repetition: The code for generating the computer’s move and comparing it with the player’s move is repeated in each button’s onclick attribute.

Inline JavaScript: Putting large blocks of JavaScript directly inside the onclick attribute makes the HTML harder to read and maintain.

No Separation of Concerns: Mixing HTML and JavaScript makes the code harder to manage, especially as the complexity grows. --

#### step 1: Computer randomly selects a move

#### step 2: Compare the moves to get the result

#### step 3: Display the result in a popup



## 2. Refactor code using function 

#### step 1: Create a function pickComputerMove

````js


//computer picks a random move
    function pickComputerMove() {
      //generate a random number
      const randomNumber = Math.random();

	let computerMove = '';  //global variable
      
        //convert random number to a random move
      if (randomNumber < 1 / 3) {
        computerMove = "rock";
      } else if (randomNumber < 2 / 3) {
        computerMove = "paper";
      } else {
        computerMove = "scissors";
      }
      return computerMove; //return statement let us get a value out of a function 
    }
````

functions create a scope, any variable that is created between the curly brackets only exists inside the curly brackets. best practice is to keep variables inside a scope if we can.

functions let us reuse code and make out code a lot cleaner by removing all the duplication that we had. 

functions also make our code easier to update



#### step 2:  Create playGame function to reuse all the code 

````js
    function playGame(playerMove) {
      //generate the computer's move
      let computerMove = pickComputerMove();
      let result = "";

      //compare moves to get the result
      if (playerMove === computerMove) {
        result = "Tie";
      } else if (
        (playerMove === "rock" && computerMove === "scissors") ||
        (playerMove === "paper" && computerMove === "rock") ||
        (playerMove === "scissors" && computerMove === "paper")
      ) {
        result = "You win";
      } else {
        result = "You lose";
      }

      alert(
        `You picked ${playerMove}. Computer picked ${computerMove}. ${result}`
      );
    }
````







## 3. Add a score to the game

**Strategy for JavaScript:**

1. Think about what steps we need
2. Convert those steps into code

**Algorithm**:
when we click a button:

1. Computer randomly selects a move
2. Compare the moves to get the result
3. **Update a score**
4. Display the result and score in a popup



#### step 1:

create a variable to store score

````js
    const score = {
      wins: 0,
      losses: 0,
      ties: 0,
    };
//keep it outside the function, because if we create it inside the playGame function, everytime we play the game, it will create a new score
````



#### step 2:

update the score 

![image-20240811233953110](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240811233953110.png)



#### step 3:

display the score in the pop up

````js
alert(
        `You picked ${playerMove}. Computer picked ${computerMove}. ${result}
Wins: ${score.wins}, Losses: ${score.losses}, Ties: ${score.ties}`
      );
````









## 4. Use LocalStorage to store the score more permanently.

issue: if we fresh the page, the score starts from zero again. that's because when we refresh the page, all of these variables are deleted, and the score gets reset back to zero . 

**localStorage**

**localStorage.setItem( )**  : save a value inside localStorage, two parameters required, only support strings  [Storage setItem() Method](https://www.w3schools.com/jsrEF/met_storage_setitem.asp) 

**example**: localStorage.setItem('message', 'hello')

**localStorage.getItem( ):** get the string out of the storage, one parameters required, only support strings

**example**: localStorage.getItem('message')



localStorage only support strings, to store the score using localStorage, we have to convert it into JSON string



#### Step 1. 

convert score object into string and store in localStorage:



**JSON.stringify()**

localStorage.setItem('score', JSON.stringify(score)): convert js object score into a JSON string

````js
localStorage.setItem("score", JSON.stringify(score));

alert(
        `You picked ${playerMove}. Computer picked ${computerMove}. ${result}
Wins: ${score.wins}, Losses: ${score.losses}, Ties: ${score.ties}`
      );
````



#### Step 2. 

localStorage.getItem('score')

get score from localStorage and convert JSON string back into a js object 

**JSON.parse()**: JSON.parse(localStorage.getItem('score'))

````js
let score = JSON.parse(localStorage.getItem("score"));

function playGame(playerMove) {...}
````



#### step 3. 

when we click the reset score, we can remove the score from localStorage using localStorage .removeItem('score')

````js
function resetScore() {
      score.wins = 0;
      score.losses = 0;
      score.ties = 0;
      localStorage.removeItem('score');
    }
````



#### step 4.

after reset score, it gives an error when playing game again because we are trying to get value from localStorage that doesn't exist, it will give a value null

````js
let score = JSON.parse(localStorage.getItem("score"));

    if (score === null) {
      score = {
        wins: 0,
        losses: 0,
        ties: 0,
      };
    }

//alternative way: using a default operator to simplify code
/*
let score = JSON.parse(localStorage.getItem("score")) || {
        wins: 0,
        losses: 0,
        ties: 0,
      };
*/
````





## 5. Display the score on the page 

![image-20240811232346567](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240811232346567.png)



#### step 1.

add HTML elements to put the results and score 

````html
    <p class="js-result"></p>
    <p class="js-moves"></p>
    <p class="js-score"></p>
````

````js
document.querySelector(".js-score").textContent = `Wins: ${score.wins}, Losses: ${score.losses}, Ties: ${score.ties}`;
````



create a function and call the function whenever needed:

````js
    function updateScoreElement() {
      document.querySelector(
        ".js-score"
      ).textContent = `Wins: ${score.wins}, Losses: ${score.losses}, Ties: ${score.ties}`;
    }
````



#### step 2.

display result on webpage

at the bottom of playGame function, add code as below

````js
localStorage.setItem("score", JSON.stringify(score));

      updateScoreElement();

      document.querySelector(".js-result").innerHTML = result;
      document.querySelector(
        ".js-moves"
      ).innerHTML = `You ${playerMove} - Computer ${computerMove}`;
````





# JSON   

[**JavaScript JSON**](https://www.w3schools.com/js/js_json.asp)

built-in Objects:

- console
- Math
- JSON: JavaScript Object Notation
- localStorage

**JSON**( JavaScript Object Notation), JSON is a syntax, similar to JavaScript Object , but has less features

**JSON** doesn't support single quotes, doesn't support functions

**Why would we JSON syntax?** JavaScript  Object only makes sense in JavaScript, JSON syntax can be understood by almost every programming language, so JSON  syntax is more universal . we use JSON  when we send data between two computers that might use different programming language. we also use JSON when we store data.

**Built-in JSON Object:**

-  convert a JavaScript object to JSON using  **JSON.stringify()**   
-  covert JSON back to a JavaScript  object using **JSON.parse()**





# localStorage

**localStorage.setItem( )**  : save a value inside localStorage, two parameters required, only support strings  [Storage setItem() Method](https://www.w3schools.com/jsrEF/met_storage_setitem.asp) 

**example**: localStorage.setItem('message', 'hello')



**localStorage.getItem( ):** get the string out of the storage, one parameters required, only support strings

**example**: localStorage.getItem('message')



**localStorage only support strings, to store the score using localStorage, we have to convert it into JSON string**