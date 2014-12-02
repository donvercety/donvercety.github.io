---
layout: posts
title:  "Ionic Basics"
date:   2014-12-01 16:35:00
category: mobile
description: >
  Advanced HTML5 Hybrid Mobile App Framework.
  Free and open source, Ionic offers a library of mobile-optimized HTML, CSS and JS components, 
  gestures, and tools for building highly interactive apps. Built with Sass and optimized for AngularJS.
  Basic setup.
---

Ionic Basics
------------

**Start a new project:**

{% highlight bash %}

$ onic start myApp blank
$ cd myApp
$ ionic platform add android
$ ionic build android
$ ionic emulate android

{% endhighlight %}

**Run app with emulator or device:**

{% highlight bash %}

$ ionic emulate android
$ ionic run android

{% endhighlight %}

**Add default emulator for android-19**
{% highlight bash %}
$ android create avd --name Default --target android-19 --abi armeabi-v7a

$ android list avd          // list all virtual devices
$ emulator -avd Default     // start default emulator
{% endhighlight %}

**Basic usage of the adb interface**
{% highlight bash %}
$ adb kill-server
$ adb start-server
$ adb connect < ip >    // use device with WiFi
$ adb devices -l        // list all connected devices
{% endhighlight %}

<br />

*Helpfull links:*

 - [Ionic Website][ionic]

<!-- Links: -->

[ionic]: http://ionicframework.com/ "Ionic Website"