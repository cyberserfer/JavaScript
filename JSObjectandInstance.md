# Object type and object instance

Suppose you want to create an object type for cars. You want this type of object to be called car, and you want it to have properties for make, model, and year. To do this, you would write the following function:
```
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}
```
Now you can create an object called mycar as follows:
```
var mycar = new Car('Eagle', 'Talon TSi', 1993);
```
This statement creates mycar and assigns it the specified values for its properties. Then the value of mycar.make is the string "Eagle", mycar.year is the integer 1993, and so on.

You can create any number of car objects by calls to new. For example:
```
var kenscar = new Car('Nissan', '300ZX', 1992);
```
