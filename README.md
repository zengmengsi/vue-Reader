[![DeepScan Grade](https://deepscan.io/api/projects/479/branches/739/badge/grade.svg)](https://deepscan.io/dashboard/#view=project&pid=479&bid=739)
# vue-Reader

整个项目一共14个页面（包括通用组件），主要使用了`vue2.0+axios+vuex`，`mint-ui`框架，主要实现了我的书架，小说排行榜，小说分类，小说详情，小说阅读，搜索页面，小说阅读记录等页面。达到了可用来看小说的基本需求。

项目中的API来自pathy后台实现，纯属共享学习之用，有任何疑问或建议可提，使用代理，本地可以完美运行。

## 本地运行

使用vue-cli工具构建，基本命令如下：
``` bash
# 安装依赖
npm install

# 开发模式
npm run dev

# 生产模式
npm run build

```
## 预览地址
项目放在阿里云的虚拟主机上，后台返回较慢，后面会继续优化


电脑端请开启开发者模式
[在线预览地址](https://www.aisbi.com/)

手机扫码：
![](https://github.com/zengmengsi/vue-Reader/blob/master/static/errBook.png)

## 实现功能

- [x] 小说书架
- [x] 分类查询
- [x] 排行榜
- [x] 搜索（搜索历史，自动补全）
- [x] 小说详情
- [x] 阅读历史记录（记录阅读章节）
- [x] 阅读夜间模式
- [x] 阅读样式设置

## TODO
- [ ] 搜索历史去重
- [ ] 搜索为空没有提示
- [ ] 书的目录不全？

- [ ] 书架点击阅读，直接打开进行阅读

- [ ] 记录滚动条的阅读位置

- [ ] 返回不正确

- [ ] 排行榜

- [ ] 分类

- [ ] 小说下载

- [ ] service worker 功能离线阅读

## 屏幕截图

<img src="https://github.com/zengmengsi/vue-Reader/blob/master/screenshot/book.png" width="280"/> <img src="https://github.com/zengmengsi/vue-Reader/blob/master/screenshot/booklist.png" width="280"/>
<img src="https://github.com/zengmengsi/vue-Reader/blob/master/screenshot/bookshelf_wu.png?raw=true" width="280"/>


## 问题
记录在项目中遇到的一些问题，和解决方法
 - [ ] 滚动条控制
    - 在不是 `HTML5 history `模式下，还没找到解决的方法

- [x] flex布局下横向滚动
    - 设置属性`flex-shrink:0`，默认下该属性值为1，空间不够时，后等比例缩小，设置为0之后，不会缩小项目

- [x] 标签选中后active样式的添加
    - 使用`:class` 判断条件为点击当前标签的索引值

- [x] 同时绑定按键修饰符（keyup事件但不包括按键enter）
    - 监听`input`事件，绑定`keyup.enter`事件

- [x] 返回路径问题
    - 使用`$router.go()`进行模拟返回

- [x] 图片加载错误处理
    - 图片加载错误的onerror方法中的静态地址webpack打包不会将其转化为base64编码，所以现在的解决方法是贴一个在线的图片地址
