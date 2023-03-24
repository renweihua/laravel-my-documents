# [小丑路人·laravel-vue-admin管理系统](http://laravel-vue-admin.cnpscy.com)

- [语言版本](#section-语言版本)
- [作者`小丑路人`](#section-作者`小丑路人`)
- [小丑路人社区](#section-小丑路人社区)
- [在线demo预览](#section-在线demo预览)
- [软件架构](#section-软件架构)
- [介绍](#section-介绍)
- [安装教程](#section-安装教程)
- [部署优化](#section-部署优化)
- [使用说明](#section-使用说明)

<a name="section-语言版本"></a>
### 语言版本

> {success} [gitee仓库·laravel-vue-admin管理系统](https://gitee.com/clown-passerby-community/laravel-vue-admin)

<p align="center">
    <img src="https://gitee.com/clown-passerby-community/laravel-vue-admin/badge/star.svg?theme=dark" />
    <img src="https://gitee.com/clown-passerby-community/laravel-vue-admin/badge/fork.svg?theme=dark" />
    <img src="https://svg.hamm.cn/badge.svg?key=License&value=MIT&color=da4a00" />
</p>

---

> {primary} [gitee仓库·hyperf-vue-admin管理系统](https://gitee.com/clown-passerby-community/hyperf-vue-admin)

<p align="center">
    <img src="https://gitee.com/clown-passerby-community/hyperf-vue-admin/badge/star.svg?theme=dark" />
    <img src="https://gitee.com/clown-passerby-community/hyperf-vue-admin/badge/fork.svg?theme=dark" />
    <img src="https://svg.hamm.cn/badge.svg?key=License&value=MIT&color=da4a00" />
</p>

<a name="section-作者`小丑路人`"></a>
### 作者`小丑路人`
[小丑路人](https://www.cnpscy.com)

<a name="section-小丑路人社区"></a>
### 小丑路人社区
[小丑路人社区](https://bbs.cnpscy.com)

<a name="section-在线demo预览"></a>
### [在线demo预览](http://laravel-vue-admin.cnpscy.com/admin)

    http://laravel-vue-admin.cnpscy.com/admin
    admin
    123456

    如果无法登录，请在评论区@我重置密码。

<a name="section-软件架构"></a>
### 软件架构

* 编程语言：`PHP7.3+`
* 后端框架： `Laravel8`
* 前端Vue框架：`vue-element-admin`
* Nodejs  v14.*

<a name="section-介绍"></a>
### 介绍

[demo站](http://laravel-vue-admin.cnpscy.com/admin)

![首页](/laravel-vue-admin/home.png)

![版本历史记录](/laravel-vue-admin/版本历史记录.png)

![西班牙语](/laravel-vue-admin/西班牙语.png)

![请求日志统计](/laravel-vue-admin/请求日志统计.png)

![图片选择器功能](/laravel-vue-admin/图片选择器.png)

![数据库管理](/laravel-vue-admin/数据库管理.png)

![备份管理](/laravel-vue-admin/备份管理.png)

<a name="section-安装教程"></a>
### 安装教程

##### 安装Vue
* 安装 npm 包：`npm install`
* 热更新vue项目：`npm run watch-poll`
  - vue无法执行：可尝试：
      - npm rebuild node-sass
          - `tui-editor` 此包引起的
    
##### PHP设置
* 命令行：`composer install`
* 命令行：`cp .env.example .env`
* 命令行，生成 APP_KEY：`php artisan key:generate`
* 命令行，JWT的key：`php artisan jwt:secret`
* 同步导入数据表：`php artisan sync:database:tables`

##### 站点配置

- 站点解析目录：`public`
- 访问网址：`你的域名/admin`
- 定时任务：
    - 自动按月分表：`php artisan command:autotablebuild`
    - 或者使用任务调度：`php artisan schedule:run`

<a name="section-部署优化"></a>
### 部署优化
* 配置信息缓存 artisan config:cache
* 路由缓存 artisan route:cache
* 类映射加载优化 artisan optimize
* 自动加载优化 composer dumpautoload

<a name="section-使用说明"></a>
### 使用说明

* 按月、按年分表的模型，皆不可使用 `with`，可使用 `load` 代替,`static::query` 会重新 实例化当前模型，之前设置的分表名称将被替换。
    
    具体原因看代码：
```php
    /**
     * Begin querying a model with eager loading.
     *
     * @param  array|string  $relations
     * @return \Illuminate\Database\Eloquent\Builder
     */
    public static function with($relations)
    {
        return static::query()->with(
            is_string($relations) ? func_get_args() : $relations
        );
    }

    ······

    /**
     * Begin querying the model.
     *
     * @return \Illuminate\Database\Eloquent\Builder
     */
    public static function query()
    {
        return (new static)->newQuery();
    }
```

### 捐助

![支付宝收款码](https://images.gitee.com/uploads/images/2020/1112/091130_811b3a6c_790553.jpeg "alipay-400.jpg")
![微信收款码](https://images.gitee.com/uploads/images/2020/1112/091305_2592a352_790553.jpeg "wechat-400-width(1).jpg")
