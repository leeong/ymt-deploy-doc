# 部署文档

### 开发环境
1. Nginx 
1. MySQL 5.7
1. PHP 7.2
1. Redis

### 其它软件
1. nodejs + npm
2. composer

### PHP扩展
1. php-mysql
1. php-redis
1. php-common
1. php-curl 
1. php-cli 
1. php-mcrypt 
1. php-mbstring 
1. php-dom
1. php-gd
1. php-bcmath

### 部署资源包
1. ymtOld.tgz 

    微信端API 及静态资源文件 [部署链接](ymtold.md)
1. ymtO.tgz 

    后台管理 [部署链接](ymt.md)

### 外部资源支持
1. 有米兔官方授权TOKEN
1. 阿里云短信 并申请验证短信模板 
   ```shell
   # 短信参考
   模板名称：短信验证码模板
   模板内容：您的验证码是$(code)，该验证码将在15分钟后失效。--轻创业·有米兔
   申请说明：用于用户注册、修改资料、短信验证码验证
   ```
    
1. 微信公众平台(需认证)
1. 微信支付
1. 微信推送模板
1. 