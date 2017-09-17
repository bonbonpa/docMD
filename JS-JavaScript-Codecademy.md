#
Note\*\*

## JS Course Codecademy

### Introduction to Object II

##### 1. An Objective Review

--- **Literal notation** creates a single object. Literal notation uses curly brackets `{ }`and the object's default properties are defined within the brackets using `property:value` notation.

--- **Constructor** notation involves defining an object constructor. And like defining a function, we use the `function` keyword. You can think of this constructor as a "template" from which you can create multiple objects. To create a new object from a constructor, we use the new keyword.

```javascript
var james = {
// add properties to this object!
job : "programmer",
married : false

};

function Person(job, married) {
this.job = job;
this.married = married;
}

// create a "gabby" object using the Person constructor!
var gabby = new Person('student',true);
```

---

##### 2. Fun with Functions

Recall that we can add methods \(i.e., functions associated with objects\) to a constructor:

```javascript
function someObject() {

this.someMethod = function() {
};

}
```

Suppose we said `var someObj = new someObject();`. When we call `someObj.someMethod()`, the code

```javascript
function Person(job, married) {
this.job = job;
this.married = married;
// add a "speak" method to Person!
this.speak = function(){
console.log('Hello!');
};
}

var user = new Person("Codecademy Student",false);
user.speak();

//result
Hello!
```

---

##### 3. Literally Speaking

In the last exercise, we added methods to objects via constructor notation. We can also add methods to objects in literal notation:

```javascript
var someObj = {

aProperty: value,
someMethod: function(some, params) { }

};
```

When we call `someObj.someMethod(some, values);`, the code between the curly brackets `{ }` will run.

```javascript
var james = {
job: "programmer",
married: false,
speak: function(param) {
console.log('Hello, I am feeling ' + param);
}
};

james.speak("great");
james.speak("just okay");

//result
Hello, I am feeling great
Hello, I am feeling just okay
```

---

##### 4. Can I See Your References?

Remember when defining a method for an object, it's easy to reference other properties in that object: just use `this.propertyName`!

When that method is called, `this.propertyName` will always refer to the most recent value of `propertyName`.

```javascript
var james = {
job: "programmer",
married: false,
sayJob: function() {
// complete this method
console.log('Hi, I work as a ' + this.job);
}
};

// james' first job
james.sayJob();

// change james' job to "super programmer" here
james.job = 'super programmer';

// james' second job
james.sayJob();

//result
Hi, I work as a programmer
Hi, I work as a super programmer
```

---

##### 5. Who's in Your Bracket?

And finally, let's go over retrieving property values. Throughout this section, we've been using **dot notation** to get the value of an object's property:

```javascript
someObj.propName;
```

However, remember that we can also use **bracket notation**:

```javascript
someObj["propName"];
```

An advantage of bracket notation is that we are not restricted to just using strings in the brackets. We can also use variables whose values are property names:

```javascript
var someObj = {propName: someValue};
var myProperty = "propName";
someObj[myProperty];
```

The last line is exactly the same as using `someObj["propName"];`.

```javascript
var james = {
job: "programmer",
married: false
};

// set to the first property name of "james"
var aProperty = 'job';
// print the value of the first property of "james"
// using the variable "aProperty"
console.log(james[aProperty]);

//result
programmer
```

---

##### 6. I.D., Please

Alright! Let's get our hands dirty and start exploring some really cool stuff about objects in JavaScript. But before we can do that, how can we even tell if something is an object \(as opposed to, say, a number or string\)? It would be great if we could tell what type something is in JavaScript. Good thing there's a handy built-in operator to do this!

Say we have a variable `thing`and we don't know what type `thing` is. We can call `typeof thing` to figure this out. Generally, the most useful types are "number," "string," "function," and of course, "object."

As an example, the following example will print `"object"`:

```javascript
var someObject = {someProperty: someValue};
console.log( typeof someObject );
```

```javascript
// complete these definitions so that they will have
// the appropriate types
var anObj = { job: "I'm an object!" };
var aNumber = 42;
var aString = "I'm a string!";

console.log( typeof anObj ); // should print "object"
console.log( typeof aNumber ); // should print "number"
console.log( typeof aString ); // should print "string"

//result
object
number
string
```

---

##### 7. Know Thyself

In the last exercise, we used `typeof`to figure out what type a variable in JavaScript is. Since we know how to tell objects apart from everything else now, let's focus on them.

You wouldn't know it, but every object in JavaScript comes with some baggage \(stay tuned for more on this!\). Part of this baggage includes a method called `hasOwnProperty`. This lets us know if an object has a particular property.

We show how to use `hasOwnProperty` in the last two lines. It returns `true` or `false`, based on whether an object has a certain property.

```javascript
var myObj = {
// finish myObj
name : 'chaiwud'

};

console.log( myObj.hasOwnProperty('name') ); // should print true
console.log( myObj.hasOwnProperty('nickname') ); // should print false

//result
true
false
```

---

##### 8. Dressed to Impress

Let's get some practice working with `hasOwnProperty`. It is an invaluable tool when working with objects!

Try to run the code in the editor as it is. You should get an error because `shorts` is not a property of the `suitcase` object.

Let's write some code to test for this so we can avoid this nasty error later.

```javascript
var suitcase = {
shirt: "Hawaiian"
};

//console.log(suitcase.shorts);
if(suitcase.hasOwnProperty('shorts')){
console.log(suitcase.shorts);
}
else{
suitcase.shorts = 'evn';
console.log(suitcase.shorts);
}

//result
evn
```

---

##### 10. List ALL the Properties!

We've just seen how to print all of an object's property names with a for-in loop. But how do we print out all the values associated with every property? Surprise! The for-in loop will be our friend again! Let's get there slowly. Our dog object can help us.

```javascript
var dog = {
species: "bulldog",
age: 3,
color: brown
};
```

First, remember that
`dog.species = dog["species"] = "bulldog";`

And if we say:

`var x = "species";`

then

`dog[x] = "bulldog";`

We see that by assigning the property name to a variable, we can then use the variable name in bracket notation to get the property's value. So to get all the values from the dog object, we would use the for-in loop and the bracket notation we just saw above. See the hint to see the code to print the property values for `dog`.

```javascript
var nyc = {
fullName: "New York City",
mayor: "Bill de Blasio",
population: 8000000,
boroughs: 5
};

// write a for-in loop to print the value of nyc's properties

for(var setup in nyc){
console.log(nyc[setup]);
}

//result
New York City
Bill de Blasio
8000000
5
```

---

##### 11. Class is in Session

Alright, it's time to learn the basics of **object-oriented programming** Often abbreviated OOP, this is a very important programming paradigm that is widely used in the industry today.

Let's start by introducing classes. We learned in the last course that constructors are a way to make objects, but they actually do even more than that.

When you make a constructor, you are in fact defining a new **class**. A class can be thought of as a type, or a category of objects—kind of like how `Number` and `String` are types in JavaScript.

Take a look at our `Person` example taken from Introduction to Objects I. In this case `bob` and `susan` are two separate objects, but both belong to the class `Person`.

```javascript
function Person(name,age) {
this.name = name;
this.age = age;
}

// Let's make bob again, using our constructor
var bob = new Person("Bob Smith", 30);
var susan = new Person("Susan Jordan", 35);

// make your own class here
function Circle(in_radius){
this.radius = in_radius ;
}
```

---

##### 12. Teach Snoopy

So we know that a class will have certain properties and methods, but what keeps track of what a given class can or can't do? What a class has or doesn't have? That is the job of the **prototype**.

JavaScript automatically defines the prototype for class with a constructor. For example, our `Dog` constructor ensures that the `Dog` prototype has a `breed` property. Remember, the `Dog` prototype keeps track of what `Dog` has, doesn't have, can, or can't do.

We know we can add methods to objects, and in line 7 we add the `bark` method to `buddy`. Hit run and you will see one `"Woof"` printed when `buddy` barks. Notice what happens when we try to get snoopy to bark in line 17 though. Even though `snoopy` is of the class `Dog`, he doesn't know how to bark because only `buddy` had `bark` added as a method.

```javascript
function Dog (breed) {
this.breed = breed;
}

// here we make buddy and teach him how to bark
var buddy = new Dog("Golden Retriever");
buddy.bark = function() {
console.log("Woof");
};
buddy.bark();

// here we make snoopy
var snoopy = new Dog("Beagle");
// we need you to teach snoopy how to bark here
snoopy.bark = function(){
console.log("Woof");
};
// this causes an error, because snoopy doesn't know how to bark!
snoopy.bark();

//result
Woof
Woof
```

---

##### 13. How do Classes Help Us?

Classes are very important in object-oriented programming. This is because a class tells us helpful information about objects, and you can think of an object as a particular instance of a class.

For example, look at our `Person` class again in the console. We know that any `Person` will have a `name` and `age`, because they are in the constructor. This allows us to create a function like `printPersonName`, which will take a `Person` as an argument and print out their name. We know the function will work on any `Person`, because `name` is a valid property for that class.

```javascript
function Person(name,age) {
this.name = name;
this.age = age;
}
// a function that prints the name of any given person
var printPersonName = function (p) {
console.log(p.name);
};

var bob = new Person("Bob Smith", 30);
printPersonName(bob);

// make a person called me with your name and age
// then use printPersonName to print your name
var me = new Person("Art",22);
printPersonName(me);

//result
Bob Smith
Art
```

---

##### 14. Prototype to the Rescue

Here we have very similar code as last time, but there is an important difference. Instead of using `buddy.bark` to add the bark method to just the `buddy` object, we use `Dog.prototype.bark`.

Click run this time, and both `buddy` and `snoopy` can bark just fine! `Snoopy` can bark too even though we haven't added a bark method to that object. How is this so? Because we have now changed the prototype for the class `Dog`. **This immediately teaches all **`Dogs`** the new method**.

In general, if you want to add a method to a class such that all members of the class can use it, we use the following syntax to extend the prototype:

```javascript
className.prototype.newMethod =

function() {
statements;
};
```

```javascript
function Dog (breed) {
this.breed = breed;
};

// here we make buddy and teach him how to bark
var buddy = new Dog("golden Retriever");
Dog.prototype.bark = function() {
console.log("Woof");
};
buddy.bark();

// here we make snoopy
var snoopy = new Dog("Beagle");
/// this time it works!
snoopy.bark();

//result
Woof
Woof
```

---

##### 15. Prototype Practice

Here we have created a new class, `Cat`, and its constructor. We also have two cats that would like to meow, but currently `Cats` have no `meow` method.

```javascript
function Cat(name, breed) {
this.name = name;
this.breed = breed;
}

// let's make some cats!
var cheshire = new Cat("Cheshire Cat", "British Shorthair");
var gary = new Cat("Gary", "Domestic Shorthair");

// add a method "meow" to the Cat class that will allow
// all cats to print "Meow!" to the console
Cat.prototype.meow = function(){
console.log("Meow!");
}

// add code here to make the cats meow!
cheshire.meow();
gary.meow();

//result
Meow!
Meow!
```

---

##### 16. It's All in the Genes

In object-oriented programming, **inheritance** allows one class to see and use the methods and properties of another class. You can think of it as a child being able to use his or her parent's money because the child inherits the money.

We will learn more about inheritance as we continue this lesson, but for now let's just refresh our memories about how classes and objects work.

```javascript
// create your Animal class here
function Animal(name,numLegs){
this.name = name ;
this.numLegs = numLegs ;
}

// create the sayName method for Animal
Animal.prototype.sayName = function(){
console.log("Hi my name is "+ this.name );
}

// provided code to test above constructor and method
var penguin = new Animal("Captain Cook", 2);
penguin.sayName();

//result
Hi my name is Captain Cook
```

---

##### 17. Marching Penguins

Let's say we're dealing with a lot of `Penguins`. It sure would be nice to create a Penguin class so that perhaps later we can give it some methods unique to a penguin and not confuse it with the `Animal` class.

```
function Animal(name, numLegs) {
this.name = name;
this.numLegs = numLegs;
}
Animal.prototype.sayName = function() {
console.log("Hi my name is " + this.name);
};


// create a Penguin constructor here
function Penguin(name, numLegs) {
this.name = name;
this.numLegs = numLegs;
}

// create a sayName method for Penguins here
Penguin.prototype.sayName = function(){
console.log("Hi my name is " + this.name);
};

// our test code
var theCaptain = new Penguin("Captain Cook", 2);
theCaptain.sayName();

//result
Hi my name is Captain Cook
```

---

##### 18. DRY Penguins

Creating a brand new `Penguin` was nice, but we did end up reusing a lot of the same code as the `Animal` class. This goes against the "DRY" principle of programming: Don't Repeat Yourself.

Inheritance can help us here! A `Penguin` is an `Animal`, so they should have all the same properties and methods as `Animal`. Whenever this **X is-a Y** relationship exists, there's a good chance that we should be using inheritance.

Remember, inheritance lets us see and use properties and methods from another class. To say that `Penguin` inherits from `Animal`, we need to set Penguin's `prototype` to be `Animal`.

```javascript
// the original Animal class and sayName method
function Animal(name, numLegs) {
this.name = name;
this.numLegs = numLegs;
}
Animal.prototype.sayName = function() {
console.log("Hi my name is " + this.name);
};

// define a Penguin class
function Penguin(name){
this.name= name;
this.numLegs = 2;
}

// set its prototype to be a new instance of Animal
Penguin.prototype = new Animal();
```

---

##### 19. Black \(and White\) Penguin Magic

Now for some black magic and to see the power of inheritance!

We never defined a `sayName` method for `Penguin`, but what happens when we try to call it?

```javascript
// the original Animal class and sayName method
function Animal(name, numLegs) {
this.name = name;
this.numLegs = numLegs;
}
Animal.prototype.sayName = function() {
console.log("Hi my name is " + this.name);
};

// define a Penguin class
function Penguin(name){
this.name= name;
this.numLegs = 2;
}

// set its prototype to be a new instance of Animal
Penguin.prototype = new Animal();

var penguin = new Penguin("pender");
penguin.sayName();

//result
Hi my name is pender
```

###### 20. Penguins, Properties, and the Prototype

We saw in the last exercise how `Penguin` inherited the `sayName` method from `Animal`. We now explore how classes can inherit properties as well.

For simplicity, we've defined a new `Penguin` class that doesn't inherit anything from `Animal`.

```javascript
function Penguin(name) {
this.name = name;
this.numLegs = 2;
}

// create your Emperor class here and make it inherit from Penguin
function Emperor(name){
this.name = name;
}

Emperor.prototype = new Penguin();

// create an "emperor" object and print the number of legs it has
var emperor = new Emperor("Pennaja");
console.log(emperor.numLegs);

//result
2
```

###### 21. Up the Food-I-mean-Prototype Chain

A penguin is an animal and an emperor penguin is a penguin. Are emperor penguins animals too? Of course!

The "prototype chain" in JavaScript knows this as well. If JavaScript encounters something it can't find in the current class's methods or properties, it looks up the prototype chain to see if it's defined in a class that it inherits from. This keeps going upwards unt```````il it stops all the way at the top: the mighty````Object.prototype`(more on this later). By default, all classes inherit directly from Object, unless we change the class's`prototype`, like we've been doing for`Penguin`and`Emperor\`\`\`.

```javascript
// original classes
function Animal(name, numLegs) {
this.name = name;
this.numLegs = numLegs;
this.isAlive = true;
}
function Penguin(name) {
this.name = name;
this.numLegs = 2;
}
function Emperor(name) {
this.name = name;
this.saying = "Waddle waddle";
}

// set up the prototype chain
Penguin.prototype = new Animal();
Emperor.prototype = new Penguin();

var myEmperor = new Emperor("Jules");

console.log(myEmperor.saying); // should print "Waddle waddle"
console.log(myEmperor.numLegs); // should print 2
console.log(myEmperor.isAlive); // should print true

//result
Waddle waddle
2
true
```

---

##### 22. Open to the Public

In JavaScript all properties of an object are automatically public. **Public** means that they can be accessed outside the class. Think of these properties as the information a class is willing to share.

Look at the `Person` class. It has 3 public properties: `firstName`, `lastName`, and `age`. On lines 8 and 9, we access the `firstName` and `lastName` properties of `john` and assign them to `myFirst` and `myLast`.

Notice that we are free to access the `firstName` and `lastName` properties, which is what we mean when we say they are public.

```javascript
function Person(first,last,age) {
this.firstName = first;
this.lastName = last;
this.age = age;
}

var john = new Person('John','Smith',30);
var myFirst = john.firstName;
var myLast = john.lastName;

//declare variable myAge set to the age of the john object.
var myAge = john.age ;
```

##### 23. Private Variables

Good! But what if an object wants to keep some information hidden?

Just as functions can have local variables which can only be accessed from within that function, objects can have private variables. **Private** variables are pieces of information you do not want to publicly share, and they can only be directly accessed from within the class.

The `Person` class has been modified to have a private variable called `bankBalance`. Notice that it looks just like a normal variable, but it is defined inside the constructor for `Person` without using `this`, but instead using `var`. This makes `bankBalance` a private variable.

```javascript
function Person(first,last,age) {
this.firstname = first;
this.lastname = last;
this.age = age;
var bankBalance = 7500;
}

// create your Person
var john = new Person("bla" ,"jama", 35);

// try to print his bankBalance
console.log(john.bankBalance);

//result
undefined
```

##### 24. Accessing Private Variables

Although we cannot directly access private variables from outside the class, there is a way to get around this. We can define a public method that returns the value of a private variable.

```javascript
function Person(first,last,age) {
this.firstname = first;
this.lastname = last;
this.age = age;
var bankBalance = 7500;

this.getBalance = function() {
// your code should return the bankBalance
return bankBalance ;
};
}

var john = new Person('John','Smith',30);
console.log(john.bankBalance);

// create a new variable myBalance that calls getBalance()
var myBalance = john.getBalance();
console.log(myBalance);

//result
undefined
7500
```

---

##### 25. Private Methods

Why did that code work? An object's private variables can only be accessed by other methods that are part of that same object. So, we just used an object's public method to access a private variable!

Methods can also be private within a class and inaccessible outside of the class. Changing `this.returnBalance` from the last exercise to `var returnBalance` makes this method private. If you run the program trying to access the method you get an undefined\`\`\`\`\`\` error this time.

The way to access a private method is similar to accessing a private variable. You must create a public method for the class that returns the private method.

```javascript
function Person(first,last,age) {
this.firstname = first;
this.lastname = last;
this.age = age;
var bankBalance = 7500;

var returnBalance = function() {
return bankBalance;
};

// create the new function here
this.askTeller = function(){
return returnBalance;
};
}

var john = new Person('John','Smith',30);
console.log(john.returnBalance);
var myBalanceMethod = john.askTeller();
var myBalance = myBalanceMethod();
console.log(myBalance);

//result
undefined
7500
```

---

##### 26. Passing Arguments

The `askTeller` function has been modified within the `Person` class to directly give you your balance. However, it now needs the account password in order to return the `bankBalance`.

```javascript
function Person(first,last,age) {
this.firstname = first;
this.lastname = last;
this.age = age;
var bankBalance = 7500;

this.askTeller = function(pass) {
if (pass == 1234) return bankBalance;
else return "Wrong password.";
};
}

var john = new Person('John','Smith',30);
/* the variable myBalance should access askTeller()
with a password as an argument */
var myBalance = john.askTeller(1234);

console.log(myBalance);

//result
7500
```

---

##### 27. Looks For-In To Me

Objects aren't so foreign if you really think about it!

Remember you can figure out the type of a variable by using `typeof myVariable`;. Types we are concerned with for now are `"object"`, `"string"`, and `"number"`.

Recall the `for-in` loop:

```javascript
for(var x in obj) {
executeSomething();
}
```

This will go through all the properties of `obj` one by one and assign the property name to `x` on each run of the loop.

Let's combine our knowledge of these two concepts.

```javascript
var languages = {
english: "Hello!",
french: "Bonjour!",
notALanguage: 4,
spanish: "Hola!"
};

// print hello in the 3 different languages
for(var x in languages){
var a = languages[x] ;
if(typeof(a) == "string"){
console.log(a);
}
}

//result
Hello!
Bonjour!
Hola!
```

##### 28. Hello? Yes, This is Dog

We should all know by now what's so cool about using `prototype`: we can define a method for a class, and any instance of the class \(i.e., object created using that class's constructor\) can use that method.

Remember that classes and the prototype are important to OOP!

```javascript
function Dog (breed) {
this.breed = breed;
};

// add the sayHello method to the Dog class
// so all dogs now can say hello
Dog.prototype.sayHello = function(){
console.log("Hello this is a " + this.breed + " dog");
};

var yourDog = new Dog("golden retriever");
yourDog.sayHello();

var myDog = new Dog("dachshund");
myDog.sayHello();

//result
Hello this is a golden retriever dog
Hello this is a dachshund dog
```

---

##### 29. So Meta I Can't Take It!

Do you remember how we said every JavaScript object has some baggage associated with it? Part of this baggage was the `hasOwnProperty` method available to all objects. Now let's see where this came from...

If we have just a plain object \(i.e., not created from a class constructor\), recall that it automatically inherits from `Object.prototype`. Could this be where we get `hasOwnProperty` from? How can we check?

```javascript
// what is this "Object.prototype" anyway...?
var prototypeType = typeof Object.prototype;
console.log(prototypeType);

// now let's examine it!
var hasOwn = Object.prototype.hasOwnProperty("hasOwnProperty");
console.log(hasOwn);

//result
object
true
```

---

##### 30. Private Eye

Recall that:

--- **Public** properties can be accessed from outside the class
--- **Private** properties can only be accessed from within the class
Using constructor notation, a property declared as `this.property = "someValue;"` will be public, whereas a property declared with `var property = "hiddenValue;"` will be private.

In this exercise, hit run and you'll see that all your grades are exposed! You really just want people to know your overall GPA.

```javascript
function StudentReport() {
var grade1 = 4;
var grade2 = 2;
var grade3 = 1;
this.getGPA = function() {
return (grade1 + grade2 + grade3) / 3;
};
}

var myStudentReport = new StudentReport();

for(var x in myStudentReport) {
if(typeof myStudentReport[x] !== "function") {
console.log("Muahaha! " + myStudentReport[x]);
}
}

console.log("Your overall GPA is " + myStudentReport.getGPA());

//result
Your overall GPA is 2.3333333333333335
```

end

---

### Building a Cash Register

##### 1. Shut the Shop!

You are working for a large supermarket and the cash register has just failed. The boss is not happy as he can't make any money.

To save the day it happens that you let slip to your boss that you know JavaScript and can build a quick virtual cash register until head office sends support staff.

Your boss is over the moon and wants you to get started right away.

```javascript
//Create the object called cashRegister
//and initialize its total property
var cashRegister = {
total : 0
};

//Using dot notation change the total property
cashRegister.total = 2.99;

//result
2.99
```

---

##### 2. Manually Add It Up?

Great! The bossman can see that you can tell the cash register the total. But we need the cash register to do more.

Your boss wants a way to manually `add` the cost of each item. We have written the add method for you. There are two things we should note.

1. We are using literal notation to include the method add.

2. We've used the `+=` operator. This is a shorthand way of saying

```
this.total = this.total + itemCost;
```

In general, `a += b;` means "add `b` to `a` and put the result of that addition back into `a`. This is also available for the other basic arithmetic functions: `-=`, `*=`, and `/=` do what you expect.

```javascript
var cashRegister = {
total:0,
add: function(itemCost){
this.total += itemCost;
}
};


//call the add method for our items
cashRegister.add(0.98);
cashRegister.add(1.23);
cashRegister.add(4.99);
cashRegister.add(0.45);
//Show the total bill
console.log('Your bill is '+cashRegister.total);

//result
Your bill is 7.65
```

##### 3. Short-Term Memory

But this method only works as long as you can remember the cost of every item in the store. We need something like a bar code scanner where just knowing the item name will automatically add the cost of that item to the total.

So we create a method called `scan`. This method takes some `item` parameter, and adds the cost of this `item` to the `total`. `item` is a string.

We also use a `switch` statement. Previously, we would have probably used multiple `if-else` statements. Here, things work in a similar way.

For example, if the item is`"eggs"` \(line 8\), we then call the `add` method, passing through `0.98` as the `itemCost`. This will add `0.98` to `cashRegister.total`. If instead the `item` is `"milk"` or `"chocolate"` or `"magazine"`, the relevant `itemCost` is added. Note no `default` case is needed for this switch statement.

```javascript
var cashRegister = {
total: 0,
//insert the add method here
add: function(itemCost){
this.total += itemCost;
}
,
scan: function (item) {
switch (item) {
case "eggs":
this.add(0.98);
break;
case "milk":
this.add(1.23);
break;
//Add other 2 items here
case "magazine":
this.add(4.99);
break;
case "chocolate":
this.add(0.45);
break;
}
return true;
}
};

//Scan 2 eggs and 3 magazines
cashRegister.scan("eggs");
cashRegister.scan("eggs");
cashRegister.scan("magazine");
cashRegister.scan("magazine");
cashRegister.scan("magazine");
//Show the total bill
console.log('Your bill is '+cashRegister.total);

//result
Your bill is 16.93
```

---

##### 4. I Have to Scan It More Than Once?

Is that a smile on the boss's face? Well, there was one until he realized that your system requires every item to be scanned individually. He finds this pretty inefficient and you probably agree. Let's get real—it was pretty annoying having to call the scan method five times in the previous exercise!

What can we do? What is the limitation of the `scan` method? Well, it has just one parameter, `item`, and you can't specify anything related to quantity.

```javascript
var cashRegister = {
total:0,
add: function(itemCost){
this.total += itemCost;
},
scan: function(item,quantity) {
switch (item) {
case "eggs": this.add(0.98 * quantity); break;
case "milk": this.add(1.23 * quantity); break;
case "magazine": this.add(4.99 * quantity); break;
case "chocolate": this.add(0.45 * quantity); break;
}
}
};

// scan each item 4 times
cashRegister.scan("eggs",4);
cashRegister.scan("milk",4);
cashRegister.scan("magazine",4);
cashRegister.scan("chocolate",4);
//Show the total bill
console.log('Your bill is '+cashRegister.total);

//result
Your bill is 30.6
```

##### 5. Bleep Bleep

The boss looks down at his pager to see Register 8 needs assistance. They have scanned an item too many times and need to void the last transaction.

So he turns to you and says: "Okay JavaScript Ninja! What do we do now?!"

```javascript
var cashRegister = {
total:0,
//Dont forget to add your property
lastTransactionAmount : 0,
add: function(itemCost) {
this.total += itemCost;
this.lastTransactionAmount = itemCost;
},
scan: function(item,quantity) {
switch (item) {
case "eggs": this.add(0.98 * quantity); break;
case "milk": this.add(1.23 * quantity); break;
case "magazine": this.add(4.99 * quantity); break;
case "chocolate": this.add(0.45 * quantity); break;
}
return true;
},
//Add the voidLastTransaction Method here
voidLastTransaction : function(){
this.total -= this.lastTransactionAmount;
}

};

cashRegister.scan('eggs',1);
cashRegister.scan('milk',1);
cashRegister.scan('magazine',1);
cashRegister.scan('chocolate',4);

//Void the last transaction and then add 3 instead
cashRegister.voidLastTransaction();
cashRegister.scan('chocolate',3);

//Show the total bill
console.log('Your bill is '+cashRegister.total);

//result
Your bill is 8.55
```

##### 6. Over the Moon

Great! The store is ticking along making money again. The boss is so happy you have just been given a bonus staff discount to the value of 20%.

However the current system doesn't know how to apply the different levels of staff discount that apply. Now the rest of the staff is not happy and demanding you make improvements!

Let's sort it out so that staff can get their well deserved discount.

```javascript
// create a constructor for the StaffMember class
function StaffMember(name, discountPercent){
this.name = name ;
this.discountPercent = discountPercent;
}

var sally = new StaffMember("Sally",5);
var bob = new StaffMember("Bob",10);

//Create a StaffMember for yourse
```

##### 7. You Deserved It!

Whew! It's been a long day fixing cash registers and now let's actually apply our well-earned discount. Now that we have our objects representing the staff, let's update our cash register to actually apply the discount.

```javascript
function StaffMember(name,discountPercent){
this.name = name;
this.discountPercent = discountPercent;
}

var sally = new StaffMember("Sally",5);
var bob = new StaffMember("Bob",10);

// Create yourself again as 'me' with a staff discount of 20%
var me = new StaffMember("ART",20);

var cashRegister = {
total:0,
lastTransactionAmount: 0,
add: function(itemCost){
this.total += (itemCost || 0);
this.lastTransactionAmount = itemCost;
},
scan: function(item,quantity){
switch (item){
case "eggs": this.add(0.98 * quantity); break;
case "milk": this.add(1.23 * quantity); break;
case "magazine": this.add(4.99 * quantity); break;
case "chocolate": this.add(0.45 * quantity); break;
}
return true;
},
voidLastTransaction : function(){
this.total -= this.lastTransactionAmount;
this.lastTransactionAmount = 0;
},
// Create a new method applyStaffDiscount here
applyStaffDiscount : function(employee){
this.total -= (this.total * (employee.discountPercent /100));
}

};

cashRegister.scan('eggs',1);
cashRegister.scan('milk',1);
cashRegister.scan('magazine',3);
// Apply your staff discount by passing the 'me' object
// to applyStaffDiscount
cashRegister.applyStaffDiscount(me);

// Show the total bill
console.log('Your bill is '+cashRegister.total.toFixed(2));


//result
Your bill is 13.74
```
