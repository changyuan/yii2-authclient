Yii Authclient for Weibo,QQ,Wechat

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
