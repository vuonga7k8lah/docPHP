# Discount API

## 1.Get All Discounts

### Method:GET

### headers
key | type | value
--- | --- | ---
Authorization | string | code xác thực 

### Method:GET

### API endpoint:

https://website.com/wp-json/wookit/v1/coupons

````ts
export interface Discount {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: (success | error)
}

export interface Data {
    items: Item[]
}

export interface Item {
    code: string
    description: string
    endsAt: string
    id: number
    startsAt: string
    status: string
}
````