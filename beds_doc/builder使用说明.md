### 说明  
builder是将源文件进行一系列构建操作,如合并、压缩、混淆、版本控制、转义,从而达到优化目的的工具。  

### 使用  
1. git上检出build项目,http://git.corp.doumi.com/doumi_browser/builder  
2. 解压builder根目录下的node_modules.tar.gz到builder根目录
3. 修改builder根目录**doumi_config.js**文件  
- 文件修改说明: 仅需要修改文件内的四个变量
```js
var proSrcRootPath = ''; //业务项目源码根目录
var proDistRootPath = ''; //builder后,经过优化的文件存放根目录。实际上线时,分发的是该目录里的文件
var remoteStaticResDomain = 'http://sta.doumistatic.com'; //静态资源域名
var remoteApiDomain = 'http://www.doumi.com'; //后端接口域名
```

4. 执行构建  
 - 全量构建  
```
./build -a
```

 - 增量构建  
两种方式  
方式一:根据git的提交版本号,构建工具会比较所提供的版本号与上一版本的changelist,找到最终需要构建的文件  
```
./build -c commit-hash    
```
方式二:将需要构建的文件路径写到任意一个文件中,一个文件路径占一行。  
```
./build -f file  //file为我们自定义的一个文本文件,文件内容为需要构建的文件路径。一个文件路径占一行
```