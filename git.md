# Git 相关操作

## 提交
   
    git init 
	
	git add .
	
	git commit -m "xxx"
	
	git remote add origin xxx(url远程仓库地址)
	
	git push -u origin master
  

## 修改git下的账号

    git config --list  查询配置
	
	git config --global --replace-all user.email "输入你的邮箱" 
	 
	git config --global --replace-all user.name "输入你的用户名"
	
	git config --list 