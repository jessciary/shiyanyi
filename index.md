#实验一 在Github上用Markdown创建技术博客

##一、实验目的
1.	熟悉Github网站
2.	掌握Markdown语法

##二、实验任务
1.	注册Github账号
2.	创建Gihub Pages repository
3. 	发布第一篇博客
4.	学习Markdown
5.	利用Hexo生成博客并部署到Github

##三、实验步骤与结果
1. ！[我复制的他人代码]https://github.com/jessciary
2. ！[我的第一个实验]https://github.com/hutct/test1

###生成hexo步骤：
1. 安装node，安装git
2. 在网页中打开http://npm.taobao.org/
3. 在该网页中复制cnpm命令
4. 在windows中打开cmd命令提示符，粘贴cnpm命令语句并执行
5. 使用cd hexo打开hexo目录
6. 进入该目录后执行cnpm install
7. 打开终端，执行hexo server
####hexo搭建完成

###hexo+github搭建博客步骤：
1. 打开blog/_config.yml文件，进行配置
 deploy:
  type: git
  repository: git@github.com:jessciary/jessciary.github.io.git
 branch: master

2. 输入创建文章命令，生成一个md文件(/blog/source/_posts/)
 hexo new "test"
 打开hello.md文件,编写完后保存

3. 设置git身份信息
 git config --global user.name "jessciary"
 git config --global user.name "10254116623@qq.com"
 
4. 安装hexo git插件
 cnpm install hexo-deployer-git --save
 
5. 发布更新博客
 hexo d -g
 
####[我的博客主页]https://jessciary.github.io/
 
##四、实验小结
