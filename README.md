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

## Grammar and Types

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
* Due to this hoisting issue, all `var` declarations should be near the top of the code
* `let` and `const` are hoisted but return a ReferenceError. The variable is in a "temporal dead zone" until the declaration is processed.

### Function Hoisting
* Only function declarations are hoisted (and don't return undefined unless given undefined). A declaration of a function looks like `function a() {}`
* declarations where a function is assigned to a variable like `var a = function b() {}` doesn't get hoisted.

### Global Variables
* global variables are properties of the global object
* FOr web pages, the global object is window.
* use window.variable to access a global variable in that case, with variable being the identifier of the variable  
* can access global variables in another window or frame by using the window or frame name in place of the earlier window for window.variable.

### Constants
* again, read-only named variables are made with `const`
* cannot change value during when the program runs and must have a value initalized to it as a result
* a constant cannot have the same name as a function or another variable in the same scope
* properties of objects like arrays can be modified though

### Data Types
* There are 8 data types described by ECMAScript
* 7 data types are "primitive":
  * Boolean: `true` and `false`
  * null: special keyword with the null type
  * undefined: top level property whose value is not defined (top value properties are variables and functions like infinity NaN that are not associated with any object)
  * Number: an integer (number with no decimal values after them) or a floating-point number (numbers with decimals)
  * Bigint: a number with arbitrary (not precise) precision like 9358203682306823068940n
  * String: sequence of characters that represent text, like "Hello"
  * Symbol: immutable and unique instanced data types
* object: data structure containing data on how to use that structure
* Objects can be thought of as "named containers for values" and functions can be thought of as "procedural instructions"

### Data Type Conversion
* dynamic type conversion, so you don't need to specify what data type is being put in the variable

### Numbers and the '+' Operator
* if using + with a string and something else, like a number, then the other data type is converted into a string
* example: `"37" + 7 // = string "377"'
* this doesn't work for other operators 

### Converting Strings to Numbers
* if a string is representing a number (like "7" for example), then parseInt() and parseFloat() can be used depedning on if the number is an integer or a floating-point
* using the radix parameter, the second parameter specifies which number system to use. 
* Although, optional, using the radix paramter is the best practice.
* example: `parseInt('101', 2) // 5` <- 2 is the radix here. bidecimal system is used as a result.
* use 10 as a radix/base for the most common 0-9 system
  ##### Alternative Method: Unary Plus
  * the unary plus, a plus operator outside and placed before a string with a number in it can also be used to get the number data type. 
  * example: `+"1.1" // 1.1` <- can be added to another string with a unary operator to produce a number with their sum

### Literals
* these represent values in JS but are not variables.
* fixed values provided in script
  #### Array Literals
  * list of 0 or more values denoted by a `[]` with objects/variables inside like `[1, 2, 3, 4, 5]`
  * specific values in the array are its elements
  * length is set to the amount of elements in the array
  * array literals are a type of object initalizer as well and array objects
  * if an array is created in a top-level script, the array literal is interpreted each an expression containing the array literal is evaluated
  * literals are created if they are in a function everytime a function is called
  * Extra Commas:
  * `let fish = ['Lion', , 'Angel'];`<- The extra commas makes index 1 undefined, fish array has length 3 as a result
  * trailing, LAST comma at the end is ignored. only one comma at the end is ignored
  * should declare these as undefined for clarity
  #### Boolean Literals
  * two literal values which are `true` and `false`
  * true and false of the primitive data type are different from the true and false of the boolean object type
  * Boolean object is a *wrapper* around the primitve type
  #### Numeric Literals
  * Number and BigInt types can be written as base 10, 16, 8, or 2 (decimal, hexadecimal, octal, and binary respectively)
  * base 10 is a sequence of digits without a leading 0 (without zeroth index of 0)
  * base 8 has a leading 0, or a 0o or a 0O, can only contain numbers 0-7
  * base 16 has a leading 0x or 0X, can have numbers 0-9 and letters A-F or a-f
  * base 2 has a leading 0b or 0B and can only have the numbers 0-1
