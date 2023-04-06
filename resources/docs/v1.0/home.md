# [小丑路人·社区·Laravel版](https://bbs.cnpscy.com)

- [源码仓库](#section-源码仓库)
- [作者`小丑路人`](#section-作者`小丑路人`)
- [小丑路人社区](#section-小丑路人社区)
- [在线预览](#section-在线预览)
- [软件架构](#section-软件架构)
- [安装教程](#section-安装教程)
- [部署优化](#section-部署优化)
- [使用说明](#section-使用说明)
- [捐助](#section-捐助)

<a name="section-源码仓库"></a>
### 源码仓库
> {success} [gitee仓库·Laravel版](https://gitee.com/clown-passerby-community/community)

<p align="center">
    <img src="https://gitee.com/clown-passerby-community/community/badge/star.svg?theme=dark" />
    <img src="https://gitee.com/clown-passerby-community/community/badge/fork.svg?theme=dark" />
    <img src="https://svg.hamm.cn/badge.svg?key=License&value=Apache-2.0&color=da4a00" />
</p>

---

> {info} [gitee仓库·Hyperf版](https://gitee.com/clown-passerby-community/hyperf-community)

<p align="center">
    <img src="https://gitee.com/clown-passerby-community/hyperf-community/badge/star.svg?theme=dark" />
    <img src="https://gitee.com/clown-passerby-community/hyperf-community/badge/fork.svg?theme=dark" />
    <img src="https://svg.hamm.cn/badge.svg?key=License&value=Apache-2.0&color=da4a00" />
</p>

<a name="section-作者`小丑路人`"></a>
### 作者`小丑路人`
> https://www.cnpscy.com

<a name="section-小丑路人社区"></a>
### 小丑路人社区
> https://bbs.cnpscy.com

<a name="section-在线预览"></a>
### [在线预览](https://bbs.cnpscy.com)
- 小丑路人社区 `https://bbs.cnpscy.com`
  ![首页](/bbs/pc.png)

<a name="section-软件架构"></a>
### 软件架构
* 编程语言：`PHP7.4+`
* 后端框架： `Laravel8`
* 前端Vue框架：`vue-element-admin`
* Nodejs：`v14.*`

<a name="section-安装教程"></a>
### 安装教程
* 命令行：`composer install`
    * composer install –ignore-platform-reqs 就相当于设置了忽略版本匹配
* 命令行：`cp .env.example .env`
* 命令行，生成 APP_KEY：`php artisan key:generate`
* 命令行，JWT的key：`php artisan jwt:secret`
* 同步导入数据表：`php artisan sync:database:tables`
* 定时任务：
    * 自动按月分表：`php artisan command:autotablebuild`
    * 或者使用任务调度：`php artisan schedule:run`
        * 后置进程：
          `* * * * * www php artisan schedule:run >> /dev/null 2>&1`
* 队列后置进程：`php artisan queue:work database --daemon --queue=default`
    * 默认 `php artisan queue:work database --queue=default`
* 一键生成模型、控制器、验证器与服务层
    * php artisan make:modular 名称 模块

<a name="section-部署优化"></a>
### 部署优化
* 配置信息缓存 php artisan config:cache
* 路由缓存 php artisan route:cache
* 类映射加载优化 php artisan optimize
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
```

* 为模型生成注释
```
    php artisan ide-helper:models
```

* 生成 PHPstorm Meta file
```
    php artisan ide-helper:meta
```

* 为 Facades 生产注释
```
    php artisan ide-helper:generate
```

<a name="section-捐助"></a>
### 捐助

![支付宝收款码](https://bbs-1252866470.cos.ap-shanghai.myqcloud.com/alipay-collection.png "alipay-400.jpg")
![微信收款码](https://bbs-1252866470.cos.ap-shanghai.myqcloud.com/wechat-collection.png "wechat-400-width(1).jpg")
