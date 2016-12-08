# JavaScript The Good Parts - Notations

## Objects

The simple types of JavaScript are numbers, strings, booleans ( true and false ), null , and undefined . All other values are objects. Numbers, strings, and booleans are object-like in that they have methods, but they are immutable. Objects in JavaScript are mutable keyed collections. In JavaScript, arrays are objects, functions are objects, regular expressions are objects, and, of course, objects are objects.

## Prototype

Every object is linked to a prototype object from which it can inherit properties. All objects created from object literals are linked to Object.prototype , an object that comes standard with JavaScript.

[Reference] (http://wbruno.com.br/javascript-puro/orientacao-a-objetos-em-javascript-funcao-construtora/)

## Function Objects

Functions in JavaScript are objects. Objects are collections of name/value pairs having a hidden link to a prototype object. Objects produced from object literals are linked to Object.prototype . Function objects are linked to Function.prototype (which is itself linked to Object.prototype ). Every function is also created with two additional hidden properties: the function’s context and the code that implements the function’s behavior.

## Function Declaration

Similar to the var statement, function declarations are hoisted to the top of other code.


## Function expression

Function expressions aren’t hoisted, which allows them to retain a copy of the local variables from the scope where they were defined.
There are several different ways that function expressions become more useful than function declarations.

- As closures
- As arguments to other functions
- As Immediately Invoked Function Expressions (IIFE)

## Recursion

Recursion is best applied when you need to call the same function repeatedly with different parameters from within a loop. While it can be used in many situations, it is most effective for solving problems involving iterative branching, such as fractal math, sorting, or traversing the nodes of complex or non-linear data structures.

## Scope

Scope in a programming language controls the visibility and lifetimes of variables and parameters.
In JavaScript, objects and functions are also variables.

**In JavaScript, scope is the set of variables, objects, and functions you have access to.**

All the variables defined in a block (a list of statements wrapped with curly braces) are not visible from outside of the block. And all variables defined anywhere within a function is visible everywhere within the function.


## Closure

A closure is created when an inner function is made accessible from outside of the function that created it. This typically occurs when an outer function returns an inner function.  When this happens, the inner function maintains a reference to the environment in which it was created.  This means that it remembers all of the variables (and their values) that were in scope at the time.


```js

function add(value1) {
  return function doAdd(value2) {
    return value1 + value2;
  };
}

var increment = add(1);
var foo = increment(2);
// foo equals 3

```

There are a number of things to note about this example.

- The add() function returns its inner function doAdd(). By returning a reference to an inner function, a closure is created.
- “value1” is a local variable of add(), and a non-local variable of doAdd(). Non-local variables refer to variables that are neither in the local nor the global scope.  “value2” is a local variable of doAdd().
- When add(1) is called, a closure is created and stored in “increment”. In the closure’s referencing environment, “value1” is bound to the value one.  Variables that are bound are also said to be closed over. This is where the name closure comes from.
- When increment(2) is called, the closure is entered. This means that doAdd() is called, with the “value1” variable holding the value one. The closure can essentially be thought of as creating the following function.

```js
function increment(value2) {
  return 1 + value2;
}
```

[Reference] (https://www.sitepoint.com/javascript-closures-demystified/)


### Things to Remember

- Closures contain a function and a reference to the environment in which the function was created.
- A closure is formed when an outer function exposes an inner function.
- Closures can be used to easily pass parameters to callback functions.
- Private data can be emulated by using closures.  This is common in object-oriented programming and namespace design.
- Closures should be not overused in constructors.  Adding to the prototype is a better idea.


## Module

We can use functions and closure to make modules. A module is a function or object that presents an interface but that hides its state and implementation.


## Memoization

[Reference] (https://www.sitepoint.com/implementing-memoization-in-javascript/)

## Pseudoclassical