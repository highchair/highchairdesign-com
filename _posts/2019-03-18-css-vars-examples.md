---
layout: post
title: "CSS Variables are Awesome"
date: 2019-03-18 16:00:00 -0500
categories: [ CSS ]
---

## What SASS Variables can do vs. What CSS native Variables can do

SASS variables give us a lot of flexibility and repeatability and were the first on the scene to begin to give front-end developers a modern syntax for keeping our code more DRY. Now that CSS Variables are on the scene — also referred to as CSS Custom Properties — we have new powers with this native implementation.

### Both of them define variables in the global scope:

**SASS**
{% highlight css %}
$text-color__default: #444;
$text-size__default: 1rem;
{% endhighlight %}

**CSS Variables**
{% highlight css %}
:root {
  --text-color__default: #444;
  --text-size__default: 1rem;
}
{% endhighlight %}

_Wondering what `:root` is?_[^1]  


### We can also define variables in a local scope:

But there is an important difference here. In SASS, you can redefine a variable inside another declaration, but it will only maintain that value until the declaration is closed. The global value will be applied again after that: 

**SASS**
{% highlight css %}
$text-color__default: #444;

.class {
  $text-color__default: #c00;
  color: $text-color__default; /* render= color: #c00 */
}

.class {
  color: $text-color__default; /* render= color: #444 */
}
{% endhighlight %}

With CSS variables we can scope “element-relative” values, but here, the same variable will maintain that value whenever it is inside that element. This means that the variable can mean different things based on its context: 

**CSS Variables**
{% highlight css %}
:root {
  --text-color__default: #444;
}

.class {
  --text-color__default: #c00;
}

/* Therefore: */
.class {
  color: $text-color__default; /* render= color: #c00 */
}

p {
  color: $text-color__default; /* render= color: #444 */
}
{% endhighlight %}


### Further, CSS Variables cascade

Its a little bit of a mind-bender, but this starts to make sense if you already understand the “Cascade” in Cascading Style Sheets. 

**CSS Variables**
{% highlight css %}
body {
  --spacing: 2rem;
}

div {
  --spacing: 1.5rem;
}

/* Therefore: */
body {
  padding: var(--spacing); /* render= 2rem */
}

div {
  padding: var(--spacing); /* render= 1.5rem */
}

/* Assuming <body><div><p>[content]</p></div></body> */
p {
  padding: var(--spacing); /* render= 1.5rem */
}

/* But, if we have this <body><p>[content]</p></body> */
p {
  padding: var(--spacing); /* render= 2rem */
}
{% endhighlight css %}


### Math with Variables

Math can be done with the `calc()` css function. With CSS variables, the output is messier because SASS renders the value of the math and removes it from the source code. For CSS Variables, on the source code, a reader will still see the math.  

**SASS**
{% highlight css %}
$text-size__default: 1rem;

h1 {
  font-size: ($text-size__default * 2.5); /* render= font-size: 2.5rem */
}
{% endhighlight css %}

**CSS Variables**
{% highlight css %}
:root {
  --text-size__default: 1rem;
}

h1 {
  font-size: calc(var(--text-size__default) * 2.5); /* render= the same */
}
{% endhighlight css %}


## By Their Powers Combined

One can put these ideas together, though, and create a viewport-size-dependent set of font-sizes with much less code to achieve “[Fluid Typography](https://css-tricks.com/snippets/css/fluid-typography/)”. 

### Element scoping and CSS calc() together

**CSS Variables**
{% highlight css %}
:root {
  --text-size__default--min: 1;
  --text-size__default--max: 1.25;
  --min-vw: 40;
  --max-vw: 85;
  --unit: 1rem;
  
  h1 {
    --text-size__default--min: 2;
    --text-size__default--max: 4;
  }
  
  h2 {
    --text-size__default--min: 1.75;
    --text-size__default--max: 3.5;
  }
}

h1,
h2,
p {
  font-size: calc(
    (var(--text-size__default--min) * var(--unit)) + 
    (var(--text-size__default--max) - var(--text-size__default--min)) * 
    (
      (100vw - (var(--min-vw) * var(--unit))) / 
      (var(--max-vw) - var(--min-vw))
    )
  );
}
/* renders 3 different ways=
  h1 { font-size: calc(2rem + (4 - 2) * (100vw - 40rem) / (85 - 40)); }
  h2 { font-size: calc(1.75rem + (3.5 - 1.75) * (100vw - 40rem) / (85 - 40)); }
  p { font-size: calc(1rem + (1.25 - 1) * (100vw - 40rem) / (85 - 40)); }
*/
{% endhighlight css %}

The way the CSS works above is like magic — after a lengthy set of `:root` declarations, the one line that follows basically sets the same calculations on three different elements and will result in three different sets of measurements within the one declaration. 


## Other reasons to use CSS variables: 

+ **They can be changed via JS:** CSS variables make dynamic themeing pretty easy. Have JS change the value of a few CSS variables and you have a user-generated theme.
+ **They support fallback values:** The syntax of an inline fallback is `var(--custom-variable, fallback)` as in `color: var(--text-color__default, #444);`. It is not used to support old browsers, but rather it provides a fallback value in case the original value has not been defined. 


## Reasons not to use them quite yet:

+ **[No support in IE 11 or Edge < 15](https://caniuse.com/#feat=css-variables):** A fallback solution almost renders CSS variables useless. It means you have to declare a normal value as the fallback, i.e. `background-color: red; background-color: var(--bg-color)`. 


## Other Resources: 
+ [More and more at CSS Tricks](https://css-tricks.com/difference-between-types-of-css-variables/)
+ [A CSS Preprocessor vs Custom Properties showdown at Smashing Magazine](https://www.smashingmagazine.com/2018/05/css-custom-properties-strategy-guide/)


[^1]: The `:root` declaration is a way to declare values for CSS Variables that are global in scope. It is defined in the CSS Selectors Level 3 spec as a “structural pseudo-class”. 

[DRY]: Don’t Repeat Yourself