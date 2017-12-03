# JavaScript Scope
## Global vs Local

Variables will be GLOBAL if defined independently.
```
var example = "value";
```
If the same variale is defined within a function it will only be available to that function. i.e. a LOCAL variable. Note that if you leave off the var
it will be considered GLOBAL.
```
function anExample(){
  var firstExample = "val1";  // will be local
  secondExample = "val2";     // will be global
}
```
