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

[Using functions](#using)

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
This is called a **function definition**, and that's exactly what it does. The definition uses the ```function``` keyword followed by the function name 'increase' that has a single argument named 'num' defined in the parenthesis. The steps needed to execute this function are defined within the curly brackets following the name and arguments. We call the steps between curly brackets the **function body**. The combination of a function's name and arguments is called the **function signature** (```increase(num)``` in this case). The keyword ```return``` will always be the last step in a function's execution and specifies the result of this function.

```javascript
// function definition
function increase(num) { // name and arguments
  // function body
  const increased = num + 1;
  return (increased); // return statement, function body code below this will not be executed
}
```
Now we know how to define a function but what does it all mean? It might be helpfull to see how we would use this function in our code. Let's say we need to increase the number 5 in our code, we would write
```javascript
increase(5);
```
When we use a function like this we talk about 'calling' the function. We have to provide it a value for ```num``` which then becomes available for the function to work this. You can see clearly how this works by replacing the value directly in the function definition.

```javascript
function increase(5) { 
  const increased = 5 + 1;
  return (increased); // return statement, function body code below this will not be executed
}
```


<a name="using"/>
## Using functions

<a name="benefits"/>
## Benefits of functions

<a name="passing"/>
## Higher order functions, passing functions around 
