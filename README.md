# About this fork

This fork adds event triggering for jQuery on open and hide events. The 
mootools version looks like it already had it, but the jQuery and Prototype 
versions did not. Maybe I'll add this feature to the Prototype version as 
well.

Documentation/Usage:

Adds support for triggering open and hide events on a selector so that
you can listen for when fancyzoom has opened and when it has closed and
perform any further logic or processing.

Events triggered for open and hide actions are `fancyzoom:open` and
`fancyzoom:hide`, respectively. These events are namespaced to fancyzoom
with a colon per jQuery convention.

By default, the open and hide events are fired on the `body` element,
but can be customized by passing in a selector to the `eventTarget`
option when intializing fancyzoom:

    $('a').fancyzoom({eventTarget: '#somediv'});

The callback function you define is also passed the original click target
that triggered the `fancyzoom:open` event. This allows you to cleanly do any 
additional operations on the original click
target. The element is passed by jQuery as the second parameter to your
function:

    $('body').bind('fancyzoom:open', function (event, clickTarget) {
      var $el = $(clickTarget);
      //...
    });


# Original README

Fancy zoom box loosely based on Cabel Sasser's FancyZoom. Built in prototype 
and jquery. Works unobtrusively with content already on the page, including 
images, headings, text and flash (pretty much any html).
