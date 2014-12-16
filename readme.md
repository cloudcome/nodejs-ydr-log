# ydr-log
## usage
### smtp
```
var log = require('ydr-util');

// 初始化邮件服务器
log.initSmtp({
    port : '465',
    ssl : true,
    host : 'smtp.qq.com',
    password : 'smtp_password',
    user : 'smtp_username'
});
```


### email
```
// 初始化邮件发送
log.initEmail({
    from: '服务器错误',
    to: '',
    subject: '服务器错误'
});
```


### log
```
// 记录日志，尽量放在路由的最后
app.use(log({
    // 运行环境，默认为开发
    env: 'pro',
    // 存放路径
    path: null,
    // YYYY年MM月DD日 HH:mm:ss.SSS 星期e a
    name: './YYYY/MM/YYYY-MM-DD'
}));
```


### holdError
```
// error handle
// log.holdError;
// 一个空函数，通常用于不需要处理的回调，但需要日志记录
model.findOne({}, log.holdError);
```