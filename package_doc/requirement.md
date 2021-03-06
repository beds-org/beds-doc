## 包管理系统
核心功能为包的生成、下载、归档。包数据来源为git获取。

## 一、功能说明
### 用户
- 注册
- 登录

### 权限
- 项目权限
    - 创建
    - 删除
    - 浏览
- 包权限
    - 创建
    - 删除
    - 浏览

### 项目
- 创建项目
- 创建版本号
- 删除项目
- 删除版本号
- 浏览

### 包
- 创建包
- 删除包
- 下载包
    - 单包
    - 多包
    
## 二、页面说明
### 登录注册页
略..  

### 首页(dashboard)
- 功能:
    - 根据权限展示创建项目按钮 
    - 根据权限展示打包安按钮
    - 根据权限展示项目列表
        - 字段:项目名称、创建人、创建时间、三种环境对应的分支、当前线上版本、线上包数量、sim包数量、测试包数量、操作按钮(管理、删除、最新线上包下载)
    - 根据权限展示人员管理按钮   
   
### 创建项目页面
- 功能:创建项目
- 表单字段:项目名称、项目git地址、指定分支(线上包分支、sim包分支、测试包分支)

### 项目管理页面
- 功能:  
    - 创建新版本。
    - 为当前项目指定可以打包的人员。 
    - 为当前项目指定可以使用包的人员。 

### 包列表页面
- 功能
    - 点击项目列表里的项目进入该项目下的包列表页面。页面中以tab标签的形式分别展示线上包列表、sim包列表和测试包列表
    - 列表里默认展示最新版本的下的包
    - 列表旁边有版本选择下拉菜单,可选择查看指定版本的包列表
    
- 列表字段:包类型(单包、多包)、创建时间、创建人、操作(下载、删除)

- 下载说明
    - 单包:提供一个下载地址。
    - 多包:提供*入口包*下载地址,以及后续包的动态下载地址(app内按需下载)。
    
### 创建包页面
- 功能:创建包
- 表单字段:项目、包类型(单包、多包)、版本号(下拉列表)、环境(单选:测试、sim、线上)

### 人员管理页面
- 仅管理员可以访问
- 功能:指定具有创建项目权限的人员

## 三、权限说明
- 管理员
    - 创建项目的权限
- 项目创建人
    - 创建项目版本的权限
    - 创建包的权限
    - 浏览包的权限
    
## 四、操作说明
- 线上包不能删除
- 项目名称唯一
- 项目下的版本号唯一
