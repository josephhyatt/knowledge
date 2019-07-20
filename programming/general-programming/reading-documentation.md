# Reading Documentation

**Table of Contents**

* [Introduction](http://cassandrawilcox.me/beginners-guide-developer-documentation/#intro)
* [What is Developer Documentation?](http://cassandrawilcox.me/beginners-guide-developer-documentation/#whatisdevdocumentation)
* [Navigating Documentation](http://cassandrawilcox.me/beginners-guide-developer-documentation/#navigatingdocumentation)
  * [Finding Answers](http://cassandrawilcox.me/beginners-guide-developer-documentation/#findinganswers)
    * [Scenario 1: Getting a general overview](http://cassandrawilcox.me/beginners-guide-developer-documentation/#overview)
    * [Scenario 2: Learning how to get started](http://cassandrawilcox.me/beginners-guide-developer-documentation/#gettingstarted)
    * [Scenario 3: Finding help when you're stuck](http://cassandrawilcox.me/beginners-guide-developer-documentation/#stuck)
* [Understanding Syntax Definitions](http://cassandrawilcox.me/beginners-guide-developer-documentation/#syntax)

Today you can find just about anything on the internet. But it seems that there still some things in this world that remain impossible to Google. Information to help with understanding and using developer documentation is one of those things. I've tried Googling things like "how to understand developer documentation" and "documentation syntax help" and at best I get resources on how to write documentation. While these turn out to be pretty helpful resources, it seems that NO ONE has written a guide on how to understand and use developer documentation. So, I thought I would write a post on the topic to help fill that void.

![](http://cassandrawilcox.me/content/images/2018/01/Screen-Shot-2018-01-08-at-11.04.52.png)

As software developers we often need to refer to documentation to understand how to use a language or library. Some documentation is very well-written, while other documentation is unhelpful and even downright painful. Even in the best cases, it can be difficult to understand developer documentation, especially if you are new to software development, because, like I said, there aren't a lot of resources available to help new developers out. In this post I'm going to share some tips that I hope you can use to confidently navigate developer documentation, find the answers you are looking for, and understand what what it all means so you can solve your dev problems quicker.

## What is Developer Documentation?

Developer documentation is meant to describe every aspect of how developers should interface with a given software service or library. When we read documentation, we are learning how to use the software's "API".

![](http://cassandrawilcox.me/content/images/2018/01/Screen-Shot-2018-01-08-at-11.08.00.png)

You've probably heard the term API before, at least as it refers to "REST APIs", which are used to exchange data with a server. But APIs or _Application Programming Interfaces_aren't limited to transmitting data between client and server applications. Any 3rd party library that you bring into your own project has an API that provides a way for your code interact with it. In addition, we have access to native JavaScript APIs like the DOM \(Document Object Model\) which allows our JavaScript code to communicate with our HTML.

![](http://cassandrawilcox.me/content/images/2018/01/api-javascript-jquery-1.png)

Here are a few examples of documentation you might use as a web developer:

* [JavaScript reference \(MDN Web Docs\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
* [Canvas API \(MDN Web Docs\)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
* [jQuery API Documentation](https://api.jquery.com/)
* [React Docs](https://reactjs.org/docs/hello-world.html)

Go ahead and take a look at each one. As you browse these examples, or others, notice what they have in common, and what about them is different. How do you feel upon initially skimming the contents? Do you feel comfortable or overwhelmed? Is there any vocabulary you don't understand? It's a lot of information right?!

You might notice that each has a sort of table of contents to the right or left of the main content. jQuery provides separate documentation for each [version](http://api.jquery.com/category/version/1.0/). Its pretty easy to find getting started tutorials for [Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage) and [React](https://reactjs.org/docs/hello-world.html) while you have to dig a little to find the same for [jQuery](http://learn.jquery.com/about-jquery/how-jquery-works/). jQuery separates their [API reference](http://api.jquery.com/) from their [Learning Center](http://learn.jquery.com/) while the Canvas and React docs seem keep both on one site.

If you were overwhelmed by any of these docs, don't worry. Experienced developers sometimes take understanding documentation for granted, as if it's an instinct all developers are born with. But, developer documentation isn't like a lot of instruction sets we are used to using outside of development. Plus, not all documentation is created equally. Sometimes documentation is written by developers who are good at writing instructions that computers can understand, but not so much that people can understand. And, as we saw from the examples above, different sets of documentation are organized differently. So, when looking at a new set of documentation, the first thing we have to do is figure out how it is organized. This can be one of the first places we can encounter frustration.

## Navigating Documentation <a id="anamenavigatingdocumentationanavigatingdocumentation"></a>

The key to effectively navigating documentation is knowing how good documentation is organized. According to [Pamela Fox](https://twitter.com/pamelafox), in her post called [_The Six Pillars of Complete Developer Documentation_](https://www.programmableweb.com/news/six-pillars-complete-developer-documentation/2011/09/12), a complete documentation set should try to include the following:

* **Class Reference:** A comprehensive listing of API functionality.
* **Changelog:** A reference of what changes in each API version.
* **Code Samples:** A set of examples showing typical API usage.
* **Code Playground:** An interactive explorer for trying the API live in the browser.
* **Developers Guide:** A conversational written guide to using the API.
* **Articles:** Tutorials and screencasts discussing different ways of using the API.

_\(I lifted this list from linked article above with no intention to claim it as my own. Just for your convenience!\)_

Not all documentation includes all of these things, but you can use the above list to get yourself oriented and to evaluate the quality of the documentation you're referencing. Maybe if what you're looking at is missing a lot from the list above you can find better docs somewhere else. If there is no better alternative documentation, maybe you can try to find another similar library with better docs. If that isn't an option, hopefully this list can at least help you set realistic expectations for the docs available to you and ease any unnecessary frustration. \(See the end of this post for more on what to do if the docs you're using are really bad.\)

As you read through the Class Reference, keep in mind that learning method names and arguments by heart probably isn't worth the time. I've been building JavaScript apps for several years and there are lots of things I still have to look up. Over time you'll start to remember the methods you use most, but there is no need to start out by trying to memorize everything. You don't need to and no one should ever expect this of you.

It is far more helpful to skim through the Class Reference headings and get an idea for what types of methods it contains. You'll likely start to pick up on the patterns used to name things. For example, there are several JavaScript methods available for selecting DOM elements including `getElementById`, `getElementsByClassName`, `getElementsByTagName` and so on. Each of these begin with `getElement`. Those with singular `Element` in the name return a single HTML object, while those with plural `Elements` in the name return a nodelist. Having a sense of what a method would be named, and what it might return based on its name, makes it easier for you to search for something even if you you aren't sure that it exists.

## Finding Answers

When using documentation to find answers, we first need to think about what kinds of questions we are asking. You may come to documentation for a number of different reasons and depending on the situation, you can optimize your approach to reading through the docs.

#### Scenario 1: Getting a general overview <a id="anameoverviewascenario1gettingageneraloverview"></a>

In this scenario, you've likely just heard about a new thing and your questions might be "What is it?" or, "What does it do?" or, "What is this used for?" These questions can usually be answered by reading the front page of the docs. The front page usually contains a summary of the software.

Let's take the [Canvas API docs](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API), for example. Right away we learn what canvas is, what it's used for, and what browser support looks like. The nice thing about this page too is that it immediately provides a code example.

Browsing the headings of the Table of Contents or Class Reference can give us an idea of how large the library is and what types of methods it contains. A glance through the Changelog will help us understand how long the software has been around and how active the maintainers are. We might also want to skim through some of the usage examples or tutorials to get a basic understanding of how complicated the code is.

Again, using the Canvas API docs as an example, we can look at Interfaces section of the links in the left side bar to get an idea of how large its API is. This list matches up with the [Reference](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API#Reference) section found further down the page. It contains a lot less than the jQuery API reference. I didn't find a Changelog, but but if we scroll to the bottom of the page we can see the page was updated a few months ago, which means we can trust that these docs are active and up to date.

#### Scenario 2: Learning how to get started <a id="anamegettingstartedascenario2learninghowtogetstarted"></a>

If you need more than an overview, and you want to get started writing code as quickly as possible, you'll want to look for a Getting Started Guide. It is common for popular and well-supported docs to offer this. If you are using a small open source library, you might not get so lucky.

The [jQuery API docs](http://api.jquery.com/) link us to the [jQuery Learning Center](http://learn.jquery.com/) right from the first paragraph. Here, we find a [basics tutorial](http://learn.jquery.com/about-jquery/how-jquery-works/) with code examples of how to get started.

The [Canvas API docs from MDN](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) provide and easy access [Canvas Tutorial series](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage) at the top of their related links. In addition, if we scroll down the front page of the Canvas API docs, there is a [Resources](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API#Resources) section that provides links to external tutorials and canvas libraries.

The React docs start out immediately by showing a [Hello World example](https://reactjs.org/docs/hello-world.html) which is pretty handy.

#### Scenario 3: Finding help when you're stuck <a id="anamestuckascenario3findinghelpwhenyourestuck"></a>

This is probably the most common and complicated scenario you'll find yourself in. You already have some experience, you're coding along, and then one day need to do something specific and you don't know how to do it. I think the best way to show how we usually handle this scenario is to go through a simple example.

Let's say you want to show a greeting on your website depending on the day in JavaScript. You may have learned how to get the time but you can't remember the syntax. The first thing you might do is Google "get current time in JavaScript". The first three results will likely be similar to the ones in the image below.

![](http://cassandrawilcox.me/content/images/2017/12/Screen-Shot-2017-12-27-at-10.42.42.png)

The first result is from StackOverflow. StackOverflow provides lots of helpful answers but it isn't going to help us understand how to use documentation so I'm going to skip over it in this example. I may write a followup post about how to get the most out of StackOverflow later, but that's not what this post is about.

The next result is [Date.now Function \(JavaScript\) \| Microsoft Docs](https://docs.microsoft.com/en-us/scripting/javascript/reference/date-now-function-javascript). I'm not familiar with Microsoft's JavaScript docs, but let's go ahead and check them out.

![](http://cassandrawilcox.me/content/images/2017/12/Screen-Shot-2017-12-27-at-10.47.26.png)

They look pretty good. We have a Class Reference to the left, the main article in the middle, and headings within the article are listed to the right. First we see the syntax for `Date.now()`. Below that it says the return value is a number of milliseconds. We want the current time in hours, right? So let's try out that filter to the left above the class reference. We will filter for the keyword 'hour'.

![](http://cassandrawilcox.me/content/images/2017/12/Screen-Shot-2017-12-27-at-10.52.19.png)

Aha! We see [getHours Method \(Date\)](https://docs.microsoft.com/en-us/scripting/javascript/reference/gethours-method-date-javascript) which looks promising. Upon clicking through, it shows the syntax `dateObj.getHours()`.

So you go paste it into JSBin to verify that it works and you are disappointed to see an error: `"ReferenceError: dateObj is not defined..."`. What the heck? I'll get into how to read syntax markup like this in a little bit, but for now, let's scroll a little further down the page to find an example. Hooray for examples! Unfortunately, the example given has way more going on than what we need.

![](http://cassandrawilcox.me/content/images/2017/12/Screen-Shot-2017-12-27-at-11.02.05.png)

On line 1 we see `var date = new Date("1/1/2001");`. To understand what is going on here we need to jump over to the documentation for [Date Object](https://docs.microsoft.com/en-us/scripting/javascript/reference/getday-method-date-javascript). It shows us 3 lines of syntax and if you start reading the Parameters section below it, you head might start to hurt a little. Its saying that a lot of the values shown are required, and that doesn't seem quite right. At this point we might want to get a second opinion from another set of documentation.

Let's see what the [JavaScript Reference from MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) has to say. They don't offer a handy filter but if you use `command + f` and search for "date", it brings you right to the section "Numbers and dates" where you can click on the [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) link.

If we read the Description section, we learn that "If no arguments are provided, the constructor creates a JavaScript Date object for the current date and time according to system settings." Now we know that we can start with `new Date();` to get a date **object**that represents the current date. This is confirmed by the first example in the Examples section, `var today = new Date();`, so you might grab that code to start with.

Now, back to getting the current hour. Since `new Date();` returns an object, we can assume that it will contain properties and methods that will allow us to get the current day in the format that we need.

Earlier, we found a method called `getHours` so let's try accessing that method on our current date object.

```text
var today = new Date();
var currentHour = today.getHours();
console.log(currentHour);
```

It works! Thank you documentation! So, you see, it can be helpful to use multiple sources of documentation, if you have that luxury. Now, let's dive into that syntax markup, because that is really going to help us understand how to use and structure our code.

## Understanding Syntax Definitions

One of the most confusing parts about documentation, especially for beginners, is how to understand complex syntax definitions. Here is an example of what the syntax definition for `array.map` looks like from [MDN Web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map).

![syntax definition screenshot](http://cassandrawilcox.me/content/images/2018/01/Screen-Shot-2018-01-08-at-10.22.52.png)

That blue block is quite overwhelming. There are a lot of parentheses and square brackets and commas in weird places. If you're like me, you probably just skim past syntax definitions like this in favor of clearer code examples. We will get into exactly what the above syntax definition means in a bit.

There doesn't seem to be a source of truth on the meaning of syntax definitions in most JavaScript documentation. I looked all over the internet for an answer on how these syntax definitions are structured and I couldn't find anything. I asked several experienced developers in my community and they all shrugged their shoulders. Consensus seems to be that you just sorta get a feel for with experience. So, I've decided to go ahead and write out the rules that I've been able to infer on my own and share them with you. I'm going to do that by showing some examples and explaining what they mean. Here we go!

#### Return type <a id="returntype"></a>

```text
void ctx.fillRect(x, y, width, height);
```

This syntax definition is fairly easy to understand. We have a `ctx` object with a `fillRect`method that takes for arguments. But what is that `void` token doing there at the beginning? `void` is a JavaScript operator that is used to evaluate a given expression and then return `undefined`. In syntax definitions it can be used to signify that the following function/method returns `undefined` by default.

```text
Array ctx.getLineDash();
```

In this example, the preceding `Array` token represents that the return type of this method is an array.

#### Optional syntax <a id="optionalsyntax"></a>

```text
ctx.currentTransform [= value];
```

\(where value is an SVGMatrix\)

Square brackets are often used to represent optional syntax. In the example above, the square brackets are used to show that `ctx.currentTransform` can be used as either a 'getter' or a 'setter'. If we exclude the bit in square brackets, we can get the current value of `ctx.currentTransform`. If we include the bit in square brackets we can set a new value with `ctx.currentTransform = mySVGMatrix;`

#### Possible values <a id="possiblevalues"></a>

```text
ctx.direction = "ltr" || "rtl" || "inherit";
```

The above demonstrates that one of the given values is required to set the property. `||`means or. This syntax definition tells us that we can set `ctx.direction` to exactly one of the given values.

#### Alternate variations <a id="alternatevariations"></a>

```text
ctx.fillStyle = color;
ctx.fillStyle = gradient;
ctx.fillStyle = pattern;
```

The above represents the different ways we can use the given method. You can use it in any of the three ways given. The reason we are given three complete examples here, instead of one example with the possible values separated by `||` like the example above, is that each of these possible values has a different type. In the previous example, each possible value was a string. In this example, the first possible value is a `DomString`string, the second is a `CanvasGradient` object, and the last is a `anvasPattern` object. A description of each value is provided within the [documentation](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillStyle).

```text
void ctx.arc(x, y, radius, startAngle, endAngle [, anticlockwise]);
```

The above example describes a method that requires five parameters \(`x`, `y`, `radius`, `startAngle`, and `endAngle`\) and may optionally accept a sixth parameter \(`anticlockwise`\). It returns `undefined` \(void\).

#### DomStrings <a id="domstrings"></a>

```text
ctx.filter = "<filter-function1> [<filter-function2] [<filter-functionN]";
ctx.filter = "none";
```

When you see caret brackets surrounding a token, it represents a `DomString`. When working with JavaScript, we can think of simply consider these as strings. These strings are expected to be filter functions. We can provide one, two, or many, as demonstrated by the `N` in `filter-functionN`. What I'm not sure about is why there is no closing `>` at the end of the last two `DomStrings`. If you know the answer, please let me know in a comment below. I will be ever grateful!

This is likely not a complete list of all the weird things you might see in syntax definitions, but these are the most common. Some other things you might notice as you browse documentation is that some documentation shows all syntax options together \(MDN\) while others describe each option separately \(jQuery\). Often times, italics represent the parts the developer should replace with their own variable names.

Now, let's take another look at that `array.map` syntax we saw at the beginning of this section.![syntax definition screenshot](http://cassandrawilcox.me/content/images/2018/01/Screen-Shot-2018-01-09-at-16.51.35.png)

First we see `var new_array = arr` in italics which means we will be using our own variable names in these places. Next we se the `.map()` method with one required argument, a callback function, and one optional argument that determines what value to use as `this` in the callback \(see full screenshot above for more info\). We also see that the callback function takes a few arguments. The first is required, and represents the current value of the array. The next optional argument is the current index of the array, and the final optional argument is the array itself. within the callback function is a comment that tells us we should return an element that will be placed into the new array that `.map` will produce.

