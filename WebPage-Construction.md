# 网站搭建文档
## 1. 环境准备
### Node环境搭建
  Hexo是基于nodeJS编写的，所以需要安装一下nodeJs和里面的npm工具。
  
  windows下载路径： [Node官网](https://nodejs.org/en/download)

### Git环境搭建
  一个分布式版本控制系统，用于项目的版本控制管理，使用Git Bash命令行工具来操作git。
  
  windows下载路径： [Git官网](https://git-scm.com/download/win)

### 验证是否搭建成功
  在命令行中依次输入以下指令，如果成功会有相应的版本号

```
  git version
  
  node -v
  
  npm -v
```



## 2. Hexo安装
1. 选择安装路径文件夹，右击选择```Git Bash here```，
2. 在命令行输入
```npm install -g hexo-cli```

3. 运行结束后输入```hexo -v```查看版本

## 3. Hexo初始化
1. 继续在命令行中依次输入

```
  hexo init my-blog

  cd my-blog

  npm install
```

2. 运行结束后，可以看到文件夹中出现如下内容：

    - node_modules: 依赖包
    - public：存放生成的页面
    - scaffolds：生成文章的一些模板
    - source：用来存放你的文章
    - themes：主题
    - _config.yml: 博客的配置文件

3. 然后再命令行中输入以下指令，进行本地启动
 
```
  $ hexo clean

  $ hexo g

  $ hexo s
```

5. 至此，任务创建完成，在浏览器中输入```localhost:4000```即可看到自己的博客界面

6. 在命令行中```ctrl + c```即可关掉服务

## 4. github仓库准备
### 创建仓库
1. 注册github账户

2. 点击```New repository```新建仓库

3. 创建github专属page，```用户名.github.io```

### SSH绑定
1. 在git bash输入以下指令，这里的yourname输入自己的GitHub用户名，youremail输入自己的GitHub邮箱。

```
   git config --global user.name "yourname"
   
   git config --global user.email "youremail"
```
   
3. 创建SSH，回车继续即可，之后可通过输入```cat id_rsa.pub```查看公钥
   
```
   ssh-keygen -t rsa -C "youremail"
```

4. 在github的setting中，设置SSH keys，将信息复制进去
   
5. 在gitbash中输入以下指令，查看SSH是否绑定成功

```
   ssh -T git@github.com
```


## 5. 部署hexo到github
 1. 打开文件夹中的站点配置文件```_config.yml```，翻到最后，修改以下部分：
```
  deploy:
    type: git
    repo: git@github.com:zjc2782171149/用户名.github.io.git
    branch: master
```

2. 安装```deploy-git```
```
  npm install hexo-deployer-git --save
```
3. 进行部署
```
  hexo clean

  hexo g

  hexo d
```
4. 部署成功，在```http://你的用户名.github.io```查看自己的博客

