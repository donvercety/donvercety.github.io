---
layout: posts
title:  "Return data after success AJAX call"
date:   2014-12-10 08:05:00
category: javascript
description: >
  The only way to return the data from the function would be 
  to make a synchronous call instead of an asynchronous call, 
  but that would freeze up the browser while it's waiting for 
  the response. You can pass in a callback function that handles 
  the result or even better you can use a promise.
  You can store your promise, you can pass it around, you can 
  use it as an argument in function calls and you can return it 
  from functions, but when you finally want to use your data that 
  is returned by the AJAX call.
---

jQuery: Return data after success AJAX call
-------------------------------------------

---

#### Using a callback:

The only way to return the data from the function would be to make a synchronous call instead of an asynchronous call, but that would freeze up the browser while it's waiting for the response.

You can pass in a callback function that handles the result:

{% highlight js linenos %} 
function testAjax(handleData) {
  $.ajax({
    url:"getvalue.php",  
    success:function(data) {
      handleData(data); 
    }
  });
}
{% endhighlight %}

Call it like this:

{% highlight js linenos %} 
testAjax(function(output){
  // here you use the output
});
// Note: the call won't wait for the result,
// so it will continue with the code here while waiting.
{% endhighlight %}

#### Using a promise:

You can't return anything from a function that is asynchronous. What you can return is a promise.
{% highlight js linenos %} 
function testAjax() {
  return $.ajax({
      url: "getvalue.php"
  });
}

// get your promise like this
var promise = testAjax();
{% endhighlight %}

You can store your promise, you can pass it around, you can use it as an argument in function calls and you can return it from functions, but when you finally want to use your data that is returned by the AJAX call, you have to do it like this:

{% highlight js linenos %} 
promise.success(function (data) {
  alert(data);
});
{% endhighlight %}
Source [Stack Overflow](http://stackoverflow.com/questions/5316697/jquery-return-data-after-ajax-call-success)
