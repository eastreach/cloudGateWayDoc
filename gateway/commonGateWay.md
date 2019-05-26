### commonGateWay: 公共网关。
1. 基础元数据的同步.

#### action。
1. [hotelSelectBatch](#hotelSelectBatch)  appId主体下的分店信息.
1. [clientSelectBatch](#clientSelectBatch)  appId主体下的康乐站点信息.


##### hotelSelectBatch
1. /commonGateWay/hotelSelectBatch:     查询groupId授权的分店数据.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | Y |  | 可选过滤 |

##### clientSelectBatch
1. /commonGateWay/clientSelectBatch:    查询groupId授权的站点数据.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| crsHotelId | 渠道酒店ID | string | Y |  | 可选过滤 |
| crsClientCode | 渠道站点编号 | string | Y |  | 可选过滤 |