# JioTV Android app modifications

This repository contains *smali* bytecode patches for the JioTV Android app. They are mainly aimed at improving user experience by disabling certain functionality.

Original app: https://play.google.com/store/apps/details?id=com.jio.jioplay.tv

## Disclaimer

JioTV is a registered trademark of Reliance Industries Limited.
By using patches in this repo, you understand that you are choosing to reverse-engineer and modify the original software distributed by [Jio Platforms Limited](https://play.google.com/store/apps/dev?id=8426036374624640337) / RJIL. Any damage or inconvenience caused by using the resulting modified software is solely your responsibility. Neither the developers of the app, nor the contributors of the patches in this repository shall be held responsible for the same.

## Current list of patches (v7.0.8-290)

1. Disable ads in the app's navigation
2. Disable ads on the channel playback screen
3. Disable floating autoplay on app home
4. Disable floating autoplay on channel playback screen
5. Disable JioEngage integration (untested)

## How to use?

1. Ensure JDK 8+ is installed and `java` is present in PATH
2. [Download](https://bitbucket.org/iBotPeaches/apktool/downloads/) and [install](https://ibotpeaches.github.io/Apktool/install) Apktool and add it to your PATH
    (It is recommended to use version **2.7.0** as using a different version of Apktool might cause variation in resulting bytecode and make the patches incompatible)
3. Decode the app's sources to `src` folder
    ```
    apktool decode --output src --no-res original\<version>.apk
    ```
4. Apply the patches for the chosen version
    ```
    for /r %i in (patches\<version>\*.patch) do git apply --verbose %i
    ```
5. Rebuild the app with modified bytecode
    ```
    apktool build --force-all src
    ```
6. Once completed successfully, you should be able to see the compiled APK file in the folder
    `src\dist\<version>.apk`
7. Sign the application with any tool of your choice
    (For example: [Uber Apk Signer](https://github.com/patrickfav/uber-apk-signer), [apk-signer](https://play.google.com/store/apps/details?id=com.haibison.apksigner))
8. Uninstall the currently installed JioTV app on your Android device (uninstall it for all users if using a multi-user setup)
    ```
    adb uninstall com.jio.jioplay.tv
    ```
9. Install the above generated signed APK (from step 7)
