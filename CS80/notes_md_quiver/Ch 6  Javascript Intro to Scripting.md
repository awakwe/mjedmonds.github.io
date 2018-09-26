Welcome to Javascript!

What is javascript?

* Client side scripting language

What is scripting?

* Generally tied with interpreted languages, meaning the code is translated to machine code right before execution (vs. compiled code)

Why do we care?

* HTML and CSS give us a lot of control over content, structure, and presentation, but we still lack the ability to do computation or implement logic into our websites
* Javascript offers client-side programming, enabling fun stuff like these:
    * <https://codepen.io/HarrisCarney/pen/dPjKyK>
    * <https://codepen.io/GabbeV/pen/viAec>
    * <https://codepen.io/dissimulate/details/eZxEBO/>
* Clearly some powerful stuff!
    * We will start small and with fundamentals; there are many libraries to help you with graphics
    * We will concentrate on logic

**Getting Started**

* `<script>` HTML element allows us to add Javascript to our HTML document
    * Typically goes in the `<head>` portion of the document
    * Example: `<script type="text/javascript"> script_stuff </script>`
* See: `hello_world.html`
    * Finally we see the object model!
    * We will see more, but for now:
        * `document` is the HTML document, represented through a javascript object
            * We will cover this concept in more detail in Chapter 12 (Document Object Model)
        * `.writeln()` is a method within the `document` object
            * It writes content to the HTML document, followed by a new line (that's the `ln`)
        * `"<h1>Welcome to JavaScript Programming!</h1>"` is a **string** and is the content to write to the HTML document
* `<script src="srcipt.js">` brings in an external javascript file 

**Javascript Basics**
* **Keywords** are words with special meaning to javascript
    * `var` is an example
* A **statement** is a program statement to execute by the javascript interpreter
    * Statements are terminated with a semicolon `;`, as in `hello_world.html`
* A **variable** is a container to store data in
    * Think about this like a math variable, but in javascript, variables can store any data
    * *Declared* with `var myVar;`
        * Can declare multiple variables at once with a comma-serparated list
        * E.g. `var myVar, myVar1, myVar2;`
    * *Define* the variable with `myVar = 5;`
    * See: `hello_world_variables.html`
    * Advanced sidenote: Javascript variables do not have a type; their type is determined by the content they store
        *  What does this mean? Well, we've seen `var` be assigned to a string (`hello_world_variables.html`) and to a number (above, `myVar =5;`).
        *  So `var` represents any variable, could be a string, could be an int
        *  This contrasts with many programming languages, like C/C++, Java
        *  Moreover, a variable is not bound to a particular type. We can reassign it at any time to any type (e.g. `myVar = 5; myVar = "cheese";`)
    * Despite the fact variables can store any types, we still have to have a notion of types (take more CS courses to learn more about this!)
        * String: a string of text. E.g. `var myVar = "cheese";`
            * Can use double or single quotes, but must be consistent (whatever you start the string with, you must end the string with)
        * Number: a number. E.g. `var myVar = 5;`
        * Boolean: True/False value. E.g. `var myVar = true;`
        * Array: multiple of values in one variable. E.g. `var myVar = [5, "cheese", false];`
            * Elements are accessed using 0-indexing
            * E.g. `myVar[0]` is `5`, `myVar[2]` is `false`
        * Object: everything in javascript is an object, and you can store objects in variables. E.g. `var myVar = document;`
* **Identifiers** 
    * Formal name for a variable's name (e.g. `myVar`)
    * Can contain letters, digits, underscores,and dollar signs.
    * Must not begin with a digit and must not be a keyword
* Comments
    * Single line: start with `//`
    * Multiline: start with `/*` ends with `*/`
* **Literals** are literal values you provide your script
    * They do not change value
    * Can you spot the literal?
        * `var myVar = 5;`
        * `var myVar = "cheese";`
    * These are not modifable, fixed values provided by you, the programmer.
* **Basic Operators** define operations on variables or literals. Used to process data. We will talk about more as we go along.
    * Addition/Concatenation: `+`, used to add two numbers together, or merge two strings
        * `6 + 9;` yields `15`
        * `"Hello " + "world!"` yields `"Hello world!"`
    * Subtract, multiply, divide: `-`, `*`, `/`, used just as they in basic math (you can't divide a string by another string, concatenation is special!)
        * `6 * 5;` yields `30`
    * Assignment: `=`, we've already seen this. It's used to take a value (either an object or a literal) and assign it another object (typically a variable)
        * `var myVar = 6 * 5;` assigns `myVar` to `30`
    * Remainder: `%`, used to perform modulo.
        * Modulo/remainder division finds the remainder of an integer division
        * E.g. `11 % 5` yields `1` because `11 = 5 * 2 + 1` 
        * We are interested in the `1`, since that is the remainder when you divide `11` by `5`
* **Operator Precedence**
    * Remember PEMDAS? (Parenthsis, Exponents, Multiplication and Division, and Addition and Subtraction)
        * Defines the mathematical order-of-operations
    * Quoted from your book:

"JavaScript applies the operators in arithmetic expressions in a precise sequence determined by the following **rules of operator precedence**, which are generally the same as those followed in algebra:

1. Multiplication, division and remainder operations are applied *first*. If an expression contains several multiplication, division and remainder operations, operators are applied from *left* to *right*. Multiplication, division and remainder operations are said to have the *same level of precedence*.

2. Addition and subtraction operations are applied next. If an expression contains several addition and subtraction operations, operators are applied from *left* to *right*. Addition and subtraction operations have the *same level of precedence*.

The rules of operator precedence enable JavaScript to apply operators in the correct order. When we say that operators are applied from *left* to *right*, we’re referring to the *associativity* of the operators—the order in which operators of equal priority are evaluated."
* **Escape sequences**
    * Used to give or take away meaning from special characters
    * `\n`: a new line (carriage return, like hitting enter)
    * `\t`: a tab
    * `\\`: a literal backslash (since `\` normally has special meaning - to escape other characters!)
    * `\"`: double quote - for nested double quotes
        * Need to escape so we don't accidentally end the string! 
    * `\'`: single quote - for nested single quotes
        * Need to escape so we don't accidentally end the string! 

**Some Examples**
* `alert.html`
    * `window` object refers the browser's window
    * `alert` opens a dialog to display the string
    * Take a look at `window` methods and attributes: [http://www.w3schools.com/jsref/obj_window.asp](http://www.w3schools.com/jsref/obj_window.asp)
* `dynamic_welcome.html`
    * Again using `window` with `prompt()` method to ask for user input
    * Creates a dynamic welcome page
    * We couldn't do with this HTML and CSS
* `addition.html`
    * `parseInt()` function converts a string to an integer
    
**Equality and Relational Operators**
* We need a way to encode logic - a way to direct the program based on the program's state
* Primary method of controlling a programs flow
* Basic idea: "if a condition is true, execute some code"
    * We can stop at the if or say "if a condition is true, execute some code, otherwise, execute this other code"
    * Example:

```js
if(5 <= 10){
  document.writeln("5 is indeed less than 10");
} else {
  document.writeln("5 is somehow not less than 10...");
}
```

* But we can do even more by nesting if's!
    * Also allows us to check for multiple potential conditions at once (e.g. `if(cond)...else if(cond)...else...`
* Example: where `time` is the hour of the day (0-23)

```js
if (time < 10) {
    greeting = "Good morning";
} else if (time < 20) {
    greeting = "Good day";
} else {
    greeting = "Good evening";
}
```

![Screenshot 2016-10-04 17.57.34.png](resources/29B279A0390F7CF5AE8E335B5BC4C0E0.png)
* The difference between `===` and `==`
    * `===` is a more strict comparison operator
    * E.g. `"75" == 75` yields true but `"75" === 75` yields false

* Compound conditionals:
    * Uses a couple of logical operations `AND`, `OR`, and `NOT`
    * `AND` is represented with `&&`
    * `OR` is represented with `||`
    * `NOT` is represented with `!`
    * Combining conditions allows us to use much more powerful program flow
    * Compound conditionals will evaluate left to right
        * If the program can determine the overall value of the compound conditional, it will stop evaluting the rest of the conditional
            * E.g. Suppose `cond_a` is `true` and `cond_b` is `false`. `if(cond_a || cond_b)` doens't need to look at the value of `cond_b`, the overall condition is determined by `cond_a`. Similarlly, `if(cond_b && cond_a)` doesn't need to look at the value of `cond_a`, since `cond_b` already determined the overall state of the compound conditional. Remeber: left to right!
        * **Key takeaway** order matters!

```js
if(cond_a && cond_b){
  // only executes if cond_a AND cond_b are true
} else if(cond_a || cond_d){
  // only executes if 1) cond_a is true AND cond_b is false (think about why) OR cond_d is true
} else if(!cond_d){
  // only executes if cond_a is false AND cond_d is true
  // will this ever execute?
} else {
  // otherwise
}
```

**So let's write some javascript**

* Determine if the inputted year is a leap year
    * Definition of a leap year:
        * Every year that is divisbly by 4, except for years divisble by 100, except for years that are divisible by 400
    * Let's come up with an algorithm to check:
* Display the current day and time in the following format:
```
Today is: Friday
Current time is: 4:50:22PM
```
    * To start, look at the `Date()` javascript  
        * http://www.w3schools.com/jsref/jsref_obj_date.asp

**Using The Developer Tools**
* No program is perfect at first
* We need a way to examine program state as the program is running
    * This will enable us to understand and fix problems in our code
* Debugging will help fix any error, but it's particularly good for identifying edge cases you may have not considered when writing your program
    * Common edge cases: empty string `""`, zero `0`, negative numbers, etc
* The debugger is present in any modern browser and has two main elements for javascript: console and debugger
* **Since we are editing the program as it executes, we need to remember where we are in execution**
    * Variables may not exist yet
* How to write information to the console to inspect state:
    * Use a `console.log()` statement in your javascript
    * The value/text arguments will be printed to the Console section of the Developer Tools
* Setting a breakpoint
    * Breakpoints say "when you hit this line of code, pause the program for me"
    * They allow you to inspect variable/program state during execution
    * Enable a breakpoint by clicking the line number
    * Important semantic note: The line of the breakpoint has **not** executed yet. It is about to execute
        * E.g. if we set a breakpoint on line 9, line 9 hasn't executed when the breakpoint triggers (line 8 has, however)
        * Keep this in mind!
* Stepping through a program
    * Once we are at a breakpoint we have multiple options to control the program:
        * Step Over: step over the current line of code. This means if we are at a method call, **do not** move the debugger into the method. Instead, the method will execute, and the program will pause after method completes
        * Step Into: If the program is about to call a method, move the debugger into that method and pause execution
        * Step Out: Finish the current function call and pause execution at the calling function
        * Continue: Continue the program's execution; basically unpauses the program
* We can also call functions or inspect variables while paused using the console
    * Move to the console, and type a javascript statement to execute
        * Can also just type variable names to get their value
    * If the javascript statement we called doesn't have a return value (e.g. statement doesn't yeild a value), then the console will report `undefined`. 

**Javascript functions/methods**
* Functions enable reuseable code
* Basic declaration:

```js
function sum1(a, b){
  // do other amazing javascript things here
  return a + b;
}
```

* We can then call `sum(10, 5)` which would return `15`
* Assigning functions to variables

```js
var sum2 = function(a,b){
  return a + b;
}
```

* Hoisting
    * The only thing you need to remember is that functions of the form of `sum1` are "hoisted" to the top of your program, meaning they can be used *before* they are declared

 

