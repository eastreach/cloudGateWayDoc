### klOrderYYGateWay: 康乐场地预约业务网关.

#### 业务说明.
1. 根据场地的容量大小限制预约人数。
1. 预约时段根据营业时段自定义设置。

#### 康乐业务流程选项(CRS后台设置并进行校验).
1. payFlag:     支付方式(预付，现付).
1. confirmFlag: 订单确认方式(自动确认，手工确认)。
1. checkFlag:  订单审核导入线下系统方式(自动审核，手工审核).
1. cancelFlag: 订单取消方式(不可取消，限时取消，手工取消).
1. levelLimit: 预约人身份校验(散客，实体会员，指定会员星级)。

#### 业务流程action.
1. [postInventorySelect](#postInventorySelect)  场地可用库存查询.
1. [klOrderAdd](#klOrderAdd)  场地预约业务下单.
1. [klOrderCancel](#klOrderCancel)  场地预约业务订单取消.
1. [klOrderSelect](#klOrderSelect)  场地预约业务订单查询.

##### postInventorySelect
1. /klOrderYYGateWay/postInventorySelect

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
##### klOrderAdd
1. /klOrderYYGateWay/klOrderAdd

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
| orderId | 订单号 | string | N |  |  |
| orderTime | 订单时间 | datetime | N |  |  |
| name | 姓名 | string | N |  |  |
| telephone | 电话 | string | N |  |  |
| memberId | 会员ID | string | Y |  | 会员星级限定 |
| memo | 备注 | string | Y |  |  |
| klOrderPostList | 位置明细列表 | list | N |  |  |
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
##### klOrderCancel
1. /klOrderYYGateWay/klOrderCancel:           康乐订单取消.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单号 | string | N |  |  |
##### klOrderSelect
1. /klOrderYYGateWay/klOrderSelect:           康乐订单查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单号 | string | N |  |  |