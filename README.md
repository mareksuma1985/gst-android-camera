Example Android App for AHCSRC
==============================

Prerequisite
------------

 - Gstreamer SDK for Android (>=1.7.1)
 - Android Studio (=3.3)
 - Android NDK (>=r15b)
 - Gradle (=4.10.1)

Build and Installation
----------------------

 - Set GSTREAMER_ROOT_ANDROID evironment varible

```
  $ export GSTREAMER_ROOT_ANDROID=/path/to/gstreamer/sdk
```

 - Create `local.properties` and add `sdk.dir` and `ndk.dir` properties:

```
  ndk.dir=/Users/justin/Library/Android/android-sdk-linux/android-ndk-r15c
  sdk.dir=/Users/justin/Library/Android/android-sdk-linux
```

 - Build with gradle

```
  $ gradle build
```

 - Install with gradle

```
  $ gradle installDebug
```

Screenshots
----------
![screenshot](screenshots/screenshot_2019-01-23.png)

Restrictions and Known bugs
---------------------------

 - ahcsrc element is a child element of GstPushSrc so it cannot be compatible
   with camerabin2 as it is.

 - No properties to set camera options like resolution, video formats.
   Each option can be set by caps filter.
   The options of real camera may vary on different android devices, so
   supported options should be analyzed on android application side.
