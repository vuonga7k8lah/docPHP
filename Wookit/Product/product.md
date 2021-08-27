# Discount API

## 1.Get All Products

### Method:GET

### headers
key | type | value
--- | --- | ---
Authorization | string | code xác thực 

### Method:GET

### API endpoint:

https://website.com/wp-json/wookit/v1/products

````ts
export interface Product {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: (success | error)
}

export interface Data {
  items: Item[]
}

export interface Item {
  id: number
  title: string
  link: string
  image: Image
  price: string[]
}

export interface Image {
  src: string
  width: number
  height: number
}
````