Android-WVersionManager
====================

![build status](https://travis-ci.org/revanmj/Android-WVersionManager.svg?branch=master)

## Objective
Things changed/added by this fork:
- Convert WVersionManager library to an Android Studio project and remove depency on deprecated org.apache.http library (replacing all calls with URLConnection or HttpURLConnection)
- Add option to download update using Android's Download Manager. Remember that your app must have "android.permission.WRITE_EXTERNAL_STORAGE" permission for this to work:
```versionManager.useDownloadManager(true);```
- Add option to automatically open downloaded APK file, as long as app has proper permissions in Oreo (android.permission.REQUEST_INSTALL_PACKAGES) or Unknown sources is enabled in case of lower versions. Otherwise Downloads app will be launched):
```versionManager.installAfterDownload(true);```
- Instead of setting strings (like button labels) by code, let them be overridden by adding them to app's strings.xml file (list of all string ids from this library can be [seen here](https://github.com/revanmj/Android-WVersionManager/blob/master/library/wversionmanager/src/main/res/values/strings.xml))

Compiled .jar file can be downloaded from [jar folder in this repo](https://github.com/revanmj/Android-WVersionManager/tree/master/jar) or [releases tab](https://github.com/revanmj/Android-WVersionManager/releases).

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
