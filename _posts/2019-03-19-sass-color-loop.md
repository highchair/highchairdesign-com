---
layout: post
title: "SASS Color Loops are Awesome"
date: 2019-03-19 15:00:00 -0500
categories: [ "Web Development", CSS ]
---

## Managing Color Themes with SASS Maps

SASS maps are great for storing information, but their real power comes out when you create a mixin or loop that traverses the map. 

We had a recent project where we had a number of background colors that could be used in the project — 30 to be exact. It seems easy at first, but with accessibility we needed to also factor how the colors of other elements might work over the selected color. We had to track foreground (text) color, header colors, link colors, link hover colors, and focus state colors. It quickly became a lot to organize and deal with. 

The power of SASS Maps helped keep these clean, and SASS loops did the heavy lifting of writing out the class declarations that we needed. 

### A one-dimensional SASS Map

At the very core, a SASS map is just a list — two or more key:value pairs in parenthesis: 

{% highlight sass %}
  $colors: (
    fg: $dark-gray,
    bg: $white,
  );
  
  /* Get values out of a map with map-get() */
  .element {
    color: map-get($colors, fg);
    background-color: map-get($colors, bg);
  }
{% endhighlight %}

Pretty simple. Too simple, in fact. To manage a list of colors associated with other colors, we need to take this list into another dimension. 

### A multi-dimensional SASS Map

Any level of nesting is supported, but just know that getting the values back out can be a little bit mind-bendy: 

{% highlight sass %}
  $colors: (
    white: (
      fg: $dark-gray,
      bg: $white,
    ),
    black: (
      fg: $light-gray,
      bg: $black,
    ),
  );
  
  /* Get values out of a map with a nested map-get() */
  .light-element {
    color: map-get(map-get($colors, white), fg);
    background-color: map-get(map-get($colors, white), bg);
  }
  
  .dark-element {
    color: map-get(map-get($colors, black), fg);
    background-color: map-get(map-get($colors, black), bg);
  }
{% endhighlight %}

The nested `map-get()` is where our minds might get bent. In this first position of the function, we are specifying a deeper map, and the second part — the value that we want to extract — remains the same. To make it easier, we can create a function to go deeper, but that's not what we are talking about right now ([Here is a nice function that does it, though](https://css-tricks.com/snippets/sass/deep-getset-maps/)).

 
### Looping over a multi-dimensional SASS map

To make all of this really powerful we can introduce a SASS loop. If we set up the structure of our color map correctly, we can construct a loop that will do the heavy lifting for us. In the future, all we would need to do is add or edit values in the map itself, and everything else will update along with it. In that project I mentioned, we ended up with something like what follows. One of the key things to understand is that our theme expects the `.bg-[value]` class on a container, and therefore, everything inside inherits the styles we are setting.

{% highlight sass %}
  /* A multidimensional SASS map */
  $color-map: (
    darkblue: (
      fg: $white,
      bg: $brand-darkblue,
      link: $white,
      hover: $gray-300,
      border: $brand-blue,
    ),
    gray-900: (
      fg: $gray-400,
      bg: $gray-900,
    ),
    white: (
      bg: $white,
      link: $brand-orange-a11y,
      border: $brand-lightergray,
    ),
  );
  
  /* Our Mixin (simplified) */
  @mixin traverse-color-map($bg-color: white) {
    @if variable-exists(color-map) == false {
      @warn 'The required color map `$color-map` is not defined';
    }
  
    /* Background color */
    @if map-has-key(map-get($background-color-map, $bg-color), bg) {
      background-color: map-get(map-get($background-color-map, $bg-color), bg);
    }

    /* Foreground color */
    @if map-has-key(map-get($background-color-map, $bg-color), fg) {
      color: map-get(map-get($background-color-map, $bg-color), fg);
    }
  
    /* Anchor colors */
    @if map-has-key(map-get($background-color-map, $bg-color), link) {
      a:not(.btn) {
        color: map-get(map-get($background-color-map, $bg-color), link);
      }
    }
  
    /* Anchor hover/active colors */
    @if map-has-key(map-get($background-color-map, $bg-color), hover) {
      a:not(.btn):hover,
      a:not(.btn):active {
        color: map-get(map-get($background-color-map, $bg-color), hover);
      }
    }
  }
  
  /* And then our mixin applied inside a Loop */
  @each $class, $colors in $background-color-map {
    .bg-#{$class} {
      @include traverse-color-map($class);
    }
  }
  
  /* Which outputs, as a sample: */
  .bg-darkblue {
    background-color: #005172;
    color: #fff;
  }
  
  .bg-darkblue a:not(.btn) {
    color: #fff;
  }
  
  .bg-darkblue a:not(.btn):hover,
  .bg-darkblue a:not(.btn):active {
    color: #d3d3d3;
  }
{% endhighlight %}


Notes of interest: 
+ Even though you might be creating this for yourself, adding a `@warn` message makes sure that things don’t quietly break without notification
+ If the loop smartly checks for the existence of values, each SASS map portion does not need to have all the same values — only the ones that need to be defined _different_ from the default in the cascade
+ A `border` keyword is being defined here, but it is not used in our example mixin. In our project, we used this color map to store things that we pull out in specific loops of their own which only output the values of certain keys


[SASS]: Syntacically Awesome Style Sheets