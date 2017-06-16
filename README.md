# Angular 2 TypeScript Snippets for Atom

This extension for Atom adds snippets for Angular 2 for TypeScript and HTML.

## Installation

Atom Package: https://atom.io/packages/angular-2-typescript-snippets

```bash
apm install angular-2-typeScript-snippets
```

Or Settings/Preferences ➔ Packages ➔ Search for `angular-2-typeScript-snippets`

## Usage

Type part of a snippet, press `enter`, and the snippet unfolds.

### TypeScript Snippets

|snippet|explanation|
|-------|-----------|
|[ng2-bootstrap](#ng2-bootstrap)          |bootstrap a module|
|[ng2-module](#ng2-module)                |create a module|
|[ng2-component](#ng2-component)          |create a component|
|[ng2-input](#ng2-input)                  |create an input property|
|[ng2-output](#ng2-output)                |create an output event|
|[ng2-directive](#ng2-directive)          |create a directive|
|[ng2-pipe](#ng2-pipe)                    |create a pipe|
|[ng2-routes](#ng2-routes)                |setup routes|
|[ng2-route-path](#ng2-route-path)        |configure single|
|[ng2-service](#ng2-service)              |create a  service|
|[ng2-subscribe](#ng2-subscribe)          |subscribe to an observable|
|[ng2-rx-map](#ng2-rx-map)                |import map-operator |

### HTML Snippets

|snippet                          |
|---------------------------------|
|[ng2-ngClass](#ng2-ngclass)      |
|[ng2-ngFor](#ng2-ngfor)          |
|[ng2-ngIf](#ng2-ngif)            |
|[ng2-ngModel](#ng2-ngmodel)      |
|[ng2-property](#ng2-property)    |
|[ng2-event](#ng2-event)          |
|[ng2-routerLink](#ng2-routerlink)|
|[ng2-ngStyle](#ng2-ngstyle)      |
|[ng2-ngSwitch](#ng2-ngswitch)    |

Alternatively, press `Ctrl`+`Space` (Windows, Linux) or `Cmd`+`Space` (OSX) to activate snippets from within the editor.

## Known Issues

It seems that you need to have a `tsconfig.json` to get the TypeScript snippets to work.

## Snippets in Detail

No one wants to buy a pig in a poke.
The following section will show you what the provided snippets actually do for you.

### ng2-bootstrap

`ng2-bootstrap` allows you to start your root module to get your app up and running.
It also prepares `enableProdMode()` for you.

```ts
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { enableProdMode } from '@angular/core';
import { <module-name> } from './<path-to-module>.module';

//enableProdMode(); //Uncomment for production
platformBrowserDynamic().bootstrapModule(<module-name>);
```

### ng2-module

`ng2-module` provides a skeleton for an Angular 2 module.

```ts
import { NgModule } from '@angular/core';

@NgModule({
  imports: [<Modules>],
  declarations: [<Components>, <Directives>],
  providers: [<Services>]
})
export class <ModuleName> { }
```

### ng2-component

`ng2-component` provides a skeleton for an Angular 2 Component.
It saves you time typing the mandatory Decorator properties.

```ts
import { Component, OnInit } from '@angular/core';

@Component({
  selector: '<selector>',
  templateUrl: '<component-name>.component.html',
})
export class <ComponentName>Component implements OnInit {
  constructor() {  }

  ngOnInit() {}
}
```

### ng2-input

`ng2-input` is a handy snippet to add an input property to a component class.

```ts
@Input() <peroperty>: <type>;
```

### ng2-output

`ng2-output`generates a output event in a component class.

```ts
@Output() <event>: EventEmitter<type> = new EventEmitter();
```

### ng2-import

`ng2-import` gives you a shorthand writing import-statements.

```ts
import {<Module or Component>} from '<path to component>';
```

### ng2-directive

`ng2-directive` provides a skeleton for an Angular 2 Attribute or Structural Directive.

```ts
import { Directive, Input } from '@angular/core';

@Directive({ selector: '[<selector>]' })
export class [DirectiveName]Directive { }
```

### ng2-pipe

`ng2-pipe` provides a skeleton for an Angular 2 Pipe.

```ts
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: '<pipe-name>'
})
export class <PipeName>Pipe implements PipeTransform {
  transform(value: <value-type>, args: any[]) : <value-type> {
    return ;
  }
}
```

### ng2-routes

`ng2-routes` creates the `@Routes` decorator with a single route in it.

```ts
import { RouterModule, Routes } from '@angular/router';

const app_routes: Routes = [
  { path: '<url-segment>', component: <component-name> },
  { path: '**', pathMatch: 'full', redirectTo: '<url-segment>' }
];

export const app_routing = RouterModule.forRoot(app_routes);
```

### ng2-route-path

`ng2-route-path` adds a single route to `@Routes`.
**Use** this snippet inside the `@Routes` decorator.

```ts
{ path: '/<route>', component: <component-name> }
```

### ng2-service

`ng2-service` provides a skeleton for an Angular 2 Service.

```ts
import { Injectable } from '@angular/core';

@Injectable()
export class <service-name>Service {
  constructor() {  }
}
```

### ng2-subscribe

`ng2-subscribe` gives you a shorthand to call a service function, that returns a observable.
The `subscribe` method is also created for you. So you can assign the response quickly.

```ts
this.<service-name>.<service-function>
    .subscribe(<response> => this.<assign-target> = <response>});
```

### ng2-rx-map

`ng2-rx-map` simply creates the import statement to reference the map operator of RxJs.

```ts
import 'rxjs/add/operator/map';
```

### ng2-ngClass

This snippet inserts the `ngClass` directive.

```html
<div [ngClass]="cssClass: expression"></div>
```

### ng2-ngFor

This snippet inserts the `ngFor` directive.

```html
<div *ngFor="let {1:$item} of list"></div>
```

### ng2-ngIf

This snippet inserts the `ngIf` directive.

```html
<div *ngIf="expression"></div>
```

### ng2-ngModel

This snippet inserts the `ngModel` directive.

```html
<div [(ngModel)]="binding"></div>
```

### ng2-property

This snippet inserts the skeleton for a property binding directive.

```html
<div [property]="value"></div>
```

### ng2-event

This snippet inserts the skeleton for a event binding directive.

```html
<div (event)="callback()"></div>
```

### ng2-routerLink

This snippet inserts the `routerLink` directive.

```html
<a [routerLink]="routeName"></a>
```

### ng2-ngStyle

This snippet inserts the `ngStyle` directive.

```html
<div [ngStyle]="'style': expression"></div>
```

### ng2-ngSwitch

This snippet inserts the `ngSwitch` directive.

```html
<div [ngSwitch]="conditionExpression">
  <div *ngSwitchCase="expression">output</div>
  <div *ngSwitchDefault>output2</div>
</div>
```
