# react native

  ## 命令行
     
     1.创建项目 react-native init AwesomeProject

     2.启动 
           android: react-native run-android
		   
           ios:react-native run-ios

  ## 解决mac下运行android命令行出错问题
   
      在项目的终端中添加以下命令：chmod 755 android/gradlew
   
  ## 刷新模拟器
  
	 夜神模拟器连接：adb connect 127.0.0.1:62001 || adb connect 127.0.0.1:62025
	 
	 查看连接是否成功：adb devices

    iOS模拟器是 com+R  安卓是 双 R
   
    React Native安卓模拟器调出Dev Setting菜单：adb shell input keyevent 82

  ## react navigation

     yarn add react-navigation
	 
     yarn add react-native-gesture-handler

     跳转语句：navigation.navigate(key,{para})

     返回：navigation.goBack()



  ## mobxjs
     
     yarn add mobx
	 
     yarn add mobx-react

     yarn add @babel/plugin-proposal-decorators:对装饰器依赖

     配置：在babel.config.js开启支持
     plugins: [
        ["@babel/plugin-proposal-decorators", { "legacy": true }],
     ]

  ## react-native-vector-icons
     
     yarn add react-native-vector-icons
	 
     react-native link react-native-vector-icons
	 
  ## 搭配Ui 框架 react-native-elements
  
     yarn add react-native-elements

     npm install --save react-native-elements
	 
  ## 生成原生依赖 react-native link
  
     react-native link react-native-gesture-handler
	 
	 react-native link @react-native-community/async-storage
	 
  ## reactnative 解决方案
  
      1.如何隐藏当前页面顶部导航栏
	  
	    在stack页，配置
		
		 const Stack = createStackNavigator(
			{
				// 只有Stack页可以隐藏顶部导航，设置header为null
				Tab: {
					screen: Tab,
					navigationOptions: ({ navigation, screeProps }) => ({
						header: (navigation.state.index === 3 || navigation.state.index === 1) && null,
					})
				},

			})
			
	 2.statusbar 更改状态栏字体颜色android 7.0以上有效，5.0无效，ios暂未发现

    3.解决android home键再次重新打开app问题：在androidmanifest.xml 中修改activity android:launchMode="singleTask"模式

    4.解决android点击返回键导致重新打开问题：在mainactivity.java文件中加入其中一个即可：
         1）
         @Override
         public void invokeDefaultOnBackPressed(){
            moveTaskToBack(true);
         }
         2）
         @Override
         public boolean onKeyDown(int keyCode, KeyEvent event) {
         
            if (keyCode == KeyEvent.KEYCODE_BACK) {
                  Intent home = new Intent(Intent.ACTION_MAIN);
                  home.setFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
                  home.addCategory(Intent.CATEGORY_HOME);
                  startActivity(home);
                  return true;
            }
            return super.onKeyDown(keyCode, event);
         }
         
    5.metro-react-native-babel-preset 若rn版本>0.6且自身版本高于0.55，则会出现 Error screen on fresh started app (RefreshReg)，目前解决方案降回0.55

    6.若rn升级后，运行react-native run-ios不会自动启动打包器，则缺少配置，在ios目录下xcodeproj，配置：
         /* Begin PBXShellScriptBuildPhase section */
       	FD10A7F022414F080027D42C /* Start Packager */ = {
			isa = PBXShellScriptBuildPhase;
			buildActionMask = 2147483647;
			files = (
			);
			inputFileListPaths = (
			);
			inputPaths = (
			);
			name = "Start Packager";
			outputFileListPaths = (
			);
			outputPaths = (
			);
			runOnlyForDeploymentPostprocessing = 0;
			shellPath = /bin/sh;
			shellScript = "export RCT_METRO_PORT=\"${RCT_METRO_PORT:=8081}\"\necho \"export RCT_METRO_PORT=${RCT_METRO_PORT}\" > \"${SRCROOT}/../node_modules/react-native/scripts/.packager.env\"\nif [ -z \"${RCT_NO_LAUNCH_PACKAGER+xxx}\" ] ; then\n  if nc -w 5 -z localhost ${RCT_METRO_PORT} ; then\n    if ! curl -s \"http://localhost:${RCT_METRO_PORT}/status\" | grep -q \"packager-status:running\" ; then\n      echo \"Port ${RCT_METRO_PORT} already in use, packager is either not running or not running correctly\"\n      exit 2\n    fi\n  else\n    open \"$SRCROOT/../node_modules/react-native/scripts/launchPackager.command\" || echo \"Can't start packager automatically\"\n  fi\nfi\n";
			showEnvVarsInLog = 0;
		};

      /* Begin PBXNativeTarget section */
      buildPhases下配置FD10A7F022414F080027D42C /* Start Packager */,
      
      7.iOS遇到error Failed to build iOS project. We ran "xcodebuild" command but it exited with error code 65错误：cd iOS  \ rm -rf build \ sudo react-native run-is
	  
	  8.Android Studio --“Cannot resolve symbol” 解决办法
	   点击菜单中的 “File” -> “Invalidate Caches / Restart”，然后点击对话框中的 “Invalidate and Restart”，清空 cache 并且重启。语法就会正确的高亮了
	 
## RN与原生交互实现

      https://juejin.im/post/5b20810ff265da6e432e697c
	  
## 样式
	  
	  1.阴影问题(Platform.OS可判断设备)
		 ios:shadowOpacity
		 android:elevation
		 
## 打包
	
   ### android 打包
	       
		   1.配置 https://reactnative.cn/docs/signed-apk-android/
		   
		     android 目录运行 gradlew assembleRelease 打包
			                  gradlew clean 清除 
                           gradlew clean build 清除build
		   
		   2.目前遇到问题：
		      
			  1) Task :@remobile_react-native-qrcode-local-image:verifyReleaseResources FAILED
			     到npm包去更改build版本
				 
			  2） Task :app:mergeReleaseResources FAILED
			      aaptOptions.cruncherEnabled = false
				  aaptOptions.useNewCruncher = false

## 安装CocoaPods

   1.sudo gem install -n /usr/local/bin cocoapods

   2.pod setup

   3.pod install 

## 使用flow检测错误

   1.安装指定版本(当前配置为0.92.0)flow-bin：yarn add flow-bin@0.92.0 --dev

   2.package.json配置启动命令："flow": "flow; test $? -eq 0 -o $? -eq 2 --all"

   3.启动检测：npm run flow
