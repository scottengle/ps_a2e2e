# Course Work for Pluralsight Course 'Angular 2 End-to-end'

https://www.pluralsight.com/courses/angular-2-end-to-end

# "It's Just Angular"

This course makes some comparisons between AngularJS (Angular 1) and Angular (Angular 2 and beyond). Whenever I reference Angular 1, I'll refer to it as "AngularJS". 

For more information:

http://angularjs.blogspot.com/2016/12/ok-let-me-explain-its-going-to-be.html

# Recommendations

This course is very fast paced and in the beginning can be quite a lot of information to absorb for people new to Angular. if you feel this course is more advanced than your current skill set, I recommend checking out one of these courses instead:

Angular 2: First Look
https://www.pluralsight.com/courses/angular-2-first-look
https://github.com/scottengle/ps_a2fl

Angular 2: Getting Started
https://www.pluralsight.com/courses/angular-2-getting-started-update
https://github.com/scottengle/ps_a2gs

# External Resources

*Angular Documentation*: https://angular.io/

*Angular Quick Start*: https://angular.io/docs/ts/latest/quickstart.html

*AngularCLI*: https://cli.angular.io

*Angular Library Packages*: https://www.npmjs.com/~angular

*TypeScript Site*: http://www.typescriptlang.org

*TypeScript Playground*: http://www.typescriptlang.org/Playground/

*Standard HTML Element Events (MDN)*: https://developer.mozilla.org/en-US/docs/Web/Events

*Rx Marbles*: http://rxmarbles.com

*Webpack*: https://webpack.github.io/

# Project Files

Project files are available from the Pluralsight course's "Exercise Files" area.

# Running the Sample App

    npm i

# Webpack

Webpack is a module bundler. It is an alternative to System.js.

Webpack will dynamically add scripts (JavaScript, CSS) into the index.html file and can handle compilation of various types of files in its loaders. These include JavaScript, HTML, CSS, PNG and Sass files.

Webpack compiles modules into bundles and imports vendor libraries such as Angular 2, Foundation and JQuery.

# TypeScript Basics

TypeScript uses ES2015 Syntax, compiles to standard ES5 JavaScript, and adds static typing to JavaScript.

For more information: http://www.typescriptlang.org

# The Project

## Root Module

    // in app.module.ts
    import { NgModule } from '@angular/core';
    import { BrowserModule } from '@angular/platform-browser';  // Required for browser based apps
    import { AppComponent } from './start/app.component';

    @NgModule({
      imports: [                    // Modules imported and used by the components of this module
        BrowserModule
      ],
      declarations: [               // Components, Directives and Pipes owned by this module
        AppComponent
      ],
      bootstrap: [ AppComponent ],  // Initiated by main.ts
      exports: [ AppComponent ],    // Exported Components, Directives and Pipes for use by other modules
      providers: [ MyService ],     // Service providers available to components contained within this module
    })
    export class AppModule { }      // Lets us import this module into other modules

## Bootstrap Process

* main.ts
  * Runs the bootstrap method against app.module.ts
  * In the Webpack config, main.ts is the entry point to the bundle. Main.ts bootstraps the application.
* app.module.ts
  * Launches the app.component.ts
  * `AppModule` by convention
* app.component.ts
  * Initial component displayed by the application
  * `AppComponent` by convention

## AppComponent

* app.component.ts
  * Component decorator for root component
* app.component.css
  * Styles for the root component
* app.component.html
  * Template file for root component
* app.component.spec.ts
  * Test spec for root component

## The Navbar Component

