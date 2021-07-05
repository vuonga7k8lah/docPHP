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
    myshokit: (free | silver | originalFree | gold)
}
````