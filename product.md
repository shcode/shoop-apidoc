## Product API Documentation

- [Get Product Detail](#get-product)
    + [Resource URL](#get-product-url)
    + [Parameters](#get-product-param)
    + [Sample Request](#get-product-request)
    + [Sample Response](#get-product-response)
- [Get Product by User](#get-product-user)
    + [Resource URL](#get-product-user-url)
    + [Parameters](#get-product-user-param)
    + [Sample Request](#get-product-user-request)
    + [Sample Response](#get-product-user-response)
- [Get Product by Category](#get-product-cat)
    + [Resource URL](#get-product-cat-url)
    + [Parameters](#get-product-cat-param)
    + [Sample Request](#get-product-cat-request)
    + [Sample Response](#get-product-cat-response)    
- [Add Product](#add-product)
    + [Resource URL](#add-product-url)
    + [Parameters](#add-product-param)
    + [Sample Request](#add-product-request)
    + [Sample Response](#add-product-response)
- [Edit Product](#edit-product)
    + [Resource URL](#edit-product-url)
    + [Parameters](#edit-product-param)
    + [Sample Request](#edit-product-request)
    + [Sample Response](#edit-product-response)


#### <a name="get-product-detail"></a> `🔒` `GET` Get Product Detail
Get detail product

##### <a name="get-product-detail-url"></a> Resource URL
/api/v2/product/get_product_detail

##### <a name="get-product-detail-param"></a> Parameters
+ `id_product` ___`required`___ ID of product. 

##### <a name="get-product-detail-request"></a>Sample Request
````sh
curl -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/product/get_product_detail?id_product=1932
````

##### <a name="get-product-detail-response"></a>Sample Response

````json
{
    "status": 1,
    "product": {
        "id_product": "1929",
        "prod_title": "tes",
        "prod_desc": "Tes",
        "prod_price": "123",
        "prod_curr": "IDR",
        "prod_order": "",
        "prod_status": "0",
        "prod_share": null,
        "prod_image": "1929.jpg",
        "prod_tag": "tes, tesx",
        "prod_stock": "1",
        "langitude": null,
        "longitude": null,
        "id_user": "667",
        "prod_time": "2014-01-13 16:12:11",
        "fb_post": null,
        "hubmeup_link": "http://www.hubmeup.com/tes-102/",
        "from_app": null,
        "id_supercat": "1",
        "id_superloc": "11",
        "discount": "0",
        "view_count": "0",
        "is_nego": "0",
        "image_migrate": "0",
        "condition": "new",
        "shoop_count": "0",
        "comment_count": "0",
        "supercat": {
            "idsc": "1",
            "name": "Perlengkapan Olahraga"
        },
        "superloc": {
            "idsl": "11",
            "name": "Jawa Tengah"
        },
        "comment_status": 0,
        "shoop_status": 0,
        "tag": [
            {
                "id_tag": "143",
                "tag": "tes"
            },
            {
                "id_tag": "178",
                "tag": "tesx"
            }
        ],
        "image": [
            {
                "id_image": "88",
                "product_image": "1929_1389604315.jpg"
            }
        ],
        "user": {
            "id_user": "667",
            "name": "afiev",
            "address": "yoyoyoyo",
            "email": "afiev@firzil.co.id",
            "phone": "1233232323",
            "city": null,
            "country": "heheheh",
            "avatar": "2014-01-1390193388912.jpg",
            "buyer_poin": "0",
            "seller_poin": "0",
            "id_location": "12",
            "follow": {
                "following": 15,
                "follower": 19
            },
            "product_count": {
                "all": 171,
                "active": 0
            }
        },
        "link": [
            {
                "store_name": "Blogger fir",
                "id_platform": "13",
                "platform_name": "Blogger",
                "status": "2",
                "link": null
            },
            {
                "store_name": "Facebook",
                "id_platform": "10",
                "platform_name": "Facebook",
                "status": "1",
                "link": "http://www.facebook.com/10201354019279997#,#http://www.facebook.com/10201354019640006"
            }
        ]
    }
}
````

#### <a name="get-product-user"></a> `🔒` `GET` Get Product User
Get product by user

##### <a name="get-product-user-url"></a> Resource URL
/api/v2/product/get_product_user

##### <a name="get-product-user-param"></a> Parameters
+ `id_user` ___`required`___ ID of user. If empty, will use default: <code>active user</code>
+ `limit` _`optional`_ Limit for browse. Default <code>6</code>
+ `offset` _`optional`_ Limit for browse. Default <code>1</code>
+ `keyword` _`optional`_ Search key
+ `id_supercat` _`optional`_ Location ID
+ `id_superloc` _`optional`_ Category ID
+ `tag` _`optional`_ Tag filter
+ `filter` _`optional`_ filter for browse, enum <code>all</all> or <code>own</code>. Default <code>all</code>
+ `since_time` _`optional`_ Browse product from since_time
+ `until_time` _`optional`_ Browse product up to until_time. ignored if since_time is not empty
+ `sort` _`optional`_ Sort product, enum <code>time</code> <code>popular</code> <code>comment</code> <code>price</code> <code>stock</code>. Default <code>time</code>
+ `direction` _`optional`_ Direction of sort. enum <code>desc</code> or <code>asc</code>. Default <code>desc</code>

##### <a name="get-product-user-request"></a>Sample Request
````sh
curl -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/product/get_product_user?limit=2
````

##### <a name="get-product-user-response"></a>Sample Response

````json
{
    "status": 1,
    "limit": "2",
    "offset": 1,
    "count": 1191,
    "product": [
        {
            "id_product": "1931",
            "prod_title": "laptop compaq",
            "prod_price": "2500000",
            "prod_curr": "IDR",
            "discount": null,
            "view_count": null,
            "prod_stock": "1",
            "id_user": "461",
            "shoop_count": "0",
            "comment_count": "0",
            "comment_status": 0,
            "shoop_status": 0,
            "user": {
                "id_user": "461",
                "name": "Akuikialieeeeee",
                "address": "Surabaya",
                "email": "ali@firzil.co.id",
                "phone": "+6285730432092",
                "city": null,
                "country": "83",
                "avatar": "461.jpg",
                "buyer_poin": "0",
                "seller_poin": "0",
                "id_location": null
            },
            "tag": [
                {
                    "id_tag": "180",
                    "tag": "shoop"
                }
            ],
            "image": []
        },
        {
            "id_product": "1929",
            "prod_title": "tes",
            "prod_price": "123",
            "prod_curr": "IDR",
            "discount": null,
            "view_count": null,
            "prod_stock": "1",
            "id_user": "667",
            "shoop_count": "0",
            "comment_count": "0",
            "comment_status": 0,
            "shoop_status": 0,
            "user": {
                "id_user": "667",
                "name": "afiev",
                "address": "yoyoyoyo",
                "email": "afiev@firzil.co.id",
                "phone": "1233232323",
                "city": null,
                "country": "heheheh",
                "avatar": "2014-01-1390193388912.jpg",
                "buyer_poin": "0",
                "seller_poin": "0",
                "id_location": "12"
            },
            "tag": [
                {
                    "id_tag": "143",
                    "tag": "tes"
                },
                {
                    "id_tag": "178",
                    "tag": "tesx"
                }
            ],
            "image": [
                {
                    "id_image": "88",
                    "product_image": "1929_1389604315.jpg"
                }
            ]
        }
    ]
}
````

#### <a name="get-product-cat"></a> `🔒` `GET` Get Product User
Get product by category

##### <a name="get-product-cat-url"></a> Resource URL
/api/v2/product/get_product_user

##### <a name="get-product-cat-param"></a> Parameters
+ `id_supercat` ___`required`___ Category ID
+ `limit` _`optional`_ Limit for browse. Default <code>6</code>
+ `offset` _`optional`_ Limit for browse. Default <code>1</code>
+ `keyword` _`optional`_ Search key
+ `id_superloc` _`optional`_ Location ID
+ `tag` _`optional`_ Tag filter
+ `filter` _`optional`_ filter for browse, enum <code>all</all> or <code>own</code>. Default <code>all</code>
+ `since_time` _`optional`_ Browse product from since_time
+ `until_time` _`optional`_ Browse product up to until_time. ignored if since_time is not empty
+ `sort` _`optional`_ Sort product, enum <code>time</code> <code>popular</code> <code>comment</code> <code>price</code> <code>stock</code>. Default <code>time</code>
+ `direction` _`optional`_ Direction of sort. enum <code>desc</code> or <code>asc</code>. Default <code>desc</code>

##### <a name="get-product-cat-request"></a>Sample Request
````sh
curl -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/product/get_product_category?id_supercat=2&limit=2
````

##### <a name="get-product-cat-response"></a>Sample Response

````json
menyusul (jek pusing)
````

#### <a name="add-product"></a> `🔒` `POST` Add Product
Add Product

##### <a name="add-product-url"></a> Resource URL
/api/v2/product/add_product

##### <a name="add-product-param"></a> Parameters
+ `id_user` ___`required`___ ID User from user which request.
+ `prod_name` ___`required`___
+ `prod_price` ___`required`___
+ `prod_curr` ___`required`___
+ `prod_tag` ___`required`___ pisah dengan <code>,</code>
+ `prod_desc` ___`required`___
+ `id_supercat` ___`required`___
+ `id_superloc` ___`required`___
+ `condition` _`optional`_ 
+ `is_nego` _`optional`_ 
+ `discount` _`optional`_ 
+ `prod_image` _`optional`_ array Product Image. 
+ `from_app` _`optional`_ 

##### <a name="add-product-request"></a>Sample Request
````sh
curl -X POST --data "prod_title=Baju&prod_price=15000&prod_curr=IDR&prod_desc=just_test&id_supercat=1&id_superloc=1" -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/user/add_product
````

##### <a name="add-product-response"></a>Sample Response

````json
{
    "status": 1,
    "product": {
        "id_product": "1937",
        "prod_title": "Baju",
        "prod_desc": "just test",
        "prod_price": "150000",
        "prod_curr": "IDR",
        "prod_order": null,
        "prod_status": "0",
        "prod_share": null,
        "prod_image": null,
        "prod_tag": null,
        "prod_stock": "1",
        "langitude": null,
        "longitude": null,
        "id_user": "2",
        "prod_time": "2014-02-01 11:40:58",
        "fb_post": null,
        "hubmeup_link": null,
        "from_app": null,
        "id_supercat": "1",
        "id_superloc": "1",
        "discount": "0",
        "view_count": "0",
        "is_nego": "0",
        "image_migrate": "0",
        "condition": "new",
        "shoop_count": "0",
        "comment_count": "0",
        "supercat": {
            "idsc": "1",
            "name": "Perlengkapan Olahraga"
        },
        "superloc": {
            "idsl": "1",
            "name": "Jawa Timur"
        }
    }
}
````

#### <a name="edit-product"></a> `🔒` `POST` Edit User <code>Not Finished Yet</code>
Edit active user

##### <a name="edit-product-url"></a> Resource URL
/api/v2/user/edit_user

##### <a name="edit-product-param"></a> Parameters
+ `name` _`optional`_ The name of the user.
+ `gcm_id` _`optional`_  
+ `address` _`optional`_ 
+ `id_location` _`optional`_ 
+ `phone` _`optional`_ 
+ `is_sundul` _`optional`_ 
+ `tw_token` _`optional`_ 
+ `tw_secret` _`optional`_ 
+ `avatar` _`optional`_ 
+ `fb_token` _`optional`_ 
+ `fb_uid` _`optional`_ 
+ `fb_token_expired` _`optional`_ 
+ `latitude` _`optional`_ 
+ `longitude` _`optional`_ 


##### <a name="edit-product-request"></a>Sample Request
````sh
curl -X POST --data "name=hayashi" -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/user/edit_user
````

##### <a name="edit-product-response"></a>Sample Response

````json
{
    "user": {
        "id_user": "2",
        "name": "hayashi",
        "email": "shcode@ymail.com",
        "phone": "+6283857723355",
        "birthdate": "1986-12-15",
        "username": "shcode",
        "address": "Jl. Merak No. 10 Surabaya",
        "city": "Surabaya",
        "country": "Indonesia",
        "bio": null,
        "avatar": "hohoho",
        "type": "2",
        "fb_token": "",
        "fb_token_expired": null,
        "tw_token": "218307206-cTmwJ7vAijoufjtbQzVvowImzP9jq2WUbADcFtnc",
        "tw_secret": "SHhfmg4jmiBEwO0EFBIMCaaI4V2hArJyI5vKnl4aq5Y",
        "album_id": "4222704171637",
        "show_phone": "1",
        "gcm_id": null,
        "updated": "1",
        "fb_uid": "null",
        "joined_date": "2013-04-01 11:00:00",
        "premium_end": "2013-10-15 00:47:55",
        "id_key": "2",
        "last_activity": null,
        "buyer_poin": "0",
        "seller_poin": "0",
        "is_trusted": "0",
        "is_premium": "1",
        "id_location": null
    },
    "product_count": {
        "all": 54,
        "active": 0
    },
    "follow": {
        "following": 0,
        "follower": 0
    },
    "status": 1
}
````
