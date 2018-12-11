### https://x5.tencent.com/tbs/product/tbs.html  针对ANDROID的腾讯X5浏览器支持

### cordova plugin add cordova-plugin-x5-webview

### 然后在build.gradle里面的defaultConfig加入ndk{abiFilters "armeabi"},如果配置后编译报错，那么需要在gradle.properties文件中加上Android.useDeprecatedNdk=true；
~~~
 defaultConfig {
        versionCode cdvVersionCode ?: new BigInteger("" + privateHelpers.extractIntFromManifest("versionCode"))
        applicationId privateHelpers.extractStringFromManifest("package")

        if (cdvMinSdkVersion != null) {
            minSdkVersion cdvMinSdkVersion
        }
        flavorDimensions "default"  //GRADELE升级到4.XXX后的一个设置
        ndk{abiFilters "armeabi"}   //腾讯X5浏览器后的一个设置
    }
~~~

### 可通过 https://x5.tencent.com/tbs/sdk.html  http://res.imtt.qq.com/TES/43624_1543909189877.zip 下载 最新的tbs_sdk_thirdapp_vxx.jar替换android/libs文件夹下的旧的JAR文件

### 判断是否已经加载了腾讯X5 http://res.imtt.qq.com/TES/HowToLoadX5Core.doc 

### 常见问题 https://x5.tencent.com/tbs/technical.html#/sdk
