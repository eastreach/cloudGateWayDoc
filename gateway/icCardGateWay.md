#### 储值卡网关服务.
1. [cardSelect](#cardSelect)        储值卡信息查询.
1. [cardPay](#cardPay)              储值卡消费.
1. [cardPayQuery](#cardPayQuery)    储值卡消费订单状态查询.
1. [cardPayCancel](#cardPayCancel)  储值卡消费订单取消.

--------------
##### cardSelect
1. /icCardGateWay/cardSelect:     储值卡信息查询.

- 请求参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| cardNum | 卡序列号 | string | N |  | 卡序号译码规则 |

- 响应参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| icCardNumber | 卡信息 | object | N |  |  |
| hgxdw | 会员信息 | object |  |  |  ||


---------------
##### cardPay
1. /icCardGateWay/cardPay:     储值卡消费.

- 请求参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| cardNum | 卡序列号 | string | N |  | 卡序号译码规则 |
| orderId | 订单唯一流水号 | string | N |  | 全局唯一 |
| mount | 消费金额 | double | N |  | >0 |
| dt | 消费时间 | datetime | N |  |  |
| posId | 消费点 | string |  |  |  |
| memo | 备注 | string |  |  |  ||

- 响应参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| icCardNumber | 卡信息 | object | N |  |  |
| hgxdw | 会员信息 | object |  |  |  ||

-----------------
##### cardPayQuery
1. /icCardGateWay/cardPayQuery:     储值卡消费订单状态查询.

- 请求参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| orderId | 订单唯一流水号 | string | N |  |||


- 响应参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| icCardNumber | 卡信息 | object | N |  |  |
| hgxdw | 会员信息 | object | Y |  |  |
| hgxdwDetail | 会员信息 | object |  |  |  ||

-------------------
##### cardPayCancel
1. /icCardGateWay/cardPayCancel:     储值卡消费订单取消,只能全额取消.

- 请求参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| cardNum | 卡序列号 | string | N |  | 卡序号译码规则 |
| orderId | 订单唯一流水号 | string | N |  |  |
| mount | 消费金额 | double | N |  | >0 |


- 响应参数.

| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| icCardNumber | 卡信息 | object | N |  |  |
| hgxdw | 会员信息 | object |  |  |  |
| hgxdwDetail | 会员信息 | object |  |  |  |


### icCardNumber 卡信息
```
private String cardNum = "";                  //物理卡号
private String cardCode;                    //逻辑卡号
private Integer status = 0;                   //卡状态 ic_zd_card_status,  1有效，2无效，3冻结，4挂失，5结清
private String psw;                         //卡密码
private Date createDt;

```

### hgxdw 会员信息
```
private String name;
private String memo;
private String cardId = "";           //会员卡号
private String cardPass = "";           //卡密码
private Double balance = 0.0;         //余额, 负数表示
private Double jfBalance = 0.0;       //积分
private String mobile = "";
private Date birthday;
private String sex;
```