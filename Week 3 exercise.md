# Arrays

## What is an array?

An array is a special variable, which can hold more than one value: 

````js
const shopping = ["bread", "milk", "cheese", "hummus", "noodles"];
````



## Why Use Arrays?

If you have a list of items (a list of car names, for example), storing the cars in single variables could look like this:

````js
let car1 = "Saab";
let car2 = "Volvo";
let car3 = "BMW";
````

However, what if you want to loop through the cars and find a specific one? And what if you had not 3 cars, but 300?

The solution is an array!

An array can hold many values under a single name, and you can access the values by referring to an index number.



## Creating arrays

Arrays consist of square brackets and items that are separated by commas.

1. Suppose we want to store a shopping list in an array. Paste the following code into the console:

   ````js
   const shopping = ["bread", "milk", "cheese", "hummus", "noodles"];
   console.log(shopping);
   ````

2. In the above example, each item is a string, but in an array we can store various data types — strings, numbers, objects, and even other arrays. We can also mix data types in a single array — we do not have to limit ourselves to storing only numbers in one array, and in another only strings. For example:

   ````js
   const sequence = [1, 1, 2, 3, 5, 8, 13];
   const random = ["tree", 795, [0, 1, 2]];
   ````

   

## Finding the length of an array

You can find out the length of an array (how many items are in it) in exactly the same way as you find out the length (in characters) of a string — by using the `length`property. Try the following:

````js
const shopping = ["bread", "milk", "cheese", "hummus", "noodles"];
console.log(shopping.length); // 5
````



## Accessing and modifying array items

Items in an array are numbered, starting from zero. This number is called the item's *index*. So the first item has index 0, the second has index 1, and so on. You can access individual items in the array using bracket notation and supplying the item's index, in the same way that you accessed the letters in a string

1. Enter the following into your console:

   ````js
   const shopping = ["bread", "milk", "cheese", "hummus", "noodles"];
   console.log(shopping[0]);
   // returns "bread"
   ````

2. You can also modify an item in an array by giving a single array item a new value. Try this:

   ````js
   const shopping = ["bread", "milk", "cheese", "hummus", "noodles"];
   shopping[0] = "tahini";
   console.log(shopping);
   // shopping will now return [ "tahini", "milk", "cheese", "hummus", "noodles" ]
   ````

   **Note:** We've said it before, but just as a reminder — JavaScript starts indexing arrays at zero!

3. Note that an array inside an array is called a multidimensional array. You can access an item inside an array that is itself inside another array by chaining two sets of square brackets together. For example, to access one of the items inside the array that is the third item inside the `random`array, we could do something like this:

   ````js
   const random = ["tree", 795, [0, 1, 2]];
   random[2][2];
   ````

4. Try making some more modifications to your array examples before moving on. Play around a bit, and see what works and what doesn't.

## Finding the index of items in an array

If you don't know the index of an item, you can use the `indexOf()`method. The `indexOf()` method takes an item as an argument and will either return the item's index or `-1` if the item is not in the array:

````js
const birds = ["Parrot", "Falcon", "Owl"];
console.log(birds.indexOf("Owl")); //  2
console.log(birds.indexOf("Rabbit")); // -1
````



## Adding items

To add one or more items to the end of an array we can use [`push()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push). Note that you need to include one or more items that you want to add to the end of your array.

````js
const cities = ["Manchester", "Liverpool"];
cities.push("Cardiff");
console.log(cities); // [ "Manchester", "Liverpool", "Cardiff" ]
cities.push("Bradford", "Brighton");
console.log(cities); // [ "Manchester", "Liverpool", "Cardiff", "Bradford", "Brighton" ]
````

The new length of the array is returned when the method call completes. If you wanted to store the new array length in a variable, you could do something like this:

````js
const cities = ["Manchester", "Liverpool"];
const newLength = cities.push("Bristol");
console.log(cities); // [ "Manchester", "Liverpool", "Bristol" ]
console.log(newLength); // 3
````

To add an item to the start of the array, use `unshift()`:

````js
const cities = ["Manchester", "Liverpool"];
cities.unshift("Edinburgh");
console.log(cities); // [ "Edinburgh", "Manchester", "Liverpool" ]
````



## Removing items

To remove the last item from the array, use `pop()`.

````js
const cities = ["Manchester", "Liverpool"];
cities.pop();
console.log(cities); // [ "Manchester" ]
````

The `pop()` method returns the item that was removed. To save that item in a new variable, you could do this:

````js
const cities = ["Manchester", "Liverpool"];
const removedCity = cities.pop();
console.log(removedCity); // "Liverpool"
````

To remove the first item from an array, use `shift()`:

````js
const cities = ["Manchester", "Liverpool"];
cities.shift();
console.log(cities); // [ "Liverpool" ]
````

If you know the index of an item, you can remove it from the array using `splice()`:

````js
const cities = ["Manchester", "Liverpool", "Edinburgh", "Carlisle"];
const index = cities.indexOf("Liverpool");
if (index !== -1) {
  cities.splice(index, 1);
}
console.log(cities); // [ "Manchester", "Edinburgh", "Carlisle" ]
````

In this call to `splice()`, the first argument says where to start removing items, and the second argument says how many items should be removed. So you can remove more than one item:

````js
const cities = ["Manchester", "Liverpool", "Edinburgh", "Carlisle"];
const index = cities.indexOf("Liverpool");
if (index !== -1) {
  cities.splice(index, 2);
}
console.log(cities); // [ "Manchester", "Carlisle" ]
````



## Access every item in an array

In JavaScript, you can access every item in an array using different methods, depending on what you want to do. 

### 1. **Using a `for` Loop**

A traditional `for` loop lets you access each item by its index:

```javascript
const array = ['apple', 'banana', 'cherry'];

for (let i = 0; i < array.length; i++) {
  console.log(array[i]);
}
```

### 2. **Using `forEach` Method**
The `forEach` method provides a more concise way to iterate over an array:

```javascript
const array = ['apple', 'banana', 'cherry'];

array.forEach(function(item) {
  console.log(item);
});

// Or using an arrow function
array.forEach(item => console.log(item));
```

### 3. **Using `for...of` Loop**
The `for...of` loop is a modern approach that iterates directly over the values:

```javascript
const array = ['apple', 'banana', 'cherry'];

for (const item of array) {
  console.log(item);
}
```

### 4. **Using `map` Method**
The `map` method is used to create a new array by applying a function to each element of the original array:

```javascript
const array = ['apple', 'banana', 'cherry'];

const newArray = array.map(function(item) {
  return item.toUpperCase();
});

console.log(newArray); // ['APPLE', 'BANANA', 'CHERRY']
```

````js
function double(number) {
  return number * 2;
}
const numbers = [5, 2, 7, 6];
const doubled = numbers.map(double);
console.log(doubled); // [ 10, 4, 14, 12 ]
````

We give a function to the `map()`, and `map()` calls the function once for each item in the array, passing in the item. It then adds the return value from each function call to a new array, and finally returns the new array.

Sometimes you'll want to create a new array containing only the items in the original array that match some test. You can do that using `filter()`. The code below takes an array of strings and returns an array containing just the strings that are greater than 8 characters long:

````js
function isLong(city) {
  return city.length > 8;
}
const cities = ["London", "Liverpool", "Totnes", "Edinburgh"];
const longer = cities.filter(isLong);
console.log(longer); // [ "Liverpool", "Edinburgh" ]
````

The `filter` method goes through each city in the `cities` array and uses the `isLong` function to decide if the city should be included in the new array. If `isLong` returns `true`, the city is included in the `longer` array.. Finally it returns the new array.

### 5. **Using `for...in` Loop**

Although less common for arrays, the `for...in` loop can be used to iterate over the indices of an array:

```javascript
const array = ['apple', 'banana', 'cherry'];

for (const index in array) {
  console.log(array[index]);
}
```

### 6. **Using `reduce` Method**
The `reduce` method is often used for accumulating or combining values from an array:

```javascript
const array = [1, 2, 3, 4];

const sum = array.reduce(function(accumulator, currentValue) {
  return accumulator + currentValue;
}, 0);

console.log(sum); // 10
```

These methods allow you to access and manipulate every item in an array effectively. The choice of method depends on your specific use case and coding style.



## Converting between strings and arrays

Often you'll be presented with some raw data contained in a big long string, and you might want to separate the useful items out into a more useful form and then do things to them, like display them in a data table. To do this, we can use the `split()`method. In its simplest form, this takes a single parameter, the character you want to separate the string at, and **returns the substrings between** the separator as items in an array.

**Note:** Okay, this is technically a string method, not an array method, but we've put it in with arrays as it goes well here.

1. Let's play with this, to see how it works. First, create a string in your console:

   ````js
   const data = "Manchester,London,Liverpool,Birmingham,Leeds,Carlisle";
   ````

2. Now let's split it at each comma:

   ````js
   const cities = data.split(",");
   ````

3. Finally, try finding the length of your new array, and retrieving some items from it:

   ````js
   cities.length;
   cities[0]; // the first item in the array
   cities[1]; // the second item in the array
   cities[cities.length - 1]; // the last item in the array
   ````

4. You can also go the opposite way using the`join()`method. Try the following:

   ````js
   const commaSeparated = cities.join(",");
   ````

5. Another way of converting an array to a string is to use the`toString()`method. `toString()`is arguably simpler than`join()` as it doesn't take a parameter, but more limiting. With`join()` you can specify different separators, whereas `toString()` 

   always uses a comma.(Try running Step 4 with a different character than a comma.)

   ````js
   const dogNames = ["Rocket", "Flash", "Bella", "Slugger"];
   dogNames.toString(); // Rocket,Flash,Bella,Slugger
   ````





# Exercise: Printing out product names and prices on an invoice

Based on what you have learned above — printing out product names and prices on an invoice, then totaling the prices and printing them at the bottom. result webpage should be like below:
![image-20240809015608310](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240809015608310.png)



**First, you need to create a HTML file, initial webpage should be look like this:**
![image-20240809015429094](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240809015429094.png)

![image-20240809020304760](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240809020304760.png)

**Then, you need to create a JavaScript file, link it to HTML file** (if you forgot how to link, refer to previous lecture note or google search 'how to link js to html'),  add code below to your JavaScript file and add/modify below each comment to print out product names and prices on the webpage :

1. Below the `// number 1` comment are a number of strings, each one containing a product name and price separated by a colon. We'd like you to turn this into an array and store it in an array called `products`.

2. Below the `// number 2` comment, start a `for...of()` loop to go through every item in the `products` array.

3. Below the `// number 3` comment, write a line of code that splits the current array item 'name:price' into two separate items, one containing just the name and one containing just the price.

4. As part of the above line of code, you'll also want to convert the price from a string to a number use Number() method.

5. There is a variable called `total` that is created and given a value of 0 at the top of the code. Inside the loop (below `// number 4`), add a line that adds the current item price to that total in each iteration of the loop

6. change the line just below `// number 5` so that the `itemText` variable is made equal to "current item name — $current item price", for example "Shoes — $23.99" in each case, so the correct information for each item is printed on the invoice. This is just simple string concatenation, which should be familiar to you.

7. below the `// number 6` comment, you'll need to add a `}` to mark the end of the `for...of()` loop.

8. At the end, add code so that the correct total is printed onto the invoice. 

9. change the text color of the whole page to red

10. screenshot the code and webpage and send it to me through Teams

````js
const list = document.querySelector('.output ul');
const totalBox = document.querySelector('.output p');
let total = 0;
list.textContent = "";
totalBox.textContent = "";
// number 1
    'Underpants:6.99'
    'Socks:5.99'
    'T-shirt:14.99'
    'Trousers:31.99'
    'Shoes:23.99';

// number 2

// number 3

// number 4

// number 5
  let itemText = 0;

  const listItem = document.createElement('li');
  listItem.textContent = itemText;
  list.appendChild(listItem);

// number 6
````













## Solution

![image-20240809020125368](C:\Users\elain\AppData\Roaming\Typora\typora-user-images\image-20240809020125368.png)





