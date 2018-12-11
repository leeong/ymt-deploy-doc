# 微信配置

### 微信公众平台 [链接](https://mp.weixin.qq.com)
1. 基本配置 操作如下
    > 后台->开发->基本配置

    ![获取AppID AppSecret](src/images/wechat-1.png)
    
    注意: 
    1. 添加IP白名单: 添加对应服务器IP
    1. 服务器配置选择兼容模式

    数据汇总
    ```code
        开发者ID(AppID): 
        开发者密码(AppSecret):
        令牌(Token): 
        消息加解密密钥(EncodingAESKey):
    ```

1. 网页授权 操作如下
    > 后台->开发->接口权限->网页服务->网页授权->网页授权获取用户基本信息->点击修改
    
    设置业务域名
    
    ![设置业务域名](src/images/wechat-2.png)
    
    将图中红线的文件下载 放至 `ymtOld/server/public` 目录下
    
    设置最终的效果如图
    
    ![最终效果](src/images/wechat-3.png)

1. 微信推送模板 操作如下
    > 后台->功能->模板消息->我的模板
    
    系统一共6套模板 如图
    
    ![模板](src/images/wechat-4.png)

    添加步骤: 
    1. 点击 `从模板库添加`
    1. 搜索上图中的 `标题`, 这里以 `服务状态提醒` 为例
        
        ![示例](src/images/wechat-5.png)
    
    1. 参考模板
    
        ![示例](src/images/wechat-6-0.png)
        
    1. 参考图片
    
        1. ![示例1](src/images/wechat-6-1.png)
        
        1. ![示例2](src/images/wechat-6-2.png)
        
        1. ![示例3](src/images/wechat-6-3.png)
        
        1. ![示例4](src/images/wechat-6-4.png)
        
        1. ![示例5](src/images/wechat-6-5.png)
        
        1. ![示例6](src/images/wechat-6-6.png)

### 微信商户平台


生成开发者ID(AppID)
生成开发者密码(AppSecret)
配置IP白名单 将部署服务器IP

服务器地址(URL) http://admin.aitenm.com/wechat/server/event
生成TOKEN

微信支付

微信商户平台->产品中心->开发配置->支付配置->公众号支付->添加支付授权目录
添加以下授权
http://api.test.hairongpuhui.com/
http://api.hairongpuhui.com/


微信商户平台->账户中心->账户设置->API安全->API证书->下载证书
微信商户平台->账户中心->账户设置->基本账户信息->微信支付商户号
微信商户平台->账户中心->账户设置->API安全->API秘钥->设置API密钥

1. 设置授权URL路径
2. 下载API证书文件
3. 获取商户号
4. 获取API密钥
