# 网站搭建文档
## 1. 环境准备
### Node环境搭建
Hexo是基于nodeJS编写的，所以需要安装一下nodeJs和里面的npm工具。

windows下载路径： [Node官网](https://nodejs.org/en/download)

### Git环境搭建
一个分布式版本控制系统，用于项目的版本控制管理，使用Git Bash命令行工具来操作git。

windows下载路径： [Git官网](https://git-scm.com/download/win)

### 验证是否搭建成功
在命令行中依次输入

```git version```

```node -v```

```npm -v```

如果成功会有相应的版本号

## 2. Hexo安装
选择安装路径文件夹，右击选择```Git Bash here```，
在命令行输入
```npm install -g hexo-cli```

运行结束后输入```hexo -v```查看版本

## 3. Hexo初始化
继续在命令行中依次输入

```hexo init my-blog```

```cd my-blog```

```npm install```

运行结束后，可以看到文件夹中出现如下内容：

- node_modules: 依赖包
- public：存放生成的页面
- scaffolds：生成文章的一些模板
- source：用来存放你的文章
- themes：主题
- _config.yml: 博客的配置文件

然后再命令行中输入以下指令，进行本地启动

```$ hexo clean```

```$ hexo g```

```$ hexo s```

至此，任务创建完成，在浏览器中输入```localhost:4000```即可看到自己的博客界面

在命令行中```ctrl + c```即可关掉服务
