Google Analytics Event Tracking jQuery Plugin
=========================

A jQuery plugin that helps you set up easy [Event Tracking With Google Analytics](http://code.google.com/apis/analytics/docs/tracking/eventTrackerGuide.html).

Features
--------

* Reading event tracking variables from HTML data attributes as default
* Support delay for links to be sure that the logging to Google Analytics will be stored.
* Ready for self defined functions to be able to handle the values that should be stored to Google Analytics by defining your own return values.

Dependencies
------------

* The plugin requires jQuery v1.4.3 (or higher). (HTML5 data attributes required)
* The plugin requires Google Analytics script with `_gaq' variable set.

Usage
-----

`.analyticsEventTracking()` to initialize event tracking at selected elements.
You may pass an options object to customize the event values:

 - **category**
   Default is HTML data attribute at the element with `data-jaet-report-category`.

 - **action**
   Default is HTML data attribute at the element with `data-jaet-report-action`.

 - **label**
   Default is HTML data attribute at the element with `data-jaet-report-label`.

 - **value**
   Default is HTML data attribute at the element with `data-jaet-report-value`.

 - **trackerName**
   Default is `_trackEvent`.

 - **delayed**
   Default is `true`.

Examples
-----
    <a href="/signup" data-jaet-report-category="signup" data-jaet-report-action="signup-click">Sign up</a>
    $("a").analyticsEventTracking();

Can also be coded like this:

    <a href="/signup">Sign up</a>
    $("a").analyticsEventTracking({
        category: "signup",
        action: "signup-click"
    });

With external function to get the value for action

    <a href="/signup">Sign up</a>
    $("a").analyticsEventTracking({
        category: "signup",
        label: "signup-click",
        action: getEventAction
    });

    function getEventAction(){
        return $(this).attr("href");
    }
Links
-----

* Author:  [Joakim Westerlund](http://github.com/jorkas) - [Homepage](http://joakim-westerlund.se)
* Company: [Mynewsdesk](http://www.mynewsdesk.com)
* Company Blog: [Mynewsdesk Blog](http://devcorner.mynewsdesk.com)

Please use the [GitHub issue tracker](https://github.com/jorkas/jquery-analyticseventtracking-plugin/issues) for bug
reports and feature requests.
