### 对象模型
#### Hotel: 分店.
1. crsHotelId: 唯一标识符.
```
//接口使用编号
private Integer state = 0;              //状态,1开,其他关.
private String groupId;                 //集团号
private Integer crsFlag = 0;            //渠道代码
private String crsHotelId = "";         //渠道分店号
private String crsHotelName = "";       //渠道分店名称
//pms内部使用编号
private String hotelId = "";            //pms酒店id
private String hotelName = "";          //pms酒店名称
//其他属性
private String address;                 //地址
private String telephone;               //电话
private String province;                //省份
private String city;                    //城市
private String district;
private String business;
private String memo;                    //备注
```
#### Client: 康乐站点
1. crsHotelId+crsClientCode: 唯一标识号
```
//接口使用编号
private Integer state = 0;                  //状态:1开,其他关.
private String groupId = "";                //集团号
private Integer crsFlag = 0;                //渠道号
private String crsHotelId = "";             //渠道分店ID
private String crsHotelName = "";           
private String crsClientCode = "";          //渠道站点编号 
private String crsClientName = "";
//pms使用编号
private String hotelId = "";                //pms酒店ID
private String hotelName = "";
private String clientCode = "";             //pms站点编号
private String clientName = "";
//其他属性
private String memo = "";
private Integer sortId = 0;    
```
#### MenuKind: 商品种类.
1. crsHotelId+crsClientCode+crsMenuKindCode: 唯一标识号.
```
//接口使用编号
private Integer state = 0;              //状态
private Integer crsFlag = 0;            //渠道号
private String crsHotelId = "";         //渠道分店号
private String crsHotelName = "";
private String crsClientCode = "";      //渠道站点号
private String crsClientName = "";
private String crsMenuKindCode = "";    //渠道商品种类编号
private String crsMenuKindName = "";    //渠道商品种类名称
private Integer sortId = 0;
```
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
#### Post: 消费位置，包间.
1. crsHotelId+crsClientCode+crsPostCode: 唯一标识符
```
//接口使用编号
private Integer state;              //状态          
private Integer crsFlag;            //
private String crsHotelId;
private String crsClientCode;
private String crsPostCode;         //位置编号
private String crsPostName;         //位置名称
//pms内部使用编号
private String hotelId;
private String clientCode;
private String postCode;
```

#### KLOrder: 康乐主单信息。
1. orderId: 唯一标识符.
```
//接口使用编号
private Integer crsFlag = 0;         //渠道类型
private String crsHotelId = "";      //渠道酒店ID
private String crsClientCode = "";   //渠道站点代码
private String orderId = "";         //渠道订单号
//pms使用编号
private String hotelId = "";         //酒店ID
//其他属性
private Date orderTime;              //订单时间
private String orderState = "";      //订单状态, 固定编号
private Double allPrice = 0.0;       //订单总金额
private String ifPay = "N";          //是否有支付
private Double payPrice = 0.0;       //实际支付金额
private String name = "";            //姓名
private String telephone = "";       //电话
private String memo = "";            //备注
private Integer checkFlag = 0;       //审核状态, 1已经审核， 0 未审核

```

#### KLOrderMenu: 康乐订单商品明细
1. 
```
//接口使用编号
private Integer crsFlag;
private String crsHotelId;              //分店编号
private String crsClientCode;           //站点编号
private String crsSpendCode;            //商品编号
private String crsSpendName;            //商品名称
private Double menuCount;               //订单商品数量
private Double crsPrice;                //订单商品单价
private String memo;                    //备注
```
#### KLOrderPay: 康乐订订单支付明细
```
//接口使用编号
private Integer crsFlag = 0;            
private String orderId;                 
private Date orderTime;                 
private String payId;               //渠道支付ID               
private Date payTime;               //渠道支付时间
private String payKind;             //渠道支付方式,固定编码
private Double payPrice;            //渠道实际支付金额
private String memo;
private String couponId = "";       //卡券ID,或者储值卡号
```