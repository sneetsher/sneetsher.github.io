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
