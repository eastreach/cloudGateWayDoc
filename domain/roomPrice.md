#### roomPrice
1. crsHotelId+crsRoomTypeCode+crsRoomPriceCode: 唯一标识符
```
private Integer state = 0;
private Integer crsFlag = 0;
private String crsHotelId = "";
private String crsHotelName = "";
private String crsRoomTypeCode = "";
private String crsRoomTypeName = "";
private String crsRoomPriceCode = "";
private String crsRoomPriceName = "";
private Double crsRoomPrice;

private String hotelId = "";
private String hotelName = "";
private String roomTypeCode = "";
private String roomTypeName = "";
private String roomPriceCode = "";
private String roomPriceName = "";
private Double roomPrice;

private Integer totalCount;
private Integer availableCount;
private String payType = "";                //支付类型 0 预付， 1 现付
private String levelLimit = "";             //星级限制
private Integer memberState = 1;          //会员房价代码限制, -1置灰, 1可买
```