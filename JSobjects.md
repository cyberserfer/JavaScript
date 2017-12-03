# JavaScript Objects

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
