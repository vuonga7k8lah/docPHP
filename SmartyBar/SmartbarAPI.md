# Smart Bar API

## Get SmartBar

#### Method: GET

#### Endpoint: https://website.com/wp-json/myshopkit/v1/smartbars

## Params

| Param | Type | Description | Default |
| --- | --- | ----| --- |
| limit| int | Số lượng items / trang. Maximum: 30. Quá 30 sử dụng default | 10 |
| page | int | Page hiện tại | 1 |
| status | 'active' / 'deactive' / 'any' | Trường hợp all thì trả về cả smartbars active và deactive| any |
| ?pluck | string | Mỗi pluck cách nhau bởi dấu phẩy. Ví dụ: title, id. Trường hợp không có pluck trả lai hết| undefined|

## Response

### Lỗi

```
export interface Response {
    message: "Message loi"
    code: Number
}
```

### Success

```
export interface Response {
    message: "Message Thanh cong"
    code: 200
    data: {
        items: [] // Items có thể rỗng nếu không có items nào.
        maxPages: Number
    }
}
```

## Get Smart Bar

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/smartbars/:id

##### parameters

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
</table>
Tham Số của Pluck

param | type | description
--- | --- | ---
title | string | Tên của smartbar
date | string | ngày tạo bài
status | string | Trạng Thái smartbar: active/deactive
config | string | các config của font-end bắn lên
views | string | views của smartbar
clicks | string | clicks của smartbar
subscribers | string | subscribers của smartbar
conversion | string | conversion của smartbar
goal | string | goal của smartbar
showToPage | string | showToPage của smartbar

````ts
export interface Smartbar {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id: string
    /** title Là tiêu đề của smartbar*/
    title: string
    /** date Là thời gian tạo của smartbar*/
    date: string
    /** config là các setting smartbar của font-end*/
    config: datafontEnd
    /** status Là trạng thái của smartbar*/
    status: (enable | disable)
    /** views Là số lượt xem của smartbar*/
    views: number,
    /** clicks là số lượt clicks của smartbar*/
    clicks: number,
    /** subscribers là số lượt gmail được gửi của smartbar*/
    subscribers: number
    /** conversion Là đánh giá của smartbar*/
    conversion: number
    /** goal là chiến dịch của smartbar*/
    goal: string
    items: []
    /** các trang hiển thi smartbar*/
    showToPage: string[] | []
}
````

## Get a specified smartbar info

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/smartbars/:id/:param

##### parameters

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
<th>param</th>
<th>string</th>
<th></th>
<th>Xem Bên Dưới</th>
</tr>
</table>
Tham Số của Pluck

param | type | description
--- | --- | ---
title | string | Tên của smartbar
date | string | ngày tạo bài
status | string | Trạng Thái Popup active/deactive
config | string | các config của font-end bắn lên
views | string | views của smartbar
clicks | string | clicks của smartbar
subscribers | string | subscribers của smartbar
conversion | string | conversion của smartbar
goal | string | goal của smartbar
showToPage | string | showToPage của smartbar

````ts
export interface Smartbar {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id: string
    /** title Là tiêu đề của smartbar*/
    title: string
    /** date Là thời gian tạo của smartbar*/
    date: string
    /** config là các setting smartbar của font-end*/
    config: datafontEnd
    /** status Là trạng thái của smartbar*/
    status: (enable | disable)
    /** views Là số lượt xem của smartbar*/
    views: number,
    /** clicks là số lượt clicks của smartbar*/
    clicks: number,
    /** subscribers là số lượt gmail được gửi của smartbar*/
    subscribers: number
    /** conversion Là đánh giá của smartbar*/
    conversion: number
    /** goal là chiến dịch của smartbar*/
    goal: string
    items: []
    /** các trang hiển thi smartbar*/
    showToPage: string[] | []
}
````

## 3.Create Smartbar

### API endpoint:

https://website.com/wp-json/myshopkit/v1/smartbars

##### parameters

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
<th>config</th>
<th>json</th>
<th></th>
<th>Config smartbar Do Font-End Bắn Lên</th>
</tr>
<tr>
<th>title</th>
<th>string</th>
<th>Random</th>
<th>Title Của smartbar</th>
</tr>
<th>?status</th>
<th>string</th>
<th>active</th>
<th>Trạng thái Của Popup</th>
</tr>
</table>

````ts
export interface Smartbar {
    /** id là id của smartbar vừa tạo*/
    id: string
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````

## 4.Get All Smartbars

### API endpoint:

https://website.com/wp-json/myshopkit/v1/smartbars

##### parameters

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
<th>?search</th>
<th>string</th>
<th></th>
<th>Tìm Kiếm</th>
</tr>
<tr>
<th>?limted</th>
<th>string</th>
<th></th>
<th>Giới Hạn Bao Nhiêu smartbars 1 Trang</th>
</tr>
<tr>
<th>?showToPage</th>
<th>string</th>
<th></th>
<th>Popups hiển thị trên các trang nào có 7 giá trị:
template-index, template-blog,
template-article, template-list-collections,
template-collection, template-product, template-page
</th>
</tr>
</table>
Tham Số của Pluck

param | type | description
--- | --- | ---
title | string | Tên của smartbar
date | string | ngày tạo bài
status | string | Trạng Thái smartbar active/deactive
config | string | các config của font-end bắn lên
views | string | views của smartbar
clicks | string | clicks của smartbar
subscribers | string | subscribers của smartbar
conversion | string | conversion của smartbar
goal | string | goal của smartbar
showToPage | string | goal của smartbar

````ts

interface Data {
    items: Items[];
    /** maxPages là số paged*/
    maxPages: number
}


export interface Smartbar {
    data: Data
    /** messege là tin nhắn code trả lại*/
    message: string
    /** status trang thái code sau khi xử lý API*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của smartbar*/
    id: string
    /** title Là tiêu đề của smartbar*/
    title: string
    /** date Là thời gian tạo của smartbar*/
    date: string
    /** config là các setting smartbar của font-end*/
    config: datafontEnd
    /** status Là trạng thái của smartbar*/
    status: (enable | disable)
    /** views Là số lượt xem của smartbar*/
    views: number,
    /** clicks là số lượt clicks của smartbar*/
    clicks: number,
    /** subscribers là số lượt gmail được gửi của smartbar*/
    subscribers: number
    /** conversion Là đánh giá của smartbar*/
    conversion: number
    /** goal là chiến dịch của smartbar*/
    goal: string
    /** các trang hiển thi smartbar*/
    showToPage: string[] | []
}
````

## 5.Update,Patch smartbar

### API endpoint:

https://website.com/wp-json/myshopkit/v1/smartbars/:id

##### parameters

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
<th>?title</th>
<th>string</th>
<th>Random</th>
<th>title của smartbar</th>
</tr>
<tr>
<th>?status</th>
<th>(enable||disable)</th>
<th>enable</th>
<th>trạng thái của smartbar</th>
</tr>
<tr>
<th>?config</th>
<th>json</th>
<th>-</th>
<th>config smartbar do font-end bắn lên</th>
</tr>
</table>

````ts
export interface Smartbar {
    /** id là id của smartbar vừa tạo*/
    id: string
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````

## 6.Delete Smartbar:

### API endpoint:

https://website.com/wp-json/myshopkit/v1/smartbars/id

##### parameters

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
</table>

````ts
export interface Smartbar {
    /** id là id của smartbar vừa tạo*/
    id: string
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````

## 7.Many Delete Smartbars:

### API endpoint:

https://website.com/wp-json/myshopkit/v1/smartbars
##### parameters

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
<th>ids</th>
<th>string</th>
<th></th>
<th>id của từng popup ví dụ 1,2,3</th>
</tr>
</table>

````ts
export interface Smartbar {
    /** id là id của smartbar vừa tạo*/
    ids: string
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````
