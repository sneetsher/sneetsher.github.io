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

دعم العربية أو الكتابة من اليمين
---

ملاحظة، تقرير مغلق لا يعني بالضرورة أن العلة قد حلت.

- Bootstrap

    jQuery

- FamousEngine (3d engine) is not active

    WebGL, AngularJS

- [Framework7](http://framework7.io/)

    Custom DOM (same syntax as jQuery), Vue.js

    [Framework7 RTL bugs](https://github.com/framework7io/framework7/issues?utf8=%E2%9C%93&q=is%3Aissue+%28Arabic+OR+RTL%29)

- [ionic](https://ionicframework.com/)
    
    node.js (dev), AngularJS (opt)

    [ionic RTL bugs](https://github.com/ionic-team/ionic/issues?utf8=%E2%9C%93&q=is%3Aissue+%28Arabic+OR+RTL%29+)

- [jQuery Mobile](https://jquerymobile.com/)

    jQuery

    [jQuery Mobile RTL bugs](https://github.com/jquery/jquery-mobile/issues?utf8=%E2%9C%93&q=is%3Aissue+%28Arabic+OR+RTL%29)

- [NativeScript](https://www.nativescript.org/)

    Angular|Vue.js|TypeScript|JavaScript

    [NativeScript RTL bugs](https://github.com/NativeScript/NativeScript/issues?utf8=%E2%9C%93&q=is%3Aissue+%28Arabic+OR+RTL%29+)

- [OnsenUI](https://onsen.io/)

    AngularJS1|Angular2+|React|Vue

    [OnsenUI RTL bugs](https://github.com/OnsenUI/OnsenUI/issues?utf8=%E2%9C%93&q=is%3Aissue+%28Arabic+OR+RTL%29+)

- [Facebook: REACT NATIVE](http://www.reactnative.com/react-native-march-2018-v0-55-0-released/)

    React

    [REACT NATIVE RTL bugs](https://github.com/facebook/react-native/issues?utf8=%E2%9C%93&q=is%3Aissue+%28Arabic+OR+RTL%29)