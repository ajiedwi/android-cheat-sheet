# APK (.apk)

`APK` stands for **Android Package** (sometimes **Android Package Kit** or **Android Application Package**). It's the file format that Android uses to distribute and install apps/ As a result, an `APK` contains all the elements that an app needs to install correctly on your device. `APK` is an archive file, meaning that it containts multiple files, plus some metadata about them. You're problaly familiar with other types of archive files, like ZIP and RAR.

`APK` is a variant of the `JAR` (Java Archive) file format, since a lot of Android is built in Java. `APK` is `ZIP` files at their core, but they must contain additional information to properly function as an `APK`. APK can directly used to install an Application to your mobile device.  It works like .exe on Windows or .dmg on Apple. We can also submit `APK` to Google Play Store to publish our apps.

# AAB (.aab)

`AAB` stands for **Android App Bundle**. App bundles are signed binaries that organize yout app's code and resources into modules. Code and resources for each module are organized similarly to what you would find in a `APK`. Each of these modules may generated as separate `APK`s. Google Play then uses the app bundle to generate the various `APK`s that are served to users, such as `base APK`, `feature APK`, `configuration APK`, and for devices that not support split `APK`s (Android 4.4 API level 19 and lower), will generate `multi-APK`.

![AAB Strucutre](https://developer.android.com/static/images/app-bundle/aab_format-2x.png)

