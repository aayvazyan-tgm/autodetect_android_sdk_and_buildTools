# Smart Autodetection
This plugin helps to:
* Avoid problems with collaborators that do not stick to the defined SDK.
* Removing the need to update the build.gradle file every time you update your android build-tools.

Available Functions:
--------------------

```@param desiredSDK defines the SDK that should be searched for, if it is found it is returned by this function, elsewise the newest found SDK is returned. If none is found or this function fails, this parameter is returned.```
* ```project.getSDKIfPossible(int desiredSDK)```

```@param defaultTools if no Build Tool is found or this function fails, it will return the input parameter.```
* ```project.getHighestAvailableTools(String defaultTools)```

Usage:
======
Put the following in your ```build.gradle```:
```gradle
apply from: 'https://github.com/aayvazyan-tgm/autodetect_android_sdk_and_buildTools/releases/download/1.0/sdktools.gradle'

android {
    //use the newest SDK automatically if the given one is not available
    compileSdkVersion project.getSDKIfPossible(21)
    //Use the lastest BuildTool Version available, default to the given value on error
    buildToolsVersion project.getHighestAvailableTools("21.1.2")
}
```
Offline Usage:
==============
Download https://github.com/aayvazyan-tgm/autodetect_android_sdk_and_buildTools/raw/master/sdktools.gradle
and refer to the local file instead of the link in the ```apply from '...'``` statement.
