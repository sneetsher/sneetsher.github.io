---
layout: post
title:  "دعم العربية والكتابة من اليمين في الواب"
date:   2018-06-05 22:06:30 +0100
categories: web
comments: true
---

مراجع
---

- [Structural markup and right-to-left text in HTML](https://www.w3.org/International/questions/qa-html-dir)
- [Inline markup and bidirectional text in HTML](https://www.w3.org/International/articles/inline-bidi-markup/)
- [CSS done right - Post RTLCSS](https://tech.trivago.com/2017/07/07/css-done-right---post-rtlcss/)
- [RTL CSS: Flipping the Web..](https://rtl-css.net/)
- [RTL CSS with Sass](http://matanich.com/2013/09/06/rtl-css-with-sass) by Tyson Matanich.

ميزات دعم ثنائية الإتجاه أو Bi-Directional
---
- HTML

    {% highlight html %}
    <!-- HTML tags -->
    <dbi>
    <bdo>
    <!-- HTML attributes -->
    <... dir="ltr | auto | rtl" />
    {% endhighlight %}

- CSS

    {% highlight css %}
    /* CSS selectors */
    dir=rtl],
    :dir(rtl) /* ff-only :/ */
    {
      /* CSS properties */
      direction: ltr | rtl;
      unicode-bidi: ;
      writing-mode: ;
      text-orientation: ;     /* lab */
      text-combine-upright: ; /* lab */
    }
    {% endhighlight %}


- Other positional/visual-control HTML attributes & CSS properties & values

الوضع الحالي
---

- نسبة ذات أثر من المصممين الأعاجم بلا خبرة التعامل مع الكتابة من اليمين أو من الأعلى.
- مقاييس CSS  ليست تامة بعد فيما يخص التعامل مع كل أنواع الكتابة المعرفة في اليونيكود.

    لم تشمل بعض الخصائص الأساسية فيضطر المصممون لترقيعها، أمثلة على ذلك.

    {% highlight css %}
    /* Visual only properties or values */

    margin-left: x;
    float: left;

    /* Why not having similar properties & values that switch 
    with text direction, as long we have dir="auto". */

    /* Logical ones (relative to script base direction) */

    margin-script-start: x;
    margin-script-end: x;
    margin-script-top: x;
    float: script-start;

    /* There is no equivalent to HTML dir="auto" in CSS */

    /* Or if possible to get generic solution, by allowing 
    variables in CSS values & properties like in SCSS
    (or let's say scss on the fly) */
    {% endhighlight %}

- يمكن استخدام الأدوات التي تترجم LTR CSS إلى RTL CSS أليا.

    لكن لا يمكن حصر المصممين في طريقة استعمالهم للخليط HTML CSS JS. فلا مهرب من مراجعة المخرجات.

مشاريع ذات علاقة
---

- [RTLCSS](http://rtlcss.com/) [Source](https://github.com/MohammadYounes/rtlcss/) 
- [PostCSS](http://postcss.org/) [Source](https://github.com/postcss/postcss)
- [CSSJanus](https://cssjanus.github.io/) [Source](https://github.com/cssjanus/cssjanus)
- [twitter-archive/RTLtextarea](https://github.com/twitter-archive/RTLtextarea)

تحديث
---
2018-06-08

الحمدلله أضيف التموضع المنطقي إلى مسودة CSS للإصدار القادم

- [CSS Box Alignment Module Level 3](https://drafts.csswg.org/css-align-3/)
- [Understanding Logical Properties And Values](https://www.smashingmagazine.com/2018/03/understanding-logical-properties-values/)
- Check browser compability in [caniuse.com/](https://caniuse.com/)