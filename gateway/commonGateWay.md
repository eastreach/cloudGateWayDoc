1. [hotelSelectBatch](#hotelSelectBatch)  appId主体下的分店信息.
1. [clientSelectBatch](#clientSelectBatch)  appId主体下的康乐站点信息.
1. [updateAppInfo](#updateAppInfo)  app收权信息同步.


##### hotelSelectBatch
1. /commonGateWay/hotelSelectBatch:     查询groupId授权的分店数据.

- 请求参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| groupId | 集团ID | string | Y |  | 平台级接入使用 |

- 响应参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| data | 分店数据 | list | N |  | 分店对象列表 |

##### clientSelectBatch
1. /commonGateWay/clientSelectBatch:    查询groupId授权的站点数据.

- 请求参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| groupId | 集团ID | string | Y |  | 平台级接入使用 |
| crsHotelId | 渠道分店ID | string | Y |  | 可选过滤 |
| crsClientCode | 渠道站点ID | string | Y |  | 可选过滤 |

- 响应参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| data | 渠道站点数据 | list | N |  |  |

##### updateAppInfo
1. /commonGateWay/updateAppInfo:    app收权信息同步.

- 请求参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| groupId | 集团ID | string | Y |  | 平台级接入使用 |
| endDt | 授权到期时间 | datetime | Y |  | yyyy-MM-dd HH:mm:ss |

- 响应参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| state | 状态 | string | N |  | success/fail |