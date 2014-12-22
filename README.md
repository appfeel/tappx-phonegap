Tappx-Admob Phonegap and Cordova plugin
===============================

This is the official Tappx plugin for Phonegap & Cordova.

## Install
To use the plugin with **Phonegap Build** add the following tag to your config.xml file:

```xml
<gap:plugin name="com.admob.google" source="plugins.cordova.io" />
```

To use the plugin with [**Cordova** or with **Phonegap CLI**](http://cordova.apache.org/docs/en/edge/guide_cli_index.md.html#The%20Command-line%20Interface) type the following command in your command line:

```shell
cordova plugin add com.admob.google
```

## Configuration

*Note: Before continuing, ensure that you have a proper [Tappx](http://www.tappx.com/?h=dec334d63287772de859bdb4e977fce6) account, and optionally, an [Admob](https://apps.admob.com/admob/signup) account.*

Place the following code in your `deviceready` event:
```javascript
    function onDeviceReady() {
      document.removeEventListener('deviceready', onDeviceReady, false);

      // Set AdMobAds options:
      admob.setOptions({
        publisherId:          "NONE",                                    // Replace with your AdMob id (if you don't have any, set it to "NONE")
        tappxIdiOs:           "/120940746/Pub-2702-iOS-8226",            // Replace with your Tappx Id for iOS
        tappxIdAndroid:       "/120940746/Pub-2700-Android-8171",        // Replace with your Tappx Id for Android
        tappxShare:           1                                          // Do not use lower tappxShare ratio if you have set publixherId to "NONE"
      });

      // Start showing banners (atomatic when autoShowBanner is set to true)
      admob.createBannerView();

      // Request interstitial (will present automatically when autoShowInterstitial is set to true)
      admob.requestInterstitial();
    }

    document.addEventListener("deviceready", onDeviceReady, false);
```

`tappxShare` parameter will specify the amout of traffic you want to share to Tappx, being 0 = 0% and 1 = 100%.

In example, if you would like to share 80% traffic source to Tappx and the rest to Admob, this would be the corresponding configuration:

```javascript
      // Set AdMobAds options:
      admob.setOptions({
        publisherId:          "ca-app-pub-8440343014846849/3119840614",  // Replace with your AdMob id
        tappxIdiOs:           "/120940746/Pub-2702-iOS-8226",            // Replace with your Tappx Id for iOS
        tappxIdAndroid:       "/120940746/Pub-2700-Android-8171",        // Replace with your Tappx Id for Android
        tappxShare:           0.8                                        // Do not use lower tappxShare ratio if you have set publixherId to "NONE"
      });
```
