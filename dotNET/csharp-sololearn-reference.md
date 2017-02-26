
# SoloLearn C#
------
## Basic Concepts

#### **1. What is C#?**

-- **Welcome to C#**

C# is an elegant object-oriented language that enables developers to build a variety of secure and robust applications that run on the **.NET Framework.**
You can use C# to create Windows applications, Web services, mobile applications, client-server applications, database applications, and much, much more.

> **Quiz**
>
> Q : C# applications run
> A : on the .NET Framework

-- **The .NET Framework**

The .NET Framework consists of the **Common Language Runtime (CLR)** and the .NET Framework **class library.**
The CLR is the foundation of the .NET Framework. It manages code at execution time, providing core services such as memory management, code accuracy, and many other aspects of your code.
The **class library** is a collection of classes, interfaces, and value types that enable you to accomplish a range of common programming tasks, such as data collection, file access, and working with text.
C# programs use the .NET Framework class library extensively to do common tasks and provide various functionalities.

> These concepts might seem complex, but for now just remember that applications written in C# use the **.NET Framework** and its components.

#### **2. Variables**

-- **Variables**

Programs typically use data to perform tasks.
Creating a **variable** reserves a memory location, or a space in memory, for storing values. It is called **variable** because the information stored in that location can be changed when the program is running.
To use a variable, it must first be declared by specifying the **name** and **data type.**
A variable name, also called an **identifier**, can contain letters, numbers and the underscore character (_) and must start with a letter or underscore.
Although the name of a variable can be any set of letters and numbers, the best identifier is **descriptive** of the data it will contain. This is very important in order to create clear, understandable and readable code!

> For example, **firstName** and **lastName** are good descriptive variable names, while **abc** and **xyz** are not.

-- **Variable Types**

A **data type** defines the information that can be stored in a variable, the size of needed memory and the operations that can be performed with the variable.
For example, to store an **integer** value (a whole number) in a variable, use the **int** keyword:
> int myAge;

The code above declares a variable named **myAge** of type **integer**.
> A line of code that completes an action is called a statement. Each statement in C# must end with a **semicolon**.

You can assign the value of a variable when you declare it:
> int myAge = 18;

or later in your code:
> int myAge;
> myAge = 18;

<br>
> Remember that you need to declare the variable before using it.

-- **Built-in Data Types**

There are a number of built-in data types in C#. The most common are:
**int - integer.**
**float** - floating point number.
**double** - double-precision version of float.
**char** - a single character.
**bool** - Boolean that can have only one of two values: True or False.
**string** - a sequence of characters.
The statements below use C# data types:
>**int** x = 42;
**double** pi = 3.14;
**char** y = 'Z';
**bool** isOnline = true;
**string** firstName = "David";

<br>
> Note that **char** values are assigned using single quotes and **string** values require double quotes.
You will learn how to perform different operations with variables in the upcoming lessons!

#### **3. Your First C# Program**

-- **Your First C# Program**

To create a C# program, you need to install an integrated development environment (IDE) with coding and debugging tools.
We will be using **Visual Studio Community Edition**, which is available to download for free.
After installing it, choose the default configuration.
Next, click **File->New->Project** and then choose **Console Application** as shown below:

![csharp](https://api.sololearn.com/DownloadFile?id=2981)

Enter a name for your Project and click OK.
> **Console application** uses a text-only interface. We chose this type of application to focus on learning the fundamentals of C#.

-- **Your First C# Program**

Visual Studio will automatically generate some code for your project:
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace SoloLearn
{
   class Program
   {
      static void Main(string[] args)
      {
      }
   }
}
```

You will learn what each of the statements do in the upcoming lessons.
For now, remember that every C# console application must contain a **method (a function) named Main**. Main is the starting point of every application, i.e. the point where our program starts execution from.

> Quiz
> Q : Every console application in C# should contain
>  A : Main method

-- **Your First C# Program**

To run your program, press **Ctrl+F5**. You will see the following screen:

![](https://api.sololearn.com/DownloadFile?id=2982)

This is a console window. As we did not have any statements in our **Main method,** the program just produces a general message. Pressing any key will close the console.
> Congratulations, you just created your first C# program.
<br>
> Q : Which type of application uses a text-only interface?
> A : Console Application

#### **4. Printing Text**

-- **Displaying Output**

Most applications require some **input** from the user and give **output** as a result.
To display text to the console window you use the **Console.Write** or **Console.WriteLine** methods. The difference between these two is that **Console.WriteLine** is followed by a line terminator, which moves the cursor to the next line after the text output.
The program below will display Hello World! to the console window:

```cs
static void Main(string[] args)
{
   Console.WriteLine("Hello World!");
}
```

[Try it](https://code.sololearn.com/811/#cs)

> Note the **parentheses** after the **WriteLine** __method__ . This is the way to pass data, or arguments, to methods. In our case **WriteLine** is the **method** and we pass "Hello World!" to it as an argument. String **arguments** must be enclosed in quotation marks.

-- **Displaying Output**

We can display variable values to the console window:

```cs
static void Main(string[] args)
{
   int x = 89;
   Console.WriteLine(x);
}
// Outputs 89
```
[Try It](https://code.sololearn.com/812/#cs)

To display a **formatted** [string](#), use the following syntax:
```cs
static void Main(string[] args)
{
   int x = 10;
   double y = 20;

   Console.WriteLine("x = {0}; y = {1}", x, y);
}
// Output: x = 10; y = 20
```
[Try It](https://code.sololearn.com/813/#cs)

As you can see, the value of **x** replaced **{0}** and the value of **y** replaced **{1}.**
> You can have as many variable placeholders as you need. (i.e.: {3}, {4}, etc.).

#### **5. Getting User Input**

User Input

You can also prompt the user to enter data and then use the **Console.ReadLine** [method](#) to assign the input to a [string](#) variable.
The following example asks the user for a name and then displays a message that includes the input:

```cs
static void Main(string[] args)
{
   string yourName;
   Console.WriteLine("What is your name?");

   yourName = Console.ReadLine();

   Console.WriteLine("Hello {0}", yourName);
}
```
[Try it](https://code.sololearn.com/814/#cs)

The **Console.ReadLine** [method](#) waits for user input and then assigns it to the variable. The next statement displays a formatted [string](#) containing Hello with the user input. For example, if you enter David, the output will be Hello David.
> Note the empty parentheses in the **ReadLine** [method](#). This means that it does not take any arguments.
```cs
string temp;
temp = Console .ReadLine();
```
-- **User Input**

The **Console.ReadLine()** [method](#) returns a [string](#) value.
If you are expecting another type of value (such as [int](#) or [double](#), the entered data must be converted to that type.
This can be done using the **Convert.ToXXX** methods, where XXX is the .NET name of the type that we want to convert to. For example, methods include **Convert.ToDouble** and **Convert.ToBoolean.**
For [integer](#) conversion, there are three alternatives available based on the bit size of the [integer](#): **Convert.ToInt16, Convert.ToInt32** and **Convert.ToInt64**. The default [int](#) type in C# is 32-bit.
Let’s create a program that takes an integer as input and displays it in a message:

```cs
static void Main(string[] args)
{
  int age = Convert.ToInt32(Console.ReadLine());
  Console.WriteLine("You are {0} years old", age);
}
```
[Try It](https://code.sololearn.com/815/#cs)

If, in the program above, a non-[integer](#) value is entered (for example, letters), the **Convert** will fail and cause an error.

```cs
double n;
string x = "77";
n = Convert .ToDouble (x);
```

#### **6. Comments**

Comments

**Comments** are explanatory statements that you can include in a program to benefit the reader of your code.
The compiler ignores everything that appears in the comment, so none of that information affects the result.

A comment beginning with two slashes (//) is called a single-line comment. The slashes tell the compiler to ignore everything that follows, until the end of the line.
```cs
 // Prints Hello
Console.WriteLine("Hello");
```
[Try It](https://code.sololearn.com/816/#cs)

> When you run this code, Hello will be displayed to the screen. The // Prints Hello line is a comment and will not appear as output.

-- **Multi-Line Comments**

Comments that require multiple lines begin with /* and end with */ at the end of the comment block.
You can place them on the same line or insert one or more lines between them.

```cs
/* Some long
    comment text
*/
int x = 42;
Console.WriteLine(x);
```
[Try It](https://code.sololearn.com/817/#cs)

> Adding comments to your code is good programming practice. It facilitates a clear understanding of the code for you and for others who read it.

#### **7. The var Keyword**

-- **The var Keyword**

A variable can be explicitly declared with its type before it is used.
Alternatively, C# provides a handy function to enable the compiler to determine the **type** of the variable automatically based on the expression it is assigned to.
The var keyword is used for those scenarios:
```cs
var num = 15;
```
> The code above makes the compiler determine the type of the variable. Since the value assigned to the variable is an [integer](#), the variable will be declared as an  [integer](#) automatically.

-- **The var Keyword**

Variables declared using the **var** keyword are called **implicitly typed** variables.
Implicitly typed variables **must** be initialized with a value.
For example, the following program will cause an error:

```cs
var num;
num = 42;
```
> Although it is easy and convenient to declare variables using the **var** keyword, overuse can harm the readability of your code. Best practice is to explicitly declare variables.

<br>
> What is the output of this code?
var n1;
n1 = true;
Console.WriteLine(n1);
//error

#### **8. Constants**

**Constants** store a value that cannot be changed from their initial assignment.
To declare a constant, use the **const** modifier.
For example:

```cs
const double PI = 3.14;
```

The value of const PI cannot be changed during program execution.
For example, an assignment statement later in the program will cause an error:

```cs
const double PI = 3.14;
PI = 8; //error
```

> Constants **must** be initialized with a value when declared.

```cs
const int num = 2;
```

#### **9. Arithmetic Operators**

-- **Operators**

An **operator** is a symbol that performs mathematical or logical manipulations.

**Arithmetic Operators**
C# supports the following arithmetic operators:

![link](https://api.sololearn.com/DownloadFile?id=2449)

For example:

```cs
int x = 10;
int y = 4;
Console.WriteLine(x-y);

//Outputs 6
```

[Try it](https://code.sololearn.com/818/#cs)

```cs
int x = 42;
int y = 7;
int z = x*y;
Console.WriteLine(z);
```

-- **Division**

The division operator (/) divides the first operand by the second. If the operands are both integers, any remainder is dropped in order to return an [integer](#) value.
```cs
Example:
int x = 10 / 4;
Console.WriteLine(x);

// Outputs 2
```
[Try It](https://code.sololearn.com/819/#cs)
> Division by 0 is undefined and will crash your program.

```cs
//What is the output of this code?

int x = 16;
int y = 5;
Console.WriteLine(x/y);

//3
```

-- **Modulus**

The modulus operator (%) is informally known as the remainder operator because it returns the remainder of an integer division.
For example:

```
int x = 25 % 7;
Console.WriteLine(x);
// Outputs 4
```
[Try it](https://code.sololearn.com/820/#cs)

-- **Operator Precedence**

Operator **precedence** determines the grouping of terms in an expression, which affects how an expression is evaluated. Certain operators take higher precedence over others; for example, the multiplication operator has higher precedence than the addition operator.
For example:

```cs
int x = 4+3*2;
Console.WriteLine(x);
// Outputs 10
```
[Try It](https://code.sololearn.com/821/#cs)

The program evaluates 3*2 first, and then adds the result to 4.
As in mathematics, using **parentheses** alters operator precedence.

```cs
int x = (4 + 3) *2;
Console.WriteLine(x);
// Outputs 14
```
[Try It](https://code.sololearn.com/822/#cs)

The operations within parentheses are performed first. If there are parenthetical expressions nested within one another, the expression within the innermost parentheses is evaluated first.
> If none of the expressions are in parentheses, multiplicative (multiplication, division, modulus) operators will be evaluated before additive (addition, subtraction) operators. Operators of equal precedence are evaluated from left to right.
```cs
int x = (2 + 3) * 3;
Console.WriteLine(x);
```

#### **10. Assignment & Increment Operators**

-- **Assignment Operators**

The = **assignment** operator assigns the value on the right side of the operator to the variable on the left side.

C# also provides **compound assignment operators** that perform an operation and an assignment in one statement.
For example:
```cs
int x = 42;
x += 2; // equivalent to x = x + 2
x -= 6; // equivalent to x = x - 6
```

[Try it](https://code.sololearn.com/823/#cs)

-- **Assignment Operators**

The same shorthand syntax applies to the multiplication, division, and modulus operators.
```cs
x *= 8; // equivalent to x = x * 8
x /= 5; // equivalent to x = x / 5
x %= 2; // equivalent to x = x % 2
```

-- **Increment Operator**

The **increment** operator is used to increase an [integer's](#) value by one, and is a commonly used C# operator.

```cs
x++; //equivalent to x = x + 1
```

For example:

```cs
int x = 10;
x++;
Console.WriteLine(x);
//Outputs 11
```
[Try it](https://code.sololearn.com/824/#cs)


-- **Prefix & Postfix Forms**

The increment operator has two forms, **prefix** and **postfix.**
```cs
++x; //prefix
x++; //postfix
```

**Prefix** increments the value, and then proceeds with the expression.
**Postfix** evaluates the expression and then performs the incrementing.

**Prefix example:**

```cs
int x = 3;
int y = ++x;
// x is 4, y is 4
```
[Try it](https://code.sololearn.com/825/#cs)

**Postfix example:**

```cs
int x = 3;
int y = x++;
// x is 4, y is 3
```
[Try It](https://code.sololearn.com/826/#cs)

> The **prefix** example increments the value of x, and then assigns it to y.
The **postfix** example assigns the value of x to y, and then increments x.

**Quiz**
> Q : What's the difference between ++x and x++?
> A : ++x increments x's value before using it
> A : x++ uses x's value then increments it

-- **Decrement Operator**

The decrement operator (--) works in much the same way as the increment operator, but instead of increasing the value, it decreases it by one.
```cs
--x; // prefix
x--; // postfix
```
**Quiz Module**

 ```cs

 static void Main(string[] args)   {
	 string msg = "Hello";
	Console.WriteLine(msg);
}
 ```

-----

## Conditionals and Loops

#### **1. The if-else Statement**

-- **The if Statement**

The **if** statement is a conditional statement that executes a block of code when a condition is true.
The general form of the **if** statement is:

```cs
if (condition)
{
    // Execute this code when condition is true
}
```

The condition can be any expression that returns true or false.
For example:

```cs
static void Main(string[] args)
{
   int x = 8;
   int y = 3;

   if (x > y)
   {
      Console.WriteLine("x is greater than y");
   }
}
```

[Try It](https://code.sololearn.com/827/#cs)

The code above will evaluate the condition **x > y**. If it is true, the code inside the if block will execute.
> When only one line of code is in the if block, the curly braces can be omitted.
For example:
if (x > y)
Console.WriteLine("x is greater than y");

```cs
int age = 24;
if(age > 16)
{
 Console.WriteLine("Welcome");
}
```

-- **Relational Operators**

Use **relational operators** to evaluate conditions. In addition to the less than (<) and greater than (>) operators, the following operators are available:

![](https://api.sololearn.com/DownloadFile?id=2455)


**Example:**

```cs
if (a == b) {
  Console.WriteLine("Equal");
}
// Displays Equal if the value of a is equal to the value of b
```

**The else Clause**

An optional **else** clause can be specified to execute a block of code when the condition in the if statement evaluates to **false**.
**Syntax**:

```cs
if (condition)
{
   //statements
}
else
{
   //statements
}
```

For example:

```
int mark = 85;

if (mark < 50)
{
   Console.WriteLine("You failed.");
}
else
{
   Console.WriteLine("You passed.");
}

// Outputs "You passed."
```

[Try it](https://code.sololearn.com/829/#cs)

```cs
int a = 42;
int b = 88;
if(a > b)
{
  Console.WriteLine(a);
}
else
{
  Console.WriteLine(b);
}
```

-- **Nested if Statements**

You can also include, or **nest**, if statements within another if statement.
**For example:**

```cs
int mark = 100;

if (mark >= 50) {
  Console.WriteLine("You passed.");
  if (mark == 100) {
    Console.WriteLine("Perfect!");
  }
}
else {
  Console.WriteLine("You failed.");
}

/*Outputs
You passed.
Perfect!
*/
```
[Try It](https://code.sololearn.com/830/#cs)

You can nest an unlimited number of if-else statements.
For example:

```cs
int age = 18;
if (age > 14) {
  if(age > 18) {
    Console.WriteLine("Adult");
  }
  else {
    Console.WriteLine("Teenager");
  }
}
else {
  if (age > 0) {
    Console.WriteLine("Child");
  }
  else {
    Console.WriteLine("Something's wrong");
  }
}
//Outputs "Teenager"
```
[Try It](https://code.sololearn.com/831/#cs)

> Remember that all **else** clauses must have corresponding **if** statements.

**Quiz**

```cs
//What is the output of this code?
int a = 8;
int b = ++a;
if(a > 5)
   b -= 3;
else
   b = 9;
Console.WriteLine(b);
//6
```

-- **The if-else if Statement**

The **if-else if** statement can be used to decide among three or more actions.
**For example:**

```cs
int x = 33;

if (x == 8) {
   Console.WriteLine("Value of x is 8");
}
else if (x == 18) {
   Console.WriteLine("Value of x is 18");
}
else if (x == 33) {
   Console.WriteLine("Value of x is 33");
}
else {
   Console.WriteLine("No match");
}
//Outputs "Value of x is 33"
```
[Try it](https://code.sololearn.com/832/#cs)

> Q : How many nested if statements can an if statement contain?
> A : As many as you want

#### **2. The switch Statement**

--


----------


 **switch**

The switch statement provides a more elegant way to test a variable for equality against a list of values.
Each value is called a case, and the variable being switched on is checked for each switch case.
For example:
```cs
int num = 3;
switch (num)
{
  case 1:
   Console.WriteLine("one");
   break;
  case 2:
   Console.WriteLine("two");
   break;
  case 3:
   Console.WriteLine("three");
   break;
}
//Outputs "three"
```
Try It Yourself

Each case represents a value to be checked, followed by a colon, and the statements to get executed if that case is matched.
A switch statement can include any number of cases. However, no two case labels may contain the same constant value.
The break; statement that ends each case will be covered shortly.
