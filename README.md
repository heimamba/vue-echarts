# my-echarts

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

# 从零开始操作如何上传文件到github以及创建vue项目

# 创建到github上操作：

1. 初始化 git init 
2.首先注册github账号，登录，创建新仓库 ，点击+，点击new repository,输入标题把README勾选中，创建完毕然后在git bash中输入： ssh-keygen -t rsa -C 'xxqiang812@163.com' 一直回车，默认在默认路径生成.ssh文件夹，打开.ssh里面有两个文件，打开id_rsa.pub复制里面的秘钥
3.打开github，选择settings。选择new SSH key， 输入标题和秘钥
4. 查看是否成功，在git bash里面输入ssh -T git@github.com，回车选中yes，其他不管
5. 克隆新建的仓库到本地，输入命令：git clone https://github.com/heimamba/vue-echarts.git

#安装vue和项目操作
1. 全局安装vue-cli ：  npm install --global vue-cli
2. 创建一个基于webpack模板的新项目： vue init webpack my-echarts   ；除了Use ESLint to lint your code，tests，nightwatch
下面这三个为no其他都是yes
3 npm run dev 就可以跑起来了
