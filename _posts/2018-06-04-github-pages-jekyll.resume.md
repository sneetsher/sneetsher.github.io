---
layout: post
title:  "Github-pages مستعملا Jekyll"
date:   2018-06-04 07:12:30 +0100
categories: github
---

1. مرجع

    - [https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)
    - [https://desiredpersona.com/install-jekyll-on-macos/](https://desiredpersona.com/install-jekyll-on-macos/)

2. مستودع غت

    `git clone git@github.com:sneetsher/sneetsher.github.io.git`

3. أدوات

        ruby -v
        sudo gem install bundler
        vim Gemfile
        sudo bundle install

    > فشل nokogiri-1.8.2 عند البناء مع lzma
    > 
    > bug# [Unable to install Nokogiri on Mac OS 10.13 with lzma from homebrew](https://github.com/sparklemotion/nokogiri/issues/1693)

    >        brew unlink xz
    >        sudo gem install nokogiri
    >        brew link xz

4. إنشاء وصيانة

        bundle exec jekyll new .
        bundle exec jekyll serve
        bundle update github-pages
        cp -r $(bundle show minima)/_* $(bundle show minima)/assets/ .

5. تعديل السمة للعربية (يمين إلي اليسار)

    commit# [https://github.com/sneetsher/sneetsher.github.io/commit/76dfd672ae5ffa2b0a81aad4d6b9545e53607a9d](https://github.com/sneetsher/sneetsher.github.io/commit/76dfd672ae5ffa2b0a81aad4d6b9545e53607a9d)

{% highlight diff  %}
diff --git a/_sass/minima.scss b/_sass/minima.scss
index cb0865b..c4db392 100644
--- a/_sass/minima.scss
+++ b/_sass/minima.scss
@@ -2,7 +2,18 @@
 
 // Define defaults for each variable.
 
+/* RTL */
+$base-direction: rtl !default;
+$side-start: right;
+$side-end: left;
+@font-face {
+  font-family: Amiri;
+  src: url(https://lib.arvancloud.com/ar/font/Amiri/Amiri.woff2);
+}
+/* RTL end */
+
 $base-font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol" !default;
+$base-font-family: Amiri; /* RTL */
 $base-font-size:   16px !default;
 $base-font-weight: 400 !default;
 $small-font-size:  $base-font-size * 0.875 !default;
@@ -18,7 +29,7 @@ $grey-color:       #828282 !default;
 $grey-color-light: lighten($grey-color, 40%) !default;
 $grey-color-dark:  darken($grey-color, 25%) !default;
 
-$table-text-align: left !default;
+$table-text-align: $side-start !default;
 
 // Width of the content area
 $content-width:    800px !default;
diff --git a/_sass/minima/_base.scss b/_sass/minima/_base.scss
index 248fad0..c25f16e 100644
--- a/_sass/minima/_base.scss
+++ b/_sass/minima/_base.scss
@@ -1,3 +1,13 @@
+/* rtl */
+body {
+  direction: $base-direction;
+}
+
+pre, code {
+  direction: ltr;
+}
+/* RTL end */
+
 /**
  * Reset some basic elements
  */
@@ -75,7 +85,7 @@ figcaption {
  * Lists
  */
 ul, ol {
-  margin-left: $spacing-unit;
+ margin-#{$side-start}: $spacing-unit;
 }
 
 li {
@@ -127,10 +137,10 @@ a {
  */
 blockquote {
   color: $grey-color;
-  border-left: 4px solid $grey-color-light;
-  padding-left: $spacing-unit / 2;
+  border-#{$side-start}: 4px solid $grey-color-light;
+  padding-#{$side-start}: $spacing-unit / 2;
   @include relative-font-size(1.125);
-  letter-spacing: -1px;
+  /* letter-spacing: -1px; */ /* RTL */
   font-style: italic;
 
   > :last-child {
@@ -210,7 +220,7 @@ pre {
     height: 16px;
     display: inline-block;
     fill: #{$grey-color};
-    padding-right: 5px;
+    padding-#{$side-end}: 5px;
     vertical-align: text-top;
 }
 
diff --git a/_sass/minima/_layout.scss b/_sass/minima/_layout.scss
index c20e202..551f17f 100644
--- a/_sass/minima/_layout.scss
+++ b/_sass/minima/_layout.scss
@@ -14,9 +14,9 @@
   @include relative-font-size(1.625);
   font-weight: 300;
   line-height: $base-line-height * $base-font-size * 2.25;
-  letter-spacing: -1px;
+  /* letter-spacing: -1px; */ /* RTL */
   margin-bottom: 0;
-  float: left;
+  float: $side-start;
 
   &,
   &:visited {
@@ -25,7 +25,7 @@
 }
 
 .site-nav {
-  float: right;
+  float: $side-end;
   line-height: $base-line-height * $base-font-size * 2.25;
 
   .nav-trigger {
@@ -42,22 +42,22 @@
 
     // Gaps between nav items, but not on the last one
     &:not(:last-child) {
-      margin-right: 20px;
+      margin-#{$side-end}: 20px;
     }
   }
 
   @include media-query($on-palm) {
     position: absolute;
     top: 9px;
-    right: $spacing-unit / 2;
+    $side-end: $spacing-unit / 2;
     background-color: $background-color;
     border: 1px solid $grey-color-light;
     border-radius: 5px;
-    text-align: right;
+    text-align: $side-end;
 
     label[for="nav-trigger"] {
       display: block;
-      float: right;
+      float: $side-end;
       width: 36px;
       height: 36px;
       z-index: 2;
@@ -66,7 +66,7 @@
 
     .menu-icon {
       display: block;
-      float: right;
+      float: $side-end;
       width: 36px;
       height: 26px;
       line-height: 0;
@@ -93,9 +93,9 @@
       padding: 5px 10px;
 
       &:not(:last-child) {
-        margin-right: 0;
+        margin-#{$side-end}: 0;
       }
-      margin-left: 20px;
+      margin-#{$side-start}: 20px;
     }
   }
 }
@@ -118,20 +118,20 @@
 .contact-list,
 .social-media-list {
   list-style: none;
-  margin-left: 0;
+  margin-#{$side-start}: 0;
 }
 
 .footer-col-wrapper {
   @include relative-font-size(0.9375);
   color: $grey-color;
-  margin-left: -$spacing-unit / 2;
+  margin-#{$side-start}: -$spacing-unit / 2;
   @extend %clearfix;
 }
 
 .footer-col {
-  float: left;
+  float: $side-start;
   margin-bottom: $spacing-unit / 2;
-  padding-left: $spacing-unit / 2;
+  padding-#{$side-start}: $spacing-unit / 2;
 }
 
 .footer-col-1 {
@@ -188,7 +188,7 @@
 }
 
 .post-list {
-  margin-left: 0;
+  margin-#{$side-start}: 0;
   list-style: none;
 
   > li {
@@ -217,7 +217,7 @@
 
 .post-title {
   @include relative-font-size(2.625);
-  letter-spacing: -1px;
+  /* letter-spacing: -1px; */ /* RTL */
   line-height: 1;
 
   @include media-query($on-laptop) {
{% endhighlight %}

{% highlight diff %}
diff --git a/_sass/minima/_base.scss b/_sass/minima/_base.scss
index c25f16e..00664de 100644
--- a/_sass/minima/_base.scss
+++ b/_sass/minima/_base.scss
@@ -5,6 +5,7 @@ body {
 
 pre, code {
   direction: ltr;
+  text-align: left;
 }
 /* RTL end */
{% endhighlight %}
