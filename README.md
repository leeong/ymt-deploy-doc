# 有米兔部署文档 v0.3

### 约定
1. 文中所有的域名 `domain.com` 替换为客户域名, eg: `baidu.com`, `sina.cn`

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
1. 有米兔官方提供的解密扩展(php_screw_plus.so)

### 数据库配置
```sql
  set global sql_mode= 'STRICT_TRANS_TABLES,NO_ENGINE_SUBSTITUTION';
```

### 部署资源包
1. ymtOld.zip 

    微信端API 及静态资源文件 [部署链接](ymtold.md)
1. ymt.zip 

    后台管理 [部署链接](ymt.md)

### 外部资源支持

1. 服务器
1. 域名备案及解析
1. 有米兔官方授权TOKEN
1. 百度统计
1. 阿里云短信
1. 微信公众平台(需认证)
1. 微信支付
1. 微信推送模板
