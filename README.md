#BST - A Bootstrap 3 Starter Theme, for WordPress

**BST is a simple WordPress starter theme loaded with Bootstrap 3.**

*Version 1.9*


##Features

* *Simple, intuitive, clean code.*
* CSS, JS, functions and template parts in different folders.
* **Bootstrap 3.3.1** - CSS and JS enqueued. You can simply swap the default Bootstrap 3 files (included) for a custom made Bootstrap 3, and this theme will still work.
* **jQuery 1.11.1** called from Google CDN, with a local fallback when offline.
* **WooCommerce** plugin support.
* **Optional:** Choice of two navbar positions (top of screen and/or below site title). Simply delete what you don't need.
* A starter CSS theme - `bst.css`, enqueued.
* **Optional:** HOVERNAV - navbar dropdown on hover. Delete the CSS and JS for this if you don't want it.
* **NEW: Optional:** MEGANAV - navbar mega-menu; whenever there are grand-child links (for screen sizes >= 768px). Delete the CSS and JS for this if you don't want it.
* Visual editor stylesheet - into which the same Bootstrap 3 and starter CSS theme are preloaded by `@import`, so that **WYSI(M!)WYG** - what you see in the visual editor is (mostly!) what you get at the front end.
* `Modernizr.js`, `respond.js` and `html5shiv.css` included - enqueued.
* Clean-up scripts - e.g. removing WordPress-specific stiff grom the <head>. (Do not rely on these for security.)
* **Optional:** in functions/cleanup.php some filters are included (but commented-out, so are inactive) for removing WordPress IDs and classes from the navbar(s). If you would like to use these filters, then simply un-comment them.
* A few simple jQuery scripts - in `bst.js`, enqueued. Example: **Hovernav** (see below).
* Custom comment list callback.
* **Optional** full-width page template - select it in the WordPress Page Editor **Page Attributes** panel.
* Easily make this theme your own - if you rename `bst.css` to `yourtheme.css`, and `bst.js` to `yourtheme.js`, and then do a global search-and-replace to rename "bst" to "yourtheme" everywhere in the theme's code, this theme will still work. (You must also modify the comments in `style.css`, and rename the root folder from **bst/** to **yourtheme/**.)
* [MIT licence](http://opensource.org/licenses/MIT) (open source).

This theme has been built for use as a starter theme and as a learning aid for people who wish to get into WordPress theme design.

###Hovernav

The navbar has some modifications that make the dropdown menu appear on hover (in `bst.js` plus `bst.css`). *The Bootstrap js and css have not been changed*.

_Hovernav_ only operates for screen sizes >=768px. It doesn't operate on phones, where Bootstrap displays the navbar as as the usual dropdown menu system).

You can easily delete the _hovernav_ segments of bst.js and bst.css if you don't want them. Removing _hovernav_ will not affect the functionality of _meganav_.

###Meganav

The navbar has some modifications that enable **child links and grandchild links** to be shown in a **megamenu** (in `bst.js` plus `bst.css`). 

**Meganav is responsive.** Explanation:

* For screen sizes < 768px, _meganav_ detects those dropdowns containing grandchild links and displays them differently: the child links are set `font-weight: bold` while their corresponding grandchild links are set `font-weight: normal` and with added left margin.
* For screen sizes >= 768px (with the navbar in menubar mode), all _dropdowns with child links and grandchild links_ are displayed as a _full-width megamenu_. Meanwhile, dropdowns not containing grandchild links are displayed in the normal Bootstrap style.
* In the megamenu: child links are displayed horizontally in bold, as heads of columns containing their respective grandchild links.
* If the megamenu content is too wide for a grid width (e.g. in medium screen sizes), then the content will scroll horizontally.

You can easily delete the _meganav_ segments of bst.js and bst.css if you don't want them. Removing _meganav_ will not affect the functionality of _hovernav_.


##Notes on WooCommerce support

* You will need to install the WooCommerce plugin - http://wordpress.org/plugins/woocommerce/
* **Improvements in version 1.9:** Now with lots of re-styling of WooCommerce as Bootstrap (see `bst.js` and `bst.css`). Note: the WooCommerce stylesheet has not been 'put out of gear'. Therefore some of the basic WooCommerce styling is implemented while others styles (e.g. buttons, form elements, message and information panels) have had their styles _over-ridden_ by Bootstrap styles. This has been accomplished mostly by using jQuery to swap WooCommerce classes for Bootstrap classes; however, some jQuery-added inline styles and some stylesheet-added button styles have also been used. (These are all easy to remove by deleting if you don't want them - see below.)
* Your website will need hyperlinks to "Shop", "My Account", "Cart" and "Checkout" e.g. in your primary menu.
* You will need to add some WooCommerce Widgets to the sidebar (at minimum, WooCommerce Cart and WooCommerce Categories)
* And, of course, you will need to add salable items to your shop, and set up your payment gateway.

Find out more about WooCommerce here: http://www.woothemes.com/woocommerce/


###What if you don't want WooCommerce support in BST?

Simply remove and delete these things that you won't be needing:

* **Remove:** woocommerce.php.
* **Remove:** /functions/woocommerce-setup.php.
* **Delete:** in /functions/setup.php, scroll to the bottom and delete the line
`add_theme_support('woocommerce');`.
* **Delete:** in /css/bst.css, scroll to the bottom and delete all style rules that have to do with WooCommerce.
* **Delete:** in /js/bst.js, scroll to the bottom and delete all jQuery code that has to do with WooCommerce.
