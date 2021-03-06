FancySelect
===========

A better select for discerning web developers everywhere, lovingly crafted by [Octopus Creative](http://octopuscreative.com). You can download it here, or [check out the demo](http://code.octopuscreative.com/fancyselect/).

Basic Usage
-----------

FancySelect is easy to use. Just include jQuery or Zepto, target any `select` element on the page, and call `.fancySelect()` on it. If the select has an option with no value, it'll be used as a sort of placeholder text.

By default, FancySelect uses native selects and styles only the trigger on iOS devices. To override this, pass an object with `forceiOS` set to `true` when initializing it.

FancySelect also passes any classes specified in the select's `data-class` attribute, which you can use to style specific FancySelect instances.


### HTML

``` html
<select class="basic">
  <option value="">Select something…</option>
  <option>Lorem</option>
  <option>Ipsum</option>
  <option>Dolor</option>
  <option>Sit</option>
  <option>Amet</option>
</select>
```

### JavaScript

``` javascript
$('.basic').fancySelect();
```

Updating Options
----------------

If the options in your select change after initializing FancySelect, you can tell it to rebuild the list of options by triggering `replace` on the select element.

### JavaScript

``` javascript
var mySelect = $('.my-select');

mySelect.fancySelect();

mySelect.append('<option>Foo</option><option>Bar</option>');

mySelect.trigger('update');
```

Enabling/Disabling
------------------

FancySelect will automatically pick up your `select`'s `disabled` property on initialization. If you need to enable or disable it again later, you can do that by triggering `enable` or `disable` on your select element.

### HTML

``` html
<select class="my-select" disabled>
	<option>First Option</option>
	<option>Second Option</option>
</select>
```

### JavaScript

``` javascript
var mySelect = $('.my-select');
mySelect.fancySelect(); // currently disabled because of html property

// later…
mySelect.trigger('enable'); // now enabled

// even later…
mySelect.trigger('disable'); // now disabled again
```