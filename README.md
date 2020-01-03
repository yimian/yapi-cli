# 部署教程
此 fork 仓库教程旨在解决官方工具不支持 MongoDB authSource 的问题（官方有提供一些建议，但不适合线上环境），这个 fork 仓库对源码进行了简单的修改，一些是对部署的简单步骤描述：
克隆本仓库到个人机器上
```
$ git clone git@github.com:yimian/yapi-cli.git
```
进入刚克隆的仓库目录，执行依赖安装
```
$ cd {path_to_yapi_cli}
$ npm install --registry https://registry.npm.taobao.org
```
运行自动部署服务
```
$ ./bin/yapi server
```
后续可参考下面的`安装`一节的说明

# YApi 平台部署工具
使用我们提供的 yapi-cli 工具，部署和升级 YApi 平台是非常容易的
## 环境要求
* nodejs（7.6+)
* mongodb（2.6+）
## 安装
执行 yapi server 启动可视化部署程序，输入相应的配置和点击开始部署，就能完成整个网站的部署。部署完成之后，可按照提示信息，执行 node/{网站路径/server/app.js} 启动服务器。在浏览器打开指定url, 点击登录输入您刚才设置的管理员邮箱，默认密码为 ymfe.org 登录系统（默认密码可在个人中心修改）。

```
$ npm 
```
    npm install -g yapi-cli --registry https://registry.npm.taobao.org
    yapi server 
    
    # 指定端口 默认 9090
    yapi server --port 9290
## 基本用法
```
yapi --help // 查看 yapi-cli 命令
yapi --version //查看 yapi-cli 当前版本号
```
## 升级
升级项目版本是非常容易的，并且不会影响已有的项目数据，只会同步 vendors 目录下的源码文件。
```
cd  {项目目录}
yapi ls //查看版本号列表
yapi update //更新到最新版本
yapi update -v {Version} //更新到指定版本
```
