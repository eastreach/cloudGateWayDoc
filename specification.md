### 规范说明.

#### 授权模型
1. 授权应用(appId): 标识唯一授权应用,CRS分配.
1. 授权级别: 数据隔离级别.
    1. 平台级授权: 针对第三方平台的统一接入.
    1. 集团级授权: 针对集团连锁的商户第三方应用的接入.
    1. 分店级授权: 针对单体商户的第三方应用的接入(默认)
1. 安全验证: 
    1. 调用方式: HTTP+HTTPS.
    1. 权限验证: 账号+密码+令牌+签名.(默认appId+appSecret)
1. 授权网关:
    1. CRS对每个appId进行网关级调用限制.
    1. 默认开放所有已注册网关.

#### 调用规范
1. 调用机制: 同步调用+异步通知.
    1. sync: request+response.
    1. async: request+notifyUrl+notifyResponse.
1. 序列化方式: JSON.
1. 字符编码: UTF-8.
1. 时间格式: yyyy-MM-dd HH:mm:ss.
1. 调用地址: /${gateWay}/${action}
1. 响应内容:
    1. state: 调用状态(success/fail).
    1. code: 错误状态码.
    1. msg: 错误说明.

#### 备注说明
1. 不匹配规范的网关方法单独进行备注说明.










