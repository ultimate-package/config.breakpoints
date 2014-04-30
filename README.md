config.breakpoints
==================

Defines the global breakpoints and width variables for generating media queries in CSS. This module contains the defaults for [Breakpoint](http://breakpoint-sass.com/), a [Compass](http://compass-style.org/) extension, which helps us write simple, responsive components. 

When we import our styles into a single stylesheet we’ll import these settings after we import Compass and Breakpoint:

```scss
@import "compass";
@import "breakpoint";
@import "breakpoint-settings";

@import "styles";
```

First we set the default min-width breakpoints in the `_breakpoint-settings.scss` file: 

```scss
$width__small: 425px;
$width__medium: 575px;
$width__large: 750px;
$width__largest: 900px;
```

Afterwards we can then add these values to the `$breakpoints` list beneath them

```scss
$breakpoint-to-ems: true;

$no-queries: 'no-query' true;

$breakpoints: add-breakpoint('small only', (max-width $width__small - 1px, $no-queries));
$breakpoints: add-breakpoint('small and above', ($width__small, $no-queries));
$breakpoints: add-breakpoint('between small and medium', ($width__small $width__medium));
$breakpoints: add-breakpoint('below medium', (max-width $width__medium - 1px, $no-queries));
$breakpoints: add-breakpoint('medium and above', ($width__medium, $no-queries));
$breakpoints: add-breakpoint('between medium and large', ($width__medium $width__large));
```


Then, inside another module (say `_media.scss` or `_island.scss`), we can take advantage of Breakpoint’s `respond-to mixin` to create simple, legible media queries like so:

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


## Browser support 

This set up is designed to allow us to easily serve stylesheets to more difficult browsers. If we needed to serve stuf


```
$breakpoint-no-queries: true;
$breakpoint-no-query-fallbacks: true;
```


For more information visit the [Breakpoint docs](http://breakpoint-sass.com/) or read more about the [respond-to mixin](https://github.com/Team-Sass/breakpoint/wiki/Respond-To) that we use above.


