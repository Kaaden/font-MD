# Nginx服务器配置

  ![image](https://github.com/Kaaden/font-MD/blob/master/1.jpg)
  
  ## 全局块
     
  
  ### 该部分配置主要影响Nginx全局，通常包括下面几个部分：
	 
	    配置运行Nginx服务器用户（组）
		worker process数
		Nginx进程PID存放路径
		错误日志的存放路径
		配置文件的引入
		
  ## events块
	
  ### 该部分配置主要影响Nginx服务器与用户的网络连接，主要包括：
	  
	  设置网络连接的序列化
	  是否允许同时接收多个网络连接
	  事件驱动模型的选择
	  最大连接数的配置
			
	
  ##  http块
	   
	    定义MIMI-Type
		自定义服务日志
		允许sendfile方式传输文件
		连接超时时间
		单连接请求数上限
		
  ## server块
	
		配置网络监听
		基于名称的虚拟主机配置
		基于IP的虚拟主机配置
		
  ## location块
	
	    location配置
		请求根目录配置
		更改location的URI
		网站默认首页配置
		
  ![image](https://github.com/Kaaden/font-MD/blob/master/2.jpg)
	
  ## window 下 cmd 命令
   
      运行:start nginx
	  
	  重载:nginx -s reload
	  
	  
	