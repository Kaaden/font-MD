# react-native 开发相关

   ## 文献

       react-navigation: https://reactnavigation.org/docs/zh-Hans/hello-react-navigation.html

       reactNative: https://reactnative.cn/docs/getting-started/

       expo: https://docs.expo.io/versions/v32.0.0/

       expo tools: https://expo.io/tools

       icon: https://expo.github.io/vector-icons/

       react native style: https://shenbao.github.io/ishehui/html/RN%20%E5%9F%BA%E7%A1%80/React%20Native%20%E6%A0%B7%E5%BC%8F%E8%A1%A8%E6%8C%87%E5%8D%97.html

       react native 第三方包：https://react.parts/?search=react+html&collection=React+Native

       mobx.js：https://cn.mobx.js.org/
       

   ## 路由问题 react-navigation
      
      1.createStackNavigator - 一次渲染一个页面，并支持页面切换， 当我们打开一个新的页面时，该页面会被置于堆栈的顶层;

      2.createBottomTabNavigator - 渲染一个 tab bar，让用户可以在多个页面之间切换。

      3.createSwitchNavigator - 在一个页面和另一个页面之间进行切换，在屏幕上没有 UI，在页面变为非活动状态时卸载页面。

      4.createDrawerNavigator - 提供从左侧滑入的抽屉

  ## react-navigation 概念

      在React Native中，从App.js导出的组件是应用程序的入口点（或根组件） -- 它处在所有组件的最下层。 与导出 stack navigator 相比，对应用程序根部的组件进行更多的控制通常更有用，所以我们导出一个只渲染了 stack navigator 的组件。

            const AppContainer = createAppContainer(AppNavigator);

            export default class App extends React.Component {
                render() {
                    return <AppContainer />;
                }
            }

  ## 命令

     1.安装：npm install -g expo-cli

     2.android打包：expo build:android

     3.ios打包： expo build:ios
  
  