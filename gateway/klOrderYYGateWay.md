### klOrderYYGateWay
1. 会场预约业务流程.
1. 无商品和支付相关业务。
1. 控制每个场地每个时段的预约人数。
1. 预约时间限制，取消时间限制。
1. 预约会员等级限制。


#### action.

##### 康乐会场预约业务流程.
1. /klOrderYYGateWay/postInventorySelect:     商品库存查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
| startDt | 开始日期 | date | N |  | 含当天 |
| endDt | 结束日期 | date | N |  | 不含当天 |
| crsPostCode | 位置编号 | string | Y |  | 可选过滤 |
```
{
  "service": "klOrderYYGateWay",
  "action": "postInventorySelect",
  "crsHotelId": "bjklrqdjd",
  "crsClientCode": "21",
  "crsPostCode": "202",
  "startDt": "2019-04-20",
  "endDt": "2019-04-21"
}
```
```
{
  "state": "success",
  "code": 0,
  "msg": "操作成功",
  "postList": [
    {
      "state": 1,
      "crsFlag": 0,
      "crsHotelId": "bjklrqdjd",
      "crsClientCode": "21",
      "crsPostCode": "202",
      "crsPostName": "玛瑙",
      "hotelId": "bjklrqdjd",
      "clientCode": "21",
      "postCode": "202"
    }
  ],
  "postDetailList": [
    {
      "state": 1,
      "crsHotelId": "bjklrqdjd",            //分店编号
      "crsClientCode": "21",                //站点编号
      "crsPostCode": "202",                 //位置编号
      "crsPostName": "玛瑙",
      "hotelDt": "2019-04-20 00:00:00",     //酒店日期
      "times": "1",                         //时段代码
      "bdt": "2019-04-20 08:00:00",         //开始时间
      "edt": "2019-04-20 12:00:00",         //结束时间
      "total": 8,                           //总量
      "available": 8,                       //可用数量
      "memo": ""
    },
    {
      "state": 1,
      "crsHotelId": "bjklrqdjd",
      "crsClientCode": "21",
      "crsPostCode": "202",
      "crsPostName": "玛瑙",
      "hotelDt": "2019-04-20 00:00:00",
      "times": "2",
      "bdt": "2019-04-20 14:00:00",
      "edt": "2019-04-20 18:00:00",
      "total": 8,
      "available": 8,
      "memo": ""
    }
  ]
}
```
1. /klOrderYYGateWay/klOrderAdd:              康乐下单.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
| orderId | 订单号 | string | N |  |  |
| orderTime | 订单时间 | datetime | N |  |  |
| name | 姓名 | string | N |  |  |
| telephone | 电话 | string | N |  |  |
| klOrderPostList | 位置想象 | list | N |  |  |
| memo | 备注 | string | Y |  |  |
```
{
  "service": "klOrderYYGateWay",
  "action": "klOrderAdd",
  "crsHotelId": "bjklrqdjd",
  "crsClientCode": "21",
  "orderId": "201904200938044",
  "orderTime": "2019-04-20 09:38:44",
  "name": "程",
  "telephone": "13701010101",
  "klOrderPostList": [
    {
      "crsHotelId": "bjklrqdjd",
      "crsClientCode": "21",
      "crsPostCode": "202",                   //位置编号
      "hotelDt": "2019-04-20 00:00:00",       //日期
      "times": "1",                           //时段
      "bdt": "2019-04-20 08:00:00",
      "edt": "2019-04-20 12:00:00",
      "orderCount": 1                         //数量
    }
  ]
}
```
1. /klOrderYYGateWay/klOrderSelect:           康乐订单查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单号 | string | N |  |  |
1. /klOrderYYGateWay/klOrderCancel:           康乐订单取消.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单号 | string | N |  |  |