# ymtOld 有米兔微信端部署
    前后端分离

### 目录结构

```shell
+-- cmds                                脚本
+-- server                              API接口 PHP开发的主要目录
+-- web                                 前端资源
```

### 配置Nginx站点

```shell
# 参考配置
server {
    listen 80;

    # $ROOT 替换为项目绝对路径
    root $ROOT/ymtOld/server/public;

    index index.html index.htm index.nginx-debian.html index.php;

    # $HOST 替换为域名
    server_name $HOST;

    location / {
        #try_files $uri $uri/ =404;
        if (!-e $request_filename) {
            rewrite  ^(.*)$  /index.php?s=$1  last;   break;
        }
    }

    # pass PHP scripts to FastCGI server
    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.2-fpm.sock;
    }
    location ~ /\.ht {
        deny all;
    }

    access_log /var/log/nginx/ymtold_access.log;
    error_log /var/log/nginx/ymtold_error.log;
}
``` 

### API部署

1. 依赖加载

    `ymtOld/server$: composer install`
1. 文件夹读写权限
    ```shell
    ymtOld/server$: mkdir runtime public/fans_avatar public/qrcode public/bankquery public/uploads
    ymtOld/server$: sudo chmod -R 755 runtime public/fans_avatar public/qrcode public/uploads
    ```
1. 配置文件

    配置文件目录 `ymtOld/server/application`
    
    其中 `conf_stage.php` 为测试/本地环境配置, `conf_prod.php`为生产环境配置
    
    ```shell
    database: 数据库配置
    redis: redis配置
    runtime: 运行环境配置
        +-- env: 当前环境 RuntimeService::ENV_PRODUCT 正式环境
                         RuntimeService::ENV_DEVELOPMENT 测试环境
        +-- domain: API域名 eg: http://api.youmitu.com
        +-- static_domain: 后台域名 eg: http://admin.youmitu.com
        +-- jwt_key: 生成JWT TOKEN 建议修改
    ```


### 前端部署
