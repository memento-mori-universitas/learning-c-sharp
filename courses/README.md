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
