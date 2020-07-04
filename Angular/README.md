# Angular:
Brief Introduction to Angular:

## Introduction

### 1.	Definition:

Angular is a JavaScript Framework which allows us to create reactive Single Page Application (SPAs).


### 2.	Topics Covered Under Angular

1.	Components & Data Binding
2.	Directives
3.	Service & Dependency Injection
4.	Routing
5.	Observables -- Working with Asynchronous code
6.	Forms
7.	Pipes
8.	Http
9.	Authentication
10.	Optimizations & NgModules
11.	Deployment
12.	Animations & Testing


### 3.	TypeScript
Offers more features than JS like classes, Interfaces, types etc <br/>
Later it will be compiled to Java script

## Components:

*	Components are the most basic building block of an angular application.
*	It controls one or more sections on the screen (what we call on the view).
*	These components are subset of Directives. Unlike directives, Components always have a template & only one component can be instantiated per an element in a template.
*	Using the Angular @Component decorator we provide additional Meta data that determines how the components should be processed, instantiated & used at runtime.
*	Component passes data to the view using process called Data Binding.


## Directive:

Directives add behavior to an existing DOM element or an existing component instance.


## Templates:

1.	A template is an HTML view where we can display data by binding the controls to properties of an Angular Component.
2. 	We can store the components template in one of two places. 
    * We can define it inline using the template property or <br>
    * We can define the template in a separate HTML file & link to it in the component metadata using @Component decorator's templateUrl Property.


## Module

*	Modules are logical boundaries in our application & the application is divided into separate modules to separate the functionality of our application. 
*	We have app module as a root module which is declared with @NgModule decorator.
*	NgModule decorator has three options: imports, declarations & bootstrap
_	Import option is used to import other dependent module like Browser Module etc.
_	Declaration option is used to define components in the respective module
_	Bootstrap option tells Angular to which Component to bootstrap in the application.


## 	Data Binding

1.  Data binding is a core concept in Angular and allows to define communication b/w a component & the DOM, making it very easy to define interactive applications without worrying about pushing & pulling data.

2.  Data Binding can be done by using
    * From the Component to the DOM:

      i.	Interpolation: {{value}} : Adds thr value of a property from the component. <br/>
    			 ex: ```  Name: {{ user.name }}</li>  Address: {{ user.address }} ```

      ii.	Property Binding: [property] ="value”: The value is passed from the component to the specified property or simple HTML attribute. <br>
    			   ex: ```<input type="email" [value]="user.email"> ```
  
     * From the DOM to the Component: 
        Event binding: (event) ="function": When specific DOM event happens.<br>
        (eg: click, change, keyup), call the specified method in the component. <br>
        ex: <button (click)="logout()"></button>   
   
    * Two way Binding: 
      Two way data binding: [(ngModule)]="value", Two way data binding allows to have  data flow in both ways. <br>
      Ex: <input type="email" [(ngModel)]="user.email"> in the above code snippet, both the email DOM input and component email property are in sync.   


## Metadata:
Metadata is used to decorate a class so that it can configure the expected behavior of the class.

Metadata is represented by decorators
1.	Class Decorators
2.	Property Decorator
3.	Method decorator
4.	Parameter Decorator

## Services:
*	Service is used when a common functionality needs to be provided to various modules. 
*	Service allow for greater separation of concerns for our application & better modularity by allowing us to extract common functionality out of components.

## Dependency Injection:
*	DI is an important design patters in which a class asks for dependencies from external source rather than creating them itself.
*	Angular comes with its own dependency injection framework for resolving dependencies.

## Pipes:
   
  Pipe takes in data as input & transforms it to a desired output.


### Parameterized Pipe:

*	Pipe can accept any number of optional parameters to fine tune its output.
*	A parameterized pipe can be created by declaring the pipe name with a colon(:) & then parameter value.
*	If Pipe accepts the multiple parameters, separate the values with colons.

## Observables

*	Observables are declarative which provide support for passing messages between publishers & subscribers in angular application.

*	They are mainly used for event handling, asynchronous programming, handling multiple values.

*	We can define a function for publishing values, but it will not be executed until a consumer subscribes to it. The subscribed consumer then receives notifications until the function completes or until they unsubscribe.


## Http Client:

*	Most of the front-end applications communicate with backend services over HTTP protocol using either XMLHttpRequest interface or the fetch() API.

*	Angular provides a simplified client HTTP API known as HttpClient which is based on top of XMLHttpRequest interface.

*	This client is available from @angular/common/http package.

*	We can import in your root module as below, import { HttpClientModule } from '@angular/common/http';


## Router

Router is a mechanism in which navigation happens from one view to the next as user performs some operation or task in the application.


## Differences

### Difference between Component and Directive

|Component	| Directive|
|----|------|
|To register component we use @Component decorator	|To Register directive we use @Directive decorator|
|Components are typically used to create UI widgets|	Directives is used to add behavior to an existing DOM element|
|Component is used to break up the application into smaller components	|Directives is used to design re-usable components|
|Only one component can be present per DOM element|	Many directives can be used per DOM element|
|@View decorator or remplateurl is mandatory|	Directives doesn't use View|


## Deployment:

Execute command to build the project
 ng build --prod

### To deploy angular app in Firebase web hosting:

1.	Install fire base cli through command
                    npm install -g firebase-tools
	
2.	Sign into Firebase using your Google account by running the following command:
                    firebase login

         Once the login is done successfully means do the following steps:
*	Go to angular project directory & execute
                    firebase init   

*	Select the feature as  
                    Hosting: Configure and deploy Firebase Hosting sites

*	Choose a project (Earlier you created in console) which you want to connect

*	What do you want to use your public directory?
                    Choose the project directory from the dist folder (ex: dist/my-project) 

*	Click yes for (rewrite all url's to index.html)

*	File already exists. Overwrite? No

*	Execute the deploy command
firebase deploy   



