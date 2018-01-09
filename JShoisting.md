# Hoisting
Key Rules of Hoisting

    Variable declarations rise to the top of their scope like hot air balloons.
    Functions create their own scope and act like cages, preventing declarations from rising out.
    Assignments, or = signs, act like anchors. They stay put, no matter how the code is rearranged.
    let and const will throw an error if called before they get assigned.

## Variable Declaration and Hoisting
  
variable declarations are hoisted to the top of their scope
  
```
console.log(magicalUnicorns);
var magicalUnicorns = "awesome";
```
Here's how the interpreter actually reads the previous example:
```
var magicalUnicorns; // the declaration gets hoisted to the top of the scope by itself
console.log(magicalUnicorns); // we log it as undefined
magicalUnicorns = "awesome"; // the assignment stays exactly where it was
```
***LET***

On the flip side, let does not allow us to do this.
```
console.log(magicalUnicorns); 
let magicalUnicorns = "awesome!";
```
In the above example, let will produce ReferenceErrors if we try to call the variable this way.

## Hoisting in Functions

We talked earlier that function calls create their own scope. How do you think the next snippet will run?
```
var foo = "bar";
function magic(){
    foo = "hello world";
    console.log(foo);
    var foo;
}
magic();
console.log(foo);
```
When you run this code, what are your console logs and in what order? The answer might be a surprise. Let's break it down.
```
var foo;                  // 'foo' is a declaration, it's global and gets hoisted
function magic(){         // 'magic()' also gets hoisted to the top
    var foo;              // here 'foo' is declared within 'magic()' and gets hoisted
    foo = "hello world";  // we assign a value to our function scoped 'foo'
    console.log(foo);     // we log it as 'hello world'
}                       
foo = "bar";              // here, we assign a value to the global 'foo'
magic();                  // magic is called, the first console.log runs
console.log(foo);         // finally we log the global foo
```
Another thing to remember is that standalone functions also get hoisted. Let's see if you can predict the output of this next example without running it:
```
magicalUnicorns();
var magicalUnicorns = function(){
    console.log("Will it blend?");
}
console.log("Don't breath this!");
```
Which console log fires first? Neither! We get the error 'magicalUnicorns is not a function'. Why? The variable magicalUnicorns got hoisted to the top, and we tried to invoke it before we assigned the function to it.
