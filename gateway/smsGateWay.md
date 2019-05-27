### [smsGateWay]短信网关

1. [balanceQuery](#balanceQuery)  余额查询.
1. [smsSend](#smsSend)   发送短信.
1. [smsSendTemplate](#smsSendTemplate)  发送短信模版.
-----------------


#### balanceQuery
1. /smsGateWay/balanceQuery
##### 请求数据.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| hotelId | 酒店ID | string | Y |  |  |

##### 响应数据.
```json
{
  "state": "success",
  "code": 0,
  "msg": "操作成功",
  "balance": 10227
}
```

#### smsSend
1. /smsGateWay/smsSend

##### 请求数据.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | Y |  |  |
| telephone | 电话号码 | string |Y|  |  |
| content | 短信内容 | string |Y|  |  |
```json
{
  "groupId": "bjklrqdjd",
  "crsHotelId": "bjklrqdjd",
  "telephone": "13701010101",
  "content": "尊敬的客户您好"
}
```
##### 响应数据
```json
{
  "state": "success",
  "code": 0,
  "msg": "操作成功"
}
```











