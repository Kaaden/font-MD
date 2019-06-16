# react native

  ## 命令行
     
     1.创建项目 react-native init AwesomeProject

     2.启动 
           android: react-native run-android
		   
           ios:react-native run-ios

  ## 刷新模拟器
  
	 夜神模拟器连接：adb connect 127.0.0.1:62001 
	 
	 查看连接是否成功：adb devices

     iOS模拟器是 com+R  安卓是 双 R

  ## react navigation

     yarn add react-navigation
	 
     yarn add react-native-gesture-handler

     Link 所有的原生依赖 react-native link react-native-gesture-handler

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