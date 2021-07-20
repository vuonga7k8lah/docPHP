# PopupAPI

## Get Popups

#### Method: GET

#### Endpoint: https://website.com/wp-json/myshopkit/v1/popups

## Params

| Param | Type | Description | Default |
| --- | --- | ----| --- |
| limit| int | Số lượng items / trang. Maximum: 30. Quá 30 sử dụng default | 10 |
| page | int | Page hiện tại | 1 |
| status | 'active' / 'deactive' / 'any' | Trường hợp all thì trả về cả popups active và deactive| any |
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

## Get Popup

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/:id

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
title | string | Tên của popup
date | string | ngày tạo bài
status | string | Trạng Thái Popups: active/deactive
config | string | các config của font-end bắn lên
views | string | views của popup
clicks | string | clicks của popup
subscribers | string | subscribers của popup
conversion | string | conversion của popup
goal | string | goal của popup

````ts
export interface Popup {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id: string
    /** title Là tiêu đề của popup*/
    title: string
    /** date Là thời gian tạo của popup*/
    date: string
    /** config là các setting popup của font-end*/
    config: datafontEnd
    /** status Là trạng thái của popup*/
    status: (enable | disable)
    /** views Là số lượt xem của popup*/
    views: number,
    /** clicks là số lượt clicks của popup*/
    clicks: number,
    /** subscribers là số lượt gmail được gửi của popup*/
    subscribers: number
    /** conversion Là đánh giá của popup*/
    conversion: number
    /** goal là chiến dịch của popup*/
    goal: string
    items: []
    /** các trang hiển thi popup*/
    showToPage: string[] | []
}
````

## Get a specified popup info

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/:id/:param

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
title | string | Tên của popup
date | string | ngày tạo bài
status | string | Trạng Thái Popup active/deactive
config | string | các config của font-end bắn lên
views | string | views của popup
clicks | string | clicks của popup
subscribers | string | subscribers của popup
conversion | string | conversion của popup
goal | string | goal của popup

````ts
export interface Popup {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id: string
    /** title Là tiêu đề của popup*/
    title: string
    /** date Là thời gian tạo của popup*/
    date: string
    /** config là các setting popup của font-end*/
    config: datafontEnd
    /** status Là trạng thái của popup*/
    status: (active | deactive)
    /** views Là số lượt xem của popup*/
    views: number,
    /** clicks là số lượt clicks của popup*/
    clicks: number,
    /** subscribers là số lượt gmail được gửi của popup*/
    subscribers: number
    /** conversion Là đánh giá của popup*/
    conversion: number
    /** goal là chiến dịch của popup*/
    goal: string
}
````

## 3.Create Popup

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups

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
<th>Config Popup Do Font-End Bắn Lên</th>
</tr>
<tr>
<th>title</th>
<th>string</th>
<th>Random</th>
<th>Title Của Popup</th>
</tr>
 <tr>
<th>?status</th>
<th>string</th>
<th>active</th>
<th>Trạng thái Của Popup</th>
</tr>
</table>

````ts
export interface Popup {
  data: Data
  /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
  upgrade: Upgrade
 /** id là id của popup vừa tạo*/
    id: string
}

export interface Upgrade {
  isUpgrade: boolean
  message?: string
}
````

## 4.Get All Popups

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups

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
<th>Giới Hạn Bao Nhiêu Popups 1 Trang</th>
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
title | string | Tên của popup
date | string | ngày tạo bài
status | string | Trạng Thái Popup active/deactive
config | string | các config của font-end bắn lên
views | string | views của popup
clicks | string | clicks của popup
subscribers | string | subscribers của popup
conversion | string | conversion của popup
goal | string | goal của popup
showToPage | string | goal của popup

````ts

interface Data {
    items: Items[];
    /** maxPages là số paged*/
    maxPages: number
}


export interface Popup {
    data: Data
    /** messege là tin nhắn code trả lại*/
    message: string
    /** status trang thái code sau khi xử lý API*/
    status: 'error' | 'success'
}

export interface Data {
    /** id là id của popup*/
    id: string
    /** title Là tiêu đề của popup*/
    title: string
    /** date Là thời gian tạo của popup*/
    date: string
    /** config là các setting popup của font-end*/
    config: datafontEnd
    /** status Là trạng thái của popup*/
    status: (enable | disable)
    /** views Là số lượt xem của popup*/
    views: number,
    /** clicks là số lượt clicks của popup*/
    clicks: number,
    /** subscribers là số lượt gmail được gửi của popup*/
    subscribers: number
    /** conversion Là đánh giá của popup*/
    conversion: number
    /** goal là chiến dịch của popup*/
    goal: string
    /** các trang hiển thi popup*/
    showToPage: string[] | []
}
````

## 5.Update,Patch Popup

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/:id

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
<th>title của popup</th>
</tr>
<tr>
<th>?status</th>
<th>(active||deactive)</th>
<th>active</th>
<th>trạng thái của popup</th>
</tr>
<tr>
<th>?config</th>
<th>json</th>
<th>-</th>
<th>config popup do font-end bắn lên</th>
</tr>
</table>

````ts
export interface Popup {
  data: Data
  /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}

export interface Data {
  upgrade: Upgrade
 /** id là id của popup vừa tạo*/
    id: string
}

export interface Upgrade {
  isUpgrade: boolean
  message?: string
}
````

## 6.Delete Popup:

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/id

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
export interface Popup {
    /** id là id của popup vừa tạo*/
    id: string
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````

## 7.Many Delete Popup:

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups

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
export interface Popup {
    /** id là id của popup vừa tạo*/
    ids: string
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    /** status là trạng thái code sau xử lý api*/
    status: 'error' | 'success'
}
````
