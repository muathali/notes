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
