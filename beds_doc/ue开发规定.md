### 项目目录结构    
.  
├── common   
├── proto_view        
├── static  
│   ├── img            
│   ├── css            
│   ├── less           
│   └── js              
├── view     
           
### 文件存放规定  
ue完成的html源文件放入proto_view目录、css文件放入/static/css目录、img文件放入/static/img目录   

> 建议:ue使用less语法实现样式,less文件需要放入/static/less目录  


### 编码规定  
1、所有资源(样式、图片)的引用路径统一使用相对于项目根目录的绝对路径(使用'/'开头),**不能使用相对路径**
例: html中
```html
    <link rel="stylesheet" href="/common/global.css">
    <link rel="stylesheet" href="/static/css/xx.css">
    <script type="text/javascript" src="/static/js/xxx.js"></script>
    <img src="/static/img/xxx.jpg" />
```
例: css中
```css
    body {
        background: url('/static/img/xxx.jpg');
    }
```