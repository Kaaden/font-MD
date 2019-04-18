# http (rest api)请求所遇到的问题

  ## 多次请求问题
      1.客户端会发起两次请求,一次是options ,一次是post
	  
	  2.options的问题是为了向服务器发送是否可以请求,可以则会发送post,故产生两次请求
	  
	  解决方案(个人解决思路):
	    
		1).服务器解决(甩锅)
		
		2).前端解决,可以在请求表头使用 "Content-Type": "application/x-www-form-urlencoded"
		
		3).angular中,使用qs包以及"Content-Type": "application/x-www-form-urlencoded"解决
    