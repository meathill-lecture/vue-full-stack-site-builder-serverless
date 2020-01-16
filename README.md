Vue full-stack site-builder
========

This is a serial practical tutorial video, teaching you how to build a site-builder with Vue, Nuxt, and serverless data engine.

Project Introduction
--------

[Salboy](http://www.salboy.cn/crescent/) 是一个给地产商网站使用的网站（链接里是一个预览页）。他们会在这个网站上更新房产项目，然后代理人员可以浏览这些房产项目，选择合适的推荐给客户。成交之后抽取佣金。

接到需求的时候，我们原本打算用传统的 WordPress + 模版来做，但是考虑到以下几点，我决定不这么做：

1. WordPress 虽然适配性强，但它本质上是个博客网站，并不适合做**格式化**的内容
2. 大部分模版开发得很一般，二次开发非常困难
3. 大部分网站运营人员（后台实际操作人）不熟悉类似的软件，培训成本很高，出错的机会也很多

为了能让客户用得更爽，也为了将来能更好的合作，我选择从零开始，用 Vue 及其它工具链一起，搭建了一个所见即所得的 CMS。

1. 整个项目基于 Vue 全家桶搭建，使用 @vue/cli 4 创建
2. 数据存储使用 LeanCloud 提供的 serverless 服务
3. 页面中的每个内容区块，都抽象成一个组件，比如：大标题、描述、照片墙等
4. 每个组件都包含两个状态：1. 编辑中；2. 纯静态。通过 props 控制。
5. 在后台中，组件呈现编辑状态。并且通过控制样式，让组件在编辑时不影响布局
6. 发布后，组件只显示静态内容
7. 利用 Nuxt.js 的生成机制，将发布后的页面生成静态页
8. 把静态页上传到服务器，然后使用 CDN 接受用户访问

整个项目中，用到了以下技术：

1. Vue 全家桶，Vuex + Vue-Router + @vue/cli
2. 后台式 SPA 搭建
3. 组件技术
4. Nuxt.js 生成静态页
5. Serverless 数据设计
6. 用工具链管理开发过程
7. 使用 nginx + 最便宜的云服务器做 host
8. 使用阿里云全站加速做 CDN

这样实现的好处：

1. 页面所见即所得，用户使用基本没有学习成本
2. 发布的是纯静态页，服务器成本很低，扩展方便
3. 不受后端限制
