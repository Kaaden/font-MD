## 安装
     下载 https://nodejs.org/zh-cn/

     安装 yarn:https://yarnpkg.com/lang/zh-hans/docs/install/#windows-stable

     镜像 

       npm get registry 得到原本的镜像地址

       yarn config get registry 得到原本的镜像地址
	   
	   
     设成淘宝的镜像

       npm config set registry http://registry.npm.taobao.org/

       yarn config set registry http://registry.npm.taobao.org/

     安装cnpm: npm install -g cnpm --registry=https://registry.npm.taobao.org

     换成原来的：npm config set registry https://registry.npmjs.org/

## 更新

    yarn更新模块：yarn upgrade-interactive  --latest

    npm使用npm-check:
     1.安装npm install -g npm-check
     2.全局检测：npm-check -u -g
     3.对应目录检测：npm-check -u


    将包更新到指定版本： yarn upgrade [pkg-name]@ver
    # jquery从2.1.4更新到3.0.0版本：
    yarn upgrade jquery@3.0.0

    将包更新到最新版本：yarn upgrade –latest [pkg-name]
    举例将3.0.0版本的 jquery更新到最新版本：
    yarn upgrade –latest jquery