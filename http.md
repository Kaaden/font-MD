 # http (rest api)请求所遇到的问题

  ## 多次请求问题
      1.客户端会发起两次请求,一次是options ,一次是post
	  
	  2.options的问题是为了向服务器发送是否可以请求,可以则会发送post,故产生两次请求
	  
	  解决方案(个人解决思路):
	    
		1).服务器解决(甩锅)
		
		2).前端解决,可以在请求表头使用 "Content-Type": "application/x-www-form-urlencoded"
		
		3).angular中,使用qs包以及"Content-Type": "application/x-www-form-urlencoded"解决
		
  ## 网页从输入网址到渲染完成经历了哪些过程？
     大致可以分为如下7步：
		输入网址；
		发送到DNS服务器，并获取域名对应的web服务器对应的ip地址；
		与web服务器建立TCP连接；
		浏览器向web服务器发送http请求；
		web服务器响应请求，并返回指定url的数据（或错误信息，或重定向的新的url地址）；
		浏览器下载web服务器返回的数据及解析html源文件；
		生成DOM树，解析css和js，渲染页面，直至显示完成；