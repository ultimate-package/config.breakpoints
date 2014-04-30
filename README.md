config.breakpoints
==================

Defines the global breakpoints and width variables for generating media queries in CSS. This module contains the defaults for [Breakpoint](http://breakpoint-sass.com/), a [Compass](http://compass-style.org/) extension, which helps us write simple responsive components. 

When we import our styles into a single stylesheet we’ll import these settings after we import Compass and Breakpoint:

```scss
@import "compass";
@import "breakpoint"
@import "breakpoint-settings"

@import "styles";
```

Once we’ve set the default min-width breakpoints in the `_breakpoint-settings.scss` file we can then add these values to the `$breakpoints` list. Then, with the breakpoint respond-to mixin we can create simple, legible media queries like this:

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


