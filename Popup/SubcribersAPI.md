# Subscriber API

## 1.Get Insights Subscribers

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/subscribers

##### parameters

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
<th>nếu không bắn lên hoặc rỗng thì lấy today</th>
<th>Xem Bên Dưới</th>
</tr>
<tr>
<th>?postType</th>
<th>string</th>
<th>(popup | smartbar)</th>
<th>Dạng post type</th>
</tr>
<tr>
<th>shopName</th>
<th>string</th>
<th>Tên Shop</th>
<th>Bắn Tên Shopify Đã Đăng Ký Lên</th>
</tr>
</table>
Tham Số của filter

param | type | description
--- | --- | ---
thisWeek | string | số subscribers của popup trong tuần này
thisMonth | string | số subscribers của popup trong tháng này
lastWeek | string | số subscribers của popup tuần trước
lastMonth | string | số subscribers của popup Tháng Trước
today | string | số subscribers của popup trong ngày
yesterday | string | số subscribers của popup ngày hôm qua
custom | string | Xem Bảng Dưới

Tham Số của customer (formatDate (Y-m-d))

param | type | description
--- | --- | ---
from | string |ngày bắt đầu trong khoảng tìm kiếm
to | string |ngày kết thúc trong khoảng tìm kiếm

````ts
export interface Subscribers {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}

export interface Data {
    /** type phân biệt với các api khác */
    type: 'subscriber'
    /** summary là tổng số lượng subscribers dựa theo filter*/
    summary: number
    /** messege là tin nhắn trả lại trên sever*/
    timeline: Timeline[]
}

export interface Timeline {
    /** summary là số lượng subscribers dựa theo filter (ví dụ là tổng số subscribers cuả 1 tháng trong filter 4 tháng trước)*/
    summary: number
    /** from là ngày đầu tiên của filter. Tra lai timestamp*/
    from: srting
    /** to là ngày cuối của filter. Tra lai timestamp*/
    to: srting
}
````

## 2.Get Subscribers

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/subscribers

##### parameters

param | Type | Data Default |Description
--- | --- | --- | -----|
?limit | number | 0 | Giới Hạn Bao Nhiêu email 1 Trang
?page | number | 1 | số Trang
shopName | string | Tên Shop |Bắn Tên Shopify Đã Đăng Ký Lên

````ts
export interface Data {
    items: Items[];
    /** maxPages là số paged*/
    maxPages: number
}
export interface Items {
    /** email là tên email*/
    email: string;
    /** createdDate là ngày tạo,Trả về dạng timestarm*/
    createdDate: string
    /** campaign là tên chiến dịch*/
    campaign: string
}
export interface Subcribers {
    data: Data
    /** messege là tin nhắn code trả lại*/
    message: string
    /** status trang thái code sau khi xử lý API*/
    status: 'error' | 'success'
}
````
## 3.Get Subscribers With Popup

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/subscribers/:id

##### parameters

param | Type | Data Default |Description
--- | --- | --- | -----|
?limit | number | 0 | Giới Hạn Bao Nhiêu email 1 Trang
?page | number | 1 | số Trang
shopName | string | Tên Shop |Bắn Tên Shopify Đã Đăng Ký Lên


````ts
export interface Data {
    items: Items[];
    /** maxPages là số paged*/
    maxPages: number
}
export interface Items {
    /** email là tên email*/
    email: string;
    /** createdDate là ngày tạo,Trả về dạng timestarm*/
    createdDate: string
    /** campaign là tên chiến dịch*/
    campaign: string
}
export interface Subcribers {
    data: Data
    /** messege là tin nhắn code trả lại*/
    message: string
    /** status trang thái code sau khi xử lý API*/
    status: 'error' | 'success'
}
````
## 4.Create Subscriber

### Method:POST

### API endpoint:

https://website.com/wp-json/myshopkit/v1/subscribers:id

##### parameters

param | Type | Data Default |Description
--- | --- | --- | -----|
email | string | - | email mà khách subscriber
?shopName | string | Tên Shop |Bắn Tên Shopify Đã Đăng Ký Lên


````ts
export interface Subscriber {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái của subscribers sau khi trả về*/
    status: 'success' | 'error'
}

export interface Data {
    /** id là id của subscribers*/
    id: string
}
````
## 5.DELETE Subscriber

### Method:DELETE

### API endpoint:

https://website.com/wp-json/myshopkit/v1/subscribers/:id

##### parameters

param | Type | Data Default |Description
--- | --- | --- | -----|
email | string | - | email mà khách đã subscriber
shopName | string | Tên Shop |Bắn Tên Shopify Đã Đăng Ký Lên


````ts
export interface Subscriber {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái của subscribers sau khi trả về*/
    status: 'success' | 'error'
}

export interface Data {
    /** id là id của subscribers*/
    id: string
}
````
## 6.Export Subscribers

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/subscribers/export

##### parameters

param | Type | Data Default |Description
--- | --- | --- | -----|
?limit | number | 0 | Giới Hạn Bao Nhiêu email 1 Trang
?page | number | 1 | số Trang
?filter | string | custom | nếu k có thì lấy hết
?from | string | - | ngày bắt đầu Lọc (Y-m-d)
?to | sring | - | ngày Kết Thúc Lọc (Y-m-d)
format | string | (d-m-Y) | format lại kiểu thời gian đã tạo subscriber
shopName | string | Tên Shop |Bắn Tên Shopify Đã Đăng Ký Lên


Tham Số của format

param | type | description
--- | --- | ---
Y-M-d | string | dạng 2021-Jun-16
d-M-Y | string | dạng 16-Jun-2021
d-m-y | string | dạng 16-06-2021

````ts

````
