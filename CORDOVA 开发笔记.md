# CORDOVA 开发笔记

### 针对ANDROID编译环境统一指定
* cordova plugin add cordova-android-support-gradle-release --variable ANDROID_SUPPORT_VERSION=$version
($version就是相应的版本了，比如28.0.0,27.0.0,还可以27.+)

### ANDROID APK启动白屏
* 将编译版本指定为比较新的版本  比如 28.0.0   27.0.0
* <4.4下的低版本,通过打包 crosswalk 可解决,因为不支持HTML5新标准（比如<4.4的版本）
cordova plugin add cordova-plugin-crosswalk-webview


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
* cordova plugin add cordova-plugin-x5-webview   腾讯，包小，视频，文件等支持都不错
* cordova plugin add cordova-plugin-crosswalk-webview

### IOS浏览器选择
* cordova plugin add CDVWKWebViewEngine

### CORDOVA 热更新
* 微软支持https://github.com/FanRongZhang/cordova-plugin-code-push
* https://www.jianshu.com/p/77c003dfa200
