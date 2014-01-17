## Auth API Documentation

<nav class="outline">
<ul>
  <li><a href="#get-key">Get Key</a>
    <ul>
      <li><a href="#get-key-url">Resource URL</a></li>
      <li><a href="#get-key-param">Parameters</a></li>
      <li><a href="#get-key-request">Sample Request</a></li>
      <li><a href="#get-key-response">Sample Response</a></li>
      <li><a href="#get-key-error">Sample Error</a></li>
    </ul>
  </li>
</ul>
</nav>


### <a id="get-key"></a> `POST` Get Key
Getting key to access another API with icon `🔒`. First step to access our system with API. 

#### <a id="get-key-url"></a> Resource URL
/api/v2/auth/login

#### <a id="get-key-param"></a> Parameters
+ `email` [required with password] Valid email address
+ `password` [required with email]
+ `fb_token` [required with fb_uid]
+ `fb_uid` [required with fb_token]
+ `gcm_id` [_optional_]

You can use with either email and password, or fb_token and fb_uid. 

#### <a id="get-key-request"></a>Sample Request
````sh
curl -X POST --data "email=shcode@ymail.com&password=rahasia" http://shoop.dev/api/v2/auth/login
````

#### <a id="get-key-response"></a>Sample Response

````json
{
    "status": 1,
    "key": "4974328ce522a3eb86ecf73a193490314cf98c74"
}
````
#### <a id="get-key-error"></a>Sample Error

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