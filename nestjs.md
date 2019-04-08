# nest.js 安装

  Nest是一套基于Node.js的强大的Web框架，可帮助你轻松构建出高效的、可扩展的应用程序。它是通过结合OOP（面向对象编程）和FP（函数式编程）的最佳理念，采用现代化JavaScript，使用TypeScript构建的。

  Nest不仅仅只是一套框架，因为它是基于绝妙的，著名的流行库Express和Socket.io构建的（你也可以根据自己的需求选择任何其他库），所以无需等待大型社区，可以直接使用，无需担心第三方库的缺失

  npm: npm i -g @nestjs/cli
  
  yarn:yarn global add @nestjs/cli
  
  创建项目:nest new project-name 
  
	  src
	├── app.controller.ts 带有单个路由的基本控制器示例。
	├── app.module.ts 应用程序的根模块。
	└── main.ts   应用程序入口文件。它使用 NestFactory 用来创建 Nest 应用实例。
	
  要使用 CLI 创建控制器，只需执行 $nest g controller cats 命令。
  
  要使用 CLI 创建服务类，只需执行 $ nest g service cats/cats 命令。
  
  要使用 CLI 创建模块，只需执行 $ nest g module cats 命令。
  
#控制器

  控制器层负责处理传入的请求, 并返回对客户端的响应
  
  为了创建一个基本的控制器，我们必须使用装饰器。装饰器将类与所需的元数据关联，并使Nest能够创建路由映射（将请求绑定到相应的控制器）。
  
 