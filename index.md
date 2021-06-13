# Functions in Javascript

In this tutorial you will learn about functions in javascript. Professional developers use functions all the time. They are a fundamental concept of coding in javascript (and most other languages). Take your time going trough this content to really get a firm grasp on this concept, it will pay off.

### Structure of this tutorial
We will start by discussing a real life analogy of functions in order to illustrate what we want to accomplish. Next, we dive into what a function looks like and how you can use it in your code. In the third part we will look at the benefits of using functions. The final part goes into advanced usage of functions, consider this material a sneak peek of how modern javascript uses functions.

> _**This tutorial assumes you are familiar with the following concepts. If you feel unsure about any of these take some time to review the before continuing this tutorial.**_
> 
> - _How to define and use variables_
> - _Built-in datatypes (Bools, numbers, strings, objects)_
> - _Boolean conditions, if-else statements_

## Table of Contents  
[How to read a recipe](#recipe)  

[Anatomy of a function](#anatomy)

[Benefits of functions](#benefits)

[Higher order functions, passing functions around](#passing)


<a name="recipe"/>

## How to read a recipe
We can think about programming as 'giving instructions', where our target for these instructions is a (dumb) machine. 
A similar case of 'giving instructions' can be in cooking recipes. 

In recipes the target is an (intelligent) human. Although a human and a machine require very different instructions there are some similarities between instructions aimed at them.


Let us take a look at a simple recipe for making a fruit smoothie
```
Step 1: Peel 2 bananas and mash them
Step 2: Peel 3 oranges, squeeze out the juice
Step 3: Clean and slice 10 strawberries
Step 4: Blend the banana mash, orange juice and\
  the sliced strawberries together until smooth
```

As we can see this recipe is very consice, it is something that a human will (probably) understand. 
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

Think of the verbs we encountered in the original recipes. They are like 'sub-instructions' that are defined somewhere else (like a different cookbook or inside your mind). This is exactly what functions are in programming. 
Take a look at the verbs and notice how most of them 'act on' **something** and then produce a **_result_**. 
The verb 'Peel' can 'act on' **banana** and then produce a **_peeled banana_**. 
Maybe you know how to juggle, you juggle something (knives, flaming torches or chainsaws) to produce a loud applause.

Most verbs can be described using this pattern so let's come up with some names for the various parts that make up a 'sub-instruction' (which we will now call functions):

- A Function has a *name* (or identifier). E.g. 'Peel' and 'Juggle.'
- A Function may 'act on' some (or multiple) things, we call this the *arguments*. E.g. 'Banana' or 'Knives'. _Some function do not 'act on' anything but just produce results (e.g 'Smiling')._
- A Function produces a *result*, this may be an effect like 'knives being thrown in a pattern' or it may be a thing like 'Peeled banana'. 

It's as simple as that! We will get to code soon enough but before you continue spent some time on the following exercises:

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
- This whole code block called a **function definition**, and that's exactly what it does. Javascript will not execute these lines of code when it encounters a definition, it just says 'These are the steps for **increase**, I should remember them'

- The definition uses the ```function``` keyword, it lets javascript know that a function is being defined here

- After the ```function``` keyword the function **name** is defined. In this case we call the function **increase**

- Directly following the function name, we specify the **arguments** between parentheses. We can choose a name for every argument we want to use, that name becomes a variable that we can provide when we use the function (we will see how we do this later). Our **increase** function takes a single argument that we named ```num```. A function with no arguments look like ```function increase() {``` and a function with multiple arguments looks like ```function increase(num1, second_num, numberthree)```. Note that we can freely choose argument names just like we can with variables.

- The steps needed to execute this function are defined within the curly brackets following the name and arguments. We call the steps between curly brackets the **function body**. In our **increase** function we only have two steps, but a function body can contain as many lines of javascript as you need. Inside these lines the arguments become available to use as variables.

- The keyword ```return``` is used to return a value to the place where we use the function. You don't have to use a return (for functions that do not want to return anything) but when javascript encounters a return, it halts execution and returns the specified result. ```return``` Is only available inside function bodies.

- The combination of a function's name, arguments and return type is called the **function signature** (```increase(number) returns number``` in this case). This is all the information we need to call the function later.

_Ex 2. Write a function named **decrease** that take a single number as an argument and returns that number - 1_

_Ex 3. Write a function that writes 'Hello world' to your console_

_Ex 4. Write a function that takes a single string as an argument and writes 'Hello + argument' to your console_

_Ex 5. How do the functions from ex. 3 & ex. 4 differ from **increase** and **decrease**?

### Using functions

Now we know how to define a function, we need to know how to use it. Instead of saying that we 'use' a function we should get used to the idea of 'calling' a function. 

After defining our function **increase** we are going to call it with an argument of 6 (essentialy asking 'increase 6':
```javascript
function increase(num) {
  const increased = num + 1;
  return increased;
}

increase(6);
```

Notice how the last line 'fits' onto the function definition ```increase(num)```. Altough the function is being called we are not doing anything with the result of this function, let's change our code to store the result in a variable and logging that to our console:

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
Let's switch it up a little and look at a function with multiple arguments, our function name will be ```biggestSquare``` it has two arguments named ```x``` and ```y``` and will log the largest argument squared. 

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

Notice that this function does not contain a return statement, it just logs something to the console. Often this is not very usefull for us as we can not 'reach' the result of the function. When we log the result we see that it return a `undefined` since nothing has been returned. Let's change our function to use ```return```

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
```
we can say that ```life```, ```greeting``` and ```sayHi``` are **in scope** (known to javascript). If something is not in scope and you use it, you will get an error.

Functions have their own scope, and anything defined in a functions body will only be available to the function code. We call the default scope that javascript uses the **global scope** and function can access that. It might help to thing that 'scope flows down, not up'. Here is an example:


```javascript
const life = 42;
const greeting = 'Hello world';

function talk() {
  // this function can acces the global scope
  console.log(greeting);
  console.log('The Answer to the Ultimate Question of Life, the Universe, and Everything is ' + life);
  
  // This is defined in function scope
  const inTalk = 'a string';
  console.log(inTalk);
}

talk();
console.log(inTalk); // You'll get an ReferenceError
```

Keep this in mind while working with functions! Altough you can access the global scope from within a function **it is good practice to avoid doing so, always prefer arguments when passing information to functions**.

That was most of the information you need to know about functions. The real way to learn is to start writing and using your own.

_Ex 6. Write a function named ```isReversed``` that takes a two strings as an argument and returns ```true``` if the strings are the reverse of each other, otherwise return ```false```_
_Ex 7. Write a function ```isPalindrome``` that takes a single string and returns ```true``` if the string is a palindrome, otherwise return ```false``` (A palindrome is word that stays the same when you reverse it. E.g. 'racecar', 'bob' and 'Never odd or even')_
_Ex 8. If you didn't already, write ```isPalidrome``` using ```isReversed``` inside the function body_
_Ex 9. Name this function:_
```javascript
 function {TODO}(length, size) {
   if length < size {
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

For this part we are going to simulate a day in the life of a professional javascript developer. We work for a hip new unicorn startup called Fruits.com, they sell fruit online and business is booming. The fruit storage of the company is managed by an automated system which we have to maintain. It allows use to add fruits to stock and remove stock once we sell some fruits. Our boss aproaches us and says that he wants to improve our system, there have been some complaints from the people over at Sales about stock numbers going negative. Of course you can (or should) not have minus one banana in stock so this problem needs solving.

We start looking into the problem by pulling up the relevant code in the system.
```javascript
// Increase stock
cont change = getInput();
const stock = getStockFromDatabase();
stock = stock + change;
saveStockToDatabase(stock);

[Thousands of lines of code]

// Decrease stock
cont change = getInput();
const stock = getStockFromDatabase();
stock = stock - change;
saveStockToDatabase(stock);
```
Don't worry about the functions ```getStockFromDatabase``` and ```SaveStockToDatabase```. They are provided by our database team and we can assume they do what they are supposed to. The ```getInput()``` function is hooked up to a panel over at Sales that will give us the amount to decrease or increase the stock.

<a name="passing"/>
## Higher order functions, passing functions around 
