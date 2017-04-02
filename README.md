# plover开发文档


## 简介


Plover（千鸟）是一个专注于 **模块化方式构建web应用** 的NodeJs MVC web框架。不同于其它web框架，它提供完整的应用和模块化模型可以让复杂的业务功能可以方便地抽象成多个模块的方式进行独立开发，让应用可以像搭积目的方式拼装模块而成。  
Plover基于[koa](http://koajs.com)构建，它可以很方便地独立部署或者集成到其他koa的应用一起部署。  
Plover专注于 **模块化** ，为 **快速构建web应用** 提供最佳方案  


## 关于文档


此文档会随着Plover的开发和发展持续维护，是使用Plover开发应用的重要参考。  
它主要分成两部分：文档和示例。  
如果某一节有相关示例，会在相应的文档页面标明，可以直接点击相应链接查看，也可以直接checkout运行查看效果。  
所有示例都是可运行的，如没有特别说明，可以使用以下方式运行。  

```shell
$ git clone git@github.com:ploverjs/examples.git
$ cd examples
$ npm install
$ npm start
```

正常启动后，可以访问`http://127.0.0.1:4000`访问示例。


## 前提

首先你需要了解[NodeJs](http://nodejs.org)。[七天学会NodeJs](http://nqdeng.github.io/7-days-nodejs/)是一份不错的入门书籍。  
由于Plover基于[Koa](http://koajs.com/)搭建，因此需要对它有个基本的了解。你需要知道什么是**中间件**，以及熟悉常见的API，至少能够使用它搭建HelloWorld应用。  
此外必须熟悉ES6中的**生成器** 或 ES7中的`async/await`，因为在正式的开发中我们会经常使用到它。可以参考阮一峰的[Generator](http://es6.ruanyifeng.com/#docs/generator)来学习。


## 开始使用

- [Hello Plover](docs/start/hello.md)


## 示例

- [Hello Plover](https://github.com/ploverjs/examples/tree/master/hello)
- [静态资源的访问](https://github.com/ploverjs/examples/tree/master/static)
- [路由和RESTful](https://github.com/ploverjs/examples/tree/master/routes)
- [结合React使用](https://github.com/ploverjs/examples/tree/master/react)


## 参考
- [路由](https://github.com/alibaba/plover/tree/master/packages/plover-router)
- [web中间件](https://github.com/alibaba/plover/tree/master/packages/plover-web)
