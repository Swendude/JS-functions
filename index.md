# Functions in Javascript

In this tutorial you will learn about functions in javascript. Professional developers use functions all the time. They are a fundamental concept of coding in javascript (and most other languages). Take your time going trough this content to really get a firm graps on this concept, it will pay off.

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


## How to read a recipe
<a name="recipe"/>
We can think about programming as 'giving instructions', the special thing about programming is that our target for these instructions is a (dumb) machine. 
A different case of 'giving instructions' is found by looking at cooking recipes. 

In recipes the target is an (intelligent) human. Although a human and a machine require very different instructions there are some similarities between instructions aimed at them.


Let us take a look at a simple recipe for making a fruit smoothie:
```
Step 1: Peel 2 bananas and mash them
Step 2: Peel 3 oranges, squeeze out the juice
Step 3: Clean and slice 10 strawberries
Step 4: Blend the banana mash, orange juice and\
  the sliced strawberries together until smooth

Enjoy!
```

As we can see this recipe is very short and free-form, it is something that a human (probably) will understand. 
The way it is written it assumes some things, such as assuming its reader knows how to peel, clean and blend different kinds of fruits. To most humans this will be obvious and maybe even trivial.

A child trying out this recipe might have trouble following the steps since it is missing this knowledge, for this child we can make the recipe more verbose like this:

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

Enjoy!
```
As we can see, our recipe got a lot longer by 'expanding' the instructions for slicing and other operations. It would be very impractical to write all reciped this way, cookbooks would be way longer and recipes would contain a lot of repetitive steps. There are [8 different approaches to peeling a banana on wikiHow](https://www.wikihow.com/Peel-a-Banana) so the details may vary between cooks.

So we might think of the verbs we encounter in the original recipes like 'sub-instructions' that are defined somewhere else. This is exactly what functions are as we will see later. Notice how most verbs 'act on' *something* and then produce a _result_ like the verb 'Peel' can 'act on' *banana* and then produce a _Peeled banana_. 

Maybe you know how to juggle, you juggle something (knives, flaming torches or chainsaws) to produce a loud applause. Most verbs can be described using this pattern so let's come up with some names for the various parts that make up a 'sub-instruction' (which we will now call functions):

- A Function has a *name* (or identifier). E.g. 'Peel' and 'Juggle'
- A Functions may 'act on' some (or multiple) thing, we call this the *arguments*. E.g. 'Banana' or 'Knives'.
  - _Some function do not 'act on' anything but just produce results. E.g 'Smiling'_
- A Function produces a *result*, this may be an effect like 'knives being thrown in a pattern' or it may be a thing like 'Peeled banana' 

I hope this made sense, even tough it's a bit artifical this analogy work pretty well to get a feel for functions without thinking about code yet. We will get to code soon enough but before continueing spent some time on the following exercises:

_Ex 1. Write down 10 examples of functions you encounter in real life, giver their *name, arguments (if any) and result*_

<a name="anatomy"/>
## Anatomy of a function

<a name="using"/>
## Using functions

<a name="benefits"/>
## Benefits of functions

<a name="passing"/>
## Higher order functions, passing functions around 
