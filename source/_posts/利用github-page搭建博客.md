---
title: 利用github page搭建博客
date: 2020-02-24 15:26:40
tags:
---


## 创建博客项目
1. 在 Github 中创建一个格式为 用户名.github.io 的 Repository。勾选 Initialize this repository with a READMECreate repository
2. 打开网页：mxjlife.github.io 这里就可以看到 README.md 里的内容了。

## Hexo
Hexo 是一个博客框架。它markdown文件里的信息生成一个网页。
使用 Hexo 之前，需要先安装 Node.js 和 Git。操作如下：
1. 安装 Node.js

2. 安装 Git

3. 安装 Hexo
 * 命令行 输入 npm install -g hexo-cli
 * 回车开始安装输入 hexo -v 得到 hexo-cli: 1.0.4 等一串数据安装成功

4. 创建本地博客
 * 创建文件夹 blog
 * Git Bash 进入blog。
 * Git Bash 中输入 hexo init 将 blog 文件夹初始化成一个博客文件夹。
 * 输入 npm install 安装依赖包。
 * 输入 hexo g 生成（generate）网页。 由于我们还没创建任何博客，生成的网页会展示 Hexo 里面自带了一个 Hello World 的博客。
 * 输入 hexo s 将生成的网页放在了本地服务器（server）。
 * 浏览器里输入 http://localhost:4000/ 。 就可以看到刚才的成果了。
 * 回到 Git Bash，按 Ctrl+C 结束。
 * 此时再看 http://localhost:4000/ 就是无法访问了。

5. 发布一篇博客
 * 在 Git Bash 里，在路径 blog。输入 hexo new "My First Post"
 * 在 blog\source_posts 路径下，会有一个 My-First-Post.md 的文件。 编辑这个文件，然后保存。
 * 回到 Git Bash，输入 hexo g输入 hexo s前往 http://localhost:4000/ 查看成果。
 * 回到 Git Bash，按 Ctrl+C 结束。

## 将本地 Hexo 博客部署在 Github 上
1. 获取 Github 对应的 Repository 
2. 修改博客的配置文件
打开配置文件 _config.yml 找到 #Deployment，填入以下内容：
```
deploy:    
type: git    
repository: https://github.com/mxjlife/mxjlife.github.io.git    
branch: master 
```
保存退出
3. 部署
 * 回到 Git Bash
 * 输入 npm install hexo-deployer-git --save 安装 hexo-deployer-git 此步骤只需要做一次。
 * 输入 hexo d得到 INFO Deploy done: git 即为部署成功之前的 ReadMe.md 会被自动覆盖掉。
4. 查看结果

## 使用 Next 主题
1. 在 Git Bash 中。 输入 git clone https://github.com/iissnan/hexo-theme-next themes/next 此时主题的文件就全部克隆到 blog\themes\next 下面。

2. 修改博客配置文件
 * 打开 blog_config.yml
 * 找到 theme:
 * 把 Hexo 默认的 lanscape 修改成 next。
 * 找到 # Site，添加博客名称，作者名字等。
 * 在 language 后面填入 en 或者 zh-Hans，选择英文或者中文。
 * 找到 # URL, 填入 url。比如 url: https://mxjlife.github.io

3. 重新生成部署

4. 查看结果