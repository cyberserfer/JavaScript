# Functional Components
  
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

