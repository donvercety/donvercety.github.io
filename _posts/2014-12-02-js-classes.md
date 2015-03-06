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

2. Function-like Class using prototype, it must be instantiated before usage.

{% highlight js %}
// namespace 'Office'
var Office = Office || {};

Office.Users = (function() {

  // constructor
  function user() {
    console.log(isAdmin('pesho'));
  }

  // private properties
  user.username = 'unknown';
  user.age      = 'unknown';

  // public properties
  user.prototype.state  = 'development';
  user.prototype.deploy = false;

  // private method
  function isAdmin(name) {
    return name == 'admin' ? true : false;
  }

  // public methods
  user.prototype.setUsername = function(username) {
    user.username = username;
  };

  user.prototype.getUsername = function() {
    return user.username;
  };

  user.prototype.setAge = function(age) {
    user.age = age;
  };

  user.prototype.getAge = function() {
    return user.age;
  };

	return user;

}());

var test = new Office.Users();
{% endhighlight %}

3. Function-like Class, it must be instantiated before usage.
{% highlight js %}
function cityLocation() {
  var city = "Paris";

  return {
    get: function() {
      console.log(city);
    }, 
    set: function(newCity) {
      city = newCity;
    }
  };
}

var myLocation = cityLocation();

myLocation.get();           // output: Paris
myLocation.set('Sydney');
myLocation.get();           // output: Sydney
{% endhighlight %}

JavaScript is a very flexible object-oriented language when it 
comes to syntax. It's important to note that there are no classes 
in JavaScript. Functions can be used to somewhat simulate classes, 
but in general JavaScript is a class-less language.