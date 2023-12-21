###  发送邮件

####  安装

```bash 
composer require xiaosongshu/mail
```

####   发送邮件

```php 
/** 发件人 你的邮箱地址 */
$user = 'xxxxxxx@qq.com';
/** 发件人授权码 在QQ邮箱的设置，账户，smtp里面 参考：https://blog.csdn.net/weixin_60387745/article/details/129344957 */
$password = 'xxxxxxxx';
/** 邮箱服务器地址 */
$url = 'smtp.qq.com:25';
try {
    /** 实例化客户端 */
    $client = new \Xiaosongshu\Mail\Client();
    /** 配置服务器地址 ，发件人信息 */
    $client->config($url,$user,$password);
    /** 发送邮件 语法：邮件主题 邮件正文 收件人邮箱 */
    $res = $client->send('测试一下','你知道我是谁吗',['xxxxx@qq.com']);
    print_r("发送邮件成功");
    print_r($res);
}catch (Exception $exception){
    print_r("发送邮件失败");
    print_r($exception->getMessage());
}

```
####  联系作者
2723659854@qq.com