Javascript
Assignment-9


1.	Explain the scope in Javascript.

 Scope determines the accessibility (visibility) of variables.

 JavaScript variables have 3 types of scope:

  - Block scope
  - Function scope
  - Global scope

  Block Scope

Before ES6 (2015), JavaScript variables had only Global Scope and Function Scope.

ES6 introduced two important new JavaScript keywords: let and const.

These two keywords provide Block Scope in JavaScript.

Variables declared inside a { } block cannot be accessed from outside the block:


Example

```js
{
  let x = 2;
}
// x can NOT be used here

```

Variables declared with the var keyword can NOT have block scope.

Variables declared inside a { } block can be accessed from outside the block.


Example

```js
{
  var x = 2;
}
// x CAN be used here
```

 - Local Scope

Variables declared within a JavaScript function, are LOCAL to the function:

Example

```js
// code here can NOT use carName

function myFunction() {
  let carName = "Volvo";
  // code here CAN use carName
}

// code here can NOT use carName
```

Local variables have Function Scope:

They can only be accessed from within the function.

Since local variables are only recognized inside their functions, variables with the same name can be used in different functions.

Local variables are created when a function starts, and deleted when the function is completed.


- Function Scope


JavaScript has function scope: Each function creates a new scope.

Variables defined inside a function are not accessible (visible) from outside the function.

Variables declared with var, let and const are quite similar when declared inside a function.


They all have Function Scope:

```js
function myFunction() {
  var carName = "Volvo";   // Function Scope
}
```

```js
function myFunction() {
  let carName = "Volvo";   // Function Scope
}
```

```js
function myFunction() {
  const carName = "Volvo";   // Function Scope
}
```

- Global JavaScript Variables

A variable declared outside a function, becomes GLOBAL.

Example

```js
let carName = "Volvo";
// code here can use carName

function myFunction() {
// code here can also use carName
}
```

A global variable has Global Scope:

All scripts and functions on a web page can access it. 

- Global Scope

Variables declared Globally (outside any function) have Global Scope.

Global variables can be accessed from anywhere in a JavaScript program.

Variables declared with var, let and const are quite similar when declared outside a block.


They all have Global Scope:

```js
var x = 2;       // Global scope
```

```js
let x = 2;       // Global scope
```

```js
const x = 2;       // Global scope
```


2.	What is a callback?

A callback is a function passed as an argument to another function.

Example

```js
function myDisplayer(some) {
  document.getElementById("demo").innerHTML = some;
}

function myCalculator(num1, num2, myCallback) {
  let sum = num1 + num2;
  myCallback(sum);
}

myCalculator(5, 5, myDisplayer);
```

In the example above, myDisplayer is a called a callback function.

It is passed to myCalculator() as an argument.



3.	Explain context in JavaScript

The execution context in JavaScript is a critical concept that defines the environment in which JavaScript code is executed. It consists of two main components: code execution and lexical environment

The code execution involves interpreting and processing statements line by line, while the lexical environment includes variables and their values accessible during execution, encompassing the scope chain

- Types of Execution Contexts

There are two types of execution contexts in JavaScript:

- Global Execution Context (GEC): This is the default context created when a JavaScript script starts to run. It represents the global scope and handles all code that is not inside a function

- Function Execution Context (FEC): This context is created whenever a function is called, representing the function's local scope. Each function call gets its own FEC, allowing multiple FECs during the script's runtime


4.	What is hoisting in JavaScript?

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their containing scope during the compilation phase. This allows variables and functions to be used before they are declared in the code.


5.	Explain lexical scope

Lexical scope means that the scope of a variable is determined by its position in the source code. This scope is fixed and does not change at runtime.

- Global Scope:

Variables declared outside any function are in the global scope and can be accessed from anywhere in the code.

- Local Scope:

Variables declared within a function are in the local scope of that function and can only be accessed within that function.

- Nested Functions:

Functions can be nested within other functions, creating multiple levels of scope. Inner functions have access to variables in their own scope as well as in the scopes of their parent functions.


6.	What is scope chaining?

- JavaScript engine uses scopes to find out the exact location or accessibility of variables and that particular process is known as Scope Chain.

- Scope Chain means that one variable has a scope (it may be global or local/function or block scope) is used by another variable or function having another scope (may be global or local/function or block scope).

- This complete chain formation goes on and stops when the user wishes to stop it according to the requirement.


7.	Explain closure.

Is the combination of function and it's lexical environment with in which the function is declared .

8.	What is the difference between undefined and not defined in javascript

- Undefined

A variable is declared but not assigned a value.

Example:

<script>
var a;
console.log(a); // Output: undefined
a = 5;
console.log(a); // Output: 5
</script>


- Not Defined

A variable is not declared in the current scope.

Example:

<script>
console.log(a); // Output: ReferenceError: a is not defined
</script>


9.	Explain spread and rest operator.


- spread operator

The spread operator is used to expand elements of an iterable (like an array or string) into individual elements. It’s particularly useful for tasks like copying arrays, merging arrays, and passing array elements as arguments to functions.

Examples:

Copying an Array:

```js
const originalArray = [1, 2, 3];
const copiedArray = [...originalArray];
console.log(copiedArray); // Output: [1, 2, 3]
```

Merging Arrays:

```js
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const mergedArray = [...array1, ...array2];
console.log(mergedArray); // Output: [1, 2, 3, 4, 5, 6]
```

Passing Elements as Function Arguments:

```js
function sum(a, b, c) {
  return a + b + c;
}
const numbers = [1, 2, 3];
console.log(sum(...numbers)); // Output: 6
```

-  Rest Operator

The rest operator collects multiple elements and condenses them into a single array. It’s often used in function parameters to handle an indefinite number of arguments.

Examples:

Function Parameters:

```js
function sum(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}
console.log(sum(1, 2, 3, 4)); // Output: 10
```


Destructuring Arrays:

```js
const [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(first); // Output: 1
console.log(second); // Output: 2
console.log(rest); // Output: [3, 4, 5]
```

10. Explain ‘this’ keyword in Javascript.

In JavaScript, this keyword refers to the current object in context. Its value depends on how it’s used: in methods, it refers to the object; in global scope, it refers to the global object.

this is not a variable. It is a keyword. You cannot change the value of this.