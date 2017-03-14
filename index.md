# 实验一 在Github上用Markdown创建技术博客

## 一、实验目的
1.	熟悉Github网站
2.	掌握Markdown语法

## 二、实验任务
1.	注册Github账号
2.	创建Gihub Pages repository
3. 	发布第一篇博客
4.	学习Markdown
5.	利用Hexo生成博客并部署到Github

## 三、实验步骤与结果
1. [pull request]https://github.com/chen-rhythm/Experience/pull/1
2. [我的测试实验]https://github.com/hutct/test1

## 生成hexo步骤：
### 1. 安装node，安装git
### 2. 使用淘宝NPM镜像,在网页中打开http://npm.taobao.org/
### 3. 在该网页中复制npm命令
```
$ npm install -g cnpm --registry=https://registry.npm.taobao.org
```
### 4. 在windows中打开cmd命令提示符，粘贴cnpm命令语句并执行
### 5. 安装Hexo
```
$ cnpm install -g hexo-cli
```
### 6. 初始化站点
```
$ hexo init hexo
$ cd /d/MD/hexo
$ cnpm install
```
### 7. 打开终端，在本地预览
```
$ hexo server
```

#### hexo搭建完成，在网页中打开<http://localhost:4000/>即可进行本地预览


## hexo+github搭建博客步骤：
### 1.新建一个仓库
登录[Github](https://github.com "Github")，创建一个新的repository，名称是：**用户名.github.io**

### 2. 打开hexo/_config.yml文件，修改配置文件
```
 deploy:
  type: git
  repository: git@github.com:jessciary/jessciary.github.io.git
 branch: master
```

### 3. 输入创建文章命令，生成一个md文件(/hexo/source/_posts/)
 ```
$  hexo new "test"
```
 打开hello.md文件,编写完后保存
 
### 4. 设置git身份信息
 ```
$  git config --global user.name "jessciary"
$  git config --global user.name "10254116623@qq.com"
```
 
### 5. 安装hexo git插件
 ```
$   cnpm install hexo-deployer-git --save
```
 
### 6. 发布更新博客
 ```
$   hexo d -g
```
 
####[我的博客主页]https://jessciary.github.io/
 
## 四、实验小结

## 错误小结
### 1.hexo/_config.yml文件冒号后必须有一个英文空格

### 2.若出现如下错误：Could not read from remote repository
是由于没有在github账号添加SSH key，可删除C:\Users\PC\.ssh目录下的.ssh文件
或进行如下处理：
获取SSH keys
```
$  ssh-keygen -t rsa -C "forwhat.cn"//注意forwhat.cn为用户名
```
回车，再次回车，回车
```
$ ssh-agent -s
$ ssh-add ~/.ssh/id_rsa
```
到这里出错，就输入如下指令
```
$ eval `ssh-agent -s`
$ ssh-add
```
复制密钥
```
$ clip < ~/.ssh/id_rsa.pub
```
通过指令复制密钥，之后可以直接Ctrl+V粘贴密钥
在Github上添加密钥：
打开[Github](https://github.com "Github")，在同名repo的右上角**Settings**里选择**Deploy keys**选项卡，点击**Add deploy keys**，将刚复制好的密钥粘贴上去，点击**Add key**，在弹出来的框中输入Github的登陆密码即可完成添加

### 3.若出现如下错误：spawn git ENOENT
是由未添加Git环境变量引起，添加Git与git管理库的环境变量即可
