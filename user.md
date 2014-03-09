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
        "avatar": null,
        "type": "2",
        "fb_token": "",
        "fb_token_expired": null,
        "tw_token": "218307206-cTmwJ7vAijoufjtbQzVvowImzP9jq2WUbADcFtnc",
        "tw_secret": "SHhfmg4jmiBEwO0EFBIMCaaI4V2hArJyI5vKnl4aq5Y",
        "album_id": "4222704171637",
        "show_phone": "1",
        "gcm_regid": "APA91bHJYsdw6tRLSMFH-ZlBrvwFwsPjNVu_Vo-q3RJZ1q9dfQs9BZ6_NrzZW1otXE1amTA-EkQwQQElqb910B1Qjs5JzGL-9wD0_vGyr71cAxEmeimJQ-HdN9SZTAAaxlQPxSH3D01nCT3VKfxwyj70t-HO2cdwBw",
        "premium_end": "2013-10-15 00:47:55",
        "is_premium": "1",
        "updated": "1",
        "fb_uid": "null",
        "joined_date": "2013-04-01 11:00:00",
        "id_key": "2",
        "longitude": null,
        "latitude": null,
        "id_location": null,
        "status": "0",
        "app_version": null,
        "last_activity": null,
        "buyer_poin": "0",
        "seller_poin": "0",
        "is_trusted": null,
        "is_sundul": null
    },
    "product_count": {
        "all": 54,
        "active": 0
    },
    "follow": {
        "following": 2,
        "follower": 2
    },
    "shoop_count": 0,
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
    "status": 1,
    "user": {
        "id_user": "444",
        "name": null,
        "address": null,
        "email": "banghen@gmail.com",
        "phone": "+628157901652",
        "city": null,
        "country": null,
        "avatar": null,
        "buyer_poin": "0",
        "seller_poin": "0",
        "id_location": null
    },
    "product_count": {
        "all": 0,
        "active": 0
    },
    "follow": {
        "following": 0,
        "follower": 0,
        "follow_status": 0
    },
    "shoop_count": 0
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
        "name": "M. Sulton Hasanuddin",
        "email": "shcode@ymail.com",
        "phone": "+6283857723355",
        "birthdate": "1986-12-15",
        "username": "shcode",
        "address": "Jl. Merak No. 10 Surabaya",
        "city": "Surabaya",
        "country": "Indonesia",
        "bio": null,
        "avatar": null,
        "type": "2",
        "fb_token": "",
        "fb_token_expired": null,
        "tw_token": "218307206-cTmwJ7vAijoufjtbQzVvowImzP9jq2WUbADcFtnc",
        "tw_secret": "SHhfmg4jmiBEwO0EFBIMCaaI4V2hArJyI5vKnl4aq5Y",
        "album_id": "4222704171637",
        "show_phone": "1",
        "gcm_regid": "APA91bHJYsdw6tRLSMFH-ZlBrvwFwsPjNVu_Vo-q3RJZ1q9dfQs9BZ6_NrzZW1otXE1amTA-EkQwQQElqb910B1Qjs5JzGL-9wD0_vGyr71cAxEmeimJQ-HdN9SZTAAaxlQPxSH3D01nCT3VKfxwyj70t-HO2cdwBw",
        "premium_end": "2013-10-15 00:47:55",
        "is_premium": "1",
        "updated": "1",
        "fb_uid": "null",
        "joined_date": "2013-04-01 11:00:00",
        "id_key": "2",
        "longitude": null,
        "latitude": null,
        "id_location": null,
        "status": "0",
        "app_version": null,
        "last_activity": null,
        "buyer_poin": "0",
        "seller_poin": "0",
        "is_trusted": null,
        "is_sundul": null
    },
    "product_count": {
        "all": 54,
        "active": 0
    },
    "follow": {
        "following": 2,
        "follower": 2
    },
    "shoop_count": 0,
    "status": 1
}
````

#### <a name="track-user-action"></a> `🔒` `POST` Track User's Action
Track User's Action

##### <a name="track-user-action-url"></a> Resource URL
/api/v2/user/action_track

##### <a name="track-user-action-params"></a> Parameters

json array of [

+ `id`  track id, should be globally unique. Can be done using md5(random_string)
+ `resource`  e.g : Profile / Feed / Browse.
+ `action`  e.g : open / close
+ `time`    e.g : 2014-03-10 08:20:10

]

##### <a name="track-user-action-request"></a>Sample Request
````sh
curl -X POST --data "data=[{\"id\": \"jasklfdjs8378329\", \"resource\": \"Profile\", \"action\": \"open\", \"time\": \"2014-03-10 08:20:10\"}]" -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/user/action_track
````

##### <a name="track-user-action-response"></a>Sample Response

````json
{
    "status": 1
}
````
