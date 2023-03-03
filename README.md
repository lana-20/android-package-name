# Android App Package Name - Retrieve via Terminal

<img width="912" alt="Screenshot 2023-03-02 at 5 00 25 PM" src="https://user-images.githubusercontent.com/70295997/222605228-76abd18e-41ca-40ce-be6f-5650a4ea6f0b.png">

With access to the app source code, the package name can be found in the *AndroidManifest.xml*. If only the compiled .apk file is available, mobile testers can use the [Android Asset Packaging Tool](https://elinux.org/Android_aapt) (**aapt**) to get the package name from the app.

**appt** is located in the build-tools folder of the installed Android SDK version.

The path to **aapt** may look as follows */Users/lana/Android/sdk/build-tools/33.0.1*.

The following command reads out the package name from the .apk file:

    % ./aapt d badging ~/TheApp.apk | grep 'pack'
    package: name='com.appiumpro.the_app' versionCode='2003' versionName='2.0' platformBuildVersionName='11' platformBuildVersionCode='30' compileSdkVersion='30' compileSdkVersionCodename='11'

## Alternative 1 - Use <code>adb shell</code> command-line tool

* <code>adb shell pm list packages</code> - returns a list of packages installed on the device
* <code>adb shell pm list packages -f <app_name></code> - returns the package for the specific app
* <code>adb shell pm list packages -3</code> - returns 3rd-party packages that were installed (side-loaded) from the Play Store or as an .apk (not pre-installed/pre-loaded)


## Alternative 2 - Use <code>dumpsys</code> util
    
First start the app to ensure that it's running on the *foreground*, then execute this command:
    
    % adb shell dumpsys window windows | grep 'mCurrentFocus'
    mCurrentFocus=Window{2c0df8a u0
    com.my_app.standalone.test2/com.the_app.standalone.features.auth.AuthActivity}
