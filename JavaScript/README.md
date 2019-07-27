# HackYourFuture

Hack Your Future JavaScript classwork.

## Topics

• JavaScript introduction

• Variables in JavaScript

• Basic Data Types in JavaScript

### JavaScript introduction

#### What

JavaScript was created in 1995 by Brendan Eich while he was an engineer at Netscape. It is a cross-platform, object-oriented scripting language used to make webpages interactive (e.g. having complex animations, clickable buttons, popup menus, etc).

Today, it works not only inside the browser, but also on the server(e.g. NodeJS), or actually on any device that has a special program called the JavaScript engine(a computer program that can execute JavaScript code).

#### Why

There are three different pieces to a webpage.

- **HTML** defines what the content is.
- **CSS** defines the appearance of the page.
- **JavaScript** defines behavior of the page.

Up until now at HackYourFuture, we have been writing websites using HTML and CSS. Even though a website written with these two languages works just fine, it is only a static page. These static pages can interact with a visitor only through the use of forms. Once a form is filled out and submitted, a request is sent back to the server where a new static web page is constructed and eventually downloaded into the browser. The big disadavantage of web pages like this is that the only way that a visitor has of interacting with the page is by filling out the form and waiting for a new page to load. It doesn't exhibit any dynamic behaviour like:

- reacting to user actions such as mouse click events or key presses.
- rendering complex animations
- sending requests over network to servers and fetching a response

And this is where JavaScript steps in.

### Variables in JavaScript

Any application written in any programming language requires data/information to work with. This information can be of simple types like strings, numbers, booleans or complex types like arrays and objects and a _variable_ is a named storage/pointer for this information.

In JavaScript, there are three ways of creating a variable.

- var
- let
- const

While `var` has been used in JavaScript for a long period of time, `let` and `const` are recent additions to the language being introduced in ES6.

#### Variable Declaration

Declaration means creating a variable and providing it with a name. During the whole program, a variable can be declared only once.

```JavaScript
// Declaring variables
var firstName;
let lastName;
```

#### Variable Initialization

Initialization is declaring a variable and assigning it an initial value at the time of declaration.

```JavaScript
// Declaring and initializing a variable
var firstName = 'Yash';
let lastName = 'Kapila';
const age = 29;
```

By default, all variables created in JavaScript have `undefined` as the default value unless explicitly given a different value.

#### Variable Assignment

Variable assignment means throwing away the old value of a variable and replacing it with a new one. Initialization can be thought of as a special way of assignment.

```JavaScript
// Declaring and initializing a variable
var firstName = 'Yash';
let lastName = 'Kapila';
const age = 29;

// Re-assigning variables to a different value
firstName = 'Kapila';
lastName = 'Yash';
```

**Note:**

- Variables created using `var` and `let` keyword behave in a similar fashion but with a few caveats which are going to be covered in later topics during JavaScript2 when we get to the concept of scopes and hoisting.

- Variables created using `const` keyword can't be reassigned unlike variables created using `var` and `let` keywords. This means the below isn't possible in JavaScript.

  ```JavaScript
  // Declaring and initializing a variable
  const age = 29;
  // Trying to re-assign a new value
  age = 30; // ERROR!!
  ```

- While creating variables in JavaScript, we should try to create variables using `const` keyword as much as possible. This has multiple advantages like giving a predictable nature to the program thus lessening the changes of bugs, easier understanding of code for other developers etc.

### Basic Data Types in JavaScript

Now that we know what variables are, how we can create them, let's have a look at the different types of information/data which is available to be used in JavaScript.

[Data Types](https://github.com/HackYourFuture/fundamentals/blob/master/fundamentals/values.md)
