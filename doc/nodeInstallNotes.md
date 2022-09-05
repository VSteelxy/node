# 安装node.js注意事项
下载地址：https://nodejs.org/en/download/
## 1.环境变量配置 

- 首先检查是否安装了Node 
```
> node --vertion 或 node -v
```
- 安装时全部next即可
- 再次确认是否安装成功
```
> node --version 或 node -v 或 node 直接进入交互模式 
```
- 配置node的全局变量；这样在任何路径下都能使用node npm npx
```
在系统环境变量path里添加node的安装路径（E:\nodejs）
```
- 配置全局安装包路径（NPM模块默认是安装在C盘，需要修改到node安装的路径下）
```
1.在nodejs路径下创建两个文件夹，node_cache和node_global
2.打开cmd，输入下面两条指令(E:\nodejs是安装node的路径）
> npm config set prefix “E:\nodejs\node_global”   //配置全局模块存放路径
> npm config set cache “E:\nodejs\node_cache”   //cache路径
3.测试是否配置成功(全局安装一个包看node_global文件夹下面是否新增了这个包)
> npm install -g vue
```
- 配置全局安装包可执行环境变量
```
- 如果不配置，当你安装一个全局可执行包时，需要给每一个都添加环境变量，或者只有进入该目录才能使用
- 配置方法：只需要将全局安装包路径添加到系统环境变量 path 即可
> 在环境变量path中添加全局安装包路径：E:\nodejs（node安装路径）\node_global\node_modules
```
- [可选]配置全局依赖包
```
每个项目我们都需要初始化npm install安装node_modules;里面有很多重复的，很麻烦，很占空间，可以配置环境变量 NODE_PATH
> 添加环境变量NODE_PATH；值为E:\Node.js(node安装路径)\node_modules
```
## 2.修改npm包管理器的registry为淘宝镜像(国外的下载慢，国内的下载快)
- 获取当前的npm镜像源；npm镜像源默认值为https://registry.npmjs.org/
```
可通过npm get registry 或 npm config get registry命令查看
```
- 通过配置文件修改npm镜像源
```
npm的registry配置信息存储在.npmrc文件;
> npm config edit 快速打开.npmrc文件
可以在文件中修改registry源的配置
```
- 通过命令的方式更快速修改registry源配置
```
> npm set registry xxxx 或 npm config set registry xxxx
> npm config set registry https://registry.npm.taobao.org   //设置为taobao镜像
```
