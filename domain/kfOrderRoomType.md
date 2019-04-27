#### klOrderRoomType
1. orderId+detailId: 唯一标识符.
```
//crs信息
private Integer crsFlag = 0;            //crs渠道
private String orderId;            //CRS订单号
private Date orderTime;                 //订单时间
private String detailId;           //明细ID , roomPriceCode
private String crsHotelId;          //crs酒店ID
private String crsRoomTypeCode;    //crs房型代码
private String crsRoomTypeName;    //crs房型名称
private String crsRoomPriceCode;   //crs房价代码
private String crsRoomPriceName;   //crs房价代码名称

//pms信息
private String hotelId;
private String roomTypeCode;    //房型代码
private String roomTypeName;    //房型名称
private String roomPriceCode;   //房价代码
private String roomPriceName;    //房价代码名称
private Integer roomTypeCount;      //同等房的数量
private Double price;           //单价
private Date checkInTime;           //入住时间
private Date checkOutTime;          //拟离时间
private Date arriveTime;            //最晚到达时间
private Double allPrice;        //该明细总价格，（退宿时间－入住时间）＊数量＊ 单价

```