# Flutter

## Preparing to Setup
### 1. Install Flutter SDK
   - Get the Flutter SDK at: https://storage.googleapis.com/flutter_infra_release/releases/stable/macos/flutter_macos_2.8.1-stable.zip.
   - Extract the file in the desired location, for example:

        ```
        cd ~/development
        unzip ~/Downloads/flutter_macos_2.8.1-stable.zip
        ```
   - Add the flutter tool to your path:

        ```
        open .zshrc
          # Flutter
          export PATH="$PATH:`pwd`/flutter/bin"
        source .zshrc
        ```
   - Run Flutter doctor:

        ```
        flutter doctor
        ```
### 2. Install Xcode
   - Get the Xcode at: https://developer.apple.com/xcode/.
   - Configure the Xcode command-line tools to use the newly-installed version of Xcode by running the following from the command line:

        ```
        sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
        sudo xcodebuild -runFirstLaunch
        ```
   - Make sure the Xcode license agreement is signed by either opening Xcode once and confirming or running ```sudo xcodebuild -license``` from the command line.
   - Set up the iOS simulator. On your Mac, find the Simulator via Spotlight or by using the following command:
 
       ```
       open -a Simulator
       ```
### 3. Install Android Studio
   - Download and install [Android Studio](https://developer.android.com/studio).
   - Set up the Android emulator follow command recommendation.
   - Agree to Android Licenses:
      
      ```
      flutter doctor --android-licenses
      ```
