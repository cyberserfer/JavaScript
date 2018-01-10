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

***this***
by using this on the front of the function name it is publicly available. Without it the items within the function will be private to the function.

```
this.drinkSake = () =>{
        this.health += 10;
    } 
```

## Return types

type of undefined retruns "undefined"

tyep of null will return "object"

