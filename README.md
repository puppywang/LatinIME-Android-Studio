# Gradle build for LatinIME (Android Keyboard)
Develop LatinIME in Android Studio without a need to download and build whole AOSP.

Currently building LatinIME requires downloading and building whole Android sources.
This requires tens of gigabytes of disk space and takes couple hours to complete.
The aim of this project is to allow development of LatingIME using Android Studio, Android SDK and NDK.

## Current status
This is still a work in progress. Currently building the Java part of the app works fine
but you still need to build native libraries separately or extract them from existing APK.
Building host tools (used to generate dictionaries) still requires some more work.

## How to build LatinIME APK

1. Checkout this build configuration:

        git clone https://github.com/iwo/LatinIME-Android-Studio.git .

1. Import project into Android Studio

Enjoy your new Android Keyboard!
