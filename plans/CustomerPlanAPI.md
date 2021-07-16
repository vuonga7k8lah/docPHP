# Plans API

## 1.Get plan

### Method:GET

### API endpoint:

https://website.com/wp-json/myshopkit/v1/me/plans

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
</table>

````ts
export interface Plan {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: (success | error)
}

export interface Data {
    /** plan là tên gói*/
    plan: (free | silver | originalFree | gold),
    extraInfo: ExtraInfo
}

export interface ExtraInfo {
    /** plan là tên gói*/
    plan: (free | silver | originalFree | gold),
    extraInfo: ExtraInfo
}

````

##2.GET Confirmation URL

### Method:POST

### API endpoint:

https://website.com/wp-json/myshopkit/v1/me/plans/charge/url

##### parameters

<table>
<tr>
<th>from-data</th>
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
<th>planSlug</th>
<th>string</th>
<th>Tên Gói plan</th>
<th>Tên gói plan đã được config</th>
</tr>
</table>

````ts
export interface Plan {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: (success | error)
}

export interface Data {
    /** redirectTo là đường dẫn chuyển trang*/
    redirectTo: string
}
````

##3.Update Plan

### Method:PUT

### API endpoint:

https://website.com/wp-json/myshopkit/v1/me/plans

##### parameters

<table>
<tr>
<th>x-www-form-urlencoded</th>
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
<th>created_at</th>
<th>string</th>
<th>--</th>
<th>ngày tạo gói</th>
</tr>
<tr>
<th>status</th>
<th>string</th>
<th>--</th>
<th>Trạng Thái</th>
</tr>
<tr>
<th>name</th>
<th>string</th>
<th>Tên Gói plan</th>
<th>Tên gói plan đã được config</th>
</tr>
</table>

````ts
export interface Plan {
    data: []
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: (success | error)
}

````
