# Javascript - Technical Interview Questions 

## Questions:

- [x] Explain event delegation.
- **Explain:** A pattern to handle events efficiently. 
- **Use:** Instead of adding an event listener to each and every similar element, we can add an event listener to a parent element and call an event on a particular target using the . target property of the event object.
- **Example:** Able to hide messages with delegation.

- [x] Explain how this works in Javascript.
- **Explain:** 
Event delegation is a technique in JavaScript where you add an event listener to a parent element instead of each individual child element. 
- **Use:**
To implement event delegation, you first attach a single event listener to a parent element, such as a div or document object. Then, you use conditional statements in the event handler function to check if the target element matches a certain selector or has a certain class name.
- **Example:** 
The benefits of using event delegation include improved performance and reduced code complexity, especially for large or dynamic web pages- [x] Explain how prototypal inheritance works?

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
```(function foo(){ console.log('Hello from foo!') }()); // "Hello from foo!" 

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

**Example:**
```let snack
console.log(snack)
// undefined
const snack = null
console.log(snack)
// null
console.log(snack)
// ReferenceError: snack is not defined§:

- [x] What is a closure, and how/why would you use one?
- **Explain:**
A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function's scope from an inner function. 
- **Use:**
They allow you to attach variables to an execution context. Variables in closures can help you maintain a state that you can use later. 
- **Example:**
`function init() {
  var name = "Mozilla"; // name is a local variable created by init
  function displayName() {
    // displayName() is the inner function, that forms the closure
    console.log(name); // use variable declared in the parent function
  }
  displayName();
}
init();`

allow you to display the display name as Mozilla

- [x] Can you describe the main difference between a .forEach loop and a.map() loop and why you would pick one versus the other?
- **Explain:**
The map method receives a function as a parameter. Then it applies it on each element and returns an entirely new array populated with the results of calling the provided function.
This means that it returns a new array that contains an image of each element of the array. It will always return the same number of items
The forEach() method receives a function as an argument and executes it once for each array element. However, instead of returning a new array like map, it returns undefined
- **Use:**
You can use a map loop to return a new array ie solving an equation. you can use a forEach loop to find name ina  database
- **Example:**
`forEach example
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



// >>>>>>>>>>>>>>>>> Output: [25, 16, 9, 4, 1]`

Map example 

- [x] What's a typical use case for anonymous funtions?
- **Explain:**
An anonymous function is a function that does not have any name associated with it.in anonymous functions in JavaScript, we use only the function keyword without the function name. An anonymous function is not accessible after its initial creation, it can only be accessed by a variable it is stored in as a function as a value. 
- **Use:**
we use an anonymous function as a self-invoking function (a special function that is invoked right after it is declared and also does not have any kind of name associated with it) 
- **Example:**
 `(function () {

        console.log("Welcome to GeeksforGeeks!");
    })();`

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

`function Person(name) {
  this.name = name;
}
var person = Person('John');
console.log(person); // undefined
console.log(person.name); // Uncaught TypeError: Cannot read property 'name' of undefined
var person = new Person('John');
console.log(person); // Person { name: "John" }
console.log(person.name); // "john"`

- [x] What's the difference between .call and .apply?
- **Explain:**
call takes in comma-separated arguments as the next arguments while .apply takes in an array of arguments as the next argument. An easy way to remember this is C for call and comma-separated and A for apply and an array of arguments.
- **Use:**
Both .call and .apply are used to invoke functions and the first parameter will be used as the value of this within the function. 
- **Example:**
`function add(a, b) {

  return a + b;
}
console.log(add.call(null, 1, 2)); // 3
console.log(add.apply(null, [1, 2])); // 3`

- [x] Explain Function.prototype.bind.
- **Explain:**
The Function.prototype.bind() method creates a new function from an existing function, allowing the this keyword to be set to the provided value with a given sequence of arguments preceding any provided when the new function is called
- **Use:**
It can take any number of arguments and return a new function that calls the original function using the JS Function.prototype
- **Example:**

- [x] When would you use document.write()?
- **Explain:**
document.write() is a JavaScript method that is used to write dynamic HTML content directly to a web page. 
- **Use:**
When the web page is loaded, the JavaScript code in the page is executed and document.write() can be used to insert text, HTML code, or even entire web pages into the page.
- **Example:**
<!DOCTYPE html>
<html>
<head>
	`<title>Example</title>
	<script>
		document.write("Hello World!");
	</script>`
</head>
<body>
</body>
</html>

When the above code is loaded in a web browser, it will display "Hello World!" on the page.

- [x] What's the difference between feature detection,feature inference, and using the UA string?
- **Explain:**
Feature detection, feature inference, and using the User-Agent (UA) string are all methods of detecting what features or capabilities a web browser supports.
- **Use:**
Feature detection:
Feature detection involves writing code that tests whether a particular feature or API is available in the user's browser before using it. This is done by checking if a property or method exists in the browser's global object, such as window or document. 

Feature inference:
Feature inference involves assuming that a particular feature is supported in a browser based on the presence of another feature.

Using the UA string:
The UA string is a string of text that identifies the browser and its version number. It can be accessed using JavaScript with the navigator.userAgent property.

- **Example:**
1.Feature detection:
`// Check if the browser supports the HTML5 canvas element
if (typeof canvas.getContext === 'function') {
  // Code that uses the canvas element
} else {
  // Fallback code for browsers that don't support the canvas element
}`

2.Feature inference:
`// If the browser supports querySelector, assume it also supports querySelectorAll
if (document.querySelector) {
  var elements = document.querySelectorAll('p');
  // Code that uses the selected elements
}`

3.Using the UA string:
`// Detect if the user is using Internet Explorer
var isIE = navigator.userAgent.indexOf('MSIE') !== -1 || navigator.appVersion.indexOf('Trident/') > 0;
if (isIE) {
  // Code that handles Internet Explorer-specific issues
}`


- [x] Explain Ajax in as much detail as possible.
- **Explain:**
Ajax (Asynchronous JavaScript and XML) is a web development technique that allows web pages to retrieve and display data from a server without requiring the entire page to be reloaded. 

- **Use:**
This results in a more seamless and responsive user experience, because the user can interact with the page without having to wait for it to reload.

- **Example:**
Ajax can be used for a variety of purposes, such as fetching data from a server, submitting form data, and updating content on the page. It is commonly used in web applications to provide a more seamless and responsive user experience.

- [x] What are the advantages and disadvantages of using Ajax?
- **Explain:**
improved user experience,increased interactivity,Cross-platform compatibility. Disadvantages: seo complications, accessibility issues, complexity. 
- **Use:**
Improved user experience: Ajax allows web pages to update content in real-time without requiring the entire page to be reloaded. This results in a more seamless and responsive user experience.

Increased interactivity: Ajax can be used to enable more interactive user interfaces, such as drag-and-drop, auto-suggest, and autocomplete features.

Cross-platform compatibility: Ajax works across different platforms and browsers, making it a versatile tool for web development.

Accessibility issues: Ajax can present accessibility issues for users with disabilities, as it can make it difficult for assistive technologies to interact with the page.

Complexity: Ajax can add complexity to web applications, making them more difficult to develop and maintain.


- [x] Explain how JSONP works (and how it;s not really Ajax).
- **Explain:**
JSONP (JSON with Padding) is a technique for retrieving data from a server in a different domain than the one that the web page is hosted on.
- **Use:**
It is often used as a workaround for the same-origin policy, which restricts web pages from making requests to servers in different domains.
- **Example:**
`<script src="http://api.example.net/data?callback=myCallback"></script>

<script>
  function myCallback(data) {
    console.log(data);
  }
</script>`

This code fetches JSON data from http://api.example.net/data using JSONP and passes it to the myCallback function defined on the page. The console.log statement will print the data to the console.

- [x] Have you ever used JavaScript templating? If so, what libraries have you used?
- **Explain:**
JavaScript templating is a technique for generating HTML markup (or other text-based formats) using JavaScript code
- **Use:**

- **Example:**

- [x] Explain "hoisting"?
- **Explain:**
Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their respective scopes during the compilation or interpretation phase, before the actual code execution. 
-**Use:**
For example, if you have a variable declaration after its usage in a function, hoisting will move the declaration to the top of the function scope:
**Example:**
`function example() {
  console.log(x); // Output: undefined
  var x = "hello";
  console.log(x); // Output: "hello"
}`

- [x] Describe event bubbling.
- **Explain:**
Event bubbling is a concept in which when an event is triggered on an element, it propagates through its parent elements in the DOM hierarchy until it reaches the document root. This means that if an event is triggered on a child element, it will also trigger the same event on all of its parent elements. 
- **Use:**
This allows event handlers to be triggered at different levels of the DOM hierarchy, allowing for more flexible and powerful event handling.
- **Example:**
`<div id="parent">
  <button id="button">Click me!</button>
</div>
// add an event listener to the parent element
document.querySelector('#parent').addEventListener('click', function(event) {
  console.log('Parent element clicked!');
});

// add an event listener to the button element
document.querySelector('#button').addEventListener('click', function(event) {
  console.log('Button clicked!');
});`

In this example, when the user clicks the button, the click event is first triggered on the button element itself, then on its parent element (the parent div). This results in the following output in the console:

- [x] What's the difference between an "attribute" and a property?
- **Explain:**
  an attribute is a value specified in HTML markup that provides additional information about an element, while a property is a value assigned to an object in JavaScript that can be accessed and modified programmatically
- **Use:**
Attributes are used to set initial property values, while properties can be modified dynamically as an application runs. 
- **Example:**
`<img id="my-image" src="image.jpg" alt="A beautiful image">`
In this example, we have an img element with an id attribute and three properties: id, src, and alt. The id attribute specifies a unique identifier for the element, while the src and alt properties specify the source URL and alternate text for the image, respectively.
We can access and modify these properties using JavaScript

- [x] Why is extending built-in JavaScript objects not a good idea?
- **Explain:**
 Extending built-in JavaScript objects, such as Array, Object, or String, can lead to unexpected behavior and potential bugs in your code.
- **Use:**
Convenience: In some cases, extending a built-in object can make code more concise and easier to read. For example, adding a custom method to the Array prototype that performs a common operation could make code that uses that method more readable than if the same operation was performed using a separate utility function.

Compatibility: If you are working with a legacy codebase that relies on an extended built-in object, it may be necessary to continue extending that object in order to maintain compatibility with existing code.
- **Example:**
Convenience: In some cases, extending a built-in object can make code more concise and easier to read. For example, adding a custom method to the Array prototype that performs a common operation could make code that uses that method more readable than if the same operation was performed using a separate utility function.

Compatibility: If you are working with a legacy codebase that relies on an extended built-in object, it may be necessary to continue extending that object in order to maintain compatibility with existing code.

- [x] Difference between document load event and document DOMContentLoaded event?
- **Explain:**
- **Use:**
- **Example:**

- [x] What is the difference between == and ===?
- **Explain:** These both are comparison operators. 
- **Use:** The one with two equal signs are for value and the three equal signs are used for value and type.
- **Example:**
`3 == '3' would return True 3 === '3' would return false`

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
The main advantages of using promises instead of callbacks are better defined and organized control flow of asynchronous logic, reduced coupling, composability, and the ability to wait for only one promise to resolve[1][2][3][4]. Promises also provide an object to decide the action that needs to be taken after the async task completes[5]. However, promises are just syntactic sugar and everything that can be done with promises can also be done with callbacks[4].
- **Use:**
- **Example:**

- [x] What are some of the advantages/disadvantages of writing Javascript code in a language that compiles to JavaScript?
- **Explain:**
Writing JavaScript code in a language that compiles to JavaScript has several advantages, such as speed and ease of reading and writing cross-browser code[1][2]. However, there are also some disadvantages, such as client-side security issues[3], browser support issues[2], lack of debugging facility[4], single inheritance[4], sluggish bitwise function[4], and more[5].
- **Use:**
- **Example:**

- [x] What tools and techniques do you use debugging Javascript code?
- **Explain:**
There are several tools and techniques for debugging JavaScript code, such as Google Dev Tools, React Dev Tools, Node Inspect, Postman and Webpack[1], as well as the console.log() method, setting breakpoints, and the debugger keyword[2][3]. Additionally, there are various debugging techniques that can be used to enhance efficient running of codes or programs in JavaScript[4].
- **Use:**
- **Example:**

- [x] What language constructions do you use for iterating over object properties and array items?
- **Explain:**
Common language constructions for iterating over object properties and array items include for loops, for..in, for each..in, map, reduce[1][2], and the for...in loop[3][4][5].
- **Use:**
- **Example:**

- [x] Explain the difference between mutable and immutable objects.
- **Explain:**
In Python, mutable objects are those whose value can be changed over time[1]
, while immutable objects are those whose value cannot be changed once they are created
. Examples of mutable objects include lists and dictionaries, while strings and tuples are examples of immutable objects

- **Use:**
- **Example:**

- [x] Explain the difference between synchronous and asycnhronous functions.
- **Explain:**
Synchronous functions are those that run in a particular sequence of instructions given in the program
, while asynchronous functions allow for the execution of upcoming instructions immediately
. Asynchronous code runs in parallel, meaning multiple operations can occur simultaneously
- **Use:**
- **Example:**

- [x] What is an event loop? What is the difference between call stack and task queue?
- **Explain:**
The Call Stack is a built-in component of the JavaScript runtime[1][2], while the Task/Event Queue is a component of the browser[1]. The Event Loop's job is to move stuff out from the callback queue and back onto the call stack when it is empty[2][3]. The Event Loop has responsibility to see if the call-stack is empty and if there are pending tasks in the task queue to process[4][5].
- **Use:**
- **Example:** t are the differences between variables created using let, var or const?

- [x] Explain the differences on the usage of foo between function foo(){} and var foo = function (){}
- **Explain:**
The difference between function foo(){} and var foo = function (){} is that the former is a function declaration while the latter is a function expression[1][2][3][4]. Function declarations have their body hoisted but function expressions do not[4]
- **Use:**
- **Example:**

- [x] What are the differences between variables created using let, var or const?
- **Explain:**
ar: Variables declared with var are function scoped, which means they are accessible within the function they are declared in. If a variable is declared with var inside a block, it is hoisted to the top of the function and can be accessed before its declaration. This can lead to unexpected behavior.

let: Variables declared with let are block scoped, which means they are only accessible within the block they are declared in. If a variable is declared with let inside a block, it is not hoisted to the top of the function and cannot be accessed before its declaration.

const: Variables declared with const are also block scoped, and their value cannot be reassigned after they are declared. However, the properties of an object declared with const can be modified.
- **Use:**
- **Example:**

- [x] What are the differences between ES6 class and ES5 function constructors?
- **Explain:**
The main difference between ES6 class and ES5 function constructors is that ES6 class allows developers to instantiate objects using the new operator[1][2][3][4], while ES5 function constructors create objects by adding functions to their prototypes (Blueprint)[1]. Additionally, ES6 classes have the ability to subclass native classes like Array[5].
- **Use:**
- **Example:**

- [x] Can you offer a use case for the new arrow => function syntax? How does this new syntax differ from other functions?
- **Explain:**
Arrow functions are a more concise syntax for writing functions compared to regular functions[1][2][3][4][5]. The main differences between arrow and regular functions include the lack of an arguments keyword in arrow functions[3], the inability to use the 'new' keyword with arrow functions[2], and the fact that arrow functions do not have their own this value[5]. Arrow functions are often used when writing callbacks or higher-order functions[4].
- **Use:**
- **Example:**

- [x] What advantage is there for using the arrow syntax for a method in a constructor?
- **Explain:**
- **Use:**
The advantage of using arrow syntax for methods in a constructor is that it binds the 'this' keyword to the surrounding code, making the code simpler and shorter
. Additionally, arrow functions can't be used as constructors since calling them with new throws a TypeError[3]
. Arrow functions also don't redefine the value of 'this' within their function body, which makes it easier to predict their behavior when used with React[4]

- **Example:**

- [x] What is the definition of a higher-order function?
- **Explain:**
A higher-order function is a function that takes one or more functions as arguments and/or returns a function[1]
 In JavaScript, functions are first-class objects, meaning they can be passed as arguments to other functions and returned from them[5].
- **Use:**
- **Example:**

- [x] Can you give an example for destructuring an object or an array?
- **Explain:**
Destructuring is a JavaScript expression that makes it possible to unpack values from arrays or properties from objects into distinct variables[1][2][3]. For example, to extract the values of an object prior to ES6, one would have to use the dot notation: var obj = {first: 'Rick', last: 'Sanchez', age: 70}; var first = obj.first[4]. With destructuring, this can be simplified to let {first} = obj[5]. Similarly, for an array, one could use the index notation to assign values to variables: let studentsArr = ['John', 'Jane', 'Bob']; let firstStudent = studentsArr[3]. With destructuring, this can be simplified to let [firstStudent] = studentsArr[3].
- **Use:**
- **Example:**

- [x] ES6 Template Literals offer a lot of flexibility in generating strings, can you give an example?
- **Explain:**
Template literals, also known as template strings, are a new feature introduced in ECMAScript 2015/ ES6[1][2]. They provide an easy way to interpolate variables and expressions into strings[3][4] and create multiline strings[1][5]. Template literals are enclosed by backtick (`) characters instead of double or single quotes[2][4].
- **Use:**
- **Example:**

- [x] Can you give an example of a curry function and why this syntax offers an advantage?
- **Explain:**
Currying is a transformation of functions that translates a function from callable as f(a, b, c) into callable as f(a)(b)(c)[1]
. Advantages of currying include making it easier to create anonymous functions[3]
 and transforming functions to take one parameter at a time[4]
. An example of a curry function is: const curry = (fn) => (x) => (y) => fn(x, y)[2]

- **Use:**
- **Example:**

- [x] What are the benefits of using spread syntax and how is it differenct from rest syntax?
- **Explain:**
The spread syntax expands the elements of an array or object into individual variables, while rest syntax condenses multiple elements into a single element[1][2][3]. Spread syntax is useful for copying arrays and objects, as well as combining them[1][2]. Rest syntax is useful for gathering the rest of the list of arguments into an array[4].
- **Use:**
- **Example:**

- [x] How can you share code between files?
- **Explain:**
To share code between files in JavaScript, use the export and import statement[1][2]. This allows us to share code between files using the native ES6 module system[2], making code reuse easy while organizing large projects[3]. An example of this is exporting variables or functions from an ES6 module in a service component and importing them into other components[4].
- **Use:**
- **Example:**

- [x] Why you migh want to create static class members?
- **Explain:**
Static class members are useful when a field needs to exist only once per class, not on every instance created
. This is beneficial as the compiler can check to make sure that no instance members are accidentally added, and static data is initialized to zero when the first object is created
. Static methods are typically used to implement functions that belong to the class as a whole, but not to any particular object of it

- **Use:**
- **Example:**

### General Questions

- [x] Can you name two programming paradigms important for JavaScript app developers?
- **Explain:**
Two important programming paradigms for JavaScript app developers are object-oriented programming and functional programming Other paradigms include imperative/procedural programming, declarative programming, and event-driven programming

- **Use:**
- **Example:**

- [x] What is functional programming?
- **Explain:**
Functional programming in JavaScript is a sub-paradigm of the Declarative programming paradigm, where functions are treated as first-class citizens[1][2][3][4][5]. It involves writing code without mutating state and data[1], and allows for passing functions as values[3]. Examples of functional programming in JavaScript include passing functions as arguments to other functions, using higher order functions, and using recursion[5]
- **Use:**
- **Example:**

- [x] What is the difference between classical inheritance and prototypal inheritance?
- **Explain:**
The difference between classical inheritance and prototypal inheritance is that classical inheritance is limited to classes inheriting from other classes while prototypes act as more of a chain[1][2]. In classical inheritance, Generalizations (like the overarching Shoe concept) are just other Objects[3], while in prototypal inheritance, objects are abstractions of real-world entities[4][5].
- **Use:**
- **Example:**

- [x] What are the pros and cons of functional programming vs object-oriented programming?
- **Explain:**
Functional programming and object-oriented programming are two different paradigms of programming, each with its own advantages and disadvantages. Object-oriented programming (OOP) is procedural programming that uses classes to group code and data together for reusability and simplicity[1], while functional programming (FP) is a declarative programming model that emphasizes the importance of functions over data[2]. OOP works great when the behaviors are fixed but the data types change[3], while FP is a better option when all the objects are clear but the behaviors vary[3]. OOP languages allow developers to establish multiple degrees of visibility for properties and methods, such as private or public[4], while FP does not give importance to data but to functions[2].
- **Use:**
- **Example:**

- [x] What are two-way data binding and one-way data flow, and how are they different?
- **Explain:**
The difference between two-way data binding and one-way data flow is that two-way data binding provides the ability to take the value of a property and display it on the view while also having an input to automatically update the data
, while one-way data binding is a situation where information flows in only one direction, typically from a data source to the control[3]

- **Use:**
- **Example:**

- [x] What is asynchronous programming, and why is it important in JavaScript?
- **Explain:**
Asynchronous programming in JavaScript enables programs to start long-running tasks and still be able to respond to other events while the task runs[1][2]. This is done through callback functions, promises, and async and await[3][4][5], which allow programs to execute code in the background without blocking the main thread. An example of this is a program that fetches two resources from the network and then combines them[3].
- **Use:**
- **Example:**
