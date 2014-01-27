
# SoBA Web Curriculum

### Lesson 4: Introduction to JavaScript


#### Overview

For this lesson you will be creating a number of web pages with embedded JavaScript. The purpose of the lesson is to introduce you to the JavaScript standard library, basic DOM manipulation and to JavaScript object literals and function callbacks.

#### Instructions

Again, make sure you fork this repository to your own account and clone it like you did for the first two assignment.

Keep up the habit of branching in git, making your changes, and then merging back into your main branch. As in Assignment 3, instead of branching from main, create a "development" branch first immediately after you clone the repository, and branch from this line when you edit the individual files.

#### Editing the files

You will be creating a number of html files from scratch. Your HTML will be minimal and will primarily support any DOM manipulations you need to make. Blank starting files have been provided. You will be editing the following:

1. input.html
2. person.html
3. callback.html
4. map.html
5. higher-order.html
6. self-executing.html

Remember to use python's SimpleHTTPServer for viewing your pages!

In order for your scripts to execute correctly, make sure you place your JavaScript at the bottom of the page. The script tag should be the last tag before the html closes.

Use Chrom's developer console to try out your JavaScript in a REPL and to2 interact with the functions you define.

#### Input.html

The point of this exercise is to introduce you to some of JavaScript’s standard library functions and basic dom manipulation. Refer to the documentation for assistance.

Create a JavaScript program that prompts a user to enter a comma separated list of grocery items. Convert their input, which will be a string, into an array of grocery items. Sort the array so that the items appear in alphabetical order. Now write the items into the web page, one paragraph for each item. Do not use a for loop. Instead use the forEach method we discussed in class.

You have a couple options for capturing user input. What are they?
#### Person.html

The purpose of this assignment is introduce object literals and functions attached to object literals.

Create an object literal that stores information about a person, such as *name*, *age*, *sex* and *weight*. Create two or three objects with these properties for different people, and set their values.

Add a function called *printInfo* to the objects that prints out this information to the console. Also add a function called *olderThan* that takes a single object as a parameter. Name the parameter *friend*. The function should first check that friend has an age property. Raise an exception if it does not. If it does, compare the values and return true if the current object is older and return false if friend is older. Return false if they are the same age.
Test your *olderThan* function with valid and invalid values. Surround it with an exception handler to catch the exception when you pass it an invalid object.

#### Callback.html

The purpose of this assignment is to introduce you to inline object literals and a design pattern that uses callback functions.

Create a function called *longOperation* that takes a **single parameter**. Call the parameter *input*. The input parameter must have two properties: *num* and *power*. The input parameter must also have a function property called *complete*. This function should take a single parameter called *result*. The longOperation function raises num to the power and then calls the complete function, passing in the result of the mathematical operation. The complete function prints the result value to the console.

Just like you can create inline functions when passing them to other functions, you can also create inline object literals when passing them to functions. When you call longOperation with an object literal, create the object literal inline. You will have to create the num, power and complete properties inline.

#### Map.html

The purpose of this assignment is expose you to anonymous functions and functional programming styles.

Using our map function, convert an array of strings containing numeric values to an array of plain numbers. For example, your function would convert the array [ “1”, “2”, “3”, “4”, “5” ] to the array [ 1, 2, 3, 4, 5 ]. Do not use a for loop, and use an inline anonymous function to do the conversion.

#### Higher-order.html

The purpose of this exercise is to expose you to higher order functions and to mess with your heads a bit.

Write a function called *root* that takes a single parameter *n*. This function **returns a function** that takes a single parameter *x* and calculates the nth root of x.

You can find the nth root of a number using the *Math.pow* function. Refer to documentation and Stack Overflow for how to do this.

For example, if you call root with n=2 and then call the returned function with x=16, the result will be 4. If you call root with n=3 and then call the returned function with x=8, the result will be 2.

You should be able to write the root function in less than five lines of code. Test it with some values.

#### Self-executing.html
The purpose of this exercise is to expose you to JavaScript's odd scoping rules, odd single-threaded asynchronous event handling, self-executing functions, and to mess with your heads some more. No, seriously. It's screwed up.
For this exercise, self-executing.html already contains JavaScript. Review the source code and make sure you understand what the intent of the code is. 

*setTimeout* is a standard library function that takes a function and a delay time in milliseconds. It waits for the delay time and then executes the function. We're using an anonymous function here.

What do you think this code will print to the console? Load the web page to run the script. What does it actually print? What the hell is going on here? Do some research and try to find out.
The solution to print the intended, *increasing* values of *i* is to use a self-executing function. In JavaScript it is possible to define and execute a function in the same code unit. You can combine the statement that defines the function and the expression that executes it to execute it when you define it. It looks like this:
	(function() {
	}());
This bizarre syntax creates an anonymous function with 
	function() { … } 
and then immediately executes it by adding the 
	() 
after it, just like calling a normal function. The trick is to surround the entire statement in parenthesis; otherwise the JavaScript interpreter thinks you are just defining a function.
Use an anonymous, self-executing function to solve our problem and print out increasing values of i. Why does this solution work the way it does?
#### Homebrew
If you're up for it, you might try installing [node.js](http://nodejs.org/). Node is server-side JavaScript that includes a REPL, so that you can actually run JavaScript from the command line. It's wild.
But don't install Node directly. Instead, use [Homebrew](http://brew.sh/). Homebrew is a package manager for OSX and is awesome. It's like apt-get for the Mac. Follow Homebrew's instructions for installation, and then install node and npm (node package manager) from the command line using homebrew.
I've used [these instructions](http://shapeshed.com/setting-up-nodejs-and-npm-on-mac-osx/) in the past, although they are a bit old now. Google around for help. You'll need to modify your path and .bashrc files to get the npm stuff working.
With node installed, you can just run `node` on the command line and it will give you a REPL.
