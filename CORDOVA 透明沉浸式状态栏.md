### https://www.jianshu.com/p/1cb9ac461649
### cordova-plugin-statusbar
### JAVA代码
```
 @Override
  public void run() {
            。。。。。。
            。。。。。。
              //添加内容start
              //实现沉浸式状态栏效果 新增代码start
              window.addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS); 
              window.addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_NAVIGATION);
              window.addFlags(WindowManager.LayoutParams.FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS);
               if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) {
                       window.setStatusBarColor(Color.TRANSPARENT);
                       window.setNavigationBarColor(Color.TRANSPARENT);
               } else if ((Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT)) {
              window.addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS); 
              }
              // 新增代码end
              window.clearFlags(WindowManager.LayoutParams.FLAG_FORCE_NOT_FULLSCREEN);
              //注释掉原来设置背景色的地方
              //setStatusBarBackgroundColor(preferences.getString("StatusBarBackgroundColor", "#000000"));

              // Read 'StatusBarStyle' from config.xml, default is 'lightcontent'.
              //setStatusBarStyle(preferences.getString("StatusBarStyle", "lightcontent"));

  }
```
