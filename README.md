## 1. Installation

### Automatically (CLI / Plugman)

```
$ cordova plugin add https://github.com/nchutchind/cordova-plugin-app-launcher.git
```
and then (this step will modify your project):
```
$ cordova prepare
```

1\. Add the following xml to your `config.xml`:
```xml
<!-- for iOS -->
<feature name="Launcher">
	<param name="ios-package" value="Launcher" />
</feature>
<!-- 
Additionally, for iOS 9+, you may need to install the cordova-plugin-queries-schemes plugin, which will allow whitelisting of what URLs your app will be allowed to launch. 

cordova plugin add cordova-plugin-queries-schemes
-->
```
```xml
<!-- for Android -->
<feature name="Launcher">
	<param name="android-package" value="com.hutchind.cordova.plugins.launcher.Launcher" />
</feature>
```
## 2. Usage
    window["plugins"].launcher.canLaunch(
        { uri: 'fb://' },
        function () {
          console.log('App launched: ');
        },
        function (err) {
          console.log('Cannot launch: ', err);
        }
    );
    This will launch the facebook App. 
## 3. Credits
Thanks to [@nchutchind](https://github.com/nchutchind/cordova-plugin-app-launcher.git), I have extended the work.
