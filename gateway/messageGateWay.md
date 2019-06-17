### [messageGateWay]消息通知网关

1. [sendPms](#sendPms)  向PMS系统推送消息.
-----------------


#### sendPms
1. /messageGateWay/sendPms
##### 请求数据.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| hotelId | 渠道酒店ID | string | N |  |  |
| uuid | 消息ID | string | N |  |  |
| resDt | 消息时间 | datetime | N |  |  |
| topic | 消息主题 | string | N |  |  |
| memo | 消息内容 | string | N |  |  |

##### 响应数据.
```json
{
  "state": "success",
  "code": 0,
  "msg": "操作成功"
}
```











