# DaKT
Dial-a-Knee-Thing is a lightning-fast, exploration-based hierarchy viewer, meant to scale from personal bookmarks all the way up to a replacement for large corporate web sites' nav pages / site maps.

It's meant to help people organize arbitrary hierarchies of URIs, while making them very quick to explore and access.  The URIs can be static or dynamic, but DaKT blazes with static URIs in particular.

Its initial implementation is in the form of an HTML page (with optional JavaScript; perhaps unusually, with JavaScript enabled, DaKT will better preserve your privacy, and also function faster.)  However, DaKT uses a set JSON format that can then be implemented in the form of other (interoperable) clients.  For example, you could implement it as a browser extension, an iOS app, a REBOL app, whatever you prefer.

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

It's a terrible pun for "anything", with connotations of being fast, like a knee-jerk reaction, but hopefully without the negative connotations of that phrase.  The "Dial" part is because it's by default as keypad-accessible as a traditional touch-tone phone.  (On a smartphone, hopefully, it will be as fast to use as dialing a phone number.)

Just wait until you hear about the Tera DaKT Till!  I kneaded that.

## Where's the code?

I'm working on it.  This is just the idea write-up for now.
