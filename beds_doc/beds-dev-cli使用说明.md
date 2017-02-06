## 说明  
服务于业务项目开发者的beds命令行工具。
提供业务项目创建初始化、全局通用模块更新、mock-server等功能。

## 安装  
### osx系统  
1. 安装node v5.10以上版本  
2. 安装git 
3. 在终端生成sshkey  

> [ssk key 生成教程](http://git.corp.doumi.com/help/ssh/README) 

4. 下载beds-dev-cli  

> [下载](http://git.corp.doumi.com/doumi_browser/doc/raw/master/bin/osx/beds-dev-cli)  

5. 将beds-dev-cli 配置到全局环境变量中
6. 通过终端,在目标目录中执行beds-dev-cli

### windows系统  
1. 安装node v5.10以上版本  
2. 安装git  
3. 使用git-bash配置ssh key  

> [ssk key 生成教程](http://git.corp.doumi.com/help/ssh/README)  

4. 下载beds-dev-cli.exe    

> [下载](http://git.corp.doumi.com/doumi_browser/doc/raw/master/bin/windows/beds-dev-cli.exe)  

5. 将beds-dev-cli.exe 配置到全局环境变量中  
6. 在目标录中点击右键,选择git bash here
7. 在git-bash中执行beds-dev-cli程序


## 使用
- beds-dev-cli init m  
创建并初始化wap站项目  

- beds-dev-cli init pc  
创建并初始化pc站项目  

- beds-dev-cli server  
启动本地mock-server 
 
- beds-dev-cli update  
更新common目录

## beds项目结构
```
├── common  
│   ├── css_lib  
│   ├── js_lib  
│   ├── js_widget  
│   ├── less_widget  
│   ├── ui_widget  
│   └── view_widget  
├── proto_view  
├── static  
│   ├── css  
│   ├── img  
│   ├── js  
│   └── less  
└── view  
```
> common目录不依赖于业务项目,独立维护。但通过bed-dev-cli创建的业务项目依赖common  