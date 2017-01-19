# The Node Beginner Book

# 1. Hello World

# About

Through 13 exercises, you follow _The Node Beginner Book_, but with live-running code examples. By the end, you'll know how to create a complete web app that allows users to view web pages and upload files.

The aim is to get you started with developing applications for Node.js, teaching you everything you need to know about "advanced" JavaScript along the way. It goes way beyond your typical "Hello World" tutorial.

![](https://hyperdev.wpengine.com/wp-content/uploads/2016/09/nodeBeginnerBookCover-200x300.png)

* 1\. Hello World (this project)

* 2\. <a href="https://gomix.com/#!/remix/NodeBeginner2/061e4ab9-d2c8-4395-ad51-c9680528e128" target="_blank">A Basic HTTP Server</a> - Begin to create a full blown web application with Node.js, starting with a basic HTTP server.

* 3\. <a href="https://gomix.com/#!/remix/NodeBeginner3/cee64121-f572-4e48-a2b0-c2fcaaac94b9" target="_blank">Function Passing</a> - Learn how in JavaScript, functions can be passed around like any other value and how that makes our HTTP server work.

* 4\. <a href="https://gomix.com/#!/remix/NodeBeginner4/90a4f7cc-42f2-47eb-983a-f3b015e5da8a" target="_blank">Asynchronous Callbacks</a> - Understand how Node.js executes our code and what that means for your approach to writing Node.js applications.

* 5\. <a href="https://gomix.com/#!/remix/NodeBeginner5/665503e6-4531-40b7-9e3a-9e91761ce53b" target="_blank">Creating Modules</a> - Here's how to turn your own code into re-usable modules that we'll use to better organize our applications.

* 6\. <a href="https://gomix.com/#!/remix/NodeBeginner6/eaeb4887-1fef-4ca8-b8c6-7ece0a403596" target="_blank">Request Routing</a> - We cover how to handle URL GET and POST requests, and route them so that the appropriate section of code acts upon them.

* 7\. <a href="https://gomix.com/#!/remix/NodeBeginner7/2bcba06c-14e7-4642-b68b-bb72f4f49fc4" target="_blank">Routing to Request Handlers</a> - We wire up request handlers into our router, giving our router something to route to.

* 8\. <a href="https://gomix.com/#!/remix/NodeBeginner8/8486131b-b94e-4e5e-b0a1-009c9b50b82e" target="_blank">How Not To Respond to Request Handlers</a> - Understand why our straight-forward approach might make a lot of sense, but will screw things up when we don't expect it.

* 9\. <a href="https://gomix.com/#!/remix/NodeBeginner9/ba34c9df-ae9d-4837-a020-c892b1876bda" target="_blank">Blocking Handlers</a> - We demonstrate what happens if we add a blocking operation to our request handlers.

* 10\. <a href="https://gomix.com/#!/remix/NodeBeginner10/158634ab-1248-452f-84a4-da9ed215e178" target="_blank">Child Processes</a> - Make use of simple yet useful non-blocking operations by adding child processes to our application.

* 11\. <a href="https://gomix.com/#!/remix/NodeBeginner11/6b829561-aed3-4dbc-8bdf-6b24067bdd4a" target="_blank">Non-blocking Handlers</a> - After learning how _not_ to do it, let's discuss how to make our request handlers respond to browser requests the right way.

* 12\. <a href="https://gomix.com/#!/remix/NodeBeginner12/db0f0e00-275a-419c-8276-43fa42046563" target="_blank">Handling POST Requests</a> - How to handle incoming POST requests to add interactivity to our web app.

* 13\. <a href="https://gomix.com/#!/remix/NodeBeginner13/4b10e2a6-da01-4b89-ae23-4a14879de8d5" target="_blank">Handling File Uploads</a> - Make use of an external Node.js module that helps us to add the ability for users to upload image files.

## Intended audience

This document will probably fit best for readers that have a background
similar to my own: experienced with at least one object-oriented
language like Ruby, Python, PHP or Java, only little experience with
JavaScript, and completely new to Node.js.

Aiming at developers that already have experience with other programming
languages means that this document won't cover really basic stuff like
data types, variables, control structures and the likes. You already
need to know about these to understand this document.

However, because functions and objects in JavaScript are different from
their counterparts in most other languages, these will be explained in
more detail.

## Structure of this course

Upon finishing this course, you will have created a complete web
application which allows the users of this application to view web pages
and upload files.

Which, of course, is not exactly world-changing, but we will go some
extra miles and not only create the code that is "just enough" to make
these use cases possible, but create a simple, yet complete framework to
cleanly separate the different aspects of our application. You will see
what I mean in a minute.

We will start with looking at how JavaScript development in Node.js is
different from JavaScript development in a browser.

Next, we will stay with the good old tradition of writing a "Hello
World" application, which is a most basic Node.js application that
"does" something.

Then, we will discuss what kind of "real" application we want to
build, dissect the different parts which need to be implemented to
assemble this application, and start working on each of these parts
step-by-step.

As promised, along the way we will learn about some of the more advanced
concepts of JavaScript, how to make use of them, and look at why it
makes sense to use these concepts instead of those we know from other
programming languages.

# JavaScript and Node.js

## JavaScript and You

Before we talk about all the technical stuff, let's take a moment and
talk about you and your relationship with JavaScript. This chapter is
here to allow you to estimate if reading this document any further makes
sense for you.

If you are like me, you started with HTML "development" long ago, by
writing HTML documents. You came along this funny thing called
JavaScript, but you only used it in a very basic way, adding
interactivity to your web pages every now and then.

What you really wanted was "the real thing", you wanted to know how to
build complex web sites - you learned a programming language like PHP,
Ruby, Java, and started writing "backend" code.

Nevertheless, you kept an eye on JavaScript, you saw that with the
introduction of jQuery, Prototype and the likes, things got more
advanced in JavaScript land, and that this language really was about
more than *window.open()*.

However, this was all still frontend stuff, and although it was nice to
have jQuery at your disposal whenever you felt like spicing up a web
page, at the end of the day you were, at best, a JavaScript *user*, but
not a JavaScript *developer*.

And then came Node.js. JavaScript on the server, how cool is that?

You decided that it's about time to check out the old, new JavaScript.
But wait, writing Node.js applications is the one thing; understanding
why they need to be written the way they are written means -
understanding JavaScript. And this time for real.

Here is the problem: Because JavaScript really lives two, maybe even
three lives (the funny little DHMTL helper from the mid-90's, the more
serious frontend stuff like jQuery and the likes, and now server-side),
it's not that easy to find information that helps you to learn
JavaScript the "right" way, in order to write Node.js applications in
a fashion that makes you feel you are not just using JavaScript, you are
actually developing it.

Because that's the catch: you already are an experienced developer, you
don't want to learn a new technique by just hacking around and
mis-using it; you want to be sure that you are approaching it from the
right angle.

There is, of course, excellent documentation out there. But
documentation alone sometimes isn't enough. What is needed is guidance.

My goal is to provide a guide for you.

## A word of warning

There are some really excellent JavaScript people out there. I'm not
one of them.

I'm really just the guy I talked about in the previous paragraph. I
know a thing or two about developing backend web applications, but I'm
still new to "real" JavaScript and still new to Node.js. I learned
some of the more advanced aspects of JavaScript just recently. I'm not
experienced.

Which is why this is no "from novice to expert" book. It's more like
"from novice to advanced novice".

If I don't fail, then this will be the kind of document I wish I had
when starting with Node.js.

## Server-side JavaScript

The first incarnations of JavaScript lived in browsers. But this is just
the context. It defines what you can do with the language, but it
doesn't say much about what the language itself can do. JavaScript is a
"complete" language: you can use it in many contexts and achieve
everything with it you can achieve with any other "complete" language.

Node.js really is just another context: it allows you to run JavaScript
code in the backend, outside a browser.

In order to execute the JavaScript you intend to run in the backend, it
needs to be interpreted and, well, executed. This is what Node.js does,
by making use of Google's V8 VM, the same runtime environment for
JavaScript that Google Chrome uses.

Plus, Node.js ships with a lot of useful modules, so you don't have to
write everything from scratch, like for example something that outputs a
string on the console.

Thus, Node.js is really two things: a runtime environment and a library.

In order to make use of these, you can install Node.js locally from https://nodejs.org/en/download/. But instead, we're going to use Gomix.

## "Hello World"

Ok, let's just jump in the cold water and write our first Node.js
application: "Hello World".

Start by <a href="https://gomix.com/#!/remix/NodeBeginner1/6c89fbec-c325-4618-9221-8da91296c6bb" target="_blank">remixing</a> this project. Then open the file called *helloworld.js*. We want it to write "Hello World" to STDOUT, and here is the code needed to do that:

    console.log("Hello World");

Locally, you'd have to save the file, and execute it through Node.js:

    node helloworld.js

On Gomix, we've put that in the `package.json` file, so it does it for us everytime we make a change. Changes are saved and deployed automatically on Gomix too. You can just click `'Logs'` to see the console output. You should see the output *Hello World*. It might say 'Error' in the logs too, and clicking 'Show' doesn't show anything - well, that's because we don't have a HTTP server yet. And that's just what we're going to add next!

<a href="https://gomix.com/#!/remix/NodeBeginner2/061e4ab9-d2c8-4395-ad51-c9680528e128" target="_blank">>> Go to the next part</a>.


# License
The Node Beginner Book (C) Manuel Kiessling
[Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License](https://creativecommons.org/licenses/by-nc-sa/3.0/). Some small text changes have been made to the original to make sense on Gomix.