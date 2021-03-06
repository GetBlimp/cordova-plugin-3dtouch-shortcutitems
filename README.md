# cordova-plugin-3dtouch-shorcutitem
by [Giovanni Collazo](http://twitter.com/gcollazo)

## Description

* This plugin will notify you JavaScript app when you app is launched or resumed using a UIApplicationShortcutItem.

* The plugin will call `window.onShortcutEvent` and pass an object. The `data` property of that object contains the `UIApplicationShortcutItemType` of the shortcut used.


## Installation

```
$ cordova plugin add cordova-plugin-3dtouch-shortcutitems
```


## Xcode Project Setup
For custom shortcut icon create an Asset catalog and add your images. In this example the custom image used is called `my-shortcut-icon`. Set the text for the shortcut, in this example we are using `Shortcut Title`. Finally set the type of the shortcut, we are using `com.example.quicklink.action`.

### Project.plist

```xml
<key>UIApplicationShortcutItems</key>
<array>
  <dict>
    <key>UIApplicationShortcutItemIconFile</key>
    <string>my-shortcut-icon</string>
    <key>UIApplicationShortcutItemTitle</key>
    <string>Shortcut Title</string>
    <key>UIApplicationShortcutItemType</key>
    <string>com.example.quicklink.action</string>
  </dict>
</array>
```

[UIApplicationShortcutItems Reference](https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/iPhoneOSKeys.html#//apple_ref/doc/uid/TP40009252-SW36)

## JavaScript Interface

```js
// Register callback
window.onShortcutEvent = function(event) {
  alert(event.data);
};

// Initialize properly
document.addEventListener('deviceready', function() {
  window.shortcutItem.initialize();
}, false);
```
