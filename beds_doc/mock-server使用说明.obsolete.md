### 说明  
mock-server是前端开发者使用的本地测试用http服务器,该服务器除了提供正常http服务功能外,还可以在访问的时候实时对ejs、less和js模块进行编译。并
且还具有接口代理服务器的功能,可以允许本地环境跨域访问后端接口,以及通过配置access_token达到访问权限接口的能力。

### 使用  
1. git上检出build项目,http://git.corp.doumi.com/doumi_browser/mockserver  
2. 解压builder根目录下的node_modules.tar.gz到builder根目录
3. 修改builder根目录**doumi_config.js**文件  
- 文件修改说明: 带注释的是需要修改的字段  
```js  
var proRootPath = '/Users/gy/WebstormProjects/vip_pc_doumi/'; //改:项目的根目录
exports.fileRootPathConfig = {
    html : proRootPath, 
    js : proRootPath,  
    css : proRootPath, 
    img : proRootPath,
    swf : proRootPath
}
//远程根路径配置
exports.remoteRootPathConfig = {
    js : "",
    css : "",
    img : "",
    beApiRootPath : "m.doumi.com", //后端php接口域名,域名后面不能带'/',前面不能加schema
    beApiServerPort : "80", //后端php接口端口号
    beAccessToken : { //登录用户的access token,如果接口需要登录权限,需要配置此处地方。两个字段都可以在cookie中找到
        'doumi_melon' : '',
        'ganji_jz_wc_jzuid' : ''
    }
}
//mock server 配置
exports.mockServerConfig = {
    port :8900 //mock-server端口号
}
```  
> 注意:配置的改动需要重启mock-server   

4. 启动:  
node server.js

5. 访问:
http://localhost:8900/view/xx/xxx.html  //view是实际业务项目里的视图根目录  