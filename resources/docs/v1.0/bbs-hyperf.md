# [小丑路人·社区·Hyperf版](https://bbs.cnpscy.com)

- [语言版本](#section-语言版本)
- [作者`小丑路人`](#section-作者`小丑路人`)
- [小丑路人社区](#section-小丑路人社区)
- [在线预览](#section-在线预览)
- [软件架构](#section-软件架构)
- [安装教程](#section-安装教程)
- [使用说明](#section-使用说明)

<a name="section-语言版本"></a>
### 语言版本

> {success} [gitee仓库·Hyperf版](https://gitee.com/clown-passerby-community/hyperf-community)

<p align="center">
    <img src="https://gitee.com/clown-passerby-community/hyperf-community/badge/star.svg?theme=dark" />
    <img src="https://gitee.com/clown-passerby-community/hyperf-community/badge/fork.svg?theme=dark" />
    <img src="https://svg.hamm.cn/badge.svg?key=License&value=Apache-2.0&color=da4a00" />
</p>

---

> {info} [gitee仓库·Laravel版](https://gitee.com/clown-passerby-community/community)

<p align="center">
    <img src="https://gitee.com/clown-passerby-community/community/badge/star.svg?theme=dark" />
    <img src="https://gitee.com/clown-passerby-community/community/badge/fork.svg?theme=dark" />
    <img src="https://svg.hamm.cn/badge.svg?key=License&value=Apache-2.0&color=da4a00" />
</p>

<a name="section-作者`小丑路人`"></a>
### 作者`小丑路人`
[小丑路人](https://www.cnpscy.com)

<a name="section-小丑路人社区"></a>
### 小丑路人社区
[小丑路人社区](https://bbs.cnpscy.com)

<a name="section-在线预览"></a>
### [在线预览](https://bbs.cnpscy.com)
- 小丑路人社区 `https://bbs.cnpscy.com`
![首页](/bbs/pc.png)

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
