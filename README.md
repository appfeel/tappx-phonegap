Tappx Phonegap and Cordova plugin
===============================

This is the [Tappx](http://www.tappx.com/?h=dec334d63287772de859bdb4e977fce6) plugin for Phonegap & Cordova. Start monetizing your Phonegap or Cordova apps with this plugin.

---
## Platform SDK supported ##

* iOS, using AdMob SDK for iOS, v7.3.1
* Android, using Google Play Service for Android, v7.5

---
## Install

Add the following tag to your `config.xml` file to show [Tappx](http://www.tappx.com/?h=dec334d63287772de859bdb4e977fce6) ads with your **Phonegap Build** apps:

```xml
<gap:plugin name="tappx-phonegap-build" source="npm"/>
```


To use the plugin with [**Cordova** or with **Phonegap CLI**](http://cordova.apache.org/docs/en/edge/guide_cli_index.md.html#The%20Command-line%20Interface) type the following command in your command line:

```shell
cordova plugin add tappx-phonegap
```

---
## Setup

*Note: Before continuing, ensure that you have a proper [Tappx](http://www.tappx.com/?h=dec334d63287772de859bdb4e977fce6) account, and optionally, an [Admob](https://apps.admob.com/admob/signup) account.*

Place the following code in your `deviceready` event:
```javascript
    function onDeviceReady() {
      document.removeEventListener('deviceready', onDeviceReady, false);

      // Set AdMobAds options:
      admob.setOptions({
        publisherId:          "NONE",                                    // Replace with your AdMob id (if you don't have any, set it to "NONE")
        tappxIdiOS:           "/XXXXXXXXX/Pub-XXXX-iOS-IIII",            // Replace with your Tappx Id for iOS
        tappxIdAndroid:       "/XXXXXXXXX/Pub-XXXX-Android-AAAA",        // Replace with your Tappx Id for Android
        tappxShare:           1                                          // Do not use lower tappxShare ratio if you have set publixherId to "NONE"
      });

      // Start showing banners (will show atomatically as autoShowBanner is set to true by default)
      admob.createBannerView();

      // Request interstitial (will present automatically as autoShowInterstitial is set to true by default)
      admob.requestInterstitial();
    }

    document.addEventListener("deviceready", onDeviceReady, false);
```

`tappxShare` parameter will specify the amout of traffic you want to share to Tappx, being 0 = 0% and 1 = 100%.

In example, if you would like to share 80% traffic source to Tappx and the rest to Admob, this would be the corresponding configuration:

```javascript
      // Set AdMobAds options:
      admob.setOptions({
        publisherId:          "ca-app-pub-XXXXXXXXXXXXXXXX/BBBBBBBBBB",  // Replace with your AdMob id
        tappxIdiOS:           "/XXXXXXXXX/Pub-XXXX-iOS-IIII",            // Replace with your Tappx Id for iOS
        tappxIdAndroid:       "/XXXXXXXXX/Pub-XXXX-Android-AAAA",        // Replace with your Tappx Id for Android
        tappxShare:           0.8                                        // Do not use lower tappxShare ratio if you have set publixherId to "NONE"
      });
```

---
## Full documentation ##

Visit the [wiki](https://github.com/appfeel/tappx-phonegap/wiki) pages to know in detail about Tappx Cordova plugin, where you will find the following topics:

* [Home](https://github.com/appfeel/tappx-phonegap/wiki)
* [Index](https://github.com/appfeel/tappx-phonegap/wiki/Index)
* [Change Log](https://github.com/appfeel/tappx-phonegap/wiki/Change-Log)
* [Testimonials](https://github.com/appfeel/tappx-phonegap/wiki/Testimonials)
* [Setup](https://github.com/appfeel/tappx-phonegap/wiki/Setup)
* [Javascript API](https://github.com/appfeel/tappx-phonegap/wiki/Javascript-API)
  * [setOptions](https://github.com/appfeel/tappx-phonegap/wiki/setOptions)
  * Banners
    * [createBannerView](https://github.com/appfeel/tappx-phonegap/wiki/createBannerView)
    * [showBannerAd](https://github.com/appfeel/tappx-phonegap/wiki/showBannerAd)
    * [destroyBannerView](https://github.com/appfeel/tappx-phonegap/wiki/destroyBannerView)
  * Interstitials
    * [requestInterstitialAd](https://github.com/appfeel/tappx-phonegap/wiki/requestInterstitialAd)
    * [showInterstitialAd](https://github.com/appfeel/tappx-phonegap/wiki/showInterstitialAd)
  * In app purchase
    * [recordResolution](https://github.com/appfeel/tappx-phonegap/wiki/recordResolution)
    * [recordPlayBillingResolution](https://github.com/appfeel/tappx-phonegap/wiki/recordPlayBillingResolution)
* [Complete example code](https://github.com/appfeel/tappx-phonegap/wiki/Complete-example-code)
* [Contributing](https://github.com/appfeel/tappx-phonegap/wiki/Contributing)
* [Screenshots](https://github.com/appfeel/tappx-phonegap/wiki/Screenshots)
* [Angular.js, Ionic apps](https://github.com/appfeel/tappx-phonegap/wiki/Angular.js,-Ionic-apps)

---
## License ##
```
The MIT License

Copyright (c) 2014 AppFeel

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

---
## Credits ##

* [appFeel](http://www.appfeel.com)
