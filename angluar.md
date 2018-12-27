# Angluar

## 特性
   
    AngularJS是一个功能强大的基于JavaScript开发框架用于创建富互联网应用(RIA)。

    AngulajJS为开发者提供的选项(使用JavaScript)在一个干净的MVC(模型 - 视图 - 控制器)的方式来编写客户端应用程序。

    AngularJS写的应用都是跨浏览器兼容。AngularJS使用JavaScript代码自动处理适应每种浏览器。

## 核心特征
   
    据绑定: 模型和视图组件之间的数据自动同步。

	适用范围: 这些对象参考模型。它们充当控制器和视图之间的胶水。

	控制器: 这些Javascript函数绑定到特定的范围。

	服务: AngularJS配有多个内置服务，例如 $http 可作为一个XMLHttpRequest请求。这些单一对象在应用程序只实例化一次。

	过滤器: 从一个数组的条目中选择一个子集，并返回一个新的数组。

	指令: 指令是关于DOM元素标记(如元素，属性，CSS等等)。这些可以被用来创建作为新的，自定义部件的自定义HTML标签。AngularJS设有内置指令(如：ngBind，ngModel…)

	模板:这些符合从控制器和模型信息的呈现的视图。这些可以是单个文件(如index.html)，或使用“谐音”在一个页面多个视图。

	路由: 它是切换视图的概念。

	模型视图: MVC是一个设计模式将应用划分为不同的部分(称为模型，视图和控制器)，每个都有不同的职责。 AngularJS并没有传统意义上的实现MVC，而是更接近于MVVM(模型 - 视图 - 视图模型)。 AngularJS团队将它作为模型视图。

	深层链接: 深层链接，可以使应用程序状态进行编码在URL中而能够添加到书签。应用程序可从URL恢复到相同的状态。

	依赖注入: AngularJS有一个内置的依赖注入子系统，开发人员通过使应用程序从而更易于开发，理解和测试。


## 优点

	AngularJS提供一个非常干净和维护的方式来创造单页的应用。

	AngularJS提供数据绑定功能在HTML中，从而给用户提供丰富和响应的体验

	AngularJS代码可进行单元测试。

	AngularJS使用依赖注入和利用关注点分离。

	AngularJS提供了可重用的组件。

	使用AngularJS，开发人员编写更少的代码，并获得更多的功能。

	在AngularJS中，视图都是纯HTML页面，并用JavaScript编写控制器做业务处理。 
	AngularJS应用程序可以在所有主要的浏览器和智能手机，包括Android和iOS系统的手机/平板电脑上运行。

## 缺点

	不安全：因为只是JavaScript一种框架，由AngularJS编写的应用程序是不安全的。服务器端身份验证和授权是必须用来保证应用程序的安全。

	不可降解：如果应用程序的用户禁用JavaScript，那最后用户看到的只是基本页面，仅此而已

## AngularJS三个主要部分

	ng-app : 指令定义和链接AngularJS应用程序到HTML。

	ng-model : 指令绑定AngularJS应用数据的值到HTML输入控件。

	ng-bind : 该指令绑定AngularJS应用程序数据到HTML标签。



## Angular-cli 目录结构

 ### 首层目录：

	node_modules        第三方依赖包存放目录
	e2e                 端到端的测试目录  用来做自动测试的
	src                 应用源代码目录 
	.angular-cli.json   Angular命令行工具的配置文件。后期可能会去修改它，引一些其他的第三方的包  比如jquery等
	karma.conf.js       karma是单元测试的执行器，karma.conf.js是karma的配置文件
	package.json        这是一个标准的npm工具的配置文件，这个文件里面列出了该应用程序所使用的第三方依赖包。实际上我们在新建项目的时候，等了半天就是在下载第三方依赖包。下载完成后会放在node_modules这个目录中，后期我们可能会修改这个文件。
	protractor.conf.js  也是一个做自动化测试的配置文件
	README.md           说明文件
	tslint.json         是tslint的配置文件，用来定义TypeScript代码质量检查的规则，不用管它

 ### src目录：

	app目录            包含应用的组件和模块，我们要写的代码都在这个目录
	assets目录         资源目录，存储静态资源的  比如图片
	environments目录   环境配置。Angular是支持多环境开发的，我们可以在不同的环境下（开发环境，测试环境，生产环境）共用一套代码，主要用来配置环境的
	index.html         整个应用的根html，程序启动就是访问这个页面
	main.ts            整个项目的入口点，Angular通过这个文件来启动项目
	polyfills.ts       主要是用来导入一些必要库，为了让Angular能正常运行在老版本下
	styles.css         主要是放一些全局的样式
	tsconfig.app.json  TypeScript编译器的配置,添加第三方依赖的时候会修改这个文件
	tsconfig.spec.json 不用管
	test.ts            也是自动化测试用的
	typings.d.ts       不用管

 
## Angular-cli 安装指令

     全局安装 npm install -g @angular/cli
     创建项目 ng new my-app
     启动 ng serve --open