# Product API

## 1.Get all Products

#### Method: GET

#### Endpoint: https://website.com/vge/magic-badges/v1/full-products

## Params
````ts
export interface Params {
    /**limit Số lượng items / trang. Maximum: 30. Quá 30 sử dụng default 10*/
    limit: int
    /** page là page hiện tại default 1*/
    page: int
     /** Mỗi pluck cách nhau bởi dấu phẩy. Ví dụ: title, id. Trường hợp không có pluck trả lai hết*/
    ?pluck: Pluck
    status: 'active' | 'deactive' | 'all'
}
export interface Pluck{
config: object,
status: string,
title:string,
date:string
}
````
## 2.Get Products 

#### Method: GET

#### Endpoint: https://website.com/vge/magic-badges/v1/products

####header

param | type | description |default
--- | --- | ---| --- |
shopName | string | Tên của shop | undefined

## Params
````ts
export interface Params {
    query:Query[]
   }
export interface Query{
    /**title tên sản phẩm*/
    title: string
    sluck: string
}
````

## 3.Create Badges Manual

#### method:post

### API endpoint:

https://website.com/vge/magic-badges/v1/products

####header:

param | type | description |default
--- | --- | ---| --- |
shopName | string | - | undefined

##### body-param

param | type | description |default
--- | --- | ---| --- |
shopName | string | Tên của shop | undefined
productID | number |  | undefined
slug | string | tên sản phẩm dưới dạng slug | undefined
config | string | config badges của sản phẩm | undefined

````ts

````

## 4.Update,Patch Badges Manual

#### method:PUT
### API endpoint:

https://website.com/wp-json/magic-badges/v1/products/:id

####header
param | type | description |default
--- | --- | ---| --- |
shopName | string | Tên của shop | undefined
##### x-www-form-urlencoded

param | type | description |default
--- | --- | ---| --- |
shopName | string | Tên của shop | undefined
productID | number | id của sản phẩm | undefined
slug | string | tên sản phẩm dưới dạng slug | undefined
config | string | config badges của sản phẩm | undefined

## 5.Delete Badges Manual

####header
param | type | description |default
--- | --- | ---| --- |
shopName | string | Tên của shop | undefined

### API endpoint:

https://website.com/wp-json/magic-badges/v1/products/:id
