# C Sharp

```bash
dotnet --list-sdks
dotnet --list-runtimes
```

Entity Framework (EF) 6 is an object-relational mapping technology that is designed to work with data that is stored in relational databases such as Oracle and Microsoft SQL Server. It has gained baggage over the years, so the cross-platform API has been slimmed down, has been given support for non-relational databases like Microsoft Azure Cosmos DB, and has been renamed Entity Framework Core. You will learn about it in Chapter 11, Working with Databases Using Entity Framework Core.

More Information: Although .NET 5 has dropped the word Core in its branding, ASP.NET Core and Entity Framework Core will retain the word Core to help differentiate from older legacy versions of those technologies, as explained at the following link:
<https://docs.microsoft.com/en-us/dotnet/core/dotnet-five>

In addition to removing large pieces from .NET Framework in order to make .NET Core, Microsoft has componentized .NET into NuGet packages, those being small chunks of functionality that can be deployed independently.

Good Practice: When you try to use Go To Definition, you will sometimes see an error saying No definition found. This is because the C# extension does not know about the current project. Navigate to View | Command Palette, enter and select OmniSharp: Select Project, and then select the correct project that you want to work with.

Top Level coding C# 9

Language Feature Next

The C# vocabulary is made up of keywords, symbol characters, and types.
Some of the symbol characters that you will see include ", ', +, -, *, /, %, @, and $

Cmd+Shift+M go to problems
Ctrl + `  go to terminal

In C#, every type can be categorized as a class, struct, enum, interface, or delegate. The C# keyword string is a class, but int is a struct. So, it is best to use the term type to refer to both.

## Revealing the extent of the C# vocabulary
