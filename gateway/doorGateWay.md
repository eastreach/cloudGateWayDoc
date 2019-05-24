### [doorGateWay] 网络门锁接口网关。

1. 门锁厂家提供接口调用服务,调用地址和授权信息。
1. 门锁控制方式含密码锁，二维码锁。

### 网关方法。 
1. [setLock](#setLock)   设置门锁开关.
1. [unSetLock](#unSetLock)  取消门锁开关.



### setLock
1. 设置门锁开关，指定时间段可开门，过期作废。
1. 可使用密码或者二维码开门。
1. /doorGateWay/setLock
##### 请求数据
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| hotelId | 酒店ID | string | N |  |  |
| roomId | 房间号 | string |N|  |  |
| starDt | 开始时间 | datetime |N|  |  |
| endDt | 结束时间 | datetime |N|  |  |
| doorId | 门锁号 | string |Y|  |根据具体门锁进行适配  |
| doorPass | 密码 | string |Y|  |短信密码锁使用  |
| barCode | 二维码 | string |Y|  |二维码使用  |
| cardId | 门锁卡卡号 | string |Y|  |  |

### unSetLock
1. 取消门锁开关。
1. /doorGateWay/unSetLock
##### 请求数据.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| hotelId | 酒店ID | string | N |  |  |
| roomId | 房间号 | string |N|  |  |
| starDt | 开始时间 | datetime |Y|  |  |
| endDt | 结束时间 | datetime |Y|  |  |
| doorId | 门锁号 | string |Y|  |根据具体门锁进行适配  |
| doorPass | 密码 | string |Y|  |短信密码锁使用  |
| barCode | 二维码 | string |Y|  |二维码使用  |
| cardId | 门锁卡卡号 | string |Y|  |  |












