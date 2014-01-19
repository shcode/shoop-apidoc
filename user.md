## User API Documentation

- [Get Active User](#get-active-user)
    + [Resource URL](#get-active-user-url)
    + [Parameters](#get-active-user-param)
    + [Sample Request](#get-active-user-request)
    + [Sample Response](#get-active-user-response)
- [Get User](#get-user)
    + [Resource URL](#get-user-url)
    + [Parameters](#get-user-param)
    + [Sample Request](#get-user-request)
    + [Sample Response](#get-user-response)
- [Edit User](#edit-user)
    + [Resource URL](#edit-user-url)
    + [Parameters](#edit-user-param)
    + [Sample Request](#edit-user-request)
    + [Sample Response](#edit-user-response)

#### <a name="get-active-user"></a> `🔒` `GET` Get Active User
Get information about active user. include count product, following, follower, and (rating [not yet])

##### <a name="get-active-user-url"></a> Resource URL
/api/v2/user/get_active_user

##### <a name="get-active-user-param"></a> Parameters
No parameter. only key.

##### <a name="get-active-user-request"></a>Sample Request
````sh
curl -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/user/get_active_user
````

##### <a name="get-active-user-response"></a>Sample Response

````json
{
    "user": {
        "id_user": "2",
        "name": "M. Sulton Hasanuddin",
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
        "gcm_regid": null,
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

#### <a name="get-user"></a> `🔒` `GET` Get User
Get information about another user. include count product, following, follower, and (rating [not yet])

##### <a name="get-user-url"></a> Resource URL
/api/v2/user/get_user

##### <a name="get-user-param"></a> Parameters
+ `id_user` ___`required`___ ID User from user which request.

##### <a name="get-user-request"></a>Sample Request
````sh
curl -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/user/get_user?id_user=444
````

##### <a name="get-user-response"></a>Sample Response

````json
{
    "user":{
        "name":null,
        "address":null,
        "email":"banghen@gmail.com",
        "phone":"+628157901652",
        "city":null,
        "country":null,
        "buyer_poin":"0",
        "seller_poin":"0",
        "id_location":null
    },
    "product_active_count":{
        "all":0,
        "active":0
    },
    "follow":{
        "following":0,
        "follower":0
    },
    "status":1
}
````

#### <a name="edit-user"></a> `🔒` `POST` Edit User
Edit active user

##### <a name="get-user-url"></a> Resource URL
/api/v2/user/edit_user

##### <a name="get-user-param"></a> Parameters
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


##### <a name="get-user-request"></a>Sample Request
````sh
curl -X POST --data "name=hayashi" -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/user/edit_user
````

##### <a name="get-user-response"></a>Sample Response

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
        "gcm_regid": null,
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
