# JavaScript Objects

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
