### klGateWay: 康乐相关静态元数据接口.

#### 接口说明.
1. 康乐业务相关的静态元数据接口。
1. 每个康乐站点区分不同的营业时段。
1. 定义不同的业务流程编码，固定编码。

#### 业务流程编码
 ```
public static final String roomType = "roomType";           //定房型
public static final String roomId = "roomId";               //定房间号

public static final String kldc = "2";                      //餐厅点餐
public static final String klyd = "3";                      //餐厅预订
public static final String klwm = "4";                      //餐厅外卖
public static final String klsc = "5";                      //康乐微商城
public static final String klTicket = "6";                  //康乐微电子票
public static final String kldb = "7";                      //餐厅打包
public static final String klyy = "klyy";                   //康乐站点预约
 ```

#### 接口action.
1. [timeDurSelectBatch](#timeDurSelectBatch)  营业时段元数据.
1. [orderTypeSelectBatch](#orderTypeSelectBatch)  业务流程元数据.
1. [menuKindSelectBatch](#menuKindSelectBatch)  商品种类元数据.
1. [menuDetailSelectBatch](#menuDetailSelectBatch)  商品明细元数据.
1. [postSelectBatch](#postSelectBatch)  消费位置元数据.


##### timeDurSelectBatch
1. /klGateWay/timeDurSelectBatch:       查询groupId授权的营业时段数据.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

##### orderTypeSelectBatch
1. /klGateWay/orderTypeSelectBatch:     查询groupId授权的订单类别(业务流程)数据.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

##### menuKindSelectBatch
1. /klGateWay/menuKindSelectBatch:      查询groupId授权的商品种类数据.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

##### menuDetailSelectBatch
1. /klGateWay/menuDetailSelectBatch:    查询groupId授权的商品明细数据.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

##### menuDetailSelectBatch
1. /klGateWay/postSelectBatch:          查询groupId授权的台位数据.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |

##### postSelectBatch
1. /klGateWay/postSelectBatch:          台位信息查询.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | N |  |  |
| crsClientCode | 渠道站点编号 | string | N |  |  |
