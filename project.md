## API Projects

## 1.Create project

### Method:POST

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth
##### parameters

````ts
export interface Data {
    label: String;
}

````

#####Response

````ts
export interface Response {
    data: Data
    /** messege là tin nhắn trả lại trên sever*/
    msg: string
    status: string
}

export interface Data {
    id: string
}

````

## 2.Get projects

### Method:GET

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

##### parameters

````ts
export interface Data {
    pluck: String;
    posts_per_page: int;
}

````

#####Response

````ts
export interface Response {
    items: Data
    /** messege là tin nhắn trả lại trên sever*/
    msg: string
    maxPages: int
    maxPosts: int
    paged: int
    status: string
}

export interface Data {
    id: int
    label: string
}

````

## 3.update Project

### Method: UPDATE

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id

#### Param

param | type | description
--- | --- | ---
label | string |

#### Response
````ts
export interface Response {
    id: string
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: string
}
````

## 4.Get all trash

### Method:GET

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/trash

##### parameters
param | type | description
--- | --- | ---
pluck | string | id,endpoint,label,color,taxonomies,thumbnail,thumbnails,totalChildren,parentInfo,totalChildrenText
#### Param

Response

````ts
export interface Response {
    msg: string
    status: string
    maxPages: number
    maxPosts: number
    items: Item[]
    paged: number
}

export interface Item {
    id: number
    endpoint: string
    label: string
    color: string
    taxonomies: Taxonomies
    thumbnail: any
    thumbnails: Thumbnails
    totalChildren: number
    parentInfo: ParentInfo
}

export interface Taxonomies {
    pl_template_category: any[]
    tags: Tag[]
}

export interface Tag {
    label: string
    id: number
    endpoint: string
}

export interface Thumbnails {
    full: any
    "5x5": any
    thumbnail: any
    medium: any
    large: any
}

export interface ParentInfo {
    id: number
    label: string
    totalChildren: number
}

````

## 5.Update project to trash

### Method:PATCH

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id/children

##### parameters


#### Response

````ts
export interface Response {
    id: int
    /** messege là tin nhắn trả lại trên sever*/
    msg: string
    status: string
}

````

## 6.Delete children project

### Method:Delete

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id/children

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

Response

````ts
export interface Response {
    id: int
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: string
}

````
## 6.Delete children project

### Method:Delete

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id/children

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

Response

````ts
export interface Response {
    id: int
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: string
}

````
## 7.GET children project

### Method:GET

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id/children

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

Response

````ts
export interface Response {
    msg: string
    status: string
    maxPages: number
    maxPosts: number
    items: Item[]
    paged: number
}

export interface Item {
    color: string
    endpoint: string
    id: number
    isGlobalTemplate: string
    label: string
    taxonomies: Taxonomies
    thumbnail: Thumbnail
    thumbnails: Thumbnails
    totalChildren: number
}

export interface Taxonomies {
    pl_template_category: any[]
    tags: Tag[]
}

export interface Tag {
    label: string
    id: number
    endpoint: string
}

export interface Thumbnail {
    id: number
    url: number
    height: boolean
    width: number
}

export interface Thumbnails {
    full: Full
    "5x5": N5x5
    thumbnail: Thumbnail2
    medium: Medium
    large: Large
}

export interface Full {
    id: number
    url: string
    width: number
    height: number
}

export interface N5x5 {
    id: number
    url: string
    width: number
    height: number
}

export interface Thumbnail2 {
    id: number
    url: string
    width: number
    height: number
}

export interface Medium {
    id: number
    url: string
    width: number
    height: number
}

export interface Large {
    id: number
    url: string
    width: number
    height: number
}

````
## 8.create children project

### Method:POST

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id/create

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

#### parameters
````ts
export interface Param {
  thumbnail: Thumbnail
  label: string
  content: string
  metadata: Metadata
  taxonomies: Taxonomies
}

export interface Thumbnail {
  id: number
}

export interface Metadata {
  color: string
}

export interface Taxonomies {
  tags: number[]
}
````

Response

````ts
export interface Response {
    id: int
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: string
}

````
## 9.update children project restore publish

### Method:PATCH

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id/detail/publish

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

Response

````ts
export interface Response {
    id: int
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: string
}

````

## 10.get children project detail

### Method:Delete

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/projects/:id/detail

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

Response

````ts
export interface Response {
    msg: string
    status: string
    item: Item
}
export interface Item {
    color: string
    content: Content
    endpoint: string
    id: number
    isGlobalTemplate: string
    label: string
    taxonomies: Taxonomies
    thumbnail: Thumbnail
    thumbnails: Thumbnails
}

````

## 11.Search project

### Method:Delete

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/search

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

Response

````ts
export interface Response {
    id: int
    /** messege là tin nhắn trả lại trên sever*/
    message: string
    status: string
}

````

## 12.Tags project

### Method:POST

### API endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/tags

#### headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

#### parameters

````ts
export interface Param {
    items: string
}

````

Response

````ts
export interface Response {
    items: Items[]
    /** messege là tin nhắn trả lại trên sever*/
    msg: string
    status: string
}

export interface Items {
    id: string
    label: string
}
````
# Upload API

## 13.Upload IMG

### Endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/images

#### Method:POST

### Headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

##### Body

content | source | value
--- | --- | ---
'base64' / 'url' / 'form_file' | 'base64' / 'self_hosted' / 'file'

````ts
export interface UploadImage {
    item: Item
    msg: string
    status: 'error' | 'success'
}

export interface Item {
    id: number
    url: string
    thumbnails: Thumbnails;
    msg: string
    status: 'error' | 'success'
}

export interface Thumbnails {
    '5x5': ThumbnailMethodGet & { width: number; height: number };
    medium: ThumbnailMethodGet & { width: number; height: number };
    large: ThumbnailMethodGet & { width: number; height: number };
    thumbnail: ThumbnailMethodGet & { width: number; height: number };
    full: ThumbnailMethodGet & { width: number; height: number };
}
````

## 14.Get Images

### Endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/me/images

#### Method: GET

### Headers

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

##### parameters

key | type | value
--- | --- | ---
order | string | 'desc'/'asc'
posts_per_page | number | Default: 20
orderby | string |  Default: id
paged | string |  Default: 1

````ts
export interface GetImages {
    items: Item[]
    msg: string
    status: 'error' | 'success'
    paged: number
}

export interface Item {
    id: number;
    label: string;
    url: string;
    thumbnails: Thumbnails;
}

export interface Thumbnails {
    '5x5': ThumbnailMethodGet & { width: number; height: number };
    medium: ThumbnailMethodGet & { width: number; height: number };
    large: ThumbnailMethodGet & { width: number; height: number };
    thumbnail: ThumbnailMethodGet & { width: number; height: number };
    full: ThumbnailMethodGet & { width: number; height: number };
}


````

## 15.Get Image

### Endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/images/:id

#### Method: GET

### Header

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

````ts
export interface GetImage {
    items: Item
    msg: string
    status: 'error' | 'success'
}

export interface Item {
    id: number
    label: string
    url: string
    width: number
    height: number
    thumbnails: Thumbnail[]
}

export interface Thumbnail {
    id: number
    url: string
    width: number
    height: number
}
````
## 16.delete Image

### Endpoint:

https://website.com/wp-json/wiloke-smart-mockup/v1/images/:id

#### Method: DELETE

### Header

key | type | value
--- | --- | ---
Authorization | string | Basic Auth

````ts
export interface GetImage {
    id: string
    msg: string
    status: 'error' | 'success'
}
````
