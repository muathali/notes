# C\#

## Helpful Commands

```bash
dotnet --list-sdks
dotnet --list-runtimes
Cmd+Shift+M go to problems
```

## General Notes

- Although .NET 5 has dropped the word Core in its branding, ASP.NET Core and Entity Framework Core will retain the word Core to help differentiate from older legacy versions of those technologies.
- In addition to removing large pieces from .NET Framework in order to make .NET Core, Microsoft has componentized .NET into NuGet packages, those being small chunks of functionality that can be deployed independently.
- Good Practice: When you try to use Go To Definition, you will sometimes see an error saying No definition found. This is because the C# extension does not know about the current project. Navigate to View | Command Palette, enter and select OmniSharp: Select Project, and then select the correct project that you want to work with.

## Language Feature

- The C# vocabulary is made up of **keywords**, **symbol characters**, and **types**. Some of the symbol characters include ", ', +, -, *, /, %, @, and $
- In C#, every **type** can be categorized as a `class`, `struct`, `enum`, `interface`, or `delegate`. The C# keyword string is a class, but int is a struct. So, it is best to use the term type to refer to both.
- C# has an operator named sizeof() that returns the number of bytes that a type uses in memory
- With C# 9, Microsoft introduced another syntax for instantiating objects known as target-typed new. When instantiating an object, you can specify the type first and then use new without repeating the type

```cs
XmlDocument xml3 = new(); // target-typed new in C# 9
```

- You can determine the default value of a type using the `default()` operator
- A reference type variable can have a null value, which is **a literal that indicates that the variable does not reference anything** (yet). null is the default for all reference types.
- if you are trying to use a member of a variable that might be `null`, use the null-conditional operator `?.`, as shown in the following code:

```cs
string authorName = null; // the following throws a NullReferenceException
int x = authorName.Length; // instead of an exception, null is assigned to y
int? y = authorName?.Length;
```

- Sometimes you want to either assign a variable to a result or use an alternative value, such as 3, if the variable is null. You do this using the **null-coalescing operator, ??**, as shown in the following code:

```cs
// result will be 3 if authorName?.Length is null
var result = authorName?.Length ?? 3;
Console.WriteLine(result);

```

### Literals

A literal is a notation that represents a fixed value. Data types have different notations for their literal value

- **Literal string**: Characters enclosed in double-quote characters. They can use escape characters like \t for tab.
- **Verbatim string**: A literal string prefixed with @ to disable escape characters so that a backslash is a backslash.
- **Interpolated string**: A literal string prefixed with $ to enable embedded formatted variables.

### Doubles and Decimals

- The **double** type is not guaranteed to be accurate because some numbers literally cannot be represented as floating-point values.
- The decimal type is accurate because it stores the number as a large integer and shifts the decimal point. For example, 0.1 is stored as 1, with a note to shift the decimal point one place to the left. 12.75 is stored as 1275, with a note to shift the decimal point two places to the left
- **Good Practice**: Use int for whole numbers and double for real numbers that will not be compared to other values. Use decimal for money, CAD drawings, general engineering, and wherever the accuracy of a real number is important.
- The double type has some useful special values: `double.NaN` means not-a-number, `double.Epsilon` is the smallest positive number that can be stored in a double, and `double.Infinity` means an infinitely large value.
- A literal number with a decimal point is inferred as double unless you add the M suffix, in which case, it infers a decimal variable, or the F suffix, in which case, it infers a float variable.
