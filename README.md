# Design_Pattern.md
It's a markdown format. Codes were written in VS-Code and it's raw copy. 
# Introduction: 

We write code to solve problems. These problems usually have many similarities, and, when trying to solve them, we notice several common patterns. This is where design patterns come in.

A **design pattern** is a term used in software engineering for a general, reusable solution to a commonly occurring problem in software design.

# Categories of Design Patterns:

*Design patterns are usually categorized into three major groups.here are three types of design patterns*

1. Creational Design Pattern

1. Structural Design Pattern

1. Behavioral Design Pattern

## Creational Design Patterns:

As the name suggests, these patterns are for handling object creational mechanisms. **A creational design pattern basically solves a problem by controlling the creation process of an object.**

## Structural Design Patterns:

These patterns are concerned with class and object composition. They help structure or restructure one or more parts without affecting the entire system. In other words, **they help obtain new functionalities without tampering with the existing ones.**

## Behavioral Design Patterns:

**These patterns are concerned with improving communication between dissimilar objects.**

* Constructor Pattern: 

    **Constructor pattern is one of the most commonly used patterns in JavaScript for creating new objects of a given kind. It is a class-based pattern that uses the constructors present in the class to create specific types of objects. There are many ways to create objects in JavaScript, such as using the {} notation or using Object.create.** 

```javascript

function Human(name, age, occupation){

    // defining properties inside the constructor function

    // constructor initializing the property values upon object creation

    this.name = name;

    this.age = age;

    this.occupation = occupation;

    // defining a method inside the constructor function

    this.describe = function(){

        console.log('${this.name} is a ${this.age} year old ${this.occupation}');

    }

}

// creating a "person" object using the Human constructor 

var person = new Human("Sanjoy", "20", "Engineer");

// calling the describe method for the person object

person.describe();

```

* Factory Pattern:

**Factory pattern is another class-based creational pattern.

This pattern is frequently used when we need to manage or manipulate collections of objects that are different yet have many similar characteristics.**

```javascript

function Car(name, type) {

  this.name = name;

  this.type = type;

}

function Truck(name, type) {

  this.name = name;

  this.type = type;

}

function VehiclesFactoryMethod() {

  this.create = function(name, type) {

      switch(type) {

         case "Car":

           return new Car(name, type);

         case "Truck":

           return new Truck(name, type);

         default;

      }

  }

}

// Let's instantiate our factory method object.

const VehiclesFactoryMethod = new VehiclesFactoryMethod();

// This array will simulate our Database for the purposes of this tutorial

const vehicles = [];

// Let's fill our array with some vehicles!

vehicles.push(VehiclesFactoryMethod.create("BMW", "Car"));

vehicles.push(VehiclesFactoryMethod.create("MAN", "Truck"));

```

* Singleton Pattern:

**The singleton pattern is used in scenarios when we need exactly one instance of a class. For example, we need to have an object which contains some configuration for something. In these cases, it is not necessary to create a new object whenever the configuration object is required somewhere in the system.**

```javascript

var singleton = (function() {

    // private singleton value which gets initialized only once

    var config;

    function initializeConfiguration(values){

        this.randomNumber = Math.random();

        values = values || {};

        this.number = values.number || 5;

        this.size = values.size || 10;

    }

    // we export the centralized method for retrieving the singleton value

    return {

        getConfig: function(values) {

            // we initialize the singleton value only once

            if (config === undefined) {

                config = new initializeConfiguration(values);

            }

            // and return the same config value wherever it is asked for

            return config;

        }

    };

})();

var configObject = singleton.getConfig({ "size": 8 });

// prints number: 5, size: 8, randomNumber: someRandomDecimalValue

console.log(configObject);

var configObject1 = singleton.getConfig({ "number": 8 });

// prints number: 5, size: 8, randomNumber: same randomDecimalValue as in first config

console.log(configObject1);

```

* Prototype Pattern:

**The prototype pattern is based on prototypical inheritance whereby objects created to act as prototypes for other objects. In reality, prototypes act as a blueprint for each object constructor created.**

```javascript

var myCar= {

name:"Ford",

brake:function(){

console.log("Stop! I am applying brakes");

}

Panic : function (){

console.log ( "wait. how do you stop thuis thing?")

}

}

// use objec create to instansiate a new car

var yourCar= object.create(myCar);

//You can now see that one is a prototype of the other

console.log (yourCar.name);

```

* Module Design Pattern:

**In the module design pattern, there is an improvement from the prototype pattern. The different types of modifiers (both private and public) are set in the module pattern. You can create similar functions or properties without conflicts.**

```javascript

function AnimalContainter () {

const container = [];

function addAnimal (name) {

container.push(name);

}

function getAllAnimals() {

return container;

}

function removeAnimal(name) {

const index = container.indexOf(name);

if(index < 1) {

throw new Error('Animal not found in container');

}

container.splice(index, 1)

}

return {

add: addAnimal,

get: getAllAnimals,

remove: removeAnimal

}

}

const container = AnimalContainter();

container.add('Hen');

container.add('Goat');

container.add('Sheep');

console.log(container.get()) //Array(3) ["Hen", "Goat", "Sheep"]

container.remove('Sheep')

console.log(container.get()); //Array(2) ["Hen", "Goat"]

```

# Conclusion:

***It is beneficial for JavaScript developers to use design patterns. Some major advantages of using design patterns include project maintainability and also cuts off unnecessary work on the development cycle. Even though JavaScript design patterns can provide solutions to complex problems, needless to say, rapid development and productivity, it is improper to conclude that these design patterns can replace the developers.***

# References:

1. Youtube Videos

1. Websites

1. Google

## Resources:

* [DevSage Youtube Channel](http;//youtu.be/kuirGzhGhyw)

* [TopTal](https://www.toptal.com/javascript/comprehensive-guide-javascript-design-patterns)

* [Telerik](https://www.telerik.com/blogs/design-patterns-in-javascript)

* [CodeSource](https://codesource.io/javascript-design-patterns/)

## Project Owner:

| name | email id | contat number |

| ---| ---|----|

| ShawanBasu|shawan.basu@mountblue.tech| 8910919085|

| SHAWAN|connectshawan@gmail.com|+918910919085|

## ThankYou

### Date: ***~~10/02/2021~~***
