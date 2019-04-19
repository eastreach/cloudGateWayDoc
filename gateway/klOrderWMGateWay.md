### klOrderWMGateWay
1. 康乐外卖网关.


#### action.
1. 

##### 康乐外卖业务流程.
1. /klOrderWMGateWay/menuInventorySelect:     商品库存查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
1. /klOrderWMGateWay/klOrderAdd:              康乐扫码点餐业务下单.
1. /klOrderWMGateWay/klOrderPay:              康乐订单支付.
1. /klOrderWMGateWay/klOrderPayExt:           康乐订单多笔支付.
1. /klOrderWMGateWay/klOrderSelect:           康乐订单查询.
1. /klOrderWMGateWay/klOrderCancel:           康乐订单取消.