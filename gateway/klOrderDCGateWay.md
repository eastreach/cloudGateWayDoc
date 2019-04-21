### klOrderDCGateWay: 康乐点餐业务网关.

#### 业务说明.
1. 扫码或选台确定消费位置。
1. 选择菜品进行业务下单。
1. 根据业务流程选择进行支付确认。

#### 康乐业务流程选项(CRS后台设置并进行校验).
1. payFlag:     支付方式(预付，现付).
1. confirmFlag: 订单确认方式(自动确认，手工确认)。
1. checkFlag:  订单审核导入线下系统方式(自动审核，手工审核).
1. cancelFlag: 订单取消方式(不可取消，限时取消，手工取消).
1. levelLimit: 预约人身份校验(散客，实体会员，指定会员星级)。
1. payKindLimit: 支付方式限定(现金,储值卡，优惠券)。

#### 业务流程action.
1. [menuInventorySelect](#menuInventorySelect)  菜品信息查询.
1. [klOrderAdd](#klOrderAdd)  点餐业务下单.
1. [klOrderPayExt](#klOrderPayExt)  点餐业务单笔多种支付方式(兼容单种).
1. [klOrderPay](#klOrderPay)  点餐业务单支付方式.
1. [klOrderCancel](#klOrderCancel)  点餐业务业务订单取消.
1. [klOrderSelect](#klOrderSelect)  点餐业务业务订单查询.

##### menuInventorySelect
1. /klOrderDCGateWay/menuInventorySelect:     商品库存查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
```
{
  "service": "klOrderDCGateWay",
  "action": "menuInventorySelect",
  "crsHotelId": "bjklrqdjd",
  "crsClientCode": "21"
}
```
```
{
  "state": "success",
  "code": 0,
  "msg": "操作成功",
  "menuKindList": [                   //商品种类list.
    {
      "state": 1,
      "crsFlag": 1,
      "crsHotelId": "bjklrqdjd",
      "crsHotelName": "",
      "crsClientCode": "21",
      "crsClientName": "",
      "crsMenuKindCode": "01",
      "crsMenuKindName": "热菜",
      "sortId": 1
    },
    {
      "state": 1,
      "crsFlag": 1,
      "crsHotelId": "bjklrqdjd",
      "crsHotelName": "",
      "crsClientCode": "21",
      "crsClientName": "",
      "crsMenuKindCode": "02",
      "crsMenuKindName": "凉菜",
      "sortId": 2
    }
  ],
  "menuDetailList": [             //商品明细list,
    {
      "state": 1,
      "crsFlag": 0,
      "crsHotelId": "bjklrqdjd",    //分店编号
      "crsHotelName": "",
      "crsClientCode": "21",        //站点编号
      "crsClientName": "",
      "crsMenuKindCode": "01",      //种类编号
      "crsMenuKindName": "",
      "crsSpendCode": "0102",       //菜品编号
      "crsSpendName": "扇饼夹糟肉",
      "menuPrice": 5,               //单价
      "sortId": 0
    }
  ]
}
```
##### klOrderAdd
1. /klOrderDCGateWay/klOrderAdd:              康乐扫码点餐业务下单.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
| crsPostCode | 台位代码 | string | N |  |  |
| orderId | 订单号 | string | N |  |  |
| orderTime | 订单时间 | datetime | N |  |  |
| allPrice | 订单总额 | double | N |  | 后台校验 |
| name | 姓名 | string | N |  |  |
| telephone | 电话 | string | N |  |  |
| memo | 备注 | string | Y |  |  |
| klOrderMenuList | 订单商品明细列表 | list | N |  |  |
```
{
  "service": "klOrderDCGateWay",
  "action": "klOrderAdd",
  "crsHotelId": "bjklrqdjd",
  "crsClientCode": "21",
  "crsPostCode": "202",
  "orderId": "201904210925010",
  "orderTime": "2019-04-21 09:25:10",
  "allPrice": "5.0",
  "name": "程",
  "telephone": "13701010101",
  "klOrderMenuList": [
    {
      "crsHotelId": "bjklrqdjd",
      "crsClientCode": "21",
      "crsSpendCode": "0102",
      "menuCount": 1
    }
  ]
}
```
```
{
  "state": "success",
  "code": 0,
  "msg": "操作成功",
  "data": {
    "crsFlag": 1,
    "crsHotelId": "bjklrqdjd",
    "crsClientCode": "",
    "orderId": "201904210925010",
    "hotelId": "bjklrqdjd",
    "orderTime": "2019-04-21 09:25:10",
    "orderState": "CRSCommit",              //订单状态
    "allPrice": 5.0,
    "ifPay": "N",
    "payPrice": 0.0,
    "name": "程",
    "telephone": "",
    "memo": "",
    "checkFlag": -1
  }
}
```
##### klOrderPayExt
1. /klOrderDCGateWay/klOrderPayExt:           康乐订单多笔支付.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单号 | string | N |  |  |
| klOrderPayList | 订单支付明细 | list | N |  |  |
```
{
  "service": "klOrderDCGateWay",
  "action": "klOrderPayExt",
  "groupId": "bjklrqdjd",
  "crsHotelId": "bjklrqdjd",
  "crsClientCode": "21",
  "orderId": "201904211214046",
  "klOrderPayList": [
    {
      "payId": "c8771ab16cd74f0d9eee2d9cb6cbf31e",      //支付ID
      "payTime": "2019-04-21 12:18:08",                 //支付时间
      "payKind": "1",                       //付款方式，固定编码
      "payPrice": 5,                        //支付金额
      "couponId": ""                        //卡ID或者券ID
    }
  ]
}
```
##### klOrderPay
1. /klOrderDCGateWay/klOrderPay:              康乐订单支付.
##### klOrderSelect
1. /klOrderDCGateWay/klOrderSelect:           康乐订单查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单号 | string | N |  |  |
##### klOrderCancel
1. /klOrderDCGateWay/klOrderCancel:           康乐订单取消.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单号 | string | N |  |  |