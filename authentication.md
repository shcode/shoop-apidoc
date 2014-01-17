## Auth API Documentation

#### `POST` Get Key
Getting key to access another API with icon `🔒`. First step to access our system with API. 

#### Resource URL
/api/v2/auth/login

#### Parameters
+ `email` [required with password] Valid email address
+ `password` [required with email]
+ `fb_token` [required with fb_uid]
+ `fb_uid` [required with fb_token]
+ `gcm_id` [required]
You can use with either email and password, or fb_token and fb_uid. 

#### Sample Response

#### Sample Error