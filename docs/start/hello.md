# Hello Plover


## 目标

- 从零搭建plover应用。
- 了解应用的基本结构。


## 示例

在开始之前可以运行以下示例：

```
git clone git@github.com:ploverjs/guides.git
cd guides
git checkout hello
npm install
npm start
```

启动成功后访问 `http://127.0.0.1:4000` 就可以看到结果。  

文档中的其他示例都会以**git分支**的方式提供，如未作特别说明都可以使用以下步骤运行：

```
git checkout ${branch-name}  # 切换到示例分支
npm install   # 安装依赖模块
npm start     # 运行
```

## 应用结构

如果没有下载示例，也可以在github上查看应用结构 [hello](https://github.com/ploverjs/guides/tree/hello)。 


```
guides/
  config/     # 配置
    app.js      # 应用配置
    routes.js   # 路由配置

  modules/    # 模块
    home/       # 一个叫`home`的模块
      index.js    # 控制器

  node_modules/

  app.js      # 入口
  package.json
```

一个应用主要包括：**Plover模块**、**配置**、**应用级代码**、**依赖库**、**入口** 和 **相关脚本** 等。  

我们简单看一下相关文件的内容。


### package.json

引入plover依赖，定义启动入口。

```
dependencies: {
  "ploverx": "~2.1.0"
}
```

[plover](https://github.com/ploverjs/plover) 核心主要提供了模块管理和渲染的功能。web应用需要的其他功能都是以插件形式提供的。为了方便使用，[ploverx](https://github.com/ploverjs/ploverx)模块聚合一组最常用的模块，所以只要使用这个模块即可。[ploverjs](https://github.com/ploverjs)组中维护着许多插件。


```
scripts: {
  "start": "node app.js"
}
```

当我们运行`npm start`时，相当于运行`node app.js`。


### app.js

应用入口文件。应用启动时就是运行这个文件。

```js
const ploverx = require('ploverx');

const app = ploverx({ applicationRoot: __dirname });
app.run();
```


### config/

应用的配置都是放在这个目录下。


### config/app.js

可以对应用进行配置。比如配置应用启动端口号，还可以对各插件进行配置。


### config/routes.js

路由配置。这是个非常重要的文件，我们对外提供的服务主要是通过这个文件配置的。

```js
module.exports = ({ get }) => {
  get('/', 'home#index');
}
```

以上表示将`/` 路由到`home`模块的`index`action。


### modules/

承载应用相关模块的主目录。刚刚的示例只有一个`home`模块。  
一个模块包含涉及功能的所有资源。由控制器、模板、js、css和图片资源等组成。  

示例模块非常简单，只包含控制器：

home/index.js

```js
exports.index = function() {
  this.body = 'Hello Plover!';
};
```

此控制器有一个action方法，用于直接输出内容。后续会看到如果使用模板输出内容。



