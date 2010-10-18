### HTML5 implementation vs. browser-native implementation

The prototype `myapps.mozillalabs.com` repository can be referenced in any website through a simple JavaScript include.  It provides the `install`, `getInstalled`, `getInstalledBy`, and `verify` methods through a secure cross-domain messaging API.    The `myapps.mozillalabs.com` dashboard can be loaded by simply navigating to the site in a browser.  It displays the currently installed applications, and launches them when they are clicked.

Note that we do not propose making `myapps.mozillalabs.com` a permanent delivery point for an application dashboard; see the <a href="security.html">Security and Privacy Considerations</a> section for a discussion of a longer-term strategy.

Browser-native implementations can take deeper security measures, and integrate more with desktop and mobile operating systems, than a pure web-content dashboard.  We propose that experimental integration with browser-native functions be organized under a "window.navigator.apps" object.  New methods can be attached at this point and made available, in a limited way, to browser-native or web-based application dashboards.


#### Native application features
Specific directions for browser integration include:

* Implementation of an installed application repository that resides in secure, tamper-evident desktop storage (e.g. with a digital signature), with a more secure installation flow.

* Ability to launch applications into an "app tab" or "pinned tab" that has a fixed location in the tab bar, or in a separate process with its own icon, menu-bar, etc.

* Access to OS-level notification systems - see the <a href="<a href="http://www.w3.org/2010/web-notifications/">W3C working group on Web Notifications</a>.

* Use of the `capabilities` field of the manifest for integration with browser-based permission APIs, including camera, microphone, geolocation, storage, file access, and cross-domain network access - see the <a href="http://www.w3.org/2009/dap/">W3C Device APIs and Policy</a> working group, especially the <a href="http://www.w3.org/TR/2010/WD-api-perms-20101005/">Permissions for Device API Access</a> working draft, for some current work on this.

* Ability to launch applications into a "chromeless" mode (with no toolbars, location bar, or forward or backward buttons).

* Ability to launch <a href="http://www.whatwg.org/specs/web-workers/current-work/">web workers</a> to perform background processing or notification polling.

* Integration with push-based notification or message delivery systems.

Any access to browser or OS-level functionality should require a more stringent installation step, and may require verification of the manifest - see <a href="security.html">Security and Privacy Considerations</a>.