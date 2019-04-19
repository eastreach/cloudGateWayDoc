### klOrderDCGateWay.
1. 扫码点餐网关

#### action.
1. menuInventorySelect: 菜品信息查询.
1. klOrderAdd:      下单.
1. klOrderPay:      支付.
1. klOrderPayExt:   多笔支付.
1. klOrderSelect: 订单查询。
1. klOrderCancel: 取消订单.


##### 康乐扫码点餐业务流程.
1. /klOrderDCGateWay/menuInventorySelect:     商品库存查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

1. /klOrderDCGateWay/klOrderAdd:              康乐扫码点餐业务下单.
1. /klOrderDCGateWay/klOrderPay:              康乐订单支付.
1. /klOrderDCGateWay/klOrderPayExt:           康乐订单多笔支付.
1. /klOrderDCGateWay/klOrderSelect:           康乐订单查询.
1. /klOrderDCGateWay/klOrderCancel:           康乐订单取消.