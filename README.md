Android-WVersionManager
====================

![build status](https://travis-ci.org/revanmj/Android-WVersionManager.svg?branch=master)  [![Download](https://api.bintray.com/packages/revanmj/Android-WVersionManager/com.winsontan520.wversionmanager/images/download.svg) ](https://bintray.com/revanmj/Android-WVersionManager/com.winsontan520.wversionmanager/_latestVersion)

## Objective
Things changed/added by this fork:
- Convert WVersionManager library to an Android Studio project and remove depency on deprecated org.apache.http library (replacing all calls with URLConnection or HttpURLConnection)
- Add option to download update using Android's Download Manager. Remember that your app must have "android.permission.WRITE_EXTERNAL_STORAGE" permission for this to work:
`versionManager.useDownloadManager(true);`
- Add option to automatically open downloaded APK file, as long as app has proper permissions in Oreo (android.permission.REQUEST_INSTALL_PACKAGES) or Unknown sources is enabled in case of lower versions. Otherwise Downloads app will be launched):
`versionManager.installAfterDownload(true);`
- Add option to force update check (by ignoring remind timer): `versionManager.checkVersion(true);`
- Instead of setting strings (like button labels) by code, let them be overridden by adding them to app's strings.xml file (list of all string ids from this library can be [seen here](https://github.com/revanmj/Android-WVersionManager/blob/master/library/wversionmanager/src/main/res/values/strings.xml))
- Implemented concept of a "blocking update" - after adding `is_blocking` field set to true in your JSON file, default update dialog will only show **Update** button (it also won't be cancelable). You also will be able to check this value by calling `versionManager.isBlockingUpdate();` after update check or using `onReceive(int status, boolean isBlocking, String result)` method from `com.winsontan520.wversionmanager.OnReceiveListener`. This will be also saved to SharedPreferences, so it will survive app restart.

Compiled .jar file can be downloaded from [releases tab](https://github.com/revanmj/Android-WVersionManager/releases) or added in build.gradle from jcenter repo:
```
dependencies {
    implementation 'com.winsontan520.wversionmanager:wversionmanager:1.7'
}
```

You can read original readme with all details about the setup here: https://github.com/winsontan520/Android-WVersionManager/blob/master/README.md
		
## License - Free to use
    Copyright 2013 Winson Tan
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
       http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
