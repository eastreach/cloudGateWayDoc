### 瑞通CRS网关接口。

#### 简介
1. 基于瑞通PMS系统,提供网关接口服务.
1. 云端+本地部署模式.

#### 调用规范
1. 调用机制: 同步调用+异步通知.
1. 序列化方式: JSON.
1. 字符编码: UTF-8.
1. 时间格式: yyyy-MM-dd HH:mm:ss(特例单独指出).
1. 调用地址: ${api_domain}/${gateWay}/${action}

### 鉴权模式(appId单选)
1. appId+appSecret: 适用于本地对接模式,一次性授权.
1. appId+sign:  签名，一次性授权.
1. appId+sign+appToken: 签名，临时授权. 

### 公共请求参数

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| appId | 唯一标识号 | string | N |  | 需申请开通 |
| appSecret | 密钥 | string |  |  | 可选鉴权模式 |
| timestamp | 时间戳 | long |  |  | 单位毫秒，时钟校验 |
| appToken | 临时令牌 | string |  |  | 可选鉴权模式 |
| sign | 签名 | string |  |  | md5(appId+appSecret+timestamp) |
| groupId | 集团ID | string | N |  |组织机构代码，单店时=hotelId|
| hotelId | 分店ID | string | N |  |需申请开通，系统唯一标识商家身份|

### 公共响应参数

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| state | 调用状态 | string | N |  | success/fail |
| code | 错误码 | int |  |  |  |
| msg | 错误说明 | string |  |  |||


##### 技术支持
- 北京昆仑瑞祺科技发展有限公司
- 010-62357019转119