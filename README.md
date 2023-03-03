# Android App Package Name - Retrieve via Terminal

<img width="912" alt="Screenshot 2023-03-02 at 5 00 25 PM" src="https://user-images.githubusercontent.com/70295997/222605228-76abd18e-41ca-40ce-be6f-5650a4ea6f0b.png">

With access to the app source code, the package name can be found in the *AndroidManifest.xml*. If only the compiled .apk file is available, mobile testers can use the [Android Asset Packaging Tool](https://elinux.org/Android_aapt) (**aapt**) to get the package name from the app.

**appt** is located in the build-tools folder of the installed Android SDK version.

The path to **aapt** may look as follows */Users/lana/Android/sdk/build-tools/33.0.1*.

The following command reads out the package name from the .apk file:

    % ./aapt d badging ~/TheApp.apk | grep 'pack'
    package: name='com.appiumpro.the_app' versionCode='2003' versionName='2.0' platformBuildVersionName='11' platformBuildVersionCode='30' compileSdkVersion='30' compileSdkVersionCodename='11'
