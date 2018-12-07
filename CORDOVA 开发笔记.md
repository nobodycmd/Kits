# CORDOVA 开发笔记

### 针对ANDROID编译环境统一指定
* cordova plugin add cordova-android-support-gradle-release --variable ANDROID_SUPPORT_VERSION=$version
* set ANDROID_SUPPORT_VERSION TO  27.+ is not bad now

### Android platform 版本
* cordova platform add android@6.4.0  因为最新的7.0.0存在默认路径问题以及可能和旧的一些插件不兼容
* after added.it will change the cordova-android-support-gradle-release plugin 's  setting (variable ANDROID_SUPPORT_VERSION)

### ANDROID minSdkVersion and targetSdkVersion
~~~
 <preference name="android-minSdkVersion" value="18" />
 <preference name="android-targetSdkVersion" value="27"/>
~~~

### APP ICON 生成网址，一键生成各尺寸ICON
* https://icon.wuruihong.com/


### 借助IONIC一键生成ICON 和 SPLASH
* [https://www.cnblogs.com/wancy86/p/7979337.html](https://www.cnblogs.com/wancy86/p/7979337.html)
* 建议通过一个空壳IONIC项目来生成，因为IONIC将自动生成相应的配置内容和文件

### 启动错误捕捉显示

    ``` javascript
    window.onerror = function(msg, url, line) {  
       var idx = url.lastIndexOf("/");  
       if(idx > -1) {  
        url = url.substring(idx+1);  
       }  
       alert("ERROR in " + url + " (line #" + line + "): " + msg);  
       return false;  
    };
    ```
### ANDROID的浏览器选择
* cordova plugin add cordova-plugin-crosswalk-webview
* cordova plugin add cordova-plugin-x5-webview   use the browser in qq or wechat,if no qq and wechat

### IOS浏览器选择
* cordova plugin add CDVWKWebViewEngine

### CORDOVA 热更新
* 微软支持https://github.com/FanRongZhang/cordova-plugin-code-push
* https://www.jianshu.com/p/77c003dfa200

### 选择图片，视频上传插件
cordova-plugin-mediapicker-dmcsdk   https://github.com/DmcSDK
