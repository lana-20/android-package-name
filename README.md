# Android App Package Name - Retrieve via Terminal

<img width="908" alt="Screenshot 2023-03-02 at 4 56 34 PM" src="https://user-images.githubusercontent.com/70295997/222604887-ea4f84a7-18f3-4a46-ba61-d87d650ae8ef.png">

With access to the app source code, the package name can be found in the *AndroidManifest.xml*. If only the compiled .apk file is available, mobile testers can use the Android Asset Packaging Tool (**aapt**) to get the package name from the app.

**appt** is located in the build-tools folder of the installed Android SDK version.

The path to **aapt may** look as follows */Users/lana/Android/sdk/build-tools/33.0.1*.

The following command reads out the package name from the .apk file:

    ./aapt d badging ~/TheApp.apk | grep 'pack'
