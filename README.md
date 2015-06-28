# Angular-2-Glossary-of-Terms

## Angular 2
Angular 2 specific terms
#### Directive
Directives allow you to attach behavior to elements in the DOM.
#### Component

#### Element
Any HTML DOM element or custom element

#### Host

#### Injector
A dependency injection container used for resolving dependencies.
An `Injector` is a replacement for a `new` operator, which can automatically resolve the constructor dependencies. In typical use, application code asks for the dependencies in the constructor and they are resolved by the `Injector`.
**Example**

Suppose that we want to inject an Engine into class Car, we would define it like this:
```javascript
class Engine {
}
class Car {
  constructor(@Inject(Engine) engine) {
  }
}
```
Next we need to write the code that creates and instantiates the `Injector`. We then ask for the `root` object, `Car`, so that the `Injector` can recursively build all of that object's dependencies.
```javascript
main() {
  var injector = Injector.resolveAndCreate([Car, Engine]);
  // Get a reference to the `root` object, which will recursively instantiate the tree.
  var car = injector.get(Car);
}
```
Notice that we don't use the `new` operator because we explicitly want to have the `Injector` resolve all of the object's dependencies automatically.

#### ElementInjector
Injector associated with an element. Each component instance has a Shadow DOM. Within the Shadow DOM each element has an ElementInjector which follow the same parent-child hierarchy as the DOM elements themselves.

#### Terminal Injector
The terminal Injector cannot resolve dependencies. It either throws an error or, if the dependency was specified as `@Optional`, returns `null`.

#### Platform Injector
The platform injector resolves browser singleton resources, such as: cookies, title, location, and others.

#### Component Injector
Each component instance has its own Injector, and they follow the same parent-child hierarchy as the component instances in the DOM.

#### ElementRef

#### ViewContainerRef

#### ProtoViewRef

#### ProtoViewDto

## General
General terms however related to Angular 2
## DOM API
#### Properties

#### Events

#### Attributes

#### Methods

## Web Components

#### Shadow DOM
Shadow DOM refers to the ability of the browser to include a subtree of DOM elements into the rendering of a document, but not into the main document DOM tree.
http://glazkov.com/2011/01/14/what-the-heck-is-shadow-dom/
http://www.html5rocks.com/en/tutorials/webcomponents/shadowdom/
http://webcomponents.org/articles/introduction-to-shadow-dom/
#### Shadow host

#### Light DOM

#### Logical DOM

#### Composed DOM



