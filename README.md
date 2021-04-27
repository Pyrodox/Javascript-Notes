# Javascript Notes

## Introduction
* The developer console is a tool that logs information about the backend parts of the program (can be errors, console.log() statements, etc). (accessed by using ctrl + shift + i)
* `console.log()` logs things put in IN the console, so `console.log("Hello world")` would put Hello world in the console.
* `console.log()` evaluates anything you put in, so `console.log(eval())` is basically what you're using when you use `console.log()`
* `eval()` evaluates things like equations that are in strings, so like `"5 + 3"` or `"5 / 1"`
* putting `"use strict";` in a function will 1) assist beginners by preventing confusing semantics for beginners; 2) will prevent code snippets executed in console from interacting with one another. (ex: one console execution code snippet being used in another console execution)

## Grammar and Types
* case sensitive, so lower case and upper case matter
* uses unicode character set, so strange characters like one with marks on top can be used in JS
* semicolons are used to mark the end of a statement and are only needed for code on the same line: so for example: `for(let a = 0; a < 5; a++)'
* It is not necessary for most other cases, but it is good practice to use semicolons to prevent some errors
* JS is read from left to right and whitespaces that aren't in strings are ignored  

### Comments  
* `//` is used for single line comments.
* `/* a multi`
* `line`
* `*/ comment`
* comments cannot be nested within each other like if loops or for loops: so no doing this `/* first comment /* second comment */ first comment */'
* comments with a `#` in the beginning indicate a special path.

### Declarations and Variables
* a declaration is creating a variable and a name for that variable
* `var` declares a variable and assigning a value to is optional, so it can be an empty variable.
* the next 2 are block scope variables, which means that THAT SPECIFIC variable (doesn't count ones with the same name not in the same available area, or scope in other words) can only be used inside the block (within for, if, and while loops) it had been declared in. curly brackets usually determine a block.  
* `let` declares a block scoped and local (can only be used within the function it is declared in, not global, or accesible everywhere). declaring a value is optional
* `const` declares a block scoped variable and is permanetly constant, so it is a read only.

* the names of variables are called "identifiers".
* these identifiers must start with a letter, an underscore (_), or a dollar sign.
* identifiers can have numbers after the correct starting character is typed.
##### How to Declare the Variables
* var can be used to declare local and global variables based on the context
* const and let are for block scoped variables
* undeclared js variables can cause errors like `x = 42`(this form creates an undeclared global variable)

### Evaluating Variables
* var or let with no declared statement are deemed undefined
* if passed as a boolean, undefined is considered `false`
* defaults to `NaN` or Not a Number when used in a anumeric context so like `var a; a + 2` and a + 2 would equal NaN
* if a variable is null (you can set it to null for example), then it will be 0 in a numeric context and false in a boolean context

### Variable Scope
* if a variable is declared outside of a function, then it is considered global
* let and const cannot be reference outside of their scope, and let is only local

### Variable Hoisting
* Definition: In JS, you can actually call a variable that would be defined later without getting an error. 
* in a sense, variables are "hoisted" or "lifted" to the top of the program, but will return undefined if hoisted
* 
