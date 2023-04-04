# [小丑路人·短域名](http://laravel-vue-admin.cnpscy.com)

- [语言版本](#section-语言版本)
- [作者`小丑路人`](#section-作者`小丑路人`)
- [小丑路人社区](#section-小丑路人社区)
- [在线预览](#section-在线demo预览)
- [软件架构](#section-软件架构)
- [安装教程](#section-安装教程)
- [部署优化](#section-部署优化)
- [使用说明](#section-使用说明)
- [捐助](#section-捐助)

<a name="section-语言版本"></a>
### 语言版本

> {success} [gitee仓库·laravel-短域名](https://gitee.com/clown-passerby-community/laravel-vue-admin)

<p align="center">
    <img src="https://gitee.com/clown-passerby-community/laravel-short-url/badge/star.svg?theme=dark" />
    <img src="https://gitee.com/clown-passerby-community/laravel-short-url/badge/fork.svg?theme=dark" />
    <img src="https://svg.hamm.cn/badge.svg?key=License&value=MIT&color=da4a00" />
</p>


<a name="section-作者`小丑路人`"></a>
### 作者`小丑路人`
> https://www.cnpscy.com

<a name="section-小丑路人社区"></a>
### 小丑路人社区
> https://bbs.cnpscy.com

<a name="section-在线预览"></a>
### 在线预览

> https://short.cnpscy.com


<a name="section-软件架构"></a>
### 软件架构
* 编程语言：`PHP:7.3^8.0`
    - imagick
* 后端框架： `Laravel8.75`

<a name="section-安装教程"></a>
### 安装教程

1. composer install
2. cp .env.example .env
3. 生成 APP_KEY：`php artisan key:generate`
4. 数据表迁移 `php artisan migrate`
5. 数据填充 `php artisan module:seed ShortUrl`
6. 创建`Storage`目录软链接 `php artisan storage:link`

<a name="section-部署优化"></a>
### 部署优化
* 配置信息缓存 php artisan config:cache
* 路由缓存 php artisan route:cache
* 类映射加载优化 php artisan optimize
* 自动加载优化 composer dumpautoload

<a name="section-使用说明"></a>
### 使用说明

- 请务必使用`master`分支
- `self-master`是共用自己的数据库

<a name="section-捐助"></a>
### 捐助

![支付宝收款码](https://bbs-1252866470.cos.ap-shanghai.myqcloud.com/alipay-collection.png "alipay-400.jpg")
![微信收款码](https://bbs-1252866470.cos.ap-shanghai.myqcloud.com/wechat-collection.png "wechat-400-width(1).jpg")
