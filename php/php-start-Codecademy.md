#
PHP

## Conditionals and Control Flow

##### 1. Comparisons
So far we've seen:

-- `strings` (e.g. "dogs go woof!")

-- `numbers` (e.g. 4, 10)
Now let's learn about comparison operators.

List of comparison operators:

```
> Greater than
< Less than
<= Less than or equal to
>= Greater than or equal to
== Equal to
!= Not equal to
```

```php

<html>
<head>
<title>Comparing Numbers</title>
</head>
<body>
<p>
<?php
8 < 9 ;
?>
</p>
</body>
</html>
```

##### 2. If statements
Nice work on comparisons! Now let's see how we can use comparisons to ask yes or no questions.

Say we want to write a program that asks whether your name is longer than 7 letters. If the answer is yes, we can respond with "You have a long name!" We can do this with an `if` statement:

```php
<?php
$age = 17;

if( $age > 16 ) {
echo "You can drive!";
}
?>
```
An if statement is made up of the if keyword, a condition like we've seen before, and a pair of curly braces { }. If the answer to the condition is yes, the code inside the curly braces will run.

```php
<html>
<head>
</head>
<body>
<p>
<?php
$items = 3; // Set this to a number greater than 5!
if($items < 5) {
echo "You get a 10% discount!";
}
?>
</p>
</body>
</html>

//result
You get a 10% discount!
```

##### 3. Adding an Else
Great! We used an `if` statement to do something if the answer to the condition was yes, or `true` as we say in PHP.

In addition to doing something when the condition is `true`, we can do something else if the condition is `false`. We can do this using an `if / else` statement:

```php
<?php
$name = "Edgar";

if ($name == "Simon") {
print "I know you!";
}
else {
print "Who are you?";
}
?>
```

Just like before, if the condition is `true`, then only the code inside the first pair of curly braces will run. Otherwise, the condition is `false`, so only the code inside the second pair of curly braces after the `else` keyword will run.

In the example above the condition `$name == "Simon"` evaluates to `false` since `$name` is `Edgar`. Since the condition is false, only the code inside the curly braces after the `else` keyword runs, and prints out `Who are you?`

```php
<html>
<head>
</head>
<body>
<p>
<?php
$items = 3;
if($items > 5) {
echo "You get a 10% discount!";
}
else{
echo "You get a 5% discount!";
}
?>
</p>
</body>
</html>

//result
You get a 5% discount!
```

##### 4. All Together Now!
Great work! Now let's practice using if / else statements. Do as much as you can by yourself, but if you need a reminder, click the "Stuck? Get a hint!" button below.

```php
<html>
<head>
</head>
<body>
<p>
<?php
// Write your if/elseif/else statement here!
if(4 < 6){
echo "The Condition is false";
}
else{
echo "The Condition is false";
}
?>
</p>
</body>
</html>

//result
The Condition is True
```
