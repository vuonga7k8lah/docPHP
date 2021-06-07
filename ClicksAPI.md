# Clicks API

## 1.Get Clicks

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/popups/clicks

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
thisWeek | string | số clicks của popup trong tuần này
thisMonth | string | số clicks của popup trong tháng này
lastWeek | string | số clicks của popup tuần trước
lastMonth | string | số clicks của popup Tháng Trước
toDay | string | số clicks của popup trong ngày
yesterday | string | số clicks của popup ngày hôm qua
customer | string | Xem Bảng Dưới

Tham Số của customer

param | type | description
--- | --- | ---
start | string |ngày bắt đầu trong khoảng tìm kiếm
end | string |ngày kết thúc trong khoảng tìm kiếm

````ts
export interface clicks {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}

export interface Data {
    /** title */
    title: string
    /** summary là tổng số lượng clicks dựa theo filter*/
    summary: number
    /** messege là tin nhắn trả lại trên sever*/
    timeline: Timeline[]
}

export interface Timeline {
    /**
     * id ngẫu nhiên và duy nhất
     */
    id: string
    /** summary là số lượng clicks dựa theo filter (ví dụ là tổng số clicks cuả 1 tháng trong filter 4 tháng trước)*/
    summary: number
    /** label là tên của filter*/
    label: string
}
````

## 2.Create Click

### Method:POST

### API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/popups/clicks

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
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}

export interface Data {
    /** id là id của clicks*/
    id: string
}
````

## 3.Update Click

### Method:PUT

### API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/popups/clicks

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
export interface Clicks {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}

export interface Data {
    /** id là id của clicks*/
    id: string
}
````

## 4.Delete Click

### Method:DELETE

### API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/popups/clicks

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
export interface Clicks {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
}

export interface Data {
    /** id là id của clicks*/
    id: string
}
````
