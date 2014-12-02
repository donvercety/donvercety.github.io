---
layout: posts
title:  "Define a JavaScript class"
date:   2014-12-02 17:20:00
category: javascript
description: >
  JavaScript is a very flexible object-oriented language when it 
  comes to syntax. It's important to note that there are no classes 
  in JavaScript. Functions can be used to somewhat simulate classes, 
  but in general JavaScript is a class-less language. Here are the two
  ways I use to create classes.
---

Define a JavaScript class
-------------------------

Here are the two ways I use to create classes.

1. Object-like Class, no instantiation is needed.

{% highlight js %}
var name = {

	methodOne: function() {
		// code
	},

	methodTwo: function( param ) {
		// code
	}
};

name.methodTwo('hello');

{% endhighlight %}

2. Function-like Class, it must be instantiated before usage.

{% highlight js %}
var name = (function() {

	// Constructor
	function SomeName() {
		// code
	}

	SomeName.prototype.methodName = function() {
		// code
	};

	return SomeName;

}());

var test = new name();

{% endhighlight %}

JavaScript is a very flexible object-oriented language when it 
comes to syntax. It's important to note that there are no classes 
in JavaScript. Functions can be used to somewhat simulate classes, 
but in general JavaScript is a class-less language.