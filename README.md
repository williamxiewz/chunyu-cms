## 项目简介
淳渔是一款快速搭建影视类网站的系统，它用户端基于[nuxt3](https://nuxt.com/)和 [element-ui](https://element.eleme.cn/#/zh-CN) ,管理端基于 [vue3](https://cn.vuejs.org/) 和 [element-ui](https://element.eleme.cn/#/zh-CN) ，后端基于 node 的后端框架 [nestjs](https://docs.nestjs.cn/8/) ，数据库采用 mysql ，缓存采用 redis。


## 在线体验
  - [用户端演示地址](http://cms.yinchunyu.com)
  - [管理端演示地址](http://cms-admin.yinchunyu.com)
  - [文档地址](https://yinMrsir.github.io/#/)
  - [码源地址](https://github.com/yinMrsir/chunyu-cms)


## 技术要求
  - [Vue](https://cn.vuejs.org/)
  - [Element-ui](https://element.eleme.cn/#/zh-CN)
  - [TypeScript](https://www.tslang.cn/index.html)
  - [Nestjs](https://docs.nestjs.cn/8/)
  - [TypeORM](https://typeorm.biunav.com/)
  - Mysql
  - Redis
  
## 技术选型
  1. **前端技术**
   - nuxt @3.0.0
   - vue @2.6.12
   - element-ui @2.15.6
   - axios @0.24.0
   - vuex @3.6.0
   - vue-router @3.4.9
   - sass-loader @10.1.1

  2. **后端技术**
   - nest @8.0
   - mysql2 @2.3.3
   - swagger-ui-express @4.2.0
   - typeorm @0.2.41
   - ioredis @4.28.2

## 开发前

如未安装`mysql`数据库和`redis`请先自行安装。可选mysql8，redis7。

如果没有安装nest-cli，先执行`npm install -g @nestjs/cli`命令全局安装

本地开发启动服务可查看：[相关视频](https://www.douyin.com/user/MS4wLjABAAAAUKMCVZGbQl7etrdd36GBIG6OGxClOwoHci_-PIlxNvE?modal_id=7213009576487177504)

## 部署

### 构建服务端：

先修改`Nest-server/src/config/config.production.ts`中的数据库连接配置信息后执行：

```shell
cd Nest-server
yarn
yarn build
```

### 构建用户端：

在Nuxt-web目录中创建`.env`文件并写入`BASE_URL=服务端请求地址`

```shell
cd Nuxt-web
yarn
yarn build
```

构建完成后，可通过pm2进行部署，未安装的可执行`npm install -g pm2`安装

执行以下命令启动服务：
```shell
pm2 start pm2.config.cjs
```

### 构建管理端

执行以下命令会生成`dist`目录，可通过`nginx`指定到目录。

```shell
cd Vue3-admin
yarn
yarn build:prod
```

### 单文件打包
如果你有需求要打包成单文件或者pkg包，可进入Nest-server执行`yarn ncc:pkg`, 因bull库不支持单文件执行，所以打包前需将引入了bull库的相关模块移除！

## 更新
### 2023-5
- [x] [友情链接支持后台配置](https://www.douyin.com/user/MS4wLjABAAAAUKMCVZGbQl7etrdd36GBIG6OGxClOwoHci_-PIlxNvE?modal_id=7225255650392132903)
- [x] 用户影视评分

### 2023-7-7
- [x] 用户签到
- [x] 用户签到获得金币
- [x] 视频支持支付付费观看

### 待完成
- [ ] 用户购买金币
- [ ] 视频发送弹幕

## 相关链接

win安装Docker: https://zhuanlan.zhihu.com/p/441965046

docker安装redis：https://www.runoob.com/docker/docker-install-redis.html

docker安装mysql：https://www.runoob.com/docker/docker-install-mysql.html

解决Navicat连接数据库提示`client does not support authentication：https://blog.csdn.net/lovedingd/article/details/106728292

## 有任何疑问可添加微信

<img height="120" src="https://gitee.com/chunyu-cms/chunyu-cms/raw/main/wx.jpg" width="120"/>

[Nuxt3教程文档](http://www.yinchunyu.com)

[Nuxt3视频教程](https://www.bilibili.com/video/BV1gu4y1R7Jt/?spm_id_from=333.999.0.0&vd_source=9dbe815ca79d8528e02be1a51583912a)
