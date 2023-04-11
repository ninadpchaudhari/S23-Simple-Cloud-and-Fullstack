# Basics of JavaScript
1. Controlling ASync function calls.\
* JS is single thereaded, blocking & Synchronous. It SUPPORTS async behaviour.(i.e. some functions are defined as async)
* It essentially has an execution stack and an event queue.
* Things are added to this execution stack, but messages can be left into the event queue in async way.
* The job of the Event loop is to look into the call stack and determine if the call stack is empty or not. If the call stack is empty, it looks into the message queue to see if there’s any pending callback waiting to be executed.
Unlike other languages, if 2 function calls are made after each other,
Function callback is a process of one function calling the other function once the first function is done it's job. We can use Callbacks or Promises to sync function calls. \\

Essentially, when we call an external API / make a DB call, it does not make sense for a language to keep the function on the top of the execution stack. Hence instead of keeping it in the top of the stack, we have the power to instruct browser engine / nodejs to put a message in the event queue once it is done fetching the DB or api call.


2. Promises\
Promises can be used to make async code synced. [Here](https://stackoverflow.com/questions/40029867/trying-to-implement-a-simple-promise-in-reactjs) is a good answer for using Promises with ReactJS.

3. Variables, Functions & Es6 syntax.
varibles can be declared in various ways. You can use `var, let or const` keywords to declare a variable. They differ by the scope. `var` has function scope, `let` & `const` have block scope. As name might suggest a `const` creates immutable variables.

ES6 classes can be used to delcare classes in JS. You can have inheritance in ES6 classes. A good example for everything in these classes : [es6 class sample](https://googlechrome.github.io/samples/classes-es6/)\

You can declare functions using the `arrow` syntax as well. These functions are same to the functions declared by using the `function` keyword.\
Eg: These are equavalent 
```javascript
// Function Expression
const doubleEXP = function(num){
  return num * 2;
}
// Arrow Function
const doubleARR = (num) => {
  return num * 2;
}
```

<details>
<summary> References </summary>

[Understanding async javascript](https://blog.bitsrc.io/understanding-asynchronous-javascript-the-event-loop-74cd408419ff)\
[When is JS async](https://stackoverflow.com/questions/2035645/when-is-javascript-synchronous)\
[What the hell is a promise](https://medium.com/better-programming/is-javascript-synchronous-or-asynchronous-what-the-hell-is-a-promise-7aa9dd8f3bfb)

[var, let & const](https://stackoverflow.com/questions/21237105/const-in-javascript-when-to-use-it-and-is-it-necessary)\
[Arrow Functions](https://codeburst.io/javascript-understand-arrow-function-syntax-ab4081bba85b)\
[W3Schools - Extreme basic JS reference](https://www.w3schools.com/js/default.asp)
</details>
