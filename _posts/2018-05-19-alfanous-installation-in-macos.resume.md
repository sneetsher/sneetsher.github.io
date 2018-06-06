---
layout: post
title:  "تجريب التثبيت للفانوس في ن.ت. ماك"
date:   2018-06-05 22:06:30 +0100
categories: alfanous
comments: true
---

سجل خام للأوامر
---

{% highlight sh %}
# installed Qt Creator package comes with Qt5 not Qt4 :/

pip install pyparsing
pip install epydoc
pip install sphinx

brew install cmake    # brobably not needed
PATH=$PATH:/Users/sneetsher/Qt/5.10.1/clang_64/bin/
pip install pyside	  # didn't work.. 

brew tap cartr/qt4
brew tap-pin cartr/qt4
brew install qt@4

brew install qt-webkit@2.3    # not sure if needed

brew install pyside
brew install pyside-tools

ln /usr/local/bin/lrelease /usr/local/bin/lrelease-qt4
make build

sudo make install_api_no_arguments

sudo make install_desktop_no_arguments  
# alfanous installing pyside using pip, didn't detect brew one.
# also tries to install in same system file structure of Linux.

pip install django==1.5.1
./manage.py runserver
{% endhighlight %}