# [小丑路人·社区](https://bbs.cnpscy.com)

> {info} 待编写

- [gitee仓库·Laravel版](https://gitee.com/clown-passerby-community/community)

### 软件架构
* 编程语言：`PHP7.4+`
* 后端框架： `Laravel8`
* 前端Vue框架：`vue-element-admin`
* Nodejs  v14.*

### 安装教程
* 命令行：`composer install`
    - composer install –ignore-platform-reqs 就相当于设置了忽略版本匹配
* 命令行：`cp .env.example .env`
* 命令行，生成 APP_KEY：`php artisan key:generate`
* 命令行，JWT的key：`php artisan jwt:secret`
* 同步导入数据表：`php artisan sync:database:tables`
* 定时任务：
    - 自动按月分表：`php artisan command:autotablebuild`
    - 或者使用任务调度：`php artisan schedule:run`
        - 后置进程：
          `* * * * * www php artisan schedule:run >> /dev/null 2>&1`
- 队列[后置进程]：`php artisan queue:work database --daemon --queue=default`
    - 默认 `php artisan queue:work database --queue=default`
- 一键生成模型、控制器、验证器与服务层
    - php artisan make:modular 名称 模块

### 部署优化
* 配置信息缓存 artisan config:cache
* 路由缓存 artisan route:cache
* 类映射加载优化 artisan optimize
* 自动加载优化 composer dumpautoload

#### 使用说明

1.  按月、按年分表的模型，皆不可使用 `with`，可使用 `load` 代替,`static::query` 会重新 实例化当前模型，之前设置的分表名称将被替换。

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

2.为模型生成注释
```
    php artisan ide-helper:models
```

3.生成 PHPstorm Meta file
```
    php artisan ide-helper:meta
```

4.为 Facades 生产注释
```
    php artisan ide-helper:generate
```
