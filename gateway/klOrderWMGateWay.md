### klOrderWMGateWay: 康乐外卖业务网关.


#### 业务说明.
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
1. [klOrderAdd](#klOrderAdd)        外卖业务下单.
1. [klOrderPayExt](#klOrderPayExt)  点餐业务单笔多种支付方式(兼容单种).
1. [klOrderCancel](#klOrderCancel)  点餐业务业务订单取消.
1. [klOrderSelect](#klOrderSelect)  点餐业务业务订单查询.

##### menuInventorySelect.
1. /klOrderWMGateWay/menuInventorySelect:     商品库存查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

##### klOrderAdd.
1. /klOrderWMGateWay/klOrderAdd:     

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
| orderId | 订单号 | string | N |  |  |
| orderTime | 订单时间 | datetime | N |  |  |
| allPrice | 订单总额 | double | N |  | 后台校验 |
| name | 姓名 | string | N |  |  |
| telephone | 电话 | string | N |  |  |
| address | 地址 | string | N |  |  |
| memo | 备注 | string | Y |  |  |
| klOrderMenuList | 订单商品明细列表 | list | N |  |  |

##### klOrderPayExt.
1. /klOrderWMGateWay/klOrderPayExt:     

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |


##### klOrderSelect.
1. /klOrderWMGateWay/klOrderSelect:     

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

##### klOrderCancel.
1. /klOrderWMGateWay/klOrderCancel:     

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |