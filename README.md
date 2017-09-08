# Yii Authclient for Weibo,QQ,Wechat and etc.
[![Latest Stable Version](https://poser.pugx.org/yiisoft/yii2-authclient/v/stable.png)](https://packagist.org/packages/yiisoft/yii2-authclient)
[![Total Downloads](https://poser.pugx.org/yiisoft/yii2-authclient/downloads.png)](https://packagist.org/packages/yiisoft/yii2-authclient)
[![Build Status](https://travis-ci.org/yiisoft/yii2-authclient.svg?branch=master)](https://travis-ci.org/yiisoft/yii2-authclient)

## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
composer require --prefer-dist changyuan/yii2-authclient
```

or add

```json
"changyuan/yii2-authclient": "~2.1.0"
```

to the `require` section of your composer.json.

## Usage
```
'components' => [
    'authClientCollection' => [
        'class' => 'yii\authclient\Collection',
        'clients' => [
            'weibo' => [
                'class' => 'changyuan\authclient\clients\Weibo',
                'clientId' => 'wb_key',
                'clientSecret' => 'wb_secret',
            ],
            'qq' => [
                'class' => 'changyuan\authclient\clients\QQ',
                'clientId' => 'qq_appid',
                'clientSecret' => 'qq_appkey',
            ],
            'wechat' => [
                'class' => 'changyuan\authclient\clients\Wechat',
                'clientId' => 'weixin_appid',
                'clientSecret' => 'weixin_appkey',
            ],
            'wechatmp' => [
                'class' => 'changyuan\authclient\clients\Wechat',
                'type' => 'mp',
                'clientId' => 'weixin_appid',
                'clientSecret' => 'weixin_appkey',
            ],
        ],
    ]
    // other components
]
```
## in view
```
 //The first way in view：
 <?= yii\authclient\widgets\AuthChoice::widget([
    'baseAuthUrl' => ['site/auth']
 ]); ?>
 
 //The second way in view:
  <?php
  use yii\authclient\widgets\AuthChoice;
  ?>
  <?php $authAuthChoice = AuthChoice::begin([
      'baseAuthUrl' => ['site/auth']
  ]); ?>
  <ul>
  <?php foreach ($authAuthChoice->getClients() as $client): ?>
      <li><?= $authAuthChoice->clientLink($client) ?></li>
  <?php endforeach; ?>
  </ul>
  <?php AuthChoice::end(); ?>
```


[参考](https://github.com/yiisoft/yii2-authclient/blob/master/docs/guide/quick-start.md)


## Q&A

 Q: this error "Invalid auth state parameter." ?

 A: remove sub class `$this->removeState('authState');`  


