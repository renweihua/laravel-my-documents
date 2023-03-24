# [小丑路人·社区·Hyperf版](https://bbs.cnpscy.com)

> {success} [gitee仓库·Hyperf版](https://gitee.com/clown-passerby-community/hyperf-community)

---

> {info} [gitee仓库·Laravel版](https://gitee.com/clown-passerby-community/community)


- [软件架构](#section-软件架构)
- [安装教程](#section-安装教程)
- [使用说明](#section-使用说明)

<a name="section-软件架构"></a>
### 软件架构
- Swoole >= 4.6.x 并关闭 `Short Name`
- PHP >= 8.0 并开启以下扩展：
  - mbstring
  - json
  - pdo
  - openssl
  - redis
  - pcntl
- Mysql >= 5.7
- Redis >= 4.0

<a name="section-安装教程"></a>
### 安装教程
* `composer install`
* 同步导入数据表：`php bin/hyperf.php sync:database:tables`

<a name="section-使用说明"></a>
### 使用说明

##### 启动服务，且热更新
* 命令行：`php bin/hyperf.php server:watch`
* www角色执行命令：`su -c "php bin/hyperf.php serve:watch" -s /bin/sh www`
* 后置进程：`nohup php 文件 2>&1 &`
* 使用`supervisor`守护进程启动服务即可

##### 数据层
- Admin 数据层级
  - controller
  - ~~service（废弃）~~
  - model
  - ~~注解路由~~
    - 存在一定的限制性，灵活性不足
  - route文件定义路由
- 社区 数据层级
  - controller
  - service
  - repository(可选性)
  - model
  - 注解路由
