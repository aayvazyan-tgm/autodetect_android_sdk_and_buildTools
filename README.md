# Smart Autodetection
This plugin may help to avoid problems when collaborating on a android project by allowing collaborators to use a different SDK version if the prefered one is not available.

As you should always use the latest available build tools version, the plugin searches for the latest installed version and allows a upgrade without the need to touch the gradle file.

Available Functions:
--------------------

```@param desiredSDK defines the SDK that should be searched for, if it is found it is returned by this function, elsewise the newest found SDK is returned. If none is found or this function fails, it will return the input parameter.```
* project.getSDKIfPossible(int desiredSDK)

```@param defaultTools if no Build Tool is found or this function fails, it will return the input parameter.```
* project.getHighestAvailableTools(String defaultTools)

Usage:
======
Put the following in your ```build.gradle```:
```
apply from: 'https://github.com/aayvazyan-tgm/autodetect_android_sdk_and_buildTools/releases/download/1.0/sdktools.gradle'

android {
    //use the newest SDK automatically if the given one is not available
    compileSdkVersion project.getSDKIfPossible(21)
    //Use the lastest BuildTool Version available, default to the given value on error
    buildToolsVersion project.getHighestAvailableTools("21.1.2")
}
```
