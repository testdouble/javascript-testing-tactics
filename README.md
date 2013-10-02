# Javascript Testing Tactics

# How my JavaScript Tests differ from the README.

## background

* make front-end dev _delightful_
* create beautiful test techniques
* discover when testing is valuable
* typically use jasmine
* maintain lots of supporting tools, like Lineman.js, jasmine-given, jasmine-fixture, jasmine-stealth, jasmine-before-all, grunt-jasmine…

## syntax

### What I don't do

* use Jasmine's (RSpec-like) DSL
* write my specs with JavaScript

### What's the problem?

* Jasmine DSL has to be learned
* idiomatic usage is non-obvious
* produces distracting, verbose code
* dat crying mustache emoticon });

### What I do

* write specs in CoffeeScript
* use the jasmine-given DSL

## test runner

### What I don't do

* default plain HTML test runner
* jasmine-rails
* jasmine-maven-plugin
* any server-side-dependent plugin

### What's the problem?

* feedback isn't fast enough
* build tools treat JS as 2nd-class
* friction of server-side coupling

### What I do

* use Testem as my runner
* use Lineman to build my code
* run all my tests in under a second on every single file change

[**DEMO**](http://youtu.be/HHcEjAQ46Io?t=18m16s)

## ajax & ui events

### What I don't do

* start a fake server that can stub & verify AJAX calls
* monkey-patch the browser's XHR facilities
* invoke code by triggering UI events

### What's the problem?

* too integrated for unit tests
* "only mock what you own"
* test pain isn't actionable
* raises concerns better handled by integrated tests (e.g. large stubs)
* doesn't help improve my API

### What I do

* wrap XHR lib in object I own
* let its API grow with my needs
* mock it away in my unit tests
* only integration test the wrapper 

[**DEMO**](http://youtu.be/HHcEjAQ46Io?t=29m03s)

## asynchronous code

### What I don't do

* write async tests for async code

### What's the problem?

* test yields execution control
* lots of noise in test setup
* speed/timeout concerns
* hard to debug race conditions
* test pain isn't actionable

### What I do

* only write async APIs when useful
* extract callbacks out of app code and into decorators and mixins
* take advantage of promises
* use jasmine-stealth to capture & discretely test callback functions

## the dom

### What I don't do

* say "(╯°□°）╯︵ ┻━<table/>━┻" and skip writing tests against the DOM

* use HTML fixture files


### What's the problem?
#### not testing DOM interactions

* most JS on the web is UI code
* low coverage limits suite's value
* you'll write more DOM-heavy code via the path of least resistance
* hampers true outside-in TDD


### What's the problem?
#### using HTML fixture files

* large input -> larger everything
* tests should push for small units
* sharing fixtures leads to a  "_Tragedy of the Commons_"

### What I do

* treat the DOM like a 3rd-party dependency—minimizing app's exposure
* affix HTML with jasmine-fixture
* arrive at single-purpose functions

[**DEMO**](http://youtu.be/HHcEjAQ46Io?t=50m42s)

## in summary

> Practicing TDD in JS for
  years taught me how to
  write better code.

  When TDD feels rote, it
  means I learned something!
  So then I use it less.

  Give it a try! I'll help!

## Lineman

You can have all these helpers pre-installed and ready to go for you with Lineman!

* [Lineman](http://linemanjs.com)
* [Install](http://lineman-install.herokuapp.com)
* [Help](mailto:justin@testdouble.com)

<hr/>

My name is **Justin Searls**
Please tweet me **[@searls](http://twitter.com/searls)** &
Say [hello@testdouble.com](mailto:hello@testdouble.com)
