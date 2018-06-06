---
layout: post
title:  "تجريب Cordova لتطبيقات الجوال"
date:   2018-06-05 22:06:30 +0100
categories: alfanous
comments: true
---

سرد خام للأوامر
---

{% highlight sh %}
## pre-installed:
# homebrew
# android studio
# jdk, v10 not compatible yet, v8 (jdk-1.8) works

# instructions:

brew install npm
npm install -g cordova
cordova create myApp_cordova
cd myApp_cordova
cordova platform add android
cordova platform add browser
cordova run browser
brew install gradle
{% endhighlight %}
