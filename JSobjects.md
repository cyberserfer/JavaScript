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

To call a method within an object:
```
myCoffee.reheat();
```
