# mysql 问题集合

  ## 存储问题 截取问题
     
	 1.当存储富文本(长文本)类型 设置text类型或者longtext一般满足 ,但存在特殊符号会导致mysql截取文本,设置字符集utf8mb4解决,目前是自己的解决方案 
	
	
  ## sql语句
  
    1.增:`INSERT INTO login(username,password,email) VALUES ('${username}','${password}','${email}')`
	
	2.删:`DELETE FROM contents where id=${id}`
	
	3.改:`UPDATE tags SET tag='${tag}' WHERE id='${id}'`
	
	4.查: 
	 
	     (1)模糊查询:`SELECT * FROM tags WHERE tag like "%${tag}%"` 
		 
		 (2)一条记录:`SELECT * FROM DATABASE WHERE ID=1`
		 
		 (3)整张表记录:`SELECT * FROM DATABASE`
		 
		 (4)指定返回内容: `SELECT ID,TITLE FROM DATABASE`

         (5)分页查询以及排序返回: `SELECT author, title FROM post WHERE status = draft AND author IN('author1','author2') ORDER BY created_at DESC LIMIT 0, 10;`
		 
	5.mysql语句 and(和) or(或者)