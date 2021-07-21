# Learning Angular

## Displaying data from the component

### Interpolation

```html
<span>{{ title }}</span>
```

### Property Binding

```html
<span [innerText]="title"></span>
```

Notice that we bind to the **Document Object Model** (DOM) property of an element, not an HTML attribute, as it looks at first sight.

The property inside square brackets is called the **target property** and is the property of the DOM element into which we want to bind. The variable on the right is called the **template expression** and corresponds to the `public title` property of the component. If the property is not public, the template will not be able to use it.

To better understand how the Angular templating mechanism works, we need to first understand how Angular interacts with attributes and properties. It defines attributes in HTML to initialize a DOM property, and then it uses data binding to interact with the property directly

### Applying styles to the template

The Angular framework provides two types of property binding to set both of them dynamically, **class binding** and **style binding**. We can apply a single class to an HTML element using the following syntax.

```html
<p [class.star]="isLiked"></p>
```

The `star` class will be added to the paragraph element when the isLiked expression is true. Otherwise, it will be removed from the element.
If we want to apply multiple classes simultaneously, we can use the following syntax:

```html
<p [class]="currentClasses"></p>
```

## Getting data from the template (event binding)

An event binding listens for DOM events that occur on the target HTML element and responds to those events by calling corresponding methods in the component.

```html
<button (click)="onClick()">Click me</button>
```

It supports native DOM events that can be found at <https://developer.mozilla.org/en-US/docs/Web/Events>.

The variable on the right is called the **template statement** and corresponds to the `onClick` public method of the component. Component methods must be public for the template to be able to call them.

## Communicating with other components

Angular components expose a public API that allows them to communicate with other components. This API encompasses **input properties**, which we use to feed the component with data. It also exposes **output properties** we can bind event listeners to, thereby getting timely information about changes in the state of the component.

## Directives

There are three types of directives:

- Components are directives with an associated template.
- Structural directives add or remove elements from the DOM.
- Attribute directives modify the appearance or define a custom behavior of a DOM element.

### Transforming elements using directives

The Angular framework includes a set of ready-made structural directives that we can start using straight away:

- **ngIf** adds or removes a portion of the DOM tree based on an expression.
- **ngFor** iterates through a list of items and binds each item to a template.
- **ngSwitch** switches between templates within a specific set and displays each one depending on a condition

## Structure an Angular App

How to create an Angular application that is correctly structured to enforce separation of concerns using modules and services
An Angular module is a TypeScript class marked with the @NgModule decorator, which defines the following properties:

- **declarations**: The components, directives, and pipes that are registered with the module.
- **imports**: Other modules that contain declarations to be used by this module. The Angular CLI defines CommonModule automatically for us in this property. It is a module that is always used in Angular applications because it contains all the built-in directives and pipes that we usually would like to use.
- **exports**: Angular artifacts that are defined in declarations and are available for other modules to use. This is the public API of the module. It defines what is publicly accessible or not. Everything else that's not explicitly exported would be considered private or internal to the module.
- **providers**: Services that are provided from the module and are accessible from any module of the application. We'll learn more about providers in the How dependency injection works in Angular section.
- **bootstrap**: The main component of the application that will be rendered when the application starts up. This property is set only once in the main application module, AppModule, and is usually AppComponent. Typically, you should not change it unless there is a particular reason to do so.Important NoteThe main application module, AppModule, does not need to import CommonModule. Instead, it imports BrowserModule, which is used to run Angular applications in a browser platform that exports CommonModule by itself.

> When creating a new Angular application, the first step is to define the different features our application needs. We should keep in mind that each one should make sense on its own in isolation from the others. Once we've defined the set of features required, we will create a module for each one. Each module will then be filled with the components, directives, pipes, and services that shape the feature it represents. Always remember the principles of encapsulation and reusability when defining your feature set. The second step is to start creating components that will be used to visualize the features on the screen.

## Dependency Injection

Angular components are responsible for the presentation logic and should not be concerned with how to get data, either from a static list or a remote endpoint. They only need to display it in the template. Thus, they delegate business logic to services to handle this type of task.

An Angular service, by default, is not registered with a specific module like components, directives, and pipes are. Instead, it is registered with an injector – the root injector of the Angular application – as defined in the providedIn option

```typescript
import { Injectable } from '@angular/core';
@Injectable({
  providedIn: 'root'
})
export class HeroService {
  constructor() { }
}
```

## Promises

Promises introduce a new way of envisioning asynchronous data management by conforming to a neater and more solid interface. Different asynchronous operations can be chained at the same level and even be split and returned from other functions

### Limitations of Promises

- They cannot be canceled.
- They are immediately executed.
- They are one-time operations only; there is no easy way to retry them.
- They respond with only one value.

## Observables

An observable is an object that maintains a list of dependents, called observers, and informs them about state and data changes by emitting events asynchronously. To do so, the observable implements all of the machinery that it needs to produce and emit such events. It can be fired and canceled any time, regardless of whether it has emitted the expected data already

Observables return a stream of events, and our subscribers receive prompt notification of those events so that they can act accordingly. They do not perform an asynchronous operation and die (although we can configure them to do so), but start a stream of continuous events on which we can subscribe.

That's not all, however. This stream can be a combination of many operations before they hit observers subscribed to it. Just as we can manipulate arrays with methods such as map or filter to transform them, we can do the same with the stream of events that are emitted by observables. This is known as reactive functional programming, and Angular makes the most of this paradigm to handle asynchronous information.
