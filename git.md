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
	
	
## 生成ssh key

   ssh-keygen -t rsa -C "your_email@example.com"(剩下一路enter)
   

## ssh测试链接是否成功

   ssh git@github.com || git@gitee.com(码云)
       
   1.查看本机ssh key
   
      cd ~/.ssh 若无则需生成key
	  
	  
	  ls
	  
	  cat id_rsa.pub（查看本地key）
	  
	