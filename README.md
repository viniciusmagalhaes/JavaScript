# JavaScript The Good Parts - Notations

## Objects

The simple types of JavaScript are numbers, strings, booleans ( true and false ), null , and undefined . All other values are objects. Numbers, strings, and booleans are object-like in that they have methods, but they are immutable. Objects in JavaScript are mutable keyed collections. In JavaScript, arrays are objects, functions are objects, regular expressions are objects, and, of course, objects are objects.

## Prototype

Every object is linked to a prototype object from which it can inherit properties. All objects created from object literals are linked to Object.prototype , an object that comes standard with JavaScript.

## Function Objects

Functions in JavaScript are objects. Objects are collections of name/value pairs having a hidden link to a prototype object. Objects produced from object literals are linked to Object.prototype . Function objects are linked to Function.prototype (which is itself linked to Object.prototype ). Every function is also created with two additional hidden properties: the function’s context and the code that implements the function’s behavior.

## Recursion

Recursion is best applied when you need to call the same function repeatedly with different parameters from within a loop. While it can be used in many situations, it is most effective for solving problems involving iterative branching, such as fractal math, sorting, or traversing the nodes of complex or non-linear data structures.

## Scope

In JavaScript, objects and functions are also variables.

**In JavaScript, scope is the set of variables, objects, and functions you have access to.**

All the variables defined in a block (a list of statements wrapped with curly braces) are not visible from outside of the block. And all variables defined anywhere within a function is visible everywhere within the function.
