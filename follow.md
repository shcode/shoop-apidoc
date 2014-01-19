## Follow API Documentation

- [Get Following](#get-following)
    + [Resource URL](#get-following-url)
	+ [Parameters](#get-following-param)
	+ [Sample Request](#get-following-request)
	+ [Sample Response](#get-following-response)
- [Get Follower](#get-follower)
    + [Resource URL](#get-follower-url)
    + [Parameters](#get-follower-param)
    + [Sample Request](#get-follower-request)
    + [Sample Response](#get-follower-response)
- [Follow User](#follow)
    + [Resource URL](#follow-url)
    + [Parameters](#follow-param)
    + [Sample Request](#follow-request)
    + [Sample Response](#follow-response)
- [Unfollow User](#unfollow)
    + [Resource URL](#unfollow-url)
    + [Parameters](#unfollow-param)
    + [Sample Request](#unfollow-request)
    + [Sample Response](#unfollow-response)


#### <a name="get-following"></a> `🔒` `GET` Get Following
Get list of following from user

##### <a name="get-following-url"></a> Resource URL
/api/v2/follow/get_following

##### <a name="get-following-param"></a> Parameters
+ `id_user` _`optional`_ User whose following. Default `active user`
+ `limit` _`optional`_ Limit list of following. Default `20`
+ `offset` ._`optional`_ Offset list of following. Default `0`

##### <a name="get-following-request"></a>Sample Request
````sh
curl -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/follow/get_following
````

##### <a name="get-following-response"></a>Sample Response

````json
{
    "status": 1,
    "count": 2,
    "follower": [
        {
            "avatar": null,
            "name": "null",
            "id": "304",
            "following": 1
        },
        {
            "avatar": "2655.jpg",
            "name": "imelyaa",
            "id": "2655",
            "following": 1
        }
    ]
}
````

#### <a name="get-follower"></a> `🔒` `GET` Get Follower
Get list of follower from user

##### <a name="get-follower-url"></a> Resource URL
/api/v2/follow/get_follower

##### <a name="get-follower-param"></a> Parameters
+ `id_user` _`optional`_ User whose follow by other user. Default `active user`
+ `limit` _`optional`_ Limit list of follower. Default `20`
+ `offset` ._`optional`_ Offset list of follower. Default `0`

##### <a name="get-following-request"></a>Sample Request
````sh
curl -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/follow/get_follower?id_user=1
````

##### <a name="get-following-response"></a>Sample Response

````json
{
    "status": 1,
    "count": 15,
    "follower": [
        {
            "avatar": null,
            "name": "",
            "id": "344",
            "following": 0
        },
        {
            "avatar": null,
            "name": "",
            "id": "372",
            "following": 0
        },
        {
            "avatar": null,
            "name": "",
            "id": "388",
            "following": 0
        },
        {
            "avatar": null,
            "name": "aku",
            "id": "615",
            "following": 0
        },
        {
            "avatar": null,
            "name": "aku",
            "id": "666",
            "following": 0
        },
        {
            "avatar": null,
            "name": "aku",
            "id": "672",
            "following": 0
        },
        {
            "avatar": null,
            "name": "putra",
            "id": "687",
            "following": 0
        },
        {
            "avatar": null,
            "name": "wek",
            "id": "688",
            "following": 0
        },
        {
            "avatar": null,
            "name": "aku",
            "id": "715",
            "following": 0
        },
        {
            "avatar": null,
            "name": "aku",
            "id": "719",
            "following": 0
        },
        {
            "avatar": null,
            "name": "aku",
            "id": "828",
            "following": 0
        },
        {
            "avatar": null,
            "name": "putra",
            "id": "2617",
            "following": 0
        },
        {
            "avatar": null,
            "name": "afi",
            "id": "2621",
            "following": 0
        },
        {
            "avatar": null,
            "name": "",
            "id": "2695",
            "following": 0
        },
        {
            "avatar": null,
            "name": "melya@tesshoop1.com",
            "id": "2743",
            "following": 0
        }
    ]
}
````

#### <a name="follow"></a> `🔒` `POST` Follow
Follow another user

##### <a name="follow-url"></a> Resource URL
/api/v2/follow/following

##### <a name="follow-param"></a> Parameters
+ `user` ___`required`___ User who want to follow. It can be `array of integer` or single `integer`

##### <a name="follow-request"></a>Sample Request
````sh
curl -X POST --data "user[]=5&user[]=4" -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/follow/set_follow
````

##### <a name="follow-response"></a>Sample Response

````json
{
    "status": 1
}
````

#### <a name="follow"></a> `🔒` `POST` Follow
Follow another user

##### <a name="follow-url"></a> Resource URL
/api/v2/follow/set_follow

##### <a name="follow-param"></a> Parameters
+ `user` ___`required`___ User who want to follow. It can be `array of integer` or single `integer`

##### <a name="follow-request"></a>Sample Request
````sh
curl -X POST --data "user[]=5&user[]=4" -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/follow/set_follow
````

##### <a name="follow-response"></a>Sample Response

````json
{
    "status": 1
}
````

#### <a name="unfollow"></a> `🔒` `POST` Follow
Unfollow another user

##### <a name="unfollow-url"></a> Resource URL
/api/v2/follow/set_unfollow

##### <a name="unfollow-param"></a> Parameters
+ `id_user` ___`required`___ User who want to follow. type `integer`

##### <a name="unfollow-request"></a>Sample Request
````sh
curl -X POST --data "id_user=4" -H "X-API-KEY: 4974328ce522a3eb86ecf73a193490314cf98c74" http://shoop.dev/api/v2/follow/set_unfollow
````

##### <a name="unfollow-response"></a>Sample Response

````json
{
    "status": 1
}
````
