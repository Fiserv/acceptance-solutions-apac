# Login

This API authenticates the external client with the unique credentials shared earlier as part of initial setup. This API respond back with a session token & expiry time for the session token. This token is required in header of each subsequent API triggered by partner.

## Endpoint

`/getToken`

## Payload Example

### Request Payload

```json
{
  "encryptData": "pv1SuId0Ca8YxWBGVBHD/e6yT1PRH8Ps4pmm6vatlcEu1xtm33Xay36ago2Ll0QNK3QpS5tRQXqhWnbLVcsTd6PzHRV+LQ6jx8OKwjmP9aQtIlY8wIAS1WxUcLPNaVb/I6qp49bERPToOLREts/X7i5g7QO/Mpd8Q7WNYT6dIKVSZ1XO8y4Yrzk8Lh5OfiqGVc4ulv99zbMZbawiN+1dmQgyzMlM9nyUa8oyoCBP2wmJjjJS83dS5Ic809cqMxqjMi1s47mNroag94WdklV41cmBDaQ3RGKQySCD7YWghocy1t0JI/QjBqF0lo32gCDYowUPHL8YnlxFdkJiqDnljePzOyNRX0wQdoEZEIx/f3pNv3XRLYVusvUMgwF6OppjdpfZW1a5ZsjnK0u2GD0GNlpUtyQjnjQsWBwgJlb6C9sRRiqeaEogPudQaoNdHjPqPvOwUYXsbGZ7sHIxpr3LPSlT4TuGKdaIpHVHFHbno2mtZweWyB1I+AnYJ97LhAdEnZOCxO+8gcuiq5nrWmMfoSGgFx/cNvo0M/zo90JJNKcTAAgdyPi6GV/VJ0g47F2ph3PI+QYaU8gizlBbwpBuNPPX2QeoEo879S1xywLjkbIDa37j21nq5i8ajzqpKmSC7LDRPKVP93kp2Tp/BFLa9Xm7EcVqqfhNI+yMBuE8lb7OQ4OXEYy3e9ZMhXkOHnWjfthgRdsy0g9nOeYEh35fsjIE757aWGOfl03u+bRn4RrXKFxo+sJ1r/CHrY4YeTY0LfiO2i72mbI4ENRuzVZTuXgx01wCCnHLZbrqsYd60SNdd4GwXq22Hm6HdZpDMnlZ5+9MvPlHnRyRli9pN/TdfWCuyYk9J64GXJkyUrDv4exm6y15hBCPrqs7NWs0YJYAy8JhqF5QnR7p6SeBlY7Sv4+iqYfk+QAgdjkJDDa4Lu4Gwo1LpJxR15osvex5frC2gZA+s5rJYL4WZLdnpHW0GB+HTvrTDYWSpU546RydhqVz25cNQu2WHtpeHeT4txtW5+UVKxm1Lo+q5EIIxoYtoJSSUrHc9Gsea/AS0ABkqwt2787Y8wzjj/BJTKTqR5o5rNCOpKVL0tFrv/3I1grbJnH2GVUwatYrWQ6PfL40G+3NmJgVRn67cu9mGZKEFOhrVEgNi35MSze+lLHzlq4EAS6+uTLwQvftRnQ02lXqwkX9lSA12F2un1pc805T4SBU6QdPCtP0wGPbgRkluNGaVdspK0Dbxo525o+3SLgVpNR4VrfcBh/QwFeNm6sj5ggyy6gQ3Pc3lIsNcbv1vf+H4B2HjZWBEK2cFP8UY93W4/uHPIWJCC7mlp1Tfi2Uxso9+bp6hHYaykj1ftU1p1qSQz/uxN9W2Etp/g+sH6jaVF9ajk2xItEcwAP0aiS//6PXKh1V7jwO003JuvniX+4C4dVIB1r8Z77kCriHDJ9DU4TjeDNKDgsgOKI6njLOcca0HqAd595Wli/vv1H0wwMy9FqfTeWFb+bj2fl3Y/tjduG2FlaNNT33EQGIjvVPeOGGL25r9qtbPI9qytl5CJw89oi++Fh0f3rjDhqhDyQlBGnVmBrThS9WeZZ3wgjiWVHXGbv5euFHoR8Ip2a/tcepgAb0G6/datzaVEbAjrNbQZK96gSneIWHeasLQgIn3eyDX+16yG/BPG5ZXWbnQzTmRqVGJtypTv7x51N6M90Ivu32oWUbbgA8nBHaFKYbhSi1yYol+YCraOlZAUhWyBeS2w=="
}

*** Get Token from above api and need to pass the same token to other apies.***
}
``` 

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/getToken).

The below table identifies the required parameters in the request payload.

| Variable | Passed as | Type | Description/Values |
| -------- | :-------: | :--: |  ------------------ |
| `encryptData` | Json property | *String* | Encrypted String |
| `keyValue` | Header | *string* |  Key Value |
| `ivValue` | Header | *string* |  IV Value |

### Successful Response Payload 

```json
{
  "status": {
    "statusCode": 200,
    "message": "Success"
  },
  "data": {
    "token": "Wl3iTXZWZVrhoqNIiFPNwLBYe32NyTvh",
    "userName": "bocmuser1"
  }
}


```

### Error Response Payload

```json
{
  "response": {
    "errorCode": "FPDR4002",
    "errorMessage": "HMAC is empty"
  }
}
```

Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
| `FPDR4002` | HMAC is empty.|
