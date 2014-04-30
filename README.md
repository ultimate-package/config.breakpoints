config.breakpoints
==================

This module defines the global breakpoints and width variables for generating media queries in CSS.

First we set the default min-width breakpoints and then add these values to the $breakpoints list. With the breakpoint respond-to feature we can then use media queries like this:

```scss
.module {
    color: yellow;
 
    @include respond-to("small and above"){
      color: red;
    }

    @include respond-to("medium and above"){
      color: blue;
    }
}
```

For more information visit the [Breakpoint docs](http://breakpoint-sass.com/) or read more about the [respond-to mixin](https://github.com/Team-Sass/breakpoint/wiki/Respond-To) that we use above.


