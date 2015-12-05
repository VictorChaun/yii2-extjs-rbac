Yii2 ExtJs5 RBAC
=========
支持ACL+RBAC

> 注: 功能正在开发中...

> 更详细的配置说明文档正在编写中...

> QQ群: 137158108 验证信息: github

> 有任何疑问可以发邮件到 myweishanli@gmail.com

安装
------------

安装这个扩展的首选方式是通过 [composer](http://getcomposer.org/download/).

执行

```
composer require --prefer-dist myweishanli/yii2-extjs-rbac
```
或添加
```
"myweishanli/yii2-extjs-rbac": ">=1.0.0"
```

配置
------------

`@app/config/main.php`
```php
'modules' => [
    'admin' => '\wsl\rbac\modules\admin\Module',
    ...
],
```

```php
'controllerMap' => [
    'site' => '\wsl\rbac\controllers\SiteController',
    ...
],
```

```php
'components' => [
    'user' => [
        'identityClass' => 'wsl\rbac\models\DpAdminUser',
        ...
    ],
    ...
]
```

导入数据
------------
```
yii migrate --migrationPath=@wsl/rbac/migrations
```

完成`配置`和`导入数据`即可访问

超级管理员帐号和密码
------------
```
username: drupecms
password: drupecms
```

控制器
------------
新建的`Controller`需要继承`\wsl\rbac\base\Controller`

```php
class ExampleController extends \wsl\rbac\base\Controller
{
}
```

自定义配置
------------
> 如果需要自定义`ExtJs`的`app.js`路径

```
'controllerMap' => [
    'site' => [
        'class' => '\wsl\rbac\controllers\SiteController',
        'extJs' => [
            'appPath' => '/app.js',
        ],
    ],
    ...
],
```

[预览图](docs/preview.md)

> 注: 每次升级记住执行`yii migrate --migrationPath=@wsl/rbac/migrations`