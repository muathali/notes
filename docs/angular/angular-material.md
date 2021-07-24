# Angular Material

## Installing Angular Material dependencies

```bash
npm install @angular/material @angular/cdk  @angular/animations hammerjs
```

## Adding Google Material Icons Font

Add this to our index.html:

```html
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```

## Choosing a Theme

inside `node_modules/@angular/material/prebuild-themes`

We can for example use the Indigo Pink theme by adding this line to our styles.css file:

```angular
@import "~@angular/material/prebuilt-themes/indigo-pink.css";
```
