# interest

## 项目介绍
  该项目为前后端分离项目，前端vue，后端Spring boot。
  
## 已有功能介绍
1. pc版展示页面。
2. mobile版展示页面。
3. pc版后台管理系统。
4. github第三方登录。
5. oauth2授权与认证。
  
## 项展示
  项目展示地址为我的网站：

## 项目结构
- 前端interest-web
.
├── package.json  项目构建配置
├── webpack.base.config.js  项目构建配置
├── webpack.dev.config.js  项目构建配置
├── webpack.prod.config.js  项目构建配置
└── src
    ├── config  其他配置
    ├── images  图片文件
    ├── libs  工具方法
    ├── store  状态管理
    ├── template  模板文件
    ├── styles  样式文件
    ├── app.vue  入口页面
    ├── axios.js  axios配置
    ├── main.js  main.js
    ├── vendors.js  公共库文件
    ├── router.js  路由配置
    └── views
        ├── mobile  mobile版
        │   ├── card.vue  帖子页
	│   ├── detail.vue  详情页
	│   ├── home.vue  主页
	│   └── index.vue  head+footer
        ├── sys  后台管理
        │   ├── interest
	│   │   ├── interest-create.vue  兴趣新建
	│   │   ├── interest-delete.vue  兴趣删除
	│   │   ├── interest-edit.vue  兴趣修改
	│   │   └── interest-quill-editor.vue  富文本编辑器组件
	│   ├── banner.vue  轮播管理
	│   ├── base.vue  head+left list
	│   ├── card.vue  帖子管理
	│   ├── email.vue  邮件管理
	│   ├── menu.vue  菜单管理
	│   ├── role.vue  角色管理
	│   ├── user.vue  用户管理
        │   └── welcome.vue  默认页
	├── template  PC版
        │   ├── card.vue  帖子页
	│   ├── detail.vue  详情页
	│   ├── home.vue  主页
	│   └── index.vue  head+footer
        ├── error404.vue  404页面  
        ├── login.vue  PC登录页面
        └── mlogin.vue  mobile登录页面
1）技术栈
vue2
vuex
vue-router
axios
iview
vue-quill-editor
webpack
2）前后端通信
使用的是axios库。
3）UI组件
使用的是axios库。
4）安全协议
oauth2
5）前端界面开发
注：需要安装nodejs

启动：
命令行进入项目文件夹
运行npm install
运行npm run init初始化项目
运行npm run dev启动前端工程
打包命令： 运行npm run build
6）打包发布
运行npm run build后，得到 dist文件+index_prod.html。（index_prod.html为项目的入口html）
使用nginx发布。（nginx配置参考文件）
7）Http状态码
在axios.js中拦截异常，并进行处理。
目前以写的异常处理有：
	1. 401 清除token信息并跳转到登录页面
	2. 403 无权限，跳转到首页
- 后端interest-server
1）项目目录结构
─ src
    ├── main  
    │	├── java  
    │	│   └── com.interest 
    │	│	├── controller  controller类
    │	│	├── dao  dao类
    │	│	├── model  entity类
    │	│	├── oauth2  spring security oauth2配置类
    │	│	├── properties  项目配置类
    │	│	├── security  spring security配置类
    │	│	├── service  service类
    │	│	└── utils  工具类
    │	└── resource  
    │	    ├── createTable 表数结构及表数据
    │	    ├── mybatis.mapper mybatis的mapper.xml
    │	    └── application.yml 项目配置文件
    └── test  测试
2）技术栈
pring boot
mybatis
Spring Security
Spring Security OAuth2
Redis
3）接口设计
RESTful
4）认证与授权
使用了Spring Security OAuth2
5）项目搭建
运行环境：

jdk1.8+maven。

数据库配置：

数据库mysql（表与表数据在interest-server\src\main\resources\createTable中,用户密码为BCrypt加密，用户admin的密码为admin）

缓存配置：

配置redis，且redis服务必须开启。

