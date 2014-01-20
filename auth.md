## Auth API Documentation

- [Get Key (Login)](#get-key)
    + [Resource URL](#get-key-url)
	+ [Parameters](#get-key-param)
	+ [Sample Request](#get-key-request)
	+ [Sample Response](#get-key-response)
	+ [Sample Error](#get-key-error)
- [Register](#register)
    + [Resource URL](#register-url)
    + [Parameters](#register-param)
    + [Sample Request](#register-request)
    + [Sample Response](#register-response)
- [Forgot Password](#forgot-password)
    + [Resource URL](#forgot-password-url)
    + [Parameters](#forgot-password-param)
    + [Sample Request](#forgot-password-request)
    + [Sample Response](#forgot-password-response)


#### <a name="get-key"></a> `POST` Get Key
Getting key to access another API with icon `🔒`. First step to access our system with API. 

##### <a name="get-key-url"></a> Resource URL
/api/v2/auth/login

##### <a name="get-key-param"></a> Parameters
+ `email` ___`required`___ with password. Valid email address
+ `password` ___`required`___ with email. User password.
+ `fb_token` ___`required`___ with fb_uid. Facebook token from Facebook Connect.
+ `fb_uid` ___`required`___ with fb_token. Facebook UID from Facebook Connect. Used for checking existing user.
+ `gcm_id` _`optional`_ Google Cloud Message ID. For notification.

You can use with either email and password, or fb_token and fb_uid. 

##### <a name="get-key-request"></a>Sample Request
````sh
curl -X POST --data "email=shcode@ymail.com&password=rahasia" http://shoop.dev/api/v2/auth/login
````

##### <a name="get-key-response"></a>Sample Response

````json
{
    "status": 1,
    "key": "4974328ce522a3eb86ecf73a193490314cf98c74"
}
````
##### <a name="get-key-error"></a>Sample Error

Missing parameter.

````json
{
    "status": 0,
    "error": "Your parameter is not complete. Missing parameter 'password'."
}
````

Password invalid.

````json
{
    "status": 0,
    "error": "Your password is invalid."
}
````

#### <a name="register"></a> `POST` Register
Register to Shoop system. If you connect with facebook please add fb_token.

##### <a name="register-url"></a> Resource URL
/api/v2/auth/register

##### <a name="register-param"></a> Parameters
+ `email` ___`required`___ Valid email address.
+ `password` ___`required`___ User password.
+ `name` ___`required`___ User name.
+ `id_location` ___`required`___ Location ID, you can get it from [Location](#).
+ `phone` _`optional`_ User phone.
+ `gcm_id` _`optional`_ Google Cloud Message ID. For notification.
+ `longitude` _`optional`_ Location user by Longitude.
+ `latitude` _`optional`_ Location user by Latitude.
+ `avatar` _`optional`_ Path for user avatar
+ `fb_token` _`optional`_ Facebook Access Token from Facebook Connect.
+ `show_phone` __`deprecated`__ 
+ `address` __`deprecated`__

##### <a name="register-request"></a>Sample Request
````sh
curl -X POST --data "email=shcode@ymail.com&password=rahasia&name=shcode&id_location=7&phone=082232856363" http://shoop.dev/api/v2/auth/register
````

##### <a name="register-response"></a>Sample Response

````json
{
    "status": 1,
    "key": "4974328ce522a3eb86ecf73a193490314cf98c74"
}
````

#### <a name="forgot-password"></a> `POST` Forgot Password
Request token to reset password and then send to email.

##### <a name="forgot-password-url"></a> Resource URL
/api/v2/auth/forgot_password

##### <a name="register-param"></a> Parameters
+ `email` ___`required`___ Valid email address.

##### <a name="register-request"></a>Sample Request
````sh
curl -X POST --data "email=shcode@ymail.com" http://shoop.dev/api/v2/auth/forgot_password
````

##### <a name="register-response"></a>Sample Response

````json
{
    "status": 1,
    "message":"Profile detail and reset password has been sent to your email."
}
````
