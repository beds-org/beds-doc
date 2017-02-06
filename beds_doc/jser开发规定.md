### 项目目录结构    
```
.  
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
     
### 文件存放规定  
1. jser将完成的html源文件放入view目录   
2. js、css业务入口文件放入/static/<js|css|less>/下非widget目录。业务组件文件放在/static/\<js|css|less\>/下的子自创建的widget目录。     
3. js、css全局通用的组件或是三方库需要放入独立项目common中,然后在业务项目中通过beds-dev-cli工具的update命令更新当前项目的common目录。  
4. 图片放在/static/img/目录下
> [项目目录结构说明]()

### ui组件开发规定
1. 一个组件由 一个js文件、一个样式文件和一个html模板文件构成。
2. pc端统一采用avalon框架开发组件。 wap端使用vue框架开发组件
3. 通用组件放在common项目中的ui_widget目录里,业务组件在业务对应目录建立widget,放到wiget目录下

### js组件开发规定
1. 通用组件放在common项目中的ui_widget目录里,业务组件在业务对应目录建立widget,放到wiget目录下

### 片段html
片段html文件统一使用**.chtml**为扩展名  
例如组件中的html模板,试图中的footer、header都是片段html

### 视图html
将/proto_view里的视图统一封装成使用下面的ejs模板格式的html文件,放入/view目录 
```html
<%setTitle('斗米商家im')%>
<%setCss(['/static/less/test/test1.less'])%>
<%setJs(['/static/js/test/test2.js','/static/js/test/test.js'])%>
<%include /view/header.chtml%>
<!--html body体里的实际内容-->
<%include /view/footer.chtml%>
```
> 1、setJs和setCss函数参数可以是数组或字符串,如果只有一个需要引用的文件,可以直接使用字符串。  
2、大部分情况,一个html页面只需要对应一个业务js文件和一个业务css文件。如果需要引用多个js文件,把入口js放在数组的最后面。

### 接口路径格式 
接口路径前统一加上**window.dm.beApiRootPath**变量,该变量会被builder或mockserver转换成实际的接口domain,例:  
```js
$.get(window.dm.beApiRootPath + '/list/more/?order=0&lat=&lng=&more=a&pageSize=10&offset=1&page=2', function(data) {
    //略..
})
```
### 资源路径格式
所有资源引用统一使用相对于根目录的绝对路径。禁止使用相对路径