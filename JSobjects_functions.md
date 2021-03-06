# JavaScript Objects
Object
    an Object Constructor is a function that returns objects
    characteristics = properties
    actions = methods

There are three main categories of objects:

    Host Objects - objects defined by the environment in which your code runs (e.g.; a browser) 
    Core Objects - objects built into the languange itself
    Objects defined by the code's author
    
In ES6, class methods are called 'static methods`, while instance methods are called 'prototype methods'.

## Callbacks

While a callback is just a fancy name for a function passed as an argument to another function, it’s also the most common way of writing asynchronous code in JavaScript. By asynchronous code, we just mean the ability to divide your code into portions that run now and later. 

Example:
```
function makePasta(pasta, makeSauce) {
  console.log("Boiling water");
  console.log("Putting " + pasta + " pasta in the water");
  // create a variable for sauce!
  var sauce = makeSauce();          // invoke makeSauce, our callback
  console.log("Mixing sauce");
  console.log("Pasta is done!");
  return pasta + " Pasta with " + sauce + " sauce! Voila!";
}
function makePesto() {
  console.log("Making Pesto");
  return "pesto";
}
function makeAlfredo() {
  console.log("Making Alfredo");
  return "alfredo";
}
// we pass the whole makePesto recipe to makePasta!
console.log(makePasta("Penne", makePesto));
// notice lack of parentheses after makePesto.
// Remember: we want to pass the function, not execute it and pass a return value.
console.log(makePasta("Farfalle", makeAlfredo));
```

Delegated

Here’s another example:
```
// This is a function that just prints the result of another list of instructions
function printResult(doSomething) {
 var result = doSomething();         // store the return value of the callback parameter
 console.log(result);                // print the result!
}
printResult(function returnFive(){ return 5 })  // this should print "5"
```
Pro Tip: JavaScript allows us to pass anonymous functions (e.g. remove returnFive from above and it will still work), but when debugging, giving them a name can really help!

Last Example: The underscore library uses delegation exceptionally effectively: Take a look here: http://underscorejs.org/

Let's recreate the 'each' method using underscore!
```
function each(arr, callback) {
  // loop through the array
  for(var i = 0; i < arr.length; i++) {
    callback(arr[i]); // invoking the callback many times... delegation!
  }
}
// call the each function
each([1,2,3], function(num) { alert(num + " I am from the callback!"); }) //so many alerts!
```


## Object Literal

```
var myCoffee = {
  flavor: "espresso",
  temperature: "piping hot",
  ounces: 100,
  milk: true,
  
  reheat: function() {
    if(myCoffee.temperature === "cold"){
      myCoffee.temperature = "piping hot";
      alert("Your coffee has been reheated.");
    }
  }
};
```

Two ways to set the value in an object:
```
myCoffee.temperature = "cold";
myCoffee["temperature"] = "cold";
```
Note that brackets used with an object is not the same as an array. Therefore you cannot reference values with a number:
```
myCoffee[4];  // does not work
```
To call a method within an object:
```
myCoffee.reheat();
```

## Object Constructor
Used to create multiple instances of an object. Each instance of the object inherits the properties and methods of the constructor.

***Remember: this and new go together. If you're using*** this ***in your Constructor, you must create new instances with new!***

Every object constructor creates a second memory space for all objects created by that constructor that is accessed by proto. It is one memory space, so any changes there affect every object spit out by that constructor.

Note that the name of the object constructor starts with a capital letter.
```
function Friend(name, tshirtColor) {
  this.name = name;
  this.tshirtColor = tshirtColor;
}
```
To use the object constructor you can call it and assign it to a variable.
```
var denny = new Friend("Denny", "green"0");
```
Then you can call the values by using:
```
denny.name
denny.tshirtColor
```

## Example with notation
```
function personConstructor(name, age) {
    // an object literal that will be returned
    const person = {};
    // attributes of a person
    person.name = name;
    person.age = age;
    // when attached to an object or instance, functions are called 'methods'.
    // this is our first method, greet
    person.greet = function(){
        console.log("Hello my name is " + person.name + " and I am " + person.age + " years old!");
    }
    // finally, this function must return an instance
    return person;
}
// create the 'steve' instance, run greet
const steve = personConstructor("Steve", 27);
steve.greet();
// create the 'anika' instance, run greet. note that it is different.
const anika = personConstructor("Anika", 33);
anika.greet();
// finally note how we can refine the greet method for any particular instance
const emily = personConstructor("Emily", 22);
emily.greet = function() {
    console.log("I am the greatest, ever!");
};
emily.greet();
```
