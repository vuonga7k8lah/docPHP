# Clicks API

## 1.Get Popup

###Method:GET

###API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/clicks

#####parameters
<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>?filter</th>
<th>string</th>
<th>nếu không bắn lên hoặc rỗng thì lấy thisDay</th>
<th>Xem Bên Dưới</th>
</tr>
<tr>
<th>shopName</th>
<th>string</th>
<th>Tên Shop</th>
<th>Bắn Tên Shopify Đã Đăng Ký Lên</th>
</tr>
<tr>
<th>accessToken</th>
<th>string</th>
<th></th>
<th>Mã Token Do Shopify Cấp</th>
</tr>
<tr>
<th>postID</th>
<th>string</th>
<th></th>
<th>là id của popup</th>
</tr>
</table>
Tham Số của filter

param | type | description
--- | --- | ---
thisDay | string |số clicks của popup trong hôm nay
thisWeek | string | số clicks của popup trong tuần này
thisMonth | string | số clicks của popup trong tháng này
yesterday | string | số clicks của popup trong ngày hôm qua
last7DaysInWeek | string | số clicks của popup trong ngày hôm qua
last7DaysInMonth | string | số clicks của popup trong ngày hôm qua
customerDays | string | Xem Bảng Dưới

Tham Số của customerDays

param | type | description
--- | --- | ---
beginDays | string |ngày bắt đầu trong khoảng tìm kiếm 
endDays | string |ngày kết thúc trong khoảng tìm kiếm 



````ts
export interface Popup {
    /** data là số lượng clicks*/
    data: number
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}
````
## 2.Create Popup

###Method:POST

###API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/clicks

#####parameters
<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>shopName</th>
<th>string</th>
<th>Tên Shop</th>
<th>Bắn Tên Shopify Đã Đăng Ký Lên</th>
</tr>
<tr>
<th>accessToken</th>
<th>string</th>
<th></th>
<th>Mã Token Do Shopify Cấp</th>
</tr>
<tr>
<th>postID</th>
<th>string</th>
<th></th>
<th>là id của popup</th>
</tr>
</table>

````ts
export interface Popup {
    /** clickID là id của clicks*/
    clickID: number
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}
````
## 3.Update Popup

###Method:PUT

###API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/clicks

#####parameters
<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>shopName</th>
<th>string</th>
<th>Tên Shop</th>
<th>Bắn Tên Shopify Đã Đăng Ký Lên</th>
</tr>
<tr>
<th>accessToken</th>
<th>string</th>
<th></th>
<th>Mã Token Do Shopify Cấp</th>
</tr>
<tr>
<th>postID</th>
<th>string</th>
<th></th>
<th>là id của popup</th>
</tr>
</table>

````ts
export interface Popup {
    /** clickID là id của clicks*/
    clickID: number
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}
````
## 4.Delete Popup

###Method:DELETE

###API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/clicks

#####parameters
<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>shopName</th>
<th>string</th>
<th>Tên Shop</th>
<th>Bắn Tên Shopify Đã Đăng Ký Lên</th>
</tr>
<tr>
<th>accessToken</th>
<th>string</th>
<th></th>
<th>Mã Token Do Shopify Cấp</th>
</tr>
<tr>
<th>postID</th>
<th>string</th>
<th></th>
<th>là id của popup</th>
</tr>
</table>

````ts
export interface Popup {
    /** clickID là id của clicks*/
    clickID: number
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}
````