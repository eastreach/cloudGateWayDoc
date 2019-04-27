#### roomPrice
1. crsHotelId+crsRoomTypeCode+hotelDt: 唯一标识符
```
private Integer state;
private Date hotelDt;           //酒店日期

private Integer crsFlag = 0;          //接口渠道
private String crsHotelId;
private String crsRoomTypeCode;
private String crsRoomTypeName;
private Integer totalCount = 0;              //总数量
private Integer availableCount = 0;     //有效数量
```