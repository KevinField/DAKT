# [Live Demo](http://codingthat.github.io/DaKT/)

# DaKT
Dial-a-Knee-Thing is a lightning-fast, exploration-based hierarchy viewer, meant to scale from personal bookmarks all the way up to a replacement for large corporate web sites' nav pages / site maps; it also refers to the ideas behind the viewer, and the format in which it stores its data.

It's meant to help people organize arbitrary hierarchies of URIs, while making them very quick to explore and access.  The URIs can be static or dynamic, but DaKT blazes with static URIs in particular.

Its initial implementation is in the form of an HTML page (with optional JavaScript; perhaps unusually, with JavaScript enabled, DaKT will better preserve your privacy, and also function faster both UI- and network-wise: keyboardability depends on JS, and with JS, we can avoid unnecessary network round-trips / page-reloads.)  However, DaKT uses a set JSON format that can then be implemented in the form of other (interoperable) clients.  For example, you could implement it as a browser extension, an iOS app, a REBOL app, whatever you prefer.

It's been tested on an old, low-spec netbook, not a swanky, cutting-edge developer workstation, so it should remain quite responsive (even more so than today's standard for responsive web UIs) even on old hardware.

## How is this different from, say, a bookmarks menu?

A bookmarks menu is adequate when its hierarchy is small enough, Fitz' law notwithstanding.  However, when the root menu has 300 folders, it's a bit like throwing your paperwork down the stairs.  DaKT forces some measure of organization, fighting back against one of the difficulties of the technological age: Too Many Choices.  It does this by limiting your hierarchy breadth (the number of options at each stage) to 9.

Does it solve the fact that your hierarchy contains 5,000,000 nodes?  No.  The hope is only to make it less overwhelming, and as a side benefit, easier for others/outsiders/newbies to find things, too (for all but the "unshared personal use" case.)

## How is this for personal use?

When I open a new browser tab, that fancy new "new tab" page is sort of what I want, except that:

1.  I don't really need a thumbnail of a screenshot of a web site.
2.  It holds only a flat number of items.
3.  On many an under-powered and/or over-multi-tasked device, it sometimes takes several seconds to load.

DaKT gives you that "easy navigation of your stuff" interface, while being extensible to an arbitrary number of items, depending on how much you like to organize your stuff with it.

Eventually, DaKT can be extended to allow you to publish your own set of bookmarks, for others to subscribe to, simply by adding your published DaKT URL to their own DaKT hierarchy.

## How is this for web and intranet sites, small and large?

It's a convenient way to let your users quickly get from an opening page to what they are looking for.  The use of static hierarchies *should* make it easier for managers of very large sites, in particular, to avoid the frustratingly common case of nav bars with differing versions on different pages sending their users in circles.  Meanwhile, because it's so fast, the exploration of a large site's content is in itself less frustrating, especially on a slow computer and/or slow connection.  Plus, it saves a tonne of server resources in the process.

## What is "a Knee-Thing", and why would I want to Dial one?

It's a terrible pun for "anything", with connotations of being fast, like a knee-jerk reaction, but hopefully without the negative connotations of that phrase.  The "Dial" part is because it's by default as keypad-accessible as a traditional touch-tone phone.  (On a smartphone, hopefully, it will be as fast to use as dialing a phone number.)  I know we all love those automated phone menus!  No?  Well, they do have the handy property of getting you to your favourite thing more easily the second time.  That, and DaKT is visual.

Just wait until you hear about the Tera DaKT Till!  I kneaded that.

## What's the data format?

Have a look at dakt-menudata-sample.js, but the idea is:

```JavaScript
var DaKT_menuData = [
['menu title',
{ menu_item },
{ menu_item }
],['menu title',
{ menu_item },
...
{ menu_item },
{ menu_item }
], ...
};

```

IOW, DaKT_menuData is an array of arrays.  The outer array's indices are menu numbers.  The inner arrays consist of a menu title string in the [0] index (used for the navbar and also to title any menu items that link to the given menu), followed by between 1 and 9 (inclusive) menu item objects.  A menu item object must contain either the `m` option or the `t` option.

Recognized options include:

### u

URI that the menu item should link to.  Mutually exclusive of the `m` option below.

### t

Title of the menu item.  Mutually exclusive of the `m` option below.

### m

Menu number that the menu item should link to.  Mutually exclusive to both of the `u` and `t` options above.

### s

Subtitle.  Display it under the title, in a smaller font.

### b

Background colour of the menu item.

### c

Text colour of the menu item (for both the title and subtitle.)

### i

Base-64-encoded image data for the menu item's icon.  Specifically, everything you would put after `;base64,` in an inline image data URI.  The image should be 64px square; if it isn't, it will be scaled to that size.
