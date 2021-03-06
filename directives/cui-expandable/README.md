# CUI expandable
Version 1.0


### Description
Cui-expandable is an angular directive that allows for the easy creation of an element that collapses.

### Usage Example
#### Markup
```html
  <cui-expandable class="cui-expandable expanded">
    <cui-expandable-title class="cui-expandable__title" ng-click="toggleExpand()">
      Not expanded
    </cui-expandable-title>
    <cui-expandable-body class="cui-expandable__body">
      Expanded
    </cui-expandable-body>
  </cui-expandable>
```

Adding expanded class to cui-expandable will show the expanded view by default. (`class="expanded"`)

### How it works / features
Everytime `toggleExpand()` gets fired from an element inside of the directive the `expanded` class will toggle. This, coupled with css rules allows the user to expand or collapse the view. You also get a scope variable called `expanded` that you can use to manipulate other elements within the expandable.
You can also use `expand()` or `collapse()` to only open or only collapse the expandable.

## Change Log 1/14/2016

* Now has a scope variable called expanded that will be true when the cui-expandable element has the expanded class. This variable should be read only and altering it will not toggle the expansion - for that use the scope method `toggleExpand()`.
* Now can be only expanded or only closed using `expand()` or `collapse()`.

## Change Log 2/18/2016

* Now using jquery's `animate({'height':'toggle'})` to toggle the height, rather than having a max-height set on the body. This makes the animations feel much smoother and more responsive.

## Change Log 2/25/2016

* Now takes an optional attribute, `transition-speed`, which is the millisecond value of the transition on expand / collapse (default is 300ms, but for smaller expandables a smaller value is recommended).

## Change Log 5/13/2016

* Fixes issue where if there was a label inside of the element with toggleExpand() and the label got clicked it would fire toggleExpand twice. To use this fix, you will have to call toggleExpand with the ng-click event, if there is a label within that toggle expand element. (`ng-click="toggleExpand($event)"`)