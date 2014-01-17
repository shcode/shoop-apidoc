## User API Documentation

##### <a id="get-active-user"></a>`GET` `🔒` Get Active User 
Mendapatkan informasi dari aktif user

##### Resource URL
[http://shoop-v4.mlopp.com/api/v2/user/get_active_user](http://shoop-v4.mlopp.com/api/v2/user/get_active_user)

##### Parameters
No Parameters

##### <a id="mutation-history-sample-request"></a> Sample Request
````sh
curl -u 204254:Sy7PRGGr4foUk22uzjMu "https://api.bukalapak.com/v1/dompet/history/mutations.json?page=1&per_page=1"

````

##### <a id="mutation-history-sample-response"></a> Sample Response
````json
{
  "status":"OK",
  "history":[{"id":346,
              "type":"Deposit::Credit",
              "action":"remit",
              "amount":30000,
              "initial_balance":0,
              "final_balance":30000,
              "transaction_id":51938,
              "transaction_no":"130925111838",
              "created_at":"2013-11-25T15:32:47+07:00",
              "updated_at":"2013-11-25T15:32:47+07:00"}],
  "message":null
}
````

#### <a id="withdrawal-history"></a> Withdrawal History
Get current user’s withdrawal history.

+ Use `GET` http method
+ Requires authentication

##### <a id="withdrawal-history-url"></a> Resource URL
[https://api.bukalapak.com/v1/dompet/history/withdrawals.json](https://api.bukalapak.com/v1/dompet/history/withdrawals.json)

##### <a id="withdrawal-history-parameters"></a> Parameters
+ `page` *(optional)*. Page number to display. Default value is `1`.
+ `per_page` *(optional)*. Number of record to display per page. Default value is `10`.

##### <a id="withdrawal-history-sample-request"></a> Sample Request
````sh
curl -u 204254:Sy7PRGGr4foUk22uzjMu "https://api.bukalapak.com/v1/dompet/history/withdrawals.json?page=1&per_page=1"

````

##### <a id="withdrawal-history-sample-response"></a> Sample Response
````json
{
  "status":"OK",
  "history":[{"amount":25000,
              "bank_account_id":41812,
              "cancelled_at":null,
              "created_at":"2013-11-22T16:00:39+07:00",
              "deposit_id":1,
              "id":4,
              "processed_at":null,
              "state":"pending",
              "updated_at":"2013-11-22T16:00:39+07:00"}],
  "message":null
}
````

#### <a id="withdrawal-request"></a> Withdrawal Request
Make withdrawal request for current user.

+ Use `POST` http method
+ Requires authentication

##### <a id="withdrawal-request-url"></a> Resource URL
[https://api.bukalapak.com/v1/dompet/withdraw.json](https://api.bukalapak.com/v1/dompet/withdraw.json)

##### <a id="withdrawal-request-parameters"></a> Parameters
+ `deposit_withdrawal[amount]` *(required)*. Amount to withdraw.
+ `deposit_withdrawal[bank_account_id]` *(required)*. Bank account id for current user’s target account.
+ `deposit_withdrawal[password]` *(required)*. Current user’s password.

##### <a id="withdrawal-request-sample-request"></a> Sample Request
````sh
curl -u 204254:Sy7PRGGr4foUk22uzjMu -X POST "https://api.bukalapak.com/v1/dompet/withdraw.json" --data "deposit_withdrawal[amount]=25000&deposit_withdrawal[bank_account_id]=41812&deposit_withdrawal[password]=testing1234"

````

##### <a id="withdrawal-request-sample-response"></a> Sample Response
Success response:

````json
{
  "status":"OK",
  "withdrawal_id":4,
  "message":"Pencairan akan diproses oleh tim Bukalapak. Dana akan ditransfer ke rekening Anda dalam waktu 1x24 jam."
}
````

Invalid account ID:

````json
{
  "status":"ERROR",
  "withdrawal_id":null,
  "message":
  "Rekening pencairan harus milik Anda."
}
````

Invalid password:

````json
{
  "status":"ERROR",
  "withdrawal_id":null,
  "message":"Password tidak valid."
}
````

More than one withdrawal request in a day:

````json
{
  "status":"ERROR",
  "withdrawal_id":null,
  "message":"Pencairan hanya bisa dilakukan satu kali sehari."
}
````

More than one withdrawal request in a day and invalid password:

````json
{ 
  "status":"ERROR",
  "withdrawal_id":null,
  "message":"Pencairan hanya bisa dilakukan satu kali sehari., Password tidak valid."
}
````

#### <a id="dictionary"></a> Dictionary
- `type` Type of muation, possible values are `Deposit::Credit` and `Deposit::Debit`
- `action` Action that trigger mutation. Possible values are  `remit`, `topup`, `payment`, `refund`, `withdrawal`, `restore`. 
