PHP开发者社区
===============


本博客系统采用ThinkPHP5开发，ThinkPHP5在保持快速开发和大道至简的核心理念不变的同时，PHP版本要求提升到5.4，对已有的CBD模式做了更深的强化，优化核心，减少依赖，基于全新的架构思想和命名空间实现，是ThinkPHP突破原有框架思路的颠覆之作。

> 运行环境要求PHP5.4以上。

详细ThinkPHP5开发文档参考 [ThinkPHP5完全开发手册](http://www.kancloud.cn/manual/thinkphp5)

## 目录结构

目录结构如下：

~~~
www  WEB部署目录（或者子目录）
├─application           应用目录
│  ├─common             公共模块目录（可以更改）
│  ├─module_name        模块目录
│  │  ├─config.php      模块配置文件
│  │  ├─common.php      模块函数文件
│  │  ├─controller      控制器目录
│  │  ├─model           模型目录
│  │  ├─view            视图目录
│  │  └─ ...            更多类库目录
│  │
│  ├─command.php        命令行工具配置文件
│  ├─common.php         公共函数文件
│  ├─config.php         公共配置文件
│  ├─route.php          路由配置文件
│  ├─tags.php           应用行为扩展定义文件
│  └─database.php       数据库配置文件
│
├─public                WEB目录（对外访问目录）
│  ├─index.php          入口文件
│  ├─router.php         快速测试文件
│  └─.htaccess          用于apache的重写
│
├─thinkphp              框架系统目录
│  ├─lang               语言文件目录
│  ├─library            框架类库目录
│  │  ├─think           Think类库包目录
│  │  └─traits          系统Trait目录
│  │
│  ├─tpl                系统模板目录
│  ├─base.php           基础定义文件
│  ├─console.php        控制台入口文件
│  ├─convention.php     框架惯例配置文件
│  ├─helper.php         助手函数文件
│  ├─phpunit.xml        phpunit配置文件
│  └─start.php          框架入口文件
│
├─extend                扩展类库目录
├─runtime               应用的运行时目录（可写，可定制）
├─vendor                第三方类库目录（Composer依赖库）
├─build.php             自动生成定义文件（参考）
├─composer.json         composer 定义文件
├─LICENSE.txt           授权说明文件
├─README.md             README 文件
├─think                 命令行入口文件
~~~

## 配置方法

###### 数据库
将文件中的bick.sql导入数据库后
修改Application目录下的database.php数据库配置文件。
~~~
├─'database'       => 'bick',  // 数据库名
├─'username'       => '',  // 用户名
└─'password'       => '',   // 密码
~~~

###### 前后台样式引用路径修改

* 前台样式路径
 Application文件夹下的config.php文件：

  'view_replace_str'       => [
        '__INDEX__'=>'http://localhost:8080/bick/public/static/index'
    ],
   将__INDEX__修改到你当前public/static/index文件下。

* 后台样式路径
 Application文件夹下的admin文件夹下config.php文件：

  'view_replace_str'       => [
        '__ADMIN__'=>'http://localhost:8080/bick/public/static/admin'
    ],
   将__ADMIN__修改到你当前public/static/admin文件下。

后台登录用户名：admin
后台登录密码：123456

