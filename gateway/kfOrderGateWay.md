#### kfOrderGateWay.
1. 客房订单网关.


### 客房接口业务说明.
1. 客房网关以OTA为准
1. 房型(hotelId+roomTypeCode): 标识分店的一个房型.
1. 房价产品(hotelId+roomTypeCode+roomPriceCode): 标识分店的一个房价产品.


#### 客房业务流程.
1. /kfOrderGateWay/roomTypeInventorySelectBatch:  查询groupId可定房数据.
1. /kfOrderGateWay/kfOrderAdd:          客房下单.
1. /kfOrderGateWay/kfOrderPay:          客房订单支付,单笔支付.
1. /kfOrderGateWay/kfOrderPayExt:       客房订单支付,多笔支付.
1. /kfOrderGateWay/kfOrderSelect:       客房订单状态查询.
1. /kfOrderGateWay/kfOrderCancel:       客房订单C端取消.