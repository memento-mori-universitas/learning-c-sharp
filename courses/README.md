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

### Working with Text

Defining a string is as follows:

```
string variableName = "puppy";
```

You can also escape characters with the backslash `\`

```
string withSlash = "Ifemelu said, \"Hello!\"";
```

Inserting a newline requires `\n`

```
string newLine = "Something \n here";
```

#### String Concatenation

String concatenation is when we combine strings using the addition symbol (+), literally adding one string to another. 

```
string yourFaveMusician = "David Bowie";
string myFaveMusician = "Solange";

Console.WriteLine("Your favorite musician is " + yourFaveMusician + " and mine is " + myFaveMusician + ".");
```

Something to remember is that if we want to concatenate a string with another data type, C# will simply convert it to a string.

#### String Interpolation

Another way to append string or concatenate is using interpolation

```
string yourFaveMusician = "David Bowie";
string myFaveMusician = "Solange";

System.Console.WriteLine($"Your favorite musician is {yourFaveMusician} and mine is {myFaveMusician}.");
```

#### Methods of String

.Length;

Returns the length of the string

.IndexOf();

Returns position of character or substring

```
myFaveMusician.Length; // returns the length of the string
myFaveMusician.IndexOf("a"); // returns position of character or substring
```

.Substring()

Grabs part of a string using the specified character position and continues until the end of the string

```
string plantName = "Cactaceae, Cactus";
string commonMame = plantName.Substring(11) // returns Cactus
```

**Bracket Notation**

Uses an integer to identify a particular value in a collection.

```
string plantName = "Cactaceae, Cactus";
int charPosition = plantName.IndexOf("u"); // returns 15
char u = plantName[charPosition]; // returns u
```

Example of return first letter and last name

```
using System;

namespace NameGrab
{
  class Program
  {
    static void Main(string[] args)
    {
      // User Name
      	string name = "Farhad Hesam Abbasi";

      // Get first letter
	int firstLetterPos = name.IndexOf("F");
	char firstLetter = name[firstLetterPos];
	
      // Get last name
	int lastNamePos = name.IndexOf("A");
	string lastName = name.Substring(lastNamePos);
	
      // Print results
	System.Console.WriteLine($"{firstLetter} {lastName}.");

    }
  }
}
```

.ToUpper();

Returns all string in uppercase

.toLower();

Returns all string in lowercase


```
using System;

namespace MovieScript
{
  class Program
  {
    static void Main(string[] args)
    {
      // Script line
      	string script = "Close on a portrait of the HANDSOME PRINCE -- as the BEAST'S giant paw slashes it.";

      // Get camera directions
      	int charPosition = script.IndexOf("Close");
      	int length = "Close on".Length;
      	string cameraDirections = script.Substring(charPosition, length);

      // Get scene description
      	charPosition = script.IndexOf("a portrait");
      	string sceneDescription = script.Substring(charPosition);

      // Make camera directions uppercase
	cameraDirections = cameraDirections.ToUpper();

      // Make scene description lowercase
	sceneDescription = sceneDescription.ToLower();

      // Print results
	System.Console.WriteLine($"{cameraDirections} {sceneDescription}");
    }
  }
}
```
### Logic

In C# we represent booleans with the data type `bool`.

`bool variableName = true;`

#### Comparison Operators

Equals: `==`
Inequality operator: `!=`
Less than: `<`
Greater than: `>`
Less than or equal to: `<=`
Greater than or equal to: `>=`

In practice it would look like so:

```
bool answer = 3 < 75; 
Console.WriteLine(answer); // prints True
```


