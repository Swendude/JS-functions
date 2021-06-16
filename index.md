# Functions in Javascript

In this tutorial you will learn about functions in javascript. Professional developers use functions all the time. They are a fundamental concept of coding in javascript (and most other languages). Take your time going through this content to really get a firm grasp on this concept, it will pay off.

### Structure of this tutorial
We will start by discussing a real life analogy of functions in order to illustrate what we want to accomplish. Next, we dive into what a function looks like and how you can use it in your code. In the third part we will look at the benefits of using functions. We can not teach you modern javascript without teaching you about arrow functions in the next chapter. We close of with some more material for you to study if you want to learn more on your own. 

> _**This tutorial assumes you are familiar with the following concepts. If you feel unsure about any of these take some time to review them before continuing this tutorial.**_
> 
> - _How to define and use variables_
> - _Built-in datatypes (Bools, numbers, strings, objects, ..)_
> - _Boolean conditions, if-else statements_

## Table of Contents  
[How to read a recipe](#recipe)  

[Anatomy of a function](#anatomy)

[Benefits of functions](#benefits)

[Function expressions](#expressions)

[Deep dive](#dive)


<a name="recipe"/>

## How to read a recipe
We can think about programming as 'giving instructions', where our target for these instructions is a (dumb) machine. 
A similar case of 'giving instructions' can be found in cooking recipes. 

In recipes the target is an (intelligent) human. Although a human and a machine require very different instructions there are some similarities between instructions aimed at them.


Let us take a look at a simple recipe for making a fruit smoothie

```
Step 1: Peel 2 bananas and mash them
Step 2: Peel 3 oranges, squeeze out the juice
Step 3: Clean and slice 10 strawberries
Step 4: Blend the banana mash, orange juice and\
  the sliced strawberries together until smooth
```

As we can see this recipe is very concise, it is something that a human will (probably) understand. 
The way it is written assumes the reader knows how to peel, clean and blend different kinds of fruits. To most humans this will be obvious and maybe even trivial but a child trying out this recipe might have trouble following the steps. For this child we can make the recipe more verbose like this:

```
Step 1.a: Take 2 bananas
Step 1.b: Remove the peel of the bananas\
  by snapping off the stem and pulling downwards
Step 1.c: Put the peeled bananas in a bowl\
  and using a fork to push them down until they become somewhat liquid
Step 2.a: Take 3 oranges
Step 2.b: Using a knife remove the skin of\ 
  the orange without cutting into the flesh
Step 2.c: cut the peeled oranges in half and\
  use a juicer to collect the juice
Step 3.a: Take 10 strawberries
Step 3.b: Using a knife cut of the top just below the stem
Step 3.c: Cut the cleaned strawberries into 4 parts
Step 4.a: Take the banana mash, orange juice and sliced strawberries
Step 4.b: Put everything into a blender and let it run until smooth
```

As we can see, our recipe got a lot longer by 'expanding' the sub-instructions into the recipe. It would be very impractical to write recipes this way, cookbooks would have to be way longer and recipes would contain a lot of repetitive steps. Another disadvantage of this method is that every cook has their own preferred method for 'slicing' and 'peeling', as seen by the [8 different approaches to peeling a banana on wikiHow](https://www.wikihow.com/Peel-a-Banana). Techniques might change over time (somebody invents a Banana-peeler 2000), rendering books obsolete or outdated. 

### Verbs as functions

You can think of the verbs we encountered in the original recipes as 'sub-instructions' that are defined somewhere else (like a different cookbook or inside your mind). This is exactly what functions are in programming. 

Take a look at the verbs and notice how most of them 'act on' **something** and then produce a **_result_**. 
The verb 'Peel' can 'act on' **banana** and then produce a **_peeled banana_**. 
Maybe you know how to juggle, you juggle something (knives, flaming torches or chainsaws) to produce a loud applause.

Most verbs can be described using this pattern so let's come up with some names for the various parts that make up a 'sub-instruction' (which we will now call functions):

- A Function has a *name* (or identifier). E.g. 'Peel' and 'Juggle.'
- A Function may 'act on' some (or multiple) things, we call this the *arguments*. E.g. 'Banana' or 'Knives'. _Some functions do not 'act on' anything but just produce results (e.g 'Smiling')._
- A Function produces a *result*, this may be an effect like 'knives being thrown in a pattern' or it may be a thing like 'Peeled banana'. 

It's as simple as that! We will get to code soon enough but before you continue spend some time on the following exercise:

_Ex 1. Write down 10 examples of functions you encounter in real life, **give their name, arguments (if any) and result**_


<a name="anatomy"/>

## Anatomy of a function
Now that we have looked at recipes we will switch to javascript. Instead of peeling bananas (quite hard to do in javascript) we will look at the simple case of increasing a given number by one. Before we go to the code let's determine the parts of the function we need:

- Our function needs a name, 'increase' seems to be a good choice
- It does have an argument, the number we want to increase
- For the result of the function we will want to produce the number we got as an argument but increased by one

> This case is simple, but writing stuff like this down will help you with complex functions later.

### Defining functions

With this 'definition' of our new function **increase** we could write an instruction like 'Increase 7'. We expect the result to be 8.
Let's look at what **increase** looks like in javascript.

```javascript
function increase(num) {
  const increased = num + 1;
  return increased;
}
```

Some terminology and remarks:
- This whole code block is called a **function definition**, and that's exactly what it does. Javascript will not execute these lines of code when it encounters a definition, it just says 'These are the steps for **increase**, I should remember them'

- The definition uses the ```function``` keyword, it lets javascript know that a function is being defined here

- After the ```function``` keyword the function **name** is defined. In this case we call the function **increase**

- Directly following the function name, we specify the **arguments** between parentheses. We can choose a name for every argument we want to use, that name becomes a variable that we can provide when we use the function (we will see how we do this later). Our **increase** function takes a single argument that we named ```num```. A function with no arguments looks like ```function increase() {``` and a function with multiple arguments looks like ```function increase(num1, second_num, numberthree)```. Note that we can freely choose argument names just like we can with variables.

- The steps needed to execute this function are defined within the curly brackets following the name and arguments. We call the steps between curly brackets the **function body**. In our **increase** function we only have two steps, but a function body can contain as many lines of javascript as you need. Inside these lines the arguments become available to use as variables.

- The keyword ```return``` is used to define the result of the function. When we use this function somewhere else in our code, we will retrieve the value specified by ```return```. You don't have to use a return (for functions that do not want to return anything) but when javascript encounters a return, it halts execution and returns the specified result. ```return``` Is only available inside function bodies.

- The combination of a function's name, arguments and return type is called the **function signature** (```increase(number) returns number``` in this case). This is all the information we need to use the function later.

_Ex 2. Write a function named **decrease** that take a single number as an argument and returns that number - 1_

_Ex 3. Write a function that writes 'Hello world' to your console_

_Ex 4. Write a function that takes a single string as an argument and writes 'Hello + argument' to your console_

_Ex 5. How do the functions from ex. 3 & ex. 4 differ from **increase** and **decrease**?_

### Using functions

Now we know how to define a function, we need to know how to use it. Instead of saying that we 'use' a function we should get used to the idea of 'calling' a function. 

After defining our function **increase** we are going to call it with an argument of 6 (essentially asking 'increase 6':

```javascript
function increase(num) {
  const increased = num + 1;
  return increased;
}

increase(6);
```

Notice how the last line 'fits' onto the function definition ```increase(num)```. Although the function is being called we are not doing anything with the result of this function, let's change our code to store the result in a variable and logging that to our console:

```javascript
function increase(num) {
  const increased = num + 1;
  return increased;
}

const should_be_seven = increase(6);
console.log(should_be_seven); // logs 7

// We don't have to use 6 as input
const should_be_nine = increase(8);

// We can even pass variables as arguments
const should_be_eight = increase(should_be_seven);

console.log(should_be_eight); // logs 8
console.log(should_be_nine); // logs 9
```

### Beyond increase
Let's switch it up a little and look at a function with multiple arguments, our function name will be ```biggestSquare``` it has two arguments named ```x``` and ```y``` and it will log the largest argument squared. 

```javascript
function biggestSquare(x, y) {
  if (x > y) {
    console.log(x * x);
  }
  else {
    console.log(y * y);
  }
}

const squared = biggestSquare(3, 9) // should log 81 (the square of 9)
console.log(squared); // logs 'undefined'
```

Notice that this function does not contain a return statement, it just logs something to the console. Often this is not very useful for us as we can not 'reach' the result of the function. When we log the result we see that it returns `undefined` since nothing has been returned by the function. Let's change our function to use 
a```return``` statement:

```javascript
function biggestSquare(x, y) {
  if (x > y) {
   return x * x;
  }
  else {
    return y * y;
  }
}

const squared = biggestSquare(3, 9) 
console.log(squared); // logs 81
```

Now we can use our result in the rest of our code.

### Function scope

One important thing to keep in mind is **function scope**. Think of the **scope** as a list of definitions that javascript knows. These definitions can be variables, functions and some other things. They can be defined by you or come 'built-in' to javascript. So in the next piece of code:

```javascript
const life = 42;
const greeting = 'Hello world';

function sayHi() {
  console.log('Hi!');
}


// This all works, we defined them so javascript has them in scope
console.log(life);
console.log(greeting);
sayHi();

// This won't work because `something` has not been defined anywhere
console.log(something);
```

we can say that ```life```, ```greeting``` and ```sayHi``` are **in scope** (known to javascript). If something is not in scope and you use it (see ```something``` above), you will get an error.

Functions have their own scope, and anything defined in a functions body will only be available to the function code. We call the default scope that javascript uses the **global scope** and function can access that. It might help to think that 'scope flows down into functions, but not up to global'. Here is an example:

```javascript
const life = 42;
const greeting = 'Hello world';

function talk() {
  // this function can access the global scope
  console.log(greeting);
  console.log('The Answer to the Ultimate Question of Life\
    , the Universe, and Everything is ' + life);
  
  // This is defined in function scope
  const inTalk = 'a string';
  console.log(inTalk);
}

talk();
console.log(inTalk); // You'll get an ReferenceError
```

Keep this in mind while working with functions! Although you can access the global scope from within a function **it is good practice to avoid doing so, always prefer arguments when passing information to functions**.

That was most of the information you need to know about functions. The real way to learn is to start writing and using your own.

_Ex 6. Write a function named ```isReversed``` that takes a two strings as an argument and returns ```true``` if the strings are the reverse of each other, otherwise return ```false```_

_Ex 7. Write a function ```isPalindrome``` that takes a single string and returns ```true``` if the string is a palindrome, otherwise return ```false``` (A palindrome is a word that stays the same when you reverse it. E.g. 'racecar', 'bob' and 'Never odd or even')_

_Ex 8. If you didn't already, write ```isPalindrome``` using ```isReversed``` inside the function body_

_Ex 9. Name this function:_

```javascript
 function {TODO}(width, height) {
   if width < height {
     return true;
   }
   else {
     return false;
   }
 }
```

Next we will take a look at why you would want to use functions and how to maximize the benefit you get from them.

<a name="benefits"/>

## Benefits of functions

For this part of this tutorial we are going to simulate a day in the life of a professional javascript developer. We work for a new unicorn startup called _fruits.com_, they sell fruit online and business is booming. Currently _fruits.com_ only sells apples (it's a startup).

The storage of the company is managed by an automated system which we have to maintain. It handles increases and decreases of the amount of apples in the storage (the stock). So when _fruits.com_ sells some apples, or a delivery of apples comes in, the system can be updated to reflect the new stock.

Our boss approaches us and says he wants to improve the system, there have been complaints about the stock number going negative. Of course the system should not allow to have minus one apples in stock. Also, the available storage should not exceed 100 apples, as there is no space for that and the apples would spoil outside of storage. 

We start looking into the problem by pulling up the relevant code in the system.

```javascript
// Increase stock on delivery
const input = getDeliveryAmount();
let stock = getStockFromDatabase();
stock = stock + input;
saveStockToDatabase(stock);

// [Thousands of lines of code]

// Decrease stock on sale
const input = getSaleAmount();
let stock = getStockFromDatabase();
stock = stock - input;
saveStockToDatabase(stock);
```

These pieces of code are executed when apples are sold or delivered over at _fruits.com_.

Don't worry about the functions ```getStockFromDatabase() returns number``` and ```SaveStockToDatabase(number) returns nothing```. They are provided by our database team and we can assume they do what they are supposed to (return the current stock as a number from the database and write a new number to the database respectively). 

The same goes for the function ```getDeliveryAmount() returns number``` and ```getSaleAmount() returns number```, they give us the amount of apples sold or delivered. 

We implement the checks to make our boss happy:

```javascript
// Increase stock on delivery
const input = getDeliveryAmount();
let stock = getStockFromDatabase();
stock = stock + input;
// Check if the stock is valid
if (stock > 0 && stock <= 100) {
  saveStockToDatabase(stock);
}
else {
  console.log('stock not updated, result was invalid');
};

// [Thousands of lines of code]

// Decrease stock on sale
const input = getSaleAmount();
let stock = getStockFromDatabase();
stock = stock - input;
if (stock > 0 && stock <= 100) {
  saveStockToDatabase(stock);
}
else {
  console.log('stock not updated, result was invalid');
};
```

Now we guarantee that our stock stays within reasonable limits. If the stock goes beyond these limits the system logs an error message to the user and it does not update the database.

As you might have noticed, there is a lot of duplicate code here. Duplication of code is considered a bad thing, which is stated as the **DRY** principle (Don't Repeat Yourself). The code we have here is very **WET** (Write Everything Twice), which is bad. 

_Ex 10. Why do you think code duplication is a bad thing?_

Two months later and _fruits.com_ has attracted serious funding. There is enough money to increase storage capacity which is now limited to 300 apples instead of only 100.
Our boss tells us to update the software to reflect this.

We dive back into the code, spend half an hour to search for all the places where we update the stock and modify the code. It's a quick fix:

```javascript
// Increase stock on delivery
const input = getDeliveryAmount();
let stock = getStockFromDatabase();
stock = stock + input;
// Check if the stock is valid
if (stock > 300 && stock <= 100) {
  saveStockToDatabase(stock);
}
else {
  console.log('stock not updated, result was invalid');
};

// [Thousands of lines of code]

// Decrease stock on sale
const input = getSaleAmount();
let stock = getStockFromDatabase();
stock = stock - input;
if (stock > 0 && stock <= 300) {
  saveStockToDatabase(stock);
}
else {
  console.log('stock not updated, result was invalid');
};
```

Yesterday was a rough night, and we made a pretty big mistake here (as all humans do sometimes). An angry boss shows up, complaining that deliveries are not being updated to the system.

As you can see in this (silly) example, maintaining code is hard and error prone. We shouldn't make it any harder than it needs to be, we should change this code into a function.

```javascript
function saveValidStock(newStock) {
  // Check if the stock is valid
  if (newStock > 0 && newStock <= 300) {
    saveStockToDatabase(stock);
  }
  else {
    console.log('stock not updated, result was invalid');
  }
}

// Increase stock on delivery
const input = getDeliveryAmount();
saveValidStock(input);

// [Thousands of lines of code]

// Decrease stock on sale
const input = getSaleAmount();
saveValidStock(input);
```

Our code is nice and DRY now. The **shared logic now** has a single place where we can modify it. Also notice how our two pieces of codes are much easier to understand, the use of functions can make code 'self-documenting'. You do not need to know the definition of ```saveValidStock(number) returns nothing``` to understand what this code is doing. The total lines of codes we need to maintain has also been reduced, which is nice because code with fewer lines tends to have less errors.

> Rewriting code in order to make it more readable, maintainable or performant is called `refactoring`. 

The 'DRY-ness' and readability of functions allow developers to better maintain and understand code. These are some of the benefits of using functions in your code. Always think twice before you copy-paste your own code, it might be time to use a function.

_Ex 11. Go through some of the code you wrote in the past, can you spot any opportunity to make it more DRY? Did it improve the readability of your code?_

<a name="expressions"/>

## Arrow functions

The last thing we have to discuss is **arrow functions**. Arrow functions are used to declare functions in a shorter way without defining it. As an example we will define a function ``triple(number) returns number`` that triples its argument using a 'normal' function declaration as we have seen before: 

```javascript
function triple(num) {
  return num * 3;
}

console.log(triple(3)); // returns 9
```

Let's define it as an arrow function: 

```javascript
var triple = (num) => {
    return num * 3;
  };
  
console.log(triple(4)); // returns 12
```

What did we do?

- The  ```function``` keyword and the function name are gone
- The arguments are followed by the arrow (```=>```) which is followed by the function body 
- We stored this function in a variable called ```triple```. The function itself has no name, we only have variable pointing to the function that we chose to call ```triple```

An arrow function can be written shorter ..

  - .. if it has a single argument, then you can omit the parentheses. If you have no arguments you do need to add empty parentheses:
      
      ```javascript
      var triple = num => {
        return num * 3;
      };
      
      // no arguments to this arrow function
      var sayHi = () => {
        console.log('hi');
      };
      
      // multiple arguments always use parentheses
      var add = (x, y) => {
        return x + y;
      };
      ```
  
  - .. if its function body contains only a single statement you can omit the curly brackets on the function body:
      
      ```javascript
      var sayHi = () => console.log('hi');
      ```
  
  - .. if its function body contains only a single statement **that is a return statement** you **MUST** omit ```return```:
      
      ```javascript
      var triple = num => num * 3;
      ```
 
Arrow functions have some limitations that you will see later, but they are a great tool if you want to quickly define a function without giving it a name.
This is handy when you want to use a **higher order function**. Higher order functions are functions that take other functions as their arguments.
 
An useful example of a higher order function is the ```Array.map()``` function (it is a function that belongs to an array, you'll learn more about this later). It takes a function as an argument and applies that to every element of the array and then returns the new array. The argument to map should be a function that takes a single element from the array as an argument and returns a new element. Let's use our ```triple``` function from before: 
 
```javascript
function triple(num) {
  return num * 3;
}

var numbers = [1, 5, 7, 13];
console.log(numbers.map( triple )); // This logs [3, 15, 21, 39]
```

Notice how we just give the function name as an argument without arguments. If we added arguments to ```triple``` we would give ```map``` the result as an argument instead of the function.

We can do write this code much shorter when we use an arrow function here:

```javascript
var numbers = [1, 5, 7, 13];
console.log(numbers.map( (num) => num * 3 )); // This logs [3, 15, 21, 39]
```

As you can see this code is shorter and we don't have to define ```triple``` somewhere else to use it's logic here. It might seem more difficult to read right now, but that will get much better when you spend more time on writing your own arrow functions. Arrow functions are very common in modern javascript, so let's quickly start writing some.

_Ex 12. Convert all the functions in this tutorial into arrow functions, make them as short as possible_

<a name="dive"/>

## Closing & Deep dive

That concludes this introduction to functions. A great place to find more information on functions are the MDN web docs (from Mozilla, the company that maintains firefox). Their [guide on functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) is a well written document that covers all there is to functions. It's a good idea to get good at reading documentation like this, it will be a helpful skill if you ever need to learn a novel topic. 

If your hunger for functions has not been satiated, here are some topic that are useful to look into:

- The function ```Array.reduce()``` is a very useful higher order function - [MDN link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
- Generators are special function that can be used to 'pause' computations until you need a new value - [MDN link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator)
- Recursive functions are crazy functions that call themselves. They can be used to calculate infinite lists and draw trees - [Wikipedia](https://en.wikipedia.org/wiki/Recursion_(computer_science))

Thanks so much for reading!
