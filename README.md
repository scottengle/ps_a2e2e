# Course Work for Pluralsight Course 'Angular 2 End-to-end'

https://www.pluralsight.com/courses/angular-2-end-to-end

# "It's Just Angular"

This course makes some comparisons between AngularJS (Angular 1) and Angular (Angular 2 and beyond). Whenever I reference Angular 1, I'll refer to it as "AngularJS". 

For more information:

http://angularjs.blogspot.com/2016/12/ok-let-me-explain-its-going-to-be.html

# Recommendations

This course is a hands-on, fast paced learning experience. In the beginning it can be quite a lot of information to absorb for people new to Angular. if you feel this course is more advanced than your current skill set, I recommend checking out one of these courses instead:

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

*Firebase*: https://firebase.google.com/

## Testing Resources

*Angular Testing*: https://angular.io/docs/ts/latest/guide/testing.html

*Karma*: https://harka-runner.github.io/1.0/index.html

*Jasmine*: https://jasmine.github.io

*Protractor*: http://www.protractortest.org/#/

# Project Files

Project files are available from the Pluralsight course's "Exercise Files" area. There is a finalized version of the project files in the `gigabyte` folder.

# Running the Sample App

    npm i
    npm start

## Building For Deployment

    npm run build

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

# Setting Up Authentication with Firebase

The application will use Firebase for as the back end authentication data store. Firebase is a cloud-based data store owned by Google, which provides some convenient mechanisms for authenticating users and protecting areas of the application behind a login wall.

Authentication for the project will be simple email / password authentication. Firebase will handle email verification as well as enforce password requirements.

# Setting up the Blog System

This module goes through a complete set up of the blog system including storing images and posts in Firebase.

## ngSwitch

    <div [ngSwitch]="menuChoice">
      <div *ngSwitchCase="'add'"><h1>Add Menu</h1></div>
      <div *ngSwitchDefault><h1>Default</h1></div>
    </div>

## Creating a Pipe

    // in truncate.pipe.ts
    import { Pipe, PipeTransform } from '@angular/core';

    @Pipe({
      name: 'truncate'
    })
    export class TruncatePipe implements PipeTransform {
      transform(value: string, chars: number): string {
        let text = `${value.substring(0, chars)} ...`;
        return text;
      }
    }

    // in template
    <p>{{posts.content | truncate:140}}

## Safe Navigation Operator

    <div class="row image-spacing">
      <img [src]="singlePost?.img">     // No error if the template loads and the data isn't present
    </div>

# Setting up the Shopping Cart

This module goes through the process of setting up a shopping cart system, based almost entirely on the blog system. It is mainly an exercise in copy/paste/change names.

# Testing

Tools for testing in Angular

* Karma Test Runner
* Jasmine
* Mocha / Chai
* QUnit
* TestBed 
  * An Angular testing package in '@angular/core/testing'
* Protractor
