## API接口调用.

### 调用规范
1. 传输方式:HTTP, 序列化方式:JSON, 字符编码:UTF-8.
1.

### 主体组织结构.
1. 商户(groupId): 标识一个对接商户.
1. 门店(hotelId): 标识商户的一个门店,可以有多个门店.
1. 康乐站点(hotelId+client): 标识商户的一个经营站点, 一个门店可以有多个站点.

### 授权模型
1. 每一个商户(groupId)申请一个appId.
1. 对appId进行网关级或方法级授权.

### 网关分类.
1. 公共网关: 分店,康乐站点相关元数据接口.
1. 会员网关: 会员相关网关接口.
1. 客房网关: 客房相关元数据接口(静态数据).
1. 康乐网关: 康乐相关元数据接口(静态数据).
1. 客房订单网关: 客房订单相关动态数据接口(动态数据).
1. 康乐订单网关: 康乐订单相关动态数据接口(动态数据).
1. 其他网关: 定制网关接口.

### 客房接口业务说明.
1. 客房网关以OTA为准
1. 房型(hotelId+roomTypeCode): 标识分店的一个房型.
1. 房价产品(hotelId+roomTypeCode+roomPriceCode): 标识分店的一个房价产品.


### 康乐接口业务说明.
1. 康乐网关以PMS为准.
1. 康乐营业时段.
1. 康乐订单类别:标识业务流程,固定编码.
1. 康乐商品种类.
1. 康乐商品明细.
1. 康乐消费台位.

### API调用.
#### 静态元数据.
1. /commonGateWay/hotelSelectBatch:     查询groupId授权的分店数据.
1. /commonGateWay/clientSelectBatch:    查询groupId授权的站点数据.
-----
1. /kfGateWay/roomTypeSelectBatch:      查询groupId授权的房型数据.
1. /kfGateWay/roomPriceSelectBatch:     查询groupId授权的房价产品数据.
------
1. /klGateWay/timeDurSelectBatch:       查询groupId授权的营业时段数据.
1. /klGateWay/orderTypeSelectBatch:     查询groupId授权的订单类别(业务流程)数据.
1. /klGateWay/menuKindSelectBatch:      查询groupId授权的商品种类数据.
1. /klGateWay/menuDetailSelectBatch:    查询groupId授权的商品明细数据.
1. /klGateWay/postSelectBatch:          查询groupId授权的台位数据.

#### 会员业务流程.
1. /memberGateWay/CouponTypeSelectBatch:    卡券数据查询.
1. /memberGateWay/memberBind:               会员绑定.
1. /memberGateWay/memberUnBind:             取消绑定.
1. /memberGateWay/memberSelect:             会员信息查询.
1. /memberGateWay/memberAdd:                新增会员.
1. /memberGateWay/memberUpdate:             修改会员.
1. /memberGateWay/memberBalanceSelect:      消费明细查询.
1. /memberGateWay/memberJfBalanceSelect:    积分明细查询.
1. /memberGateWay/memberCouponSelect:       卡券查询.
1. /memberGateWay/activitySelectBatch:      会员活动查询.
1. /memberGateWay/activitySelect:           活动详情查询.
1. /memberGateWay/memberActivity:           参加会员活动.
1. /memberGateWay/memberActivityLogSelect:  活动日志查询.

#### 客房业务流程.
1. /kfOrderGateWay/roomTypeInventorySelectBatch:  查询groupId可定房数据.
1. /kfOrderGateWay/kfOrderAdd:          客房下单.
1. /kfOrderGateWay/kfOrderPay:          客房订单支付,单笔支付.
1. /kfOrderGateWay/kfOrderPayExt:       客房订单支付,多笔支付.
1. /kfOrderGateWay/kfOrderSelect:       客房订单状态查询.
1. /kfOrderGateWay/kfOrderCancel:       客房订单C端取消.

#### 康乐业务流程
##### 康乐扫码点餐业务流程.
1. /klOrderDCGateWay/menuInventorySelect:     商品库存查询.
1. /klOrderDCGateWay/klOrderAdd:              康乐扫码点餐业务下单.
1. /klOrderDCGateWay/klOrderPay:              康乐订单支付.
1. /klOrderDCGateWay/klOrderPayExt:           康乐订单多笔支付.
1. /klOrderDCGateWay/klOrderSelect:           康乐订单查询.
1. /klOrderDCGateWay/klOrderCancel:           康乐订单取消.

##### 康乐外卖业务流程.
1. /klOrderWMGateWay/menuInventorySelect:     商品库存查询.
1. /klOrderWMGateWay/klOrderAdd:              康乐扫码点餐业务下单.
1. /klOrderWMGateWay/klOrderPay:              康乐订单支付.
1. /klOrderWMGateWay/klOrderPayExt:           康乐订单多笔支付.
1. /klOrderWMGateWay/klOrderSelect:           康乐订单查询.
1. /klOrderWMGateWay/klOrderCancel:           康乐订单取消.

##### 康乐会场预约业务流程.
1. /klOrderYYGateWay/postInventorySelect:     商品库存查询.
1. /klOrderYYGateWay/klOrderAdd:              康乐扫码点餐业务下单.
1. /klOrderYYGateWay/klOrderSelect:           康乐订单查询.
1. /klOrderYYGateWay/klOrderCancel:           康乐订单取消.




