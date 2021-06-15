# Subscriber API

## 1.Get Insights Subscribers

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/insights/popups/subscribers

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

https://website.com/wp-json/myshopkit/v1/popups/subscribers

##### parameters

param | Type | Data Default |Description
--- | --- | --- | -----|
?search | string | - | Tìm Kiếm
?limited | number | 30 | Giới Hạn Bao Nhiêu email 1 Trang

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
}
export interface Subcribers {
    data: Data
    /** messege là tin nhắn code trả lại*/
    message: string
    /** status trang thái code sau khi xử lý API*/
    status: 'error' | 'success'
}
````

## 3.DELETE Subscriber

### Method:DELETE

### API endpoint:

https://website.com/wp-json/myshopkit/v1/popups/subscribers/:id

##### parameters

<table>
<tr>
<th>Param</th>
<th>Type</th>
<th>Data Default</th>
<th>Description</th>
</tr>
</table>

````ts
export interface View {
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
