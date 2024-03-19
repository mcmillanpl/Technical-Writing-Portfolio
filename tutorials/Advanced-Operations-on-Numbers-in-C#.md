# Advanced Operations on Numbers in C#

In this module, you will practice further with number operations in C#. This tutorial contains two exercises on converting one unit of measure to another. Once you’ve calculated the data, you will also display that information in a formatted message to the user. By the end of this module, you will be able to write code that performs more advanced operations on literal and variable values.

**NOTE:** you can also experience this module on teachable.com as an interactive course by visiting: https://pamela-mcmillan-s-school.teachable.com/purchase?product_id=5305079 

## Learning Objective

In this module, you will:
-	convert one unit into another using a method
-	share information with the user in a formatted message

## Prerequisites
-	Experience with basic C# syntax rules
-	Experience with displaying a message to a console using the ``Console.WriteLine`` and ``Console.Write methods``
-	Experience with creating literal values and declare variables of basic data types like ``string``, ``int``, and ``decimal``
-	Experience with string concatenation and string interpolation

## Exercise – Convert Celsius to Fahrenheit
Methods are blocks of code within C# that contain statements and are used to perform certain actions as defined by the programmer. They are important because they can encapsulate a block of code that can then be used repeatedly and save space within the program. 

In this exercise, we will be using a method to convert a Fahrenheit temperature to Celsius. 

To start this exercise, you will need to create a class called ``Conversion``. Make sure to define the entry point of the program as ``static void Main``. 

Your code should look like:

```C#
 class Conversion
 {
     static void Main()
     {
  
     }
 }	
```

Next, you will need to define your temperature variables. The first, labeled ``fahrenheit``, will be used in the method for conversion. The second, labeled ``celsius``, will store the output. 
At this stage in the creation of the method, the ``celsius`` variable will be unassigned. We will add a method to it later.

**NOTE:** Both variables should have the type ``decimal`` as they will not always be integers. 

Copy the following into your class:

```C#
decimal fahrenheit = 90m;
 decimal celsius;
```

Your code should now look like:

```C#
class Conversion
 {
     static void Main()
     {
         decimal fahrenheit = 90m;
         decimal celsius;
     }
 }
```

## Define the method
Now that your class is defined, you will now create your method. This method will take the value of the ``fahrenheit`` variable and return an equivalent value in Celsius to the ``celsius`` variable. 
In your code, declare a static method called ``F_to_c``, which returns a decimal value and takes a decimal argument named ``temp``. 

**NOTE:** It’s important to set the return value as a decimal because it will not likely be a whole number. The argument must also be a ``decimal`` type because the method will be passed a decimal type when it’s called from the ``Main`` method. 
The code should look like:

 ```C#
static decimal F_to_c(decimal temp)
 {
  
 }
 ```

To define the logic of the method, we will need to add a formula that will convert Fahrenheit to Celsius. 

This formula will look like:

 ```C#
 return (temp - 32m)*(5m / 9m);
```

To finish the conversion, return to the main method and assign the return value of the ``F_to_c`` method to the ``celsius`` variable with a method call. 

**NOTE:** Both the variable and the return value of the method must be of the same type to avoid compilation errors. In this case, the type must be ``decimal``. 

Your code block should now look like this:

```C#
class Conversion
 {
     static decimal F_to_c(decimal temp)
     {
         return (temp - 32m)*(5m / 9m);
     }
  
  
     static void Main()
     {
         decimal fahrenheit = 90m;
         decimal celsius = F_to_c(fahrenheit);
     }
 }
```

Now it’s time to test the method. Do this by adding a ``Console.WriteLine`` or ``Console.Write`` to your code to display the following message to the user. 

``90 degrees Fahrenheit is equal to 32.222222222222222222222222225 degrees Celsius.`` 

Your code should look like:

  ```C#
class Conversion
  {
      static decimal F_to_c(decimal temp)
      {
          return (temp - 32m)*(5m / 9m);
      }
   
   
      static void Main()
     {
         decimal fahrenheit = 90m;
         decimal celsius = F_to_c(fahrenheit);
  
         Console.WriteLine($"{fahrenheit} degrees Fahrenheit is equal to {celsius} degrees      Celsius");
     }
 }
```

Run your code and your result should be:
``90 degrees Fahrenheit is equal to 32.222222222222222222222222225 degrees Celsius.``


## Recap
Here’s what you learned about advanced operations in numbers:
-	How to create a method.
-	How to pass variables to a method.
-	Store the return value of the method in a variable.
-	The variable being passed into the method and the argument the method accepts must be the same type to avoid compilation errors.
-	The return type of the method must match the variable that it is stored in to avoid compilation errors.

## Challenge – Convert Feet to Meters
Now it’s time to apply what you’ve learned by converting feet to meters. You’ll print the result in a message to the user. 

1.	Clear your code editor or start a new program.
2.	Create a class called ``Conversion`` and define the entry point of the program as ``static void Main``. 
3.	Enter the following code into the ``Main`` method: ``decimal feet = 12.6m;``
4.	Create another ``decimal`` variable for ``meters``. 
5.	Create a static method that returns a decimal value to convert feet to meters, you’ll need to multiple by 0.3048. 
6.	Assign the return value of the method to the ``meters`` variable.
7.	Display the result in a formatted message to say: ``12.6 feet is equal to 3.84048 meters.``

Run your program and check your result. 

Continue to view an example of a solution:

```C#
class conversion
  {
   
      static decimal F_to_m(decimal feet)
      {
          return feet * 0.3048m;
      }
   
      static void Main()
     {
         decimal feet = 12.6m;
         decimal meters = F_to_m(feet);
  
         Console.WriteLine($"{feet} feet is equal to {meters} meters");
     }
 }
```

### Knowledge Check
1.	What is a method?
a.	A type of variable.
b.	A data structure that contains fields.
c.	A block of code that can perform specific tasks.


2.	What should the return type of this method be?

```C#
static _____ Km_to_mi(float Km)
 {
     return Km/1.60934;
 }
```

a.	bool
b.	int
c.	float 


3.	Which method would result in a compilation error?
a.

```C#
static decimal C_to_f(decimal temp)
 {
     return (temp * (9m/5m)) + 32m ;
 }
```

b.

```C#
static int M_to_f(decimal meters)
 {
     return meters/3.28m;
 }
```

c.

```C#
static double Mi_to_km(int miles)
 {
     return miles * 1.60934;
 }
```






Answers
1.	C -  a method is a block of code that performs specific tasks set by the developer.
2.	C – the return type should be float because the variable Km is a ``float`` type.
3.	B – the method return type does not match the type of the calculated value produced by ``meters/3.28m``.
