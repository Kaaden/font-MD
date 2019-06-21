# react native

  ## 命令行
     
     1.创建项目 react-native init AwesomeProject

     2.启动 
           android: react-native run-android
		   
           ios:react-native run-ios

  ## 刷新模拟器
  
	 夜神模拟器连接：adb connect 127.0.0.1:62001 || adb connect 127.0.0.1:62025
	 
	 查看连接是否成功：adb devices

     iOS模拟器是 com+R  安卓是 双 R

  ## react navigation

     yarn add react-navigation
	 
     yarn add react-native-gesture-handler


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