# eggjs mysql 操作

 ## 1.获取当前时间
 
     this.app.mysql.literals.now
 
 ## 2.查询一条记录时 
 
     await this.app.mysql.get('posts', { id: 12 });
 
 ## 3.查询全表
 
     await this.app.mysql.select('posts')
 
 ## 4.插入  
 
     await this.app.mysql.insert('posts', { title: 'Hello World' }); 
     ### // 判断插入成功
     const insertSuccess = result.affectedRows === 1;
 
 ## 5.条件查询和结果定制 
 
	 await this.app.mysql.select('posts', { // 搜索 post 表
	  where: { status: 'draft', author: ['author1', 'author2'] }, // WHERE 条件
	  columns: ['author', 'title'], // 要查询的表字段
	  orders: [['created_at','desc'], ['id','desc']], // 排序方式
	  limit: 10, // 返回数据量
	  offset: 0, // 数据偏移量
	 });
 
 ## 6.更新 
 
		 const row = {
		  id: 123,
		  name: 'fengmk2',
		  otherField: 'other field value',    // any other fields u want to update
		  modifiedAt: this.app.mysql.literals.now, // `now()` on db server
		};
		const result = await this.app.mysql.update('posts', row); // 更新 posts 表中的记录
		
		### // 判断更新成功
		const updateSuccess = result.affectedRows === 1;


 ## 7.删除
 
		const result = await this.app.mysql.delete('posts', {
		  author: 'fengmk2',
		});

		=> DELETE FROM `posts` WHERE `author` = 'fengmk2';
 
 ## 8.解决Unicode emoji存储数据乱码问题
 
      1.首先在mysql 字符集设置utf8mb4
	  
	  2.在eggjs配置mysql出添加上  charset: "utf8mb4"
	  
	  3.虽然在mysql上看数据还是一个"?",但api请求已经正确返回
 
