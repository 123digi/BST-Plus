#BST Plus - A Bootstrap 3 Starter Theme, for WordPress - with Add-ons

*Version 2.1*

BST Plus is a WordPress starter theme loaded with Bootstrap 3. **It is the big brother of BST [https://github.com/SimonPadbury/bst](https://github.com/SimonPadbury/bst), and in fact shares the same base files as BST.**

BST started out as a *Bootstrap Starter Theme* for WordPress, but then it got more complicated when modifications were added over the years. I received feedback that has moded me to split BST into two projects:

(1) taking BST back to original idea as a *starter* theme (i.e. removing all the modifications), and then

(2) retaining all the modifications in this new theme, BST Plus (and hopefully adding more here, over time).

##Features of BST Plus

* *Simple, intuitive, clean code.*
* CSS, JS, functions and template parts are organized into different folders.
* **Bootstrap 3.3.1** - CSS and JS enqueued. You can simply swap the default Bootstrap 3 files (included) for a custom made Bootstrap 3, and this theme will still work.
* **jQuery 1.11.1** either using the hosted Google CDN or WordPress's onboard jQuery. You decide (see below).
* A starter CSS theme - `bst.css`, enqueued. (**Don't** put your own styles in `style.css`.)
* Visual editor stylesheet - into which the same Bootstrap 3 and starter CSS theme are preloaded by `@import`, so that what you see in the visual editor is (mostly!) what you get at the front end (WYSI(M!)WYG).
* [MIT licence](http://opensource.org/licenses/MIT) (open source).

##Optional Features of BST Plus

* The [BOOTSTRAP THEME](http://getbootstrap.com/examples/theme/) stylesheet is included, to show you how to include int in BST (see `functions/enqueues.php`). If you are getting bored with [flat UI design](http://en.wikipedia.org/wiki/Flat_UI_Design) already, keep it, and begin your own website design from there. Alternatively, you can simply remove it by deleting its enqueue. (And if you are using WooCommerce (see below), you will want to delete some BOOTSTRAP THEME segments from the 'Bootstrapped' WooCommerce `.button` style rules at the bottom of `bst.css`.
* In `functions/enqueues.php` there is a block of some code that calls jQuery from Google CDN when this theme is on a live website, or alternatively calls a local fallback when offline (i.e. from your WordPress installation's own jQuery). _Some developers like to depend on the Google CDN; some don't._ If this causes your site problems (e.g. goes slow) or if you prefer not to depend on the Google CDN, you can simply remove this stuff from functions/enqueues.php and instead then enqueue WordPress's onboard jQuery (see the comments in `finctions/enqueues.php` for more explanation). 
* Also, some developers prefer to call `http://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js` while some prefer `//ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js` - you can choose. (Read more about this in the file functions/enqueues.php). 
* `Modernizr.js`, `respond.js` and `html5shiv.css` included - enqueued. (Keep what you want; delete what you don't.)
* **WooCommerce** plugin support. (You will also need the [WooCommerce plugin] (http://wordpress.org/plugins/woocommerce/)). _Delete the CSS and JS for this if you don't want it._
* Choice of two navbar positions (top of screen and/or below site title). _Simply delete what you don't need._ **You can't have both** navbars because that will give you a two hamburgers (and two collapsed navbars) on small-screen devices.
* **Hovernav** - navbar dropdown on hover. _Delete the CSS and JS for this if you don't want it._
* **Meganav** - navbar mega-menu, which automatically works whenever there are grand-child links (for screen sizes >= 768px). _Delete the CSS and JS for this if you don't want it._
* In `functions/cleanup.php` there are some filters are included (but commented-out, so are inactive) for removing WordPress IDs and classes from the navbar(s). If you would like to use these filters, then simply un-comment them.
* A few simple jQuery scripts - in `bst.js`, enqueued. Example: **Hovernav** (see below).
* Custom comment list callback.
* **A full-width page template** - you can select it in the WordPress Page Editor **Page Attributes** panel.

-----

##Hovernav

The navbar has some modifications that make the dropdown menu appear on hover (in `bst.js` plus `bst.css`). *The Bootstrap js and css have not been changed*.

_Hovernav_ only operates for screen sizes >=768px. It doesn't operate on phones, where Bootstrap displays the navbar as as the usual dropdown menu system).

You can easily delete the _hovernav_ segments of bst.js and bst.css if you don't want them. Removing _hovernav_ will not affect the functionality of _meganav_.

-----

##Meganav

The navbar has some modifications that enable **child links and grandchild links** to be shown in a **megamenu** (in `bst.js` plus `bst.css`). 

Meganav is **responsive**. Explanation:

* For screen sizes < 768px, _meganav_ detects those dropdowns containing grandchild links and displays them differently: the child links are set `font-weight: bold` while their corresponding grandchild links are set `font-weight: normal` and with added left margin.
* For screen sizes >= 768px (with the navbar in menubar mode), all _dropdowns with child links and grandchild links_ are displayed as a _full-width megamenu_. Meanwhile, dropdowns not containing grandchild links are displayed in the normal Bootstrap style.
* In the megamenu: child links are displayed horizontally in bold, as heads of columns containing their respective grandchild links.
* If the megamenu content is too wide for a grid width (e.g. in medium screen sizes), then the content will scroll horizontally.

You can easily delete the _meganav_ segments of bst.js and bst.css if you don't want them. Removing _meganav_ will not affect the functionality of _hovernav_.

-----

##WooCommerce support

* You will need to install the [WooCommerce plugin](http://wordpress.org/plugins/woocommerce/).
* **Improvements since version 1.9:** Now with lots of re-styling of WooCommerce as Bootstrap (see `bst-plus.js` and `bst-plus.css`). Note: the WooCommerce stylesheet has not been 'put out of gear'. Therefore some of the basic WooCommerce styling is implemented while others styles (e.g. buttons, form elements, message and information panels) have had their styles _over-ridden_ by Bootstrap styles. This has been accomplished mostly by using jQuery to swap WooCommerce classes for Bootstrap classes; however, some jQuery-added inline styles and some stylesheet-added button styles have also been used. (These are all easy to remove by deleting if you don't want them - see below.)
* Your website will need hyperlinks to "Shop", "My Account", "Cart" and "Checkout" e.g. in your primary menu.
* You will need to add some WooCommerce Widgets to the sidebar (at minimum, WooCommerce Cart and WooCommerce Categories)
* And, of course, you will need to add salable items to your shop, and set up your payment gateway.

Find out more about WooCommerce here: [http://www.woothemes.com/woocommerce/](http://www.woothemes.com/woocommerce/).

-----

####What if you don't want WooCommerce support?

Simply remove and delete these things that you won't be needing - and everything else will just work fine:

* **Remove:** woocommerce.php.
* **Remove:** /functions/woocommerce-setup.php.
* **Delete:** in /functions/setup.php, scroll to the bottom and delete the line
`add_theme_support('woocommerce');`.
* **Delete:** in /css/bst.css, scroll to the bottom and delete all style rules that have to do with WooCommerce.
* **Delete:** in /js/bst.js, scroll to the bottom and delete all jQuery code that has to do with WooCommerce.

-----

##Easily make this theme your own

* **Rename** the root folder from `bst-plus/` to `yourtheme/`.
* **Rename** `bst-plus.css` to `yourtheme.css`.
* **Rename** `bst-plus.js` to `yourtheme.js`.
* **Do a global search-and-replace** ("Replace in files...") to rename "bst-plus" to "your-theme" and "bst_plus" to "your_theme" **everywhere** in the theme's code.
* **Modify** the comments in `style.css`.

Do all that correctly, and this WordPress theme will still work!
