#### roomPrice
1. crsHotelId+crsRoomTypeCode+crsRoomPriceCode＋hotelDt: 唯一标识符
```
private Integer state = 0;      //状态
private Date hotelDt;           //酒店日期

private Integer crsFlag;        //渠道标识
private String crsHotelId;
private String crsRoomTypeCode;
private String crsRoomPriceCode;
private Double crsRoomPrice;


private String hotelId;         //分店ID
private String roomTypeCode;    //房型代码
private String roomPriceCode;   //房价代码
private Double roomPrice;           //酒店价格

private Integer availableCount;  //可用库存
```