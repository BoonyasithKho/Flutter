# Flutter macOS

## Preparing
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
