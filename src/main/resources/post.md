## 痛点

每次发布一篇新博文，如果想发布到不同的平台，需要人工处理好多事情，诸如，登录，点击发布文章，拷贝，粘贴，发布。想寻找一款工具能够一次编辑，同步到不同的社交平台。

## 解决方案
使用 `Post Dispatcher` 自动发送博文到不同社交平台，掘金、简书、CSDN等，弊端是需要熟悉 `JAVA` 的同学使用运行程序的方式实现。

## 实现原理
本项目的实现原理比较简单，主要是使用 `Selenium` 的 `Webdriver`，模拟浏览在操作，从登陆，编辑，到发布一系列的流程如同自动化。

## 使用说明

### 环境准备
当selenium升级到3.0之后，对不同的浏览器驱动进行了规范。如果想使用selenium驱动不同的浏览器，必须单独下载并设置不同的浏览器驱动。

- JDK 1.8 
- Idea(安装Lombok) 
- Firefox
- 配置浏览器驱动

Firefox浏览器驱动：[geckodriver](https://github.com/mozilla/geckodriver/releases)

Chrome浏览器驱动：[chromedriver](https://sites.google.com/a/chromium.org/chromedriver/home) 
### 克隆代码
```bash
git clone https://github.com/codedrinker/post-dispatcher.git
```
### 配置依赖
因为使用原生的 `Maven` 的依赖不能运行 `Selenium`，所以并未深究，直接使用下载版本的依赖，放在项目 `lib` 目录，所以需要我们手动添加整个目录为 `Library` 即可。

### 配置账号
上文已经说了，使用模拟账号登录的方式，所以需要在 `post-dispatcher.properties` 里面配置好每一个平台的用户名和密码。  
同时也支持使用`-Dcustom-config=dp.properties` 自定义配置名称。

### 运行
配置全部完成以后直接运行 `PostDispatcher` 即可。


## 支持平台
- SegmentFault：用户名密码登录
- CSDN：Github 登录
- 简书：豆瓣登录。

## 参考
https://github.com/codedrinker/post-dispatcher/issues



