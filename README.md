Bootstrap CMS
=============

Bootstrap CMS was created by, and is maintained by [Graham Campbell](https://github.com/GrahamCampbell), and is a PHP CMS powered by [Laravel 5.1](http://laravel.com) and [Sentry](https://cartalyst.com/manual/sentry). It utilises many of my packages including [Laravel Core](https://github.com/GrahamCampbell/Laravel-Core) and [Laravel Credentials](https://github.com/BootstrapCMS/Credentials). Feel free to check out the [releases](https://github.com/BootstrapCMS/CMS/releases), [license](LICENSE), [screenshots](SCREENSHOTS.md), and [contribution guidelines](CONTRIBUTING.md).

![Bootstrap CMS](https://cloud.githubusercontent.com/assets/2829600/4432327/c1ae6436-468c-11e4-84eb-4e5e546da3ff.PNG)

<p align="center">
<a href="https://travis-ci.org/BootstrapCMS/CMS"><img src="https://img.shields.io/travis/BootstrapCMS/CMS/master.svg?style=flat-square" alt="Build Status"></img></a>
<a href="https://scrutinizer-ci.com/g/BootstrapCMS/CMS/code-structure"><img src="https://img.shields.io/scrutinizer/coverage/g/BootstrapCMS/CMS.svg?style=flat-square" alt="Coverage Status"></img></a>
<a href="https://scrutinizer-ci.com/g/BootstrapCMS/CMS"><img src="https://img.shields.io/scrutinizer/g/BootstrapCMS/CMS.svg?style=flat-square" alt="Quality Score"></img></a>
<a href="LICENSE"><img src="https://img.shields.io/badge/license-AGPL%203.0-brightgreen.svg?style=flat-square" alt="Software License"></img></a>
<a href="https://github.com/BootstrapCMS/CMS/releases"><img src="https://img.shields.io/github/release/BootstrapCMS/CMS.svg?style=flat-square" alt="Latest Version"></img></a>
</p>


## Installation

[PHP](https://php.net) 5.5+ or [HHVM](http://hhvm.com) 3.6+, a database server, and [Composer](https://getcomposer.org) are required.

1. There are 3 ways of grabbing the code:
  * Use GitHub: simply download the zip on the right of the readme
  * Use Git: `git clone git@github.com:BootstrapCMS/CMS.git`
  * Use Composer: `composer create-project graham-campbell/bootstrap-cms --prefer-dist -s dev`
2. From a command line open in the folder, run `composer install --no-dev -o` and then `npm install`.
3. Enter your database details into `config/database.php`.
4. Run `php artisan app:install` followed by `gulp --production` to setup the application.
5. You will need to enter your mail server details into `config/mail.php`.
  * You can disable verification emails in `config/credentials.php`
  * Mail is still required for other functions like password resets and the contact form
  * You must set the contact email in `config/contact.php`
  * I'd recommend [queuing](#setting-up-queing) email sending for greater performance (see below)
6. Finally, setup an [Apache VirtualHost](http://httpd.apache.org/docs/current/vhosts/examples.html) to point to the "public" folder.
  * For development, you can simply run `php artisan serve`


## Setting Up Queuing

Bootstrap CMS uses Laravel's queue system to offload jobs such as sending emails so your users don't have to wait for these activities to complete before their pages load. By default, we're using the "sync" queue driver.

1. Check out Laravel's [documentation](http://laravel.com/docs/master/queues#configuration).
2. Enter your queue server details into `config/queue.php`.


## Setting Up Caching

Bootstrap CMS provides caching functionality, and when enabled, requires a caching server.
Note that caching will not work with Laravel's `file` or `database` cache drivers.

1. Choose your poison - I'd recommend [Redis](http://redis.io).
2. Enter your cache server details into `config/cache.php`.
3. Setting the driver to array will effectively disable caching if you don't want the overhead.


## Setting Up Themes

Bootstrap CMS also ships with 18 themes, 16 from [Bootswatch](http://bootswatch.com).

1. You can set your theme in `config/theme.php`.
2. You can also set your navbar style in `config/theme.php`.
3. After making theme changes, you will have to run `php artisan app:update`.


## Setting Up Google Analytics

Bootstrap CMS natively supports [Google Analytics](http://www.google.com/analytics).

1. Setup a web property on [Google Analytics](http://www.google.com/analytics).
2. Enter your tracking id into `config/analytics.php`.
3. Enable Google Analytics in `config/analytics.php`.


## Setting Up CloudFlare Analytics

Bootstrap CMS can read [CloudFlare](https://www.cloudflare.com/) analytic data through a package.

1. Follow the install instructions for my [Laravel CloudFlare](https://github.com/BootstrapCMS/CloudFlare) package.
2. Bootstrap CMS will auto-detect the package, only allow admin access, and add links to the navigation bar.


## License

GNU AFFERO GENERAL PUBLIC LICENSE

Bootstrap CMS Is A PHP CMS Powered By Laravel 5 And Sentry

Copyright (C) 2013-2015 Graham Campbell

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.




## 中文版

### 1、简介

<font color="red">Bootstrap CMS </font>不是一个网站，而是一个建站CMS，由Graham Campbell维护，基于Laravel5.1和Sentry。Bootstrap CMS将多个Laravel包整合到一起（但不止于此），包括<font color="red">Laravel Core</font>和<font color="red">Laravel Credentials</font>等，从而为我们打造一个由Laravel驱动的功能强大的CMS。

### 2、GitHub

<a href="https://github.com/BootstrapCMS/CMS"><font color="red">https://github.com/BootstrapCMS/CMS</font></a>

### 3、文档
#### 3.1 安装

使用Bootstrap CMS之前要先安装PHP 5.5+或HHVM 3.6+，数据库以及Composer。

1.有三种方式获取Bootstrap CMS代码：

- 使用GitHub：简单下载zip格式文件即可
- 使用Git：<font color="red">git clone git@github.com:BootstrapCMS/CMS.git</font>
- 使用Composer：<font color="red">composer create-project graham-campbell/bootstrap-cms --prefer-dist -s dev</font>

2.在命令行进入项目根目录，运行<font color="red">composer install --no-dev -o</font>然后运行<font color="red">npm install</font>。

3.将本地数据库配置信息填写到配置文件<font color="red">config/database.php</font>。

4.运行<font color="red">php artisan app:install</font>。和<font color="red">gulp --production</font>安装应用。

5.将邮件服务器配置信息填写到配置文件config/mail.php。

- 你可以在配置文件config/credentials.php中禁止邮件认证
- 某些功能如密码重置和联系表单需要邮件功能
- 必须在配置文件config/contact.php中设置联系邮箱地址
- 推荐使用邮件队列发送大量邮件（详见下面设置队列部分）

6.最后，设置Apache/Nginx指向public目录

- 本地开发的话也可以简单运行php artisan serve开启服务器

#### 3.2 设置队列

Bootstrap CMS使用Laravel的队列系统来负载批量任务，比如发送邮件，这种任务需要较长时间完成，使用队列异步执行则用户无需等待页面的长时间加载。默认情况下，我们使用“sync”队列驱动。

- 查看Laravel队列文档
- 在配置文件 config/queue.php中填写你的队列服务器配置信息

#### 3.3 设置缓存

Bootstrap CMS提供了缓存功能，启用缓存需要一个缓存服务器。需要注意的是这里的缓存不支持Laravel的file和database缓存驱动。

- 选择一个缓存系统——我们推荐Redis
- 在配置文件<font color="red">config/cache.php</font>中填写你的缓存服务器信息
- 如果设置缓存驱动为数组的话将会禁止缓存

#### 3.4 设置主题

Bootstrap CMS还提供了18个主题，其中16个来自Bootswatch

- 可以在配置文件 config/theme.php中设置主题
- 还可以在 config/theme.php中设置导航栏样式
- 修改主题后，需要运行 php artisan app:update。

#### 3.5 设置<font color="red">Google Analytics</font>

Bootstrap CMS原生支持 Google Analytics。

- 在 Google Analytics设置web属性
- 在配置文件中 config/analytics.php填写你的跟踪ID
- 在 config/analytics.php中开启 Google Analytics。

#### 3.6 设置<font color="red">CloudFlare</font> Analytics

Bootstrap CMS可以通过一个包读取 CloudFlare统计数据

- 按照 Laravel CloudFlare包安装指南安装该Laravel包
- Bootstrap CMS会自动检测这个包，只允许管理员访问，以及添加链接到导航条



## 报错解决方案 服务器500错误

*production.ERROR: exception 'RuntimeException' with message 'No supported en*

复制文件

	copy .env.example =>.env  

执行命令，生成key 
	
	php artisan key:generate