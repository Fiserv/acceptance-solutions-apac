# Login

As part of the initial set-up, prior to integration, merchants would have received unique credentials as part of the set up process.
Login API authenticates merchants’ unique credentials, with a response that 

- Includes a session token
- Expiry time of the session token
- This token is mandatory in the header submitted for each API being triggered. 


## API Category: Mandatory

## How it works

1. Merchants need to initiate a Login request to fetch a session token before submitting any APIs to Fiserv backend system.
2. Each session token is active for a specific amount of time provided in ttl (time to live) field in the response message.
3. If the merchant tries to use the token beyond the session token’s expiry period, Fiserv backend system will return with an error response.
4. The merchant will then need to initiate another login request to request for a fresh token, in order to submit any creation of new user request.


## Endpoint

`https://www.uat.fdmerchantservices.com/boardinggateway/boarding/auth/signin`

## Payload Examples

### Request Payload

```json
{
  "username": "Testuser135",
  "password": "Test@1234"
}
*** Get Token from above api and need to pass the same token to other apies.***
}
``` 

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/boardinggateway/boarding/auth/signin).

The table below identifies the required parameters in the request payload.

| Variable | Passed as | Type | Length | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
| `username` | JSON Property | *string* | 15 | User ID. |
| `Password ` | JSON Property | *string* | 15 | Password. |

### Successful Response in Payload

```json
{
  "status": {
    "statusCode": 200,
    "message": "Success"
  },
  "data": {
    "token": "Wl3iTXZWZVrhoqNIiFPNwLBYe32NyTvh",
    "userName": "Testuser135"
  }
}
```

### Error Response in Payload

```json
{
  "status": {
    "statusCode": 402,
    "message": "Bad Credential"
  },
  "data": {}
}
```

The table below provides the list of error codes and description for this application.


|  Error Code | Description / Values | Comments | 
| -------- | ------- | -- |
| `200` | Request executed. |  Request is successfully processed. Merchant should use the generated token and proceed with Payment API transaction Initiation.  | 
| `300` |   Request failure. |  Redirection error. Merchant should validate and retry with new request. |
| `402` |   Bad Credential. |  Invalid Credentials. | 
| `404` |  Not found. |   Server cannot find the requested resource. Contact Customer Support / Business Manager.  | 
| `500 ` |   Internal Server Error. |  Server Error. Contact Customer Support / Business Manager. | 
