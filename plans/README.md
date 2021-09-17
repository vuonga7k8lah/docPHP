# Product API

## Get Products

#### Method: GET

#### Endpoint: https://website.com/wp-json/magic-badges/v1/products

## Params

| Param | Type | Description | Default |
| --- | --- | ----| --- |
| limit| int | Số lượng items / trang. Maximum: 30. Quá 30 sử dụng default | 10 |
| page | int | Page hiện tại | 1 |
| status | 'active' / 'deactive' / 'any' | Trường hợp all thì trả về cả popups active và deactive| any |
| ?pluck | string | Mỗi pluck cách nhau bởi dấu phẩy. Ví dụ: title, id. Trường hợp không có pluck trả lai hết| undefined|


## 2.Create Badges Manual

#### method:post

### API endpoint:

https://website.com/wp-json/magic-badges/v1/products

##### body-param

param | type | description |default
--- | --- | ---| --- |
shopName | string | Tên của shop | undefined
productID | number | id của sản phẩm | undefined
handle | string | tên sản phẩm dưới dạng slug | undefined
config | string | config badges của sản phẩm | undefined

````ts

````

## 3.Update,Patch Badges Manual

#### method:PUT
### API endpoint:

https://website.com/wp-json/magic-badges/v1/products/:id

##### x-www-form-urlencoded

param | type | description |default
--- | --- | ---| --- |
shopName | string | Tên của shop | undefined
productID | number | id của sản phẩm | undefined
handle | string | tên sản phẩm dưới dạng slug | undefined
config | string | config badges của sản phẩm | undefined

## 4.Delete Badges Manual

### API endpoint:

https://website.com/wp-json/magic-badges/v1/products/:id
