# 介绍

### 通过NPM安装
 安装 GitBook 的最好办法是通过 NPM。在终端提示符下，只需运行以下命令即可安装 GitBook：
```
    npm install gitbook-cli -g
```
gitbook-cli 是 GitBook 的一个命令行工具。它将自动安装所需版本的 GitBook 来构建一本书。

执行下面的命令，查看 GitBook 版本，以验证安装成功。
```
    gitbook -V
```
### 安装历史版本
gitbook-cli 可以轻松下载并安装其他版本的GitBook来测试您的书籍：
```
    gitbook fetch beta
```
使用 gitbook ls-remote 会列举可以下载的版本。

### 创建一本书
#### 初始化
GitBook可以设置一个样板书：
```
    gitbook init
```
如果您希望将书籍创建到一个新目录中，可以通过运行 gitbook init ./directory 这样做。

#### 构建
使用下面的命令，会在项目的目录下生成一个 _book 目录，里面的内容为静态站点的资源文件：
``` 
    gitbook build
```
#### Debugging
您可以使用选项 --log=debug 和 --debug 来获取更好的错误消息（使用堆栈跟踪）。例如：
``` 
    gitbook build ./ --log=debug --debug
```
### 启动服务
使用下列命令会运行一个 web 服务, 通过 http://localhost:4000/ 可以预览书籍
```
    gitbook serve
 ```
#### GitBook 命令
这里主要介绍一下 GitBook 的命令行工具 gitbook-cli 的一些命令, 首先说明两点:

* gitbook-cli 和 gitbook 是两个软件
* gitbook-cli 会将下载的 gitbook 的不同版本放到 ~/.gitbook中, 可以通过设置GITBOOK_DIR环境变量来指定另外的文件夹
#### 列出 gitbook 所有的命令

- gitbook help 输出 gitbook-cli 的帮助信息


- gitbook --help 生成静态网页


- gitbook build 生成静态网页并运行服务器


- gitbook serve 生成时指定gitbook的版本, 本地没有会先下载


- gitbook build --gitbook=2.0.1 列出本地所有的gitbook版本


- gitbook ls 列出远程可用的gitbook版本


- gitbook ls-remote 安装对应的gitbook版本
 

- gitbook fetch 标签/版本号 更新到gitbook的最新版本


- gitbook update卸载对应的gitbook版本 


- gitbook uninstall 2.0.1 指定log的级别


- gitbook build --log=debug 输出错误信息

- gitbook builid --debug