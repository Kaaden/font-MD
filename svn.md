# svn（mac自带svn）

 ## 1.初始化（下载仓库）
     
      组成：svn checkout svn||http (仓库地址) --username= --password=  path(克隆到本地文件夹地址)
      例如：svn checkout http://47.112.190.110:8443/svn/007-ClientDesign   --username=zhonghuaiyu --password=HeepmY%r0Vox /Users/yukaaden/Desktop/File/007

## 2.更新
         svn update

## 3.Error
      
          升级mac系统到10.15.4，使用idea svn拉代码提示错误

          Can't use Subversion command line client: svn Probably the path to Subversion executable is wrong.
          使用命令行 运行 svn --version 提示错误：

          The subversion command line tools are no longer provided by Xcode
          解决办法
          命令行输入下面两行，重新安装command line tools


          sudo rm -rf /Library/Developer/CommandLineTools
          xcode-select --install

