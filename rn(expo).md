# react-native 开发相关


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