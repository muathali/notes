# Angular Material

Add Angular Material Module to your Application

```shell
ng add @angular/material 
ng g m material --flat -m app
```

> Note the use of the `--flat` flag, which indicates that an additional directory shouldn't be created for material.module.ts. Also, note that `-m`, an alias for `--module`, is specified so that our new module is automatically imported into `app.module.ts`.

```
npm i @angular/flex-layout
```

For a richer set of icons, check out MaterialDesignIcons.com. This icon set contains the base set of Material icons, plus a rich set of third-party icons that contains useful imagery from social media sites for a rich set of actions that cover a lot of ground. This font is 118 KB in size.

## Angular Material schematics

Since Angular 6 and the introduction of schematics, libraries like Material can provide their own code generators. At the time of publication, Angular Material ships with three rudimentary generators to create Angular components with a side navigation, a dashboard layout, or a data table. You can read more about generator schematics at  https://material.angular.io/guide/schematics.
