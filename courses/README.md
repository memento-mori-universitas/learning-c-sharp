# Learning C# Project
      
## CodeAcademy

- [ ] https://www.codecademy.com/learn/learn-c-sharp

C# is **strongly typed** which requires we specify us to specify the data type we are using. It is also **statically-typed** which means it will check we used the correct type *before* running the program.

### Data Types

https://s3.amazonaws.com/codecademy-content/courses/learn-c-sharp/data-types-variables/C%23+Data+Types+Cheat+Sheet.pdf

Simple example of using the most common types in a program

```
using System;

namespace Form
{
  class Program
  {
    static void Main(string[] args)
    {
    // Create Variables
    string name = "Shadow";
    string breed = "Golden Retriever";
    int age = 5;
    double weight = 65.22;
    bool spayed = true;

      // Print variables to the console
      Console.WriteLine(name);
      Console.WriteLine(breed);
      Console.WriteLine(age);
      Console.WriteLine(weight);
      Console.WriteLine(spayed);
    }
  }
}

```

C# follows this best practices:
 - camelCase style for naming
 - Finishing each statement with a semicolon (;)
 - Reserved words: https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/
 
### Converting Data Types

If we need to change the data type we need to do **data type conversion**. There are a couple ways to do data type conversion:

- Implicit Conversion

Happens automatically if no data will be lost in the converstion. An example would be convertion an integer into a double

```
int myInt = 3;
// Turn it into a decimal
double MyDouble = myInt;
```

- Explicit Conversion

Requires a *cast operator* to convert data type into another.

```
double myDouble = 3.2;

// Round myDouble to the nearest whole number
int myInt = (int)myDouble;
```

For a full list of Convert class built-in methods, check out https://docs.microsoft.com/en-us/dotnet/api/system.convert?view=netframework-4.7.2.

There are some use cases that we cannot cast automatically, so we have to use methods build-in methods. An example of this is converting an string to an integer and vice-versa. https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/how-to-convert-a-string-to-a-number

```
using System;

namespace FavoriteNumber
{
  class Program
  {
    static void Main(string[] args)
    {
      // Ask user for fave number
      Console.Write("Enter your favorite number!: ");
      
       try
       {
           int faveNumber = Convert.ToInt32(Console.ReadLine());
           Console.WriteLine($"Your favorite number is {faveNumber}.");
       }
       catch (FormatException)
       {
           Console.WriteLine("Unable to parse");
       }
        
    }
  }
}
```

### Working with Numbers

In C# we have different type of numbers and depending in our needs we can choose appropiately

**Int**

An int is a whole integer value, it is a good way to count unit of things with them.

**Double and Decimal**

If we need to define a decimal value we have: float, double & decimal.

Those types are good for measuring precise location of an object in 3D space.

A *double* is usually the best choice because it is more precise than a *float* and faster to process than a *decimal*.

However, for financial applications *decimal* is the best choice.

```
// Int
int variableName = 7;

// Double
double variableName = 39.76876;

// Decimal
decimal variableName = 489872.76m;
```

#### Arithemtic Operators

The following arithmetic operators are supported by C#:

```
addition +
subtraction -
multiplication *
division /
```

When using operators, it’s important to pay attention to data types. If we use two integers, it will return an integer every time. However, if we combine an integer with a double, the answer will be a double.

We can also use shorthand operators

```
using System;

namespace MakingProgress
{
  class Program
  {
    static void Main(string[] args)
    {
      // declare steps variable
			int steps = 0;

      // Two steps forward 
			steps = steps + 2;

      // One step back 
			steps = steps--;

      // Print result to the console
			System.Console.WriteLine(steps);
    }
  }
}
```

#### Modulus

A modulus returns the *remainder* of what is left over when we divide a number by another.

```
int eggs = 56;
int crateAmount = 12;

int eggsLeftOver = eggs % crateAmount; 
Console.Write(eggsLeftOver); // prints 8
```

Modulus can also be used to return if a number is odd or even

```
int myNum = 85939824;
Console.Write(myNum % 2); // prints 0, so number is even
```

#### Built-In Methods

This are the most used methods, however there are many more. Please see the documenation here: https://docs.microsoft.com/en-us/dotnet/api

**Math.Abs()** — will find the absolute value of a number. Example: Math.Abs(-5) returns 5.

**Math.Sqrt()** — will find the square root of a number. Example: Math.Sqrt(16) returns 4.

**Math.Floor()** — will round the given double or decimal down to the nearest whole number. Example: Math.Floor(8.65) returns 8.

**Math.Min()** — returns the smaller of two numbers. Example: Math.Min(39, 12) returns 12.

```
using System;

namespace LowestNumber
{
  class Program
  {
    static void Main(string[] args)
    {
      // Starting variables 
      int numberOne = 12932;
      int numberTwo = -2828472;

      // Use built-in methods and save to variable 
			double numberOneSqrt = Math.Floor(Math.Sqrt(numberOne));

      // Use built-in methods and save to variable 
			double numberTwoSqrt = Math.Floor(Math.Sqrt(Math.Abs(numberTwo)));

      // Print the lowest number
			System.Console.WriteLine(Math.Min(numberOneSqrt, numberTwoSqrt));
    }
  }
}

```
