#### klOrder
1. orderId: 唯一标识符.
```
//接口使用编号
private Integer crsFlag = 0;         //渠道类型
private String crsHotelId = "";      //渠道酒店ID
private String crsClientCode = "";   //渠道站点代码
private String orderId = "";         //*渠道订单号
//pms使用编号
private String hotelId = "";         //酒店ID
//其他属性
private Date orderTime;              //*订单时间
private String orderState = "";      //订单状态, 固定编号
private Double allPrice = 0.0;       //*订单总金额
private String ifPay = "N";          //是否有支付
private Double payPrice = 0.0;       //实际支付金额
private String name = "";            //*姓名
private String telephone = "";       //*电话
private String memberId = "";       //*会员ID
private String memo = "";            //备注
private Integer checkFlag = 0;       //审核状态, 1已经审核， 0 未审核

```