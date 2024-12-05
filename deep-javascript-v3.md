
# Deep JavaScript Foundations, v3 | Frontend Masters

### Introduction

### Types

**Primitive Types**

- Everything in JS is not an Object but can behave like Object. Read the spec to undersatnd the language more.
- Primitive types are(undefined, string,number,boolean) and Object type.
- the typeof check for the type of value that is the variable. It will always return a string.


**Kinds of Emptiness**
- undefined does not mean does not have a value yet but means does not currently have a value.
- undefined is a type of primitive that is able to reference a thing that does not exit and not throw error.
- undeclared means the variable has not been created unlike undefined
- uninitialized are some scope variable that is declared but untouchable.`


**NaN & isNaN**
- NaN is an sentinel value that idicates an invalid number. not Not a number, it is a type of number that represent when a value is not a number.
- The number zero is not a way to indicate the the absent of a valid numberic value. is a number that is important.
- NaN is th only value that does not have indentity property.i.e not equal to itself.


Tip: The IEEE 754 spec is a set of technical standards for how numbers are represented

**Type Check Exercise**



**Type Check Exercise Solution**

### Coercion

**Abstract Operations**
- Abstract operation are the fundamental block of how we complete type coercion. coercion is same as convertion.
- ToBoolean are type of AO, undefined, null,NaN, 0,-0, "", are falsy while anything asides from these are truthy value.
- The toboolean does not invoke the two primituve algorithms(i.e valueof() and tostring). it just look it the value up.


### Philosophy of Coercion

**Intentional Coercion**



**Coercion Exercise**


### Equality

**Double & Triple Equals**
- The double equal allow coercion when the type are different and triple  allow coercion when type are same. In the case where the type are match, the equals are doing same things.
- Is Coercion  helpful in an equality comparison or not, we should ask ourself if we want to allow a coercion or not when using == or ===
- The double equality behave like === when the type are same but when the type are not same, when x is null and y is undefined it will return true(viceversa)
- Coercive equality null == undefined.
- Double equals prefers numeric comparison.
- == compares primitives, if you use it to compares to what is not priitve with primitive, it will turn into a primitive .
- The comparison equalities are recursive in nature.
- If the type are same thw == uses ===, null and undefined are equal, if non-primitive, to primitives, prefers ToNumber.
- Slides 109 for equality



**Coercive Equality**

- If checking for truthy construct do if(isTrue) notif(isTrue==/===true) bcos comparison for a boolean and array is going to go through a corner cases. just do the ToBoolean implicitly.

**Equality Exercise**

- Avoid double equals(==) when with 0 or ""(empty string), with non-primitives, true or false, use Implicit boolean or triple equals instead.
- When you know the type always go for the double equals.and when uncertain use triple equals
- spec for double equal (https://262.ecma-international.org/9.0/index.html#sec-strict-equality-comparison);


### Scope
- Scope is where we look for things
- In a JS code that is lexical scoped, all of the scope and identifiers that we are dealing with are all determined at the compiled time.not at the run time, this is so bcos it helps the JS engine to efficiently optimise the known/fixed value
- JS is a two parse processsor. compilling and execution time
- Never auto create variable like any assignment to a variable that is undeclared at that moment is going to end up create for us a global variable if we are not in the strict mode.
- RefenceError is when you could not find the variablewhile Typeerror is when you found the variable and the value that it is currently holding is not legal to do whatever you are trying to do with it.


**Scope**


### Scope & Function Expressions
- Function Expression add name to their identifiers or scope into their own scope while Function Declaration add their name and to the enclosing  scope .
- When theline start with function  that is FD while when it does not start with the function but e.g (), var it is a FE.

**Function Expressions**



**Arrow Functions**
- Arror functions are anonymous




### Advanced Scope
- Lexical scope is decided at compile time not at run time,
- Dynamic scope does not exit in JS. But exit in other laguages
- the Principle of least exposure/priviledge means, you should default to keeping everything private and expose only minimal necessary.
- You can create a IIFE to make code private.
- If you want to make assignment into a variable and make that assignment into a try and catch. TC is a statement does not work in an expression position but you can make it an expresion by wrapping the function expression aroud it
- , IIFE can be use any place that you need an expression and anytime you need a statament or a scope in a expression position.
- Var can be reused in a scope, Let cannot be reuse. is good to have both var and let code in a codebase bcos of semantic and behavioral reasons.
- Make an explicity block curly braces when a variable is use in two or three lines of code.
- Const mean a variable thst cannot be reassign not a variable that cannot be change.Use const with only Primitive immutable values and when this value is a semantic placeholder for where the literal or value be use in one or few places. e.g API URL.
- Hoisting is just a english language to define lexical scope and what will happen when the JS parse process or variable before executing them. 
- Hoist is not in JS spec.
- to use a variable assign to a function, you have to call them after the declaaration. Function Hoisting is useful for code readability. let / const hoist to a block while var hoist to a fuction.
- When let hoist it variable into its block scope , its create a location and make it uninitialize hece throw a TDZ error while var create a location and return undefined.
- Function expression does not hoist
- You can use hoisting to organise your code where the function call will be up and the function declaration will be down.


### Closure

**Origin of Closure*
- Closure is when a function “remembers” its lexical scope even when the function is executed outside that lexical scope.
- In closure you close over a variable(the current value the variable has at the moment not what he had before) not the value of the variable.



**ES6 Modules & Node.js**
- Modules encapsulate data and behavior (methods) together. The state (data) of a module is held by its methods via closure. you can not have a module pattern if you do not have a closure

Note: TC39 is an ECMA committee which follows a process to develop language features for JavaScript

Note: libuv is a JavaScript library focused on asynchronous IO

**Module Exercise**



### Objects

**Objects Overview**
- A function's this references the execution context for that call, determined entirely by how the function was called.
- A this-aware function can thus have a different context each time it's called, which makes it more flexible & reusable.
- This allows make JS to beb dynamic in  nature.
- The new keyword do the following list, (1. Create a brand new empty object 2.* Link that object to another object 3. Call function with this set to the new object 4. If function does not return an object, assume return of this)

- An arrow function does not define a this keyword atall and so it resolve lexically.
- use bind when the function is this aware function.
**this Exercise**


**Fixing this in Classes**

**class Exercise**



**class Exercise Solution**



### Prototypes

**Prototypes**



**The Prototype Chain**


**this & prototypes Q&A**


**OLOO Pattern**

