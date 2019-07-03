### memberGateWay
1. 会员网关.

#### action。
1. [memberBind](#memberBind)                            会员绑定.
1. [memberUnBind](#memberUnBind)                        取消绑定.
1. [memberSelect](#memberSelect)                        会员信息查询.
1. [memberAdd](#memberAdd)                              新增会员.
1. [memberUpdate](#memberUpdate)                        修改会员.
1. [memberBalanceSelect](#memberBalanceSelect)          消费明细查询.
1. [memberJfBalanceSelect](#memberJfBalanceSelect)      积分明细查询.
1. [memberCouponSelect](#memberCouponSelect)            会员已领卡券查询.
1. [memberCouponTrans](#memberCouponTrans)              会员已领卡券转赠.
1. [activitySelectBatch](#activitySelectBatch)          会员活动查询.
1. [activitySelect](#activitySelect)                    活动详情查询.
1. [memberActivity](#memberActivity)                    参加会员活动.
1. [memberActivityLogSelect](#memberActivityLogSelect)  活动日志查询.
----------
1. [couponTypeSelectBatch](#couponTypeSelectBatch)      可领券查询.
1. [couponTypePut](#couponTypePut)                      领券.

##### couponTypeSelectBatch
1. /memberGateWay/couponTypeSelectBatch:    可领券信息查询.
###### 请求参数.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| memberId | 渠道会员ID | string | N |  |  |
```
{
  "state": "success",
  "code": 0,
  "msg": "操作成功",
  "total": 2,             //卡券总数量
  "rows": [
    {
      "id": 3,
      "state": 1,
      "createDt": "2018-07-16 10:53:38",
      "groupId": "bjklrqdjd",
      "hotelId": "bjklrqdjd",
      "code": "DJQ20",
      "name": "20元代金券",       //卡券名称
      "memo": "",
      "couponKind": "DJQ",
      "couponValue": 20,
      "validDays": 5,
      "bValue": 100,
      "eValue": 1000,
      "onLineState": 0,
      "total": 100,
      "lpd": 1,
      "memberState": 1,         //当前会员是否可领 1可领,非1不可领
      "todayTotal": 100,          //当天总数量
      "todayAvailable": 100,      //当前剩余可领数量
      "memberCount": 0          //当前会员已领数量
    },
    {
      "id": 2,
      "state": 1,
      "createDt": "2018-07-16 10:53:38",
      "groupId": "bjklrqdjd",
      "hotelId": "bjklrqdjd",
      "code": "DJQ100",
      "name": "100元代金券",
      "memo": "",
      "couponKind": "DJQ",
      "couponValue": 100,
      "validDays": 3,
      "bValue": 200,
      "eValue": 1000,
      "onLineState": 0,
      "total": 100,
      "lpd": 1,
      "memberState": 1,
      "todayTotal": 0,
      "todayAvailable": 0,
      "memberCount": 0
    }
  ]
}
```

##### couponTypePut
1. /memberGateWay/couponTypePut:    领券.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| memberId | 渠道会员ID | string | N |  |  |
| hotelId | 分店ID | string | N |  |  |
| code | 卡券代码 | string | N |  |  |

##### memberBind
1. /memberGateWay/memberBind:               会员绑定.

##### memberUnBind
1. /memberGateWay/memberUnBind:             取消绑定.

##### memberSelect
1. /memberGateWay/memberSelect:             会员信息查询.
###### 请求参数.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| memberId | 渠道会员ID | string | N |  |  |

##### memberAdd
1. /memberGateWay/memberAdd:                新增会员.
###### 请求参数.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| memberId | 会员ID | string | N |  |  |
| name | 姓名 | string |Y|  |  |
| telephone | 电话 | string |Y|  |  |
| birthday | 出生日期 | date |Y|  |  |
| sex | 性别 | integer |Y|  | 1男,2女,3未知 |
| memo | 备注 | string |Y|  |  |

##### memberUpdate
1. /memberGateWay/memberUpdate:             修改会员.

##### memberBalanceSelect
1. /memberGateWay/memberBalanceSelect:      消费明细查询.

##### memberJfBalanceSelect
1. /memberGateWay/memberJfBalanceSelect:    积分明细查询.

##### memberCouponSelect
1. /memberGateWay/memberCouponSelect:       卡券查询.
```
{
  "state": "success",
  "code": 0,
  "msg": "操作成功",
  "total": 5,             //总数据,分页使用
  "rows": [
    {
      "id": 130,
      "state": 1,
      "activityId": "",
      "couponType": 0,
      "onLineState": 0,    //线上状态， 1线上可用，其他线上不可用
      "couponId": "d3605d11d2ea4009bc4425a2ec4e55bf",     //券ID,唯一流水号,二维码
      "confirmId": "d3605d11d2ea4009bc4425a2ec4e55bf",
      "couponCode": "DJQ20",                            //券代码,客户添加
      "couponKind": "DJQ",                              //券种类,固定编码,程序校验.
      "couponName": "20元代金券",         //券名称
      "couponValue": 20,                //面值
      "bDt": "2019-07-01 16:44:39",     //有效期始
      "eDt": "2019-07-06 16:44:39",     //有效期止
      "totalCount": 1,
      "validCount": 1,                  //有效数量,大部分为一券一销, 支持一券多销.
      "telephone": "13716182307",     //电话, 卡券所有权归属.
      "crsFlag": 1,
      "memberId": "13716182307",
      "groupId": "bjklrqdjd",
      "hotelId": "bjklrqdjd",
      "cardId": "3716182307",
      "createDt": "2019-07-01 16:44:39",
      "mountIn": 0,
      "mountOut": 0,
      "value": 0
    }
  ]
}
```

##### memberCouponTrans
1. /memberGateWay/memberCouponTrans:       卡券转赠.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| couponId | 分店ID | string | N |  |  |
| memberId | 发券渠道会员ID | string | N |  |  |
| toMemberId | 收券渠道会员ID | string | N |  |  |

##### activitySelectBatch
1. /memberGateWay/activitySelectBatch:      会员活动查询.

##### activitySelect
1. /memberGateWay/activitySelect:           活动详情查询.

##### memberActivity
1. /memberGateWay/memberActivity:           参加会员活动.

##### memberActivityLogSelect
1. /memberGateWay/memberActivityLogSelect:  活动日志查询.