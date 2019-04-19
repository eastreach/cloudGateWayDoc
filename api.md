## API接口调用.

### 调用规范
1. 传输方式:HTTP, 序列化方式:JSON, 字符编码:UTF-8.
1. 时间格式: 无特殊说明为 yyyy-MM-dd HH:mm:ss.
1. 授权验证: 账号+密码+令牌+签名.
1. 调用方式: 微服务,service+action.

### 主体组织结构.
1. 商户(groupId): 标识一个对接商户.
1. 门店(hotelId): 标识商户的一个门店,可以有多个门店.
1. 康乐站点(hotelId+client): 标识商户的一个经营站点, 一个门店可以有多个站点.

### 授权模型
1. 每一个商户(groupId)申请一个appId.
1. 对appId进行网关级或方法级授权.

### 网关分类.
1. [公共网关](gateway/commonGateWay.md): 基础元数据接口.
1. [客房网关](gateway/kfGateWay.md): 客房静态元数据接口.
1. [康乐网关](gateway/klGateWay.md): 康乐静态元数据接口.
----
1. [会员网关](gateway/memberGateWay.md): 会员接口.
----
1. [客房订单网关](gateway/kfOrderGateWay.md): 客房订单业务流程接口.
---
1. [康乐扫码点餐](gateway/klOrderDCGateWay.md): 扫码点餐业务流程.
1. [康乐外卖](gateway/klOrderWMGateWay.md): 外卖业务流程.
1. [场地预约](gateway/klOrderYYGateWay.md): 场地挂号预约流程.









