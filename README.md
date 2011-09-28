## jQuery.fn.autoResize

*This is a much-needed update of the [slightly buggy 2009 version](http://james.padolsey.com/javascript/jquery-plugin-autoresize/)*

A plugin for jQuery which changes the dimensions of input elements to suit the amount of data entered. It operates on `textarea`, `input[type=text]` and `input[type=password]` elements.

Usage is as follows:

	$('textarea#foo').autoResize();

You can pass options:

	$('textarea#foo').autoResize({
		maxHeight: 200,
		minHeight: 100
	});

Available options include:

 * `minWidth`: (default: `"original"`) A number or the string `"original"` to signify the current width as the minimum (note: This option is only useful on `<input>` elements, i.e. elements that resize width-ways)
 * `maxWidth`: (default: `500`) A number or the string `"original"` to signify the current width as the maximum (note: This option is only useful on `<input>` elements, i.e. elements that resize width-ways)
 * `minHeight`: (default: `"original"`) A number or the string `"original"` to signify the current height as the minimum (note: This option is only useful on `<textarea>` elements, i.e. elements that resize height-ways)
 * `maxHeight`: (default: `500`) A number or the string `"original"` to signify the current height as the maxiumum (note: This option is only useful on `<textarea>` elements, i.e. elements that resize height-ways)
 * `onResize`: A callback function fired whenever a resize occurs.
 * `animate`: (default: `{duration: 200}`) Set to either `false` or an animation configuration object, i.e. the one passed as the second argument to `jQuery.fn.animate`. This signifies whether or not the element should animate when it resizes (set to `false` if you don't want animation).

 You can unbind listeners bound to by this plugin like so:

 	$(foo).unbind('.autoResize');

... or destroy everything, including stub clone objects used for the effect:

	$(foo).data('AutoResizer').destroy();

---

**Please report bugs in Github (the issues tab).**

### Tested on the following browsers:

 * Opera 11.5
 * Firefox 4/6
 * Safari 5.0
 * IE9 (*IE6-8 too, but see below*)
 * Chrome 15

*Note*: It will work in IE6-8 also, but only if your TEXTAREA has `display:block;` (`display:inline;`, the default, doesn't appear to work very well)