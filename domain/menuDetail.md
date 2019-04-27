#### MenuDetail: 商品明细.
1. crsHotelId+crsClientCode+crsSpendCode: 唯一标识号.
1. crsMenuKindCode指向对应的商品种类.
```
 //接口使用编号
private Integer state = 0;              //状态
private Integer crsFlag = 0;
private String crsHotelId = "";
private String crsHotelName = "";
private String crsClientCode = "";
private String crsClientName = "";
private String crsMenuKindCode = "";
private String crsMenuKindName = "";
private String crsSpendCode = "";       //渠道商品编号
private String crsSpendName = "";       //商品名称
private Double menuPrice;               //商品单价
private Integer sortId = 0;

```