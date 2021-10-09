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
