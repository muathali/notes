# Type Script

## Template Literals

The use of the backtick ( ` ) to delineate strings gives us the ability to inject values directly into the string, as follows:

```typescript
var version = `es6`;
console.log(`hello ${version} TypeScript`);
```

## Declaration files

Keep in mind that third-party libraries, such as the inquirer library that we just installed, are published as JavaScript libraries. This means that the TypeScript compiler does not have access to any type annotations that it would have if the library was written in TypeScript. So how does TypeScript enforce strict type checking on external JavaScript libraries?

The solution to this problem is, in fact, surprisingly simple. TypeScript uses files known as declaration files as a sort of header file, similar to languages such as C++, in order to superimpose strong typing on existing JavaScript libraries. These declaration files, which have a .d.ts extension, hold information that describes the available functions and variables that a library exposes, along with their associated type annotations.