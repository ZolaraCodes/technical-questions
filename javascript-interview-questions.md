# Javascript - Technical Interview Questions 

## Questions:

- [x] Explain event delegation.
- **Explain:** A pattern to handle events efficiently. 
- **Use:** Instead of adding an event listener to each and every similar element, we can add an event listener to a parent element and call an event on a particular target using the . target property of the event object.
- **Example:** Able to hide messages with delegation.

- [x] Explain how this works in Javascript.
- **Explain:** Efficiently handles events within one event listener.
- **Use:**
- **Example:** Create a tree that shows/hides node children on click.

- [x] Explain how prototypal inheritance works?
- **Explain:** Every object with its methods and properties contains an internal and hidden property known as Prototype.
- **Use:** An object can inherit the properties and methods of another object.
- **Example:** 
<!-- using __proto__ to access and set the [[Prototype]] of "anObject"
anObject.__proto__ = someotherObject -->

- [x] What do you think of AMD vs CommonJS?
- **Explain:** AMD(Asynchronous Module Definition). 
- **Use:** Common JS use exports to create exportable/public properties or methods. In AMD, we return any object which we want to make publicly available.
- **Example:**  example of common.js is Node.js; example of AMD is javascript in the browser.

- [x] Explain why the following doesn't work as an IIFE: function foo (){}();. What needs to be changed to properly make it an IIFE?
- **Explain:**
In order to make the second parens (immediately) invoke foo(), we need to make the function declaration evaluate to a function expression first. And guess what, we do it with another parens.Another fix would be to wrap the entire code in an overarching parens. This will also make it work as an IIFE:- 
**Use:**
If code returns a token error
- **Example:**
(function foo(){ console.log('Hello from foo!') }()); // "Hello from foo!"

- [x] What's the difference between a variable that is: null, undefined or undeclared? How would you go about checking for any of these states?
- **Explain:**
a variable is undeclared when the variable has not been created
a variable is undefined when the variable is declared, but does not have a value
a variable is null when the variable is declared, and has a value of nothing, the absence of a value

- **Use:**
Undeclared variables do not exist until the code assigning to them is executed,Undeclared variables are always global,Undeclared variables are configurable (e.g. can be deleted).
null expresses a lack of identification, indicating that a variable points to no object.
undefined is a non-configurable, non-writable property. Even when this is not the case, avoid overriding it.
A variable that has not been assigned a value is of type undefined. A method or statement also returns undefined if the variable that is being evaluated does not have an assigned value.
- **Example:**
let snack
console.log(snack)
// undefined
const snack = null
console.log(snack)
// null
console.log(snack)
// ReferenceError: snack is not defined

- [x] What is a closure, and how/why would you use one?
- **Explain:**
A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function. 
- **Use:**
They allow you to attach variables to an execution context. Variables in closures can help you maintain a state that you can use later. 
- **Example:**
function init() {
  var name = "Mozilla"; // name is a local variable created by init
  function displayName() {
    // displayName() is the inner function, that forms the closure
    console.log(name); // use variable declared in the parent function
  }
  displayName();
}
init();

allow you to display the display name as Mozilla

- [x] Can you describe the main difference between a .forEach loop and a.map() loop and why you would pick one versus the other?
- **Explain:**
The map method receives a function as a parameter. Then it applies it on each element and returns an entirely new array populated with the results of calling the provided function.
This means that it returns a new array that contains an image of each element of the array. It will always return the same number of items
The forEach() method receives a function as an argument and executes it once for each array element. However, instead of returning a new array like map, it returns undefined
- **Use:**
You can use a map loop to return a new array ie solving an equation. you can use a forEach loop to find name ina  database
- **Example:**
forEach example
const myAwesomeArray = [

  { id: 1, name: "john" },
  { id: 2, name: "Ali" },
  { id: 3, name: "Mass" },
]

myAwesomeArray.forEach(element => console.log(element.name))
// >>>>>>>>> Output : john
//                    Ali
//                    Mass


const myAwesomeArray = [5, 4, 3, 2, 1]

myAwesomeArray.map(x => x * x)



// >>>>>>>>>>>>>>>>> Output: [25, 16, 9, 4, 1]

Map example 

- [x] What's a typical use case for anonymous funtions?
- **Explain:**
An anonymous function is a function that does not have any name associated with it.in anonymous functions in JavaScript, we use only the function keyword without the function name. An anonymous function is not accessible after its initial creation, it can only be accessed by a variable it is stored in as a function as a value. 
- **Use:**
we use an anonymous function as a self-invoking function (a special function that is invoked right after it is declared and also does not have any kind of name associated with it) 
- **Example:**
 (function () {

        console.log("Welcome to GeeksforGeeks!");
    })();

- [x]  How do you organize your code? (module pattern, classical inheritance?)
- **Explain:**
 The module pattern is still great, but these days, I use React/Redux which utilize a single-directional data flow based on Flux architecture. I would represent my app's models using plain objects and write utility pure functions to manipulate these objects. 
- **Use:**
- **Example:**

- [x] What's the difference between host objects and native objects?
- **Explain:**
Native objects are objects that are part of the JavaScript language defined by the ECMAScript specification
Host objects are provided by the runtime environment (browser or Node)
- **Use:**
 A host object is created automatically the moment the page renders in a browser. A Native Object is created by the developer using predefined classes of JavaScript. Native Objects are in your written script.
- **Example:**
Native objects:  String, Math, RegExp, Object, Function
Host objects: window, XMLHTTPRequest

- [x] Difference between: function Person(){}, var person = Person(), and var person = new Person()?
- **Explain:**
Technically speaking, function Person(){} is just a normal function declaration. The convention is to use PascalCase for functions that are intended to be used as constructors.
var person = new Person() creates an instance of the Person object using the new operator, which inherits from Person.prototype
- **Use:**
function person Declares (instantiates) a named function in memory, but does not execute it.
Declares a new function, Person, invokes it and then assigns the return value to the variable person.

Var person new person: In this case, we have the introduction of the new keyword which means that Person is an object constructor function which returns a new object instance. So while person in the example above is the returned value of Person (a string, number or whatever), the value of person in this example is actually an object.


- **Example:**

function Person(name) {
  this.name = name;
}
var person = Person('John');
console.log(person); // undefined
console.log(person.name); // Uncaught TypeError: Cannot read property 'name' of undefined
var person = new Person('John');
console.log(person); // Person { name: "John" }
console.log(person.name); // "john"

- [x] What's the difference between .call and .apply?
- **Explain:**
call takes in comma-separated arguments as the next arguments while .apply takes in an array of arguments as the next argument. An easy way to remember this is C for call and comma-separated and A for apply and an array of arguments.
- **Use:**
Both .call and .apply are used to invoke functions and the first parameter will be used as the value of this within the function. 
- **Example:**
function add(a, b) {

  return a + b;
}
console.log(add.call(null, 1, 2)); // 3
console.log(add.apply(null, [1, 2])); // 3

- [x] Explain Function.prototype.bind.
- **Explain:**
The Function.prototype.bind() method creates a new function from an existing function, allowing the this keyword to be set to the provided value with a given sequence of arguments preceding any provided when the new function is called
- **Use:**
It can take any number of arguments and return a new function that calls the original function using the JS Function.prototype
- **Example:**

- [x] When would you use document.write()?
- **Explain:**
- **Use:**
- **Example:**
Examples of Function.prototype.bind include pre-configuring the this keyword to be set to a provided value with a given sequence of arguments preceding any provided when the new function is called[1]
[2]
, creating a new function from an existing function[3]
, and binding the this keyword to an HTML element

- [x] What's the difference between feature detection,feature inference, and using the UA string?
- **Explain:**
- **Use:**
- **Example:**

- [x] Explain Ajax in as much detail as possible.
- **Explain:**
- **Use:**
- **Example:**

- [x] What are the advantages and disadvantages of using Ajax?
- **Explain:**
- **Use:**
- **Example:**

- [x] Explain how JSONP works (and how it;s not really Ajax).
- **Explain:**
- **Use:**
- **Example:**

- [x] Have you ever used JavaScript templating? If so, what libraries have you used?
- **Explain:**
- **Use:**
- **Example:**

- [x] Explain "hoisting"?
- **Explain:**
- **Use:**
- **Example:**

- [x] Describe event bubbling.
- **Explain:**
- **Use:**
- **Example:**

- [x] What's the difference between an "attribute" and a property?
- **Explain:**
- **Use:**
- **Example:**

- [x] Why is extending built-in JavaScript objects not a good idea?
- **Explain:**
- **Use:**
- **Example:**

- [x] Difference between document load event and document DOMContentLoaded event?
- **Explain:**
- **Use:**
- **Example:**

- [x] What is the difference between == and ===?
- **Explain:** These both are comparison operators. 
- **Use:** The one with two equal signs are for value and the three equal signs are used for value and type.
- **Example:** 3 == '3' would return True 3 === '3' would return false

- [x] Explain the same-origin policy with regards to Javascript.
- **Explain:**
- **Use:**
- **Example:**

- [x] Make this work: duplicate ([1,2,3,4,5]); //[1,2,3,4,5,1,2,3,4,5]
- **Explain:**
- **Use:**
- **Example:**

- [x] Why is it called a Ternary expression, what does the word "Ternary" indicate?
- **Explain:**
- **Use:**
- **Example:**

- [x] What is "use strict";? what are the advantages and disadvantages to using it?
- **Explain:**
- **Use:**
- **Example:**

- [x] Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5
- **Explain:**
- **Use:**
- **Example:**

- [x] Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
- **Explain:**
- **Use:**
- **Example:**

- [x] Why would you use something like the load event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
- **Explain:**
- **Use:**
- **Example:**

- [x] Explain what a single page app is and how to make one SEO-friendly.
- **Explain:**
- **Use:**
- **Example:**

- [x] What is the extent of your experience with Promises and/or their polyfills?
- **Explain:**
- **Use:**
- **Example:**

- [x] What are the pros and cons of using Promises instead of callbacks?
- **Explain:**
- **Use:**
- **Example:**

- [x] What are some of the advantages/disadvantages of writing Javascript code in a language that compiles to JavaScript?
- **Explain:**
- **Use:**
- **Example:**

- [x] What tools and techniques do you use debugging Javascript code?
- **Explain:**
- **Use:**
- **Example:**

- [x] What language constructions do you use for iterating over object properties and array items?
- **Explain:**
- **Use:**
- **Example:**

- [x] Explain the difference between mutable and immutable objects.
- **Explain:**
- **Use:**
- **Example:**

- [x] Explain the difference between synchronous and asycnhronous functions.
- **Explain:**
- **Use:**
- **Example:**

- [x] What is an event loop? What is the difference between call stack and task queue?
- **Explain:**
- **Use:**
- **Example:**

- [x] Explain the differences on the usage of foo between function foo(){} and var foo = function (){}
- **Explain:**
- **Use:**
- **Example:**

- [x] What are the differences between variables created using let, var or const?
- **Explain:**
- **Use:**
- **Example:**

- [x] What are the differences between ES6 class and ES5 function constructors?
- **Explain:**
- **Use:**
- **Example:**

- [x] Can you offer a use case for the new arrow => function syntax? How does this new syntax differ from other functions?
- **Explain:**
- **Use:**
- **Example:**

- [x] What advantage is there for using the arrow syntax for a method in a constructor?
- **Explain:**
- **Use:**
- **Example:**

- [x] What is the definition of a higher-order function?
- **Explain:**
- **Use:**
- **Example:**

- [x] Can you give an example for destructuring an object or an array?
- **Explain:**
- **Use:**
- **Example:**

- [x] ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
- **Explain:**
- **Use:**
- **Example:**

- [x] Can you give an example of a curry function and why this syntax offers an advantage?
- **Explain:**
- **Use:**
- **Example:**

- [x] What are the benefits of using spread syntax and how is it differenct from rest syntax?
- **Explain:**
- **Use:**
- **Example:**

- [x] How can you share code between files?
- **Explain:**
- **Use:**
- **Example:**

- [x] Why you migh want to create static class members?
- **Explain:**
- **Use:**
- **Example:**

### General Questions

- [x] Can you name two programming paradigms important for JavaScript app developers?
- **Explain:**
- **Use:**
- **Example:**

- [x] What is functional programming?
- **Explain:**
- **Use:**
- **Example:**

- [x] What is the difference between classical inheritance and prototypal inheritance?
- **Explain:**
- **Use:**
- **Example:**

- [x] What are the pros and cons of functional programming vs object-oriented programming?
- **Explain:**
- **Use:**
- **Example:**

- [x] What are two-way data binding and one-way data flow, and how are they different?
- **Explain:**
- **Use:**
- **Example:**

- [x] What is asynchronous programming, and why is it important in JavaScript?
- **Explain:**
- **Use:**
- **Example:**
