# MSF Tariff Inquiry

This API is used to msf tariff inquiry. Merchants needs to add session token received during login API call in the header of this API.


## Endpoint

GET `https://www.uat.fdmerchantservices.com/Externalboarding/secure/msf/{msfId}`

## Payload Example

### Request Payload

```json
Path variabe : 
                example:
                99000154

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/msf/{msfId}`).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `msfId` | *Path variable* | 10 |  | Application Type |


### Successful Response Payload

```json


```

### Error Response Payload

```json
{
  "status": {
    "statusCode": 401,
    "message": "Token not found"
  }
}
```

### Response
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |





The table below provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`401` |Token not found|  
|`200` |Success|
|`300` |Request Failure|
|`500` |Internal Server Error|
|`404` |Not Found|
|`502` |Request Timed Out|
