# logic
  
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
## Loops
For - good when you can determine how many times the loop will need to run.

Do While - will run at least once before the condition is evaluated.

While - evaluates the condition before executing anything.

```
var i = 0;

do {
  console.log(i);
  i++;
} while (i <= 10);

while(i <= 10){
  console.log(i);
  i++;
}
```
## Functions
  
funtions will return "undefined" unless there is an explicit ***return***.

Functions will be denoted with parentesis (). 

Functions should return something.

Functions are values. Can also be consider a var.

Each function has access to all the variables in its ***parent function***.

No function has access to the variables in its ***child functions***.

Your entire .js file can be thought of as the outermost function or 'global' scope.

## Return types

type of undefined retruns "undefined"

tyep of null will return "object"

