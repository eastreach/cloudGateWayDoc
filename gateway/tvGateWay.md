### [tvGateWay]智能电视网关接口

1. [guestInfoSelect](#guestInfoSelect)   单房间宾客信息查询.
1. [billInfoSelect](#billInfoSelect)  单房间账务信息查询.
-----------------


### guestInfoSelect
1. /tvGateWay/guestInfoSelect
##### 请求数据
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| hotelId | 酒店ID | string | N |  |  |
| roomId | 房间号 | string |N|  |  |
##### 响应数据.
 ```json
{
  "state": "success",
  "data": [
    {
      "num": 16352,
      "roomId": "8601",
      "name": "刘备",
      "sex": "1",
      "race": "HA",
      "idName": "11",
      "inTime": "2018-04-10 09:49:44",
      "outTime": "2018-04-11 17:00:00",
      "ifVip": "N",
      "operator": "001",
      "ifLeave": "N",
      "guestKind": "1",
      "countNum": 9822,
      "preNo": 0,
      "NewPrice": 288,
      "surName": "",
      "firstName": "",
      "nation": "CHN",
      "totalArrivals": 0,
      "totalRoomNights": 0,
      "totalNoShows": 0,
      "totalCancel": 0,
      "totalRevenue": 0,
      "arAccount": 1,
      "status": "N",
      "ifKeep": "N",
      "ifBorrow": "N"
    }
  ]
}
 ```

### billInfoSelect
1. /tvGateWay/billInfoSelect
##### 请求数据.
| 字段名称 | 字段描述 | 类型 | 允许为空 | 长度 | 说明 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| hotelId | 酒店ID | string | N |  |  |
| roomId | 房间号 | string |N|  |  |

##### 响应数据.
 ```json
{
  "state": "success",
  "roomInfo": {
    "hotelName": "北京昆仑瑞祺科技发展有限公司",
    "inTime": "2018-04-10 09:49:44",
    "outTime": "2018-04-11 17:00:00",
    "stayTime": 594698,
    "stayTimeStr": "9分",
    "roomId": "8601",
    "outBalance": 112,
    "inBalance": 600,
    "balance": 488
  },
  "billInfo": [
    {
      "memo": "青岛啤酒*1.0*6.0",
      "name": "青岛啤酒*1.0*6.0",
      "dt": "2018-04-10 09:59:20",
      "mountin": "0",
      "mountout": "6.0",
      "mountsum": 6,
      "flag": "1"
    },
    {
      "memo": "雪津啤酒*1.0*6.0",
      "name": "雪津啤酒*1.0*6.0",
      "dt": "2018-04-10 09:59:20",
      "mountin": "0",
      "mountout": "6.0",
      "mountsum": 6,
      "flag": "1"
    },
    {
      "name": "会 议 费",
      "memo": "",
      "dt": "2018-04-10 09:58:47",
      "mountin": 0,
      "mountout": "100.0",
      "mountsum": 100,
      "flag": "1"
    },
    {
      "name": "预 收 款",
      "memo": "8601",
      "dt": "2018-04-10 09:49:44",
      "mountin": 600,
      "mountout": "600.0",
      "mountsum": 600,
      "flag": "-1"
    }
  ]
}
 ```












