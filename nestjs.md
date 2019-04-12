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
  
 「Request」对象表示 HTTP 请求，并具有「Request」查询字符串，参数，HTTP 标头 和 正文的属性（在这里阅读更多），但在大多数情况下, 不必手动获取它们。 我们可以使用专用的装饰器，比如开箱即用的 @Body() 或 @Query() 。
  下面是装饰器和 普通表达对象的比较
        @Request()	req
		@Response()	res
		@Next()	next
		@Session()	req.session
		@Param(key?: string)	req.params / req.params[key]
		@Body(key?: string)	req.body / req.body[key]
		@Query(key?: string)	req.query / req.query[key]
		@Headers(name?: string)	req.headers / req.headers[name]
		
  每个异步函数都必须返回 Promise
       @Get()
		async findAll(): Promise<any[]> {
		  return [];
		}
		
#提供者
  
  几乎所有的东西都可以被认为是提供者 - service, repository, factory, helper 等等。他们都可以通过 constructor 注入依赖关系，也就是说，他们可以创建各种关系。但事实上，提供者不过是一个用@Injectable() 装饰器注解的类。
 
#模块

  模块是具有 @Module() 装饰器的类。 @Module() 装饰器提供了元数据，Nest 用它来组织应用程序结构。
  
  @module() 装饰器接受一个描述模块属性的对象：
  
     providers	由 Nest 注入器实例化的提供者，并且可以至少在整个模块中共享
	 controllers	必须创建的一组控制器
	 imports	导入模块的列表，这些模块导出了此模块中所需提供者
	 exports	由本模块提供并应在其他模块中可用的提供者的子集。
	 
  @Injectable 表示服务类
  
  @Global 装饰器使模块成为全局作用域
  
  @Entity 定义实体对应数据库的一张表，Typeorm 在每次启动都会同步表结构到数据库