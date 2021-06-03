# PopupAPI

## 1.Get Popup

###Method:GET

###API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/:id

#####parameters
<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>pluck</th>
<th>string</th>
<th></th>
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
</table>
Tham Số của Pluck

param | type | description
--- | --- | ---
title | string | Tên của popup
date | string | ngày tạo bài
status | string | Trạng Thái Popups
config | string | các config của font-end bắn lên
views | string | views của popup
clicks | string | clicks của popup
subscribers | string | subscribers của popup
rate | string | rate của popup


````ts
export interface Popup {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    messege: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id : string
    /** title Là tiêu đề của popup*/
    title : string
    /** date Là thời gian tạo của popup*/
    date : string
    /** config là các setting popup của font-end*/
    config: datafontEnd
    /** status Là trạng thái của popup*/
    status : (enable | disable)
    /** views Là số lượt xem của popup*/
    views: string,
    /** clicks là số lượt clicks của popup*/
    clicks: string,
    /** subscribers là số lượt gmail được gửi của popup*/
    subscribers: string
    /** rate Là đánh giá của popup*/
    rate:string
    /** goal là chiến dịch của popup*/
    goal:string
}
````

## 2.Get one Popup one param

###Method:GET

###API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/:id/:param


#####parameters
<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>param</th>
<th>string</th>
<th></th>
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
<th>Mã token do shopify cấp</th>
</tr>
</table>
Tham Số của Pluck

param | type | description
--- | --- | ---
title | string | Tên của popup
date | string | ngày tạo bài
status | string | Trạng Thái Popups
config | string | các config của font-end bắn lên
views | string | views của popup
clicks | string | clicks của popup
subscribers | string | subscribers của popup
rate | string | rate của popup


````ts
export interface Popup {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    messege: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id : string
    /** title Là tiêu đề của popup*/
    title : string
    /** date Là thời gian tạo của popup*/
    date : string
    /** config là các setting popup của font-end*/
    config: datafontEnd
    /** status Là trạng thái của popup*/
    status : (enable | disable)
    /** views Là số lượt xem của popup*/
    views: string,
    /** clicks là số lượt clicks của popup*/
    clicks: string,
    /** subscribers là số lượt gmail được gửi của popup*/
    subscribers: string
    /** rate Là đánh giá của popup*/
    rate:string
    /** goal là chiến dịch của popup*/
    goal:string
}
````
## 3.Create Popup
###API endpoint:
https://website.com/wp-json/myshopkit/v1/popups
###Request
#####parameters

<table>
<tr>
<th>Form-Data</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>config</th>
<th>string</th>
<th></th>
<th>Config Popup Do Font-End Bắn Lên</th>
</tr>
<tr>
<th>title</th>
<th>string</th>
<th>Random</th>
<th>Title Của Popup</th>
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
</table>

````ts
export interface Popup {
    /** id là id của popup vừa tạo*/
    id: string  
    /** messege là tin nhắn trả lại trên sever*/
    messege: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````
## 4.Get All Popups
###API endpoint:
https://website.com/wp-json/myshopkit/v1/popups
###Request
#####parameters

<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
<tr>
<th>param</th>
<th>string</th>
<th></th>
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
<th>Mã token do shopify cấp</th>
</tr>
<tr>
<th>?search</th>
<th>string</th>
<th></th>
<th>Tìm Kiếm</th>
</tr>
<tr>
<th>?limted</th>
<th>string</th>
<th></th>
<th>Giới Hạn Bao Nhiêu Popups 1 Trang</th>
</tr>
</table>
Tham Số của Pluck

param | type | description
--- | --- | ---
title | string | Tên của popup
date | string | ngày tạo bài
status | string | Trạng Thái Popups
config | string | các config của font-end bắn lên
views | string | views của popup
clicks | string | clicks của popup
subscribers | string | subscribers của popup
rate | string | rate của popup

````ts

interface Data {
    items: Items[];
    /** maxPages là số paged*/
    maxPages: number 
}


export interface Popup {
    data: Data
    /** messege là tin nhắn code trả lại*/
    messege: string
    /** status trang thái code sau khi xử lý API*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id : string
    /** title Là tiêu đề của popup*/
    title : string
    /** date Là thời gian tạo của popup*/
    date : string
    /** config là các setting popup của font-end*/
    config: datafontEnd
    /** status Là trạng thái của popup*/
    status : (enable | disable)
    /** views Là số lượt xem của popup*/
    views: string,
    /** clicks là số lượt clicks của popup*/
    clicks: string,
    /** subscribers là số lượt gmail được gửi của popup*/
    subscribers: string
    /** rate Là đánh giá của popup*/
    rate:string
    /** goal là chiến dịch của popup*/
    goal:string
}
````
## 5.Update,Patch Popup

###API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/:id
#####parameters
<table>
<tr>
<th>x-wwww-form-urlencoded</th>
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
<th>Mã token do shopify cấp</th>
</tr>
<tr>
<th>?title</th>
<th>string</th>
<th>Random</th>
<th>title của popup</th>
</tr>
<tr>
<th>?status</th>
<th>(enable||disable)</th>
<th>enable</th>
<th>trạng thái của popup</th>
</tr>
<tr>
<th>?config</th>
<th>string</th>
<th>-</th>
<th>config popup do font-end bắn lên</th>
</tr>
</table>


````ts
export interface Popup {
    /** id là id của popup vừa tạo*/
    id: string
    /** messege là tin nhắn trả lại trên sever*/
    messege: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````
## 6.Delete Popup:

###API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/id

#####parameters
<table>
<tr>
<th>Form-Data</th>
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
<th>Mã token do shopify cấp</th>
</tr>
</table>

````ts
export interface Popup {
    /** id là id của popup vừa tạo*/
    id: string
    /** messege là tin nhắn trả lại trên sever*/
    messege: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````

#1: Đổi Tên ID thành id 

#2: Đổi kiểu ID thành string

#3: Thay đổi cấu Trúc data trả về

````ts
export interface Popup {
    /** postID la id cua bai post*/
    data:{
        id: string
    }
    /** msg la tin nhan code tra lai*/
    msg: string
    /** status la trang thai cua api sau xu ly*/
    status: 'error' | 'success'
}
````
#4 Đổi Msg thành Message 

#5 Thêm api get 1 param vd popups/:id/configs

#6 Xem Lại Token 

#7 sửa lại mô tả api post,put (params thành body)