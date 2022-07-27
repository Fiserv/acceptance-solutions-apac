# Login

This API authenticates the external client with the unique credentials shared with each partner. This API respond back with a session token & expiry time for the session token. This token is required in header of each subsequent API triggered by partner.

## API Category: Mandatory

## How it works

1. Merchants need to initiates a Login request to fetch a session token before submitting any APIs to Fiserv backend system.
2. If merchant tries to use the token beyond the session token’s expiry period, Fiserv backend system will return with an error response. 
3. The merchant will then need to initiate another login request to request for a fresh token, in order to submit any of the Boarding APIs.
4. This is a Mandatory API that has to be triggered first to create a session token.

## Endpoint

`https://www.uat.fdmerchantservices.com/Externalboarding/partner/login`

## Payload Example

### Request Parameters

```
?ain=4700000&source=API

*** Get Token from above api and need to pass the same token to other APIs.***

``` 

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/partner/login).

The table below identifies the required parameters in the request payload.

| Variable |	Type |	Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- | ------------------ | ------------------ |
|`username`|	String|	15|	M|	User Id / Fiserv Lan ID |
|`password`|	String|	15|	M|	Password |
|`source`|	String |	10|	M|	Source Type like API / TAB |
|`ain`|	String	 |16|	M|	This is a query parameter which should be keyed as a part of request|


### Successful Response Payload

```json
  {
  "authToken": "eyJhbGciOiJBMTI4S1ciLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0.Lb1bHTkIf39A3aZjPQlovMegOPquGZQxNZHMMmBkodKYFgEKkSoocQ.ouWgCX3kAAt3yxFTLsZjQw.hEkAaKujQuNj7_3L2WjtKyY2pf-lRv5ARTMNq1-YQWGnSDWswEsxba6BY4n8gifp07eKdw7c9cYtGWcnZ1FCRJaKJqHAn8dn55xOjYEYFv8JRCZI4KHjAPIgkHhKZrxuKFw8hPRkzFx5ANC4MMetTizAlgKx8f0JUvhSF1qVzhBMwHUqw4seG2D7fDCMlNujLGWRJrU_Dz9BIW7yWMKkN8kXho7A3lC7QeMR7k1_NJb7aEQ_m8hO0Cb9tP9Sc2ivSjMg4yGtOvo3WAegbfsahJsfknYODV5Pj0jignTIcx7SLNfjUMMzFOVuv7dSRaQl52xYCAu0zxrWBnF3QmaZROejY55Fm3gBHKChPP2q1gcsDLX9vBW_TgpKD7sLOh_ltjDUNCJPCjujGZJfRDdW5IurGcNpif075zEdSvydENwV_5KJj1bPjOFPENWDJEhvCQbQsNmMES6qYeSouS2epl6X6UoFcCoIrVK9geyOdOJPtYK5kwDdkGCmJPlnc6OfPgjdVMqep1KwYkQOzqVrnnihP1wj7Ei-W94UvS6fVGvB2nR55fJz-Ztoy7zez7HV6D0HETcPDaA_gz8fsHuHZc4KhDwTrB452iWjAB-Eed93AtKGVUPuty2VPfis_tt4QqWMQMqNQeOGRoViSgmeixnZmYhz9z3tkF-bFAc_DSB_WvPlnxzcYRxSB7q4LYgDImJETHJDi_OSPreqoaneCTjTJoeXOOTtj7qHEj99N47UeXOIvK3W1UFta7pjcpDFbbir2zrpVvyhHtuOEtbDJXxqiUDbuc80HfpsgsBwtnbZWavJg7ABUea165EkLjdgqHFvV2da2FCV3Qq6v2pS5hufLNfpw9yOAD-czZrLeH5DaRMcHhEDkYDlYhQmcwKwsPA-rHgqFGYNLZWyWFIZH0VEPsCsoY74ptJ93uKthtgiHszfNsX7Qm8J5q25W6-QhbHdfY0WRdiK3U3Ym2H_8vK-Vgk1CKZX_NwqZWfcyCdDjtMB6x3EkOUqNYS-OsXpFrH-v9WareSrlFkgbNIY5LD4TdTu8wuid7-V8XQ1q54B4VPXCAt3q9Pcevt3RnpDzsDVS-1kkoGq4N8aj3TwAugB91PaqvhROWWEEwdRbNhugKbKRHtVW9oyDAkmVKjJx8hkFLkFMWbCeeyipuZH-MhhZBVIX0DabEHX7IJMvVOAiR9rtAgfUmJ5VrTud52dao1pMPnOt7xgWxocG3KHBbNIwk9_ub0kutLQ4P0eaFGIluqhfnJYz1nTzM_EU4CIKpI-LVcknWuNMmHbJlsvcFlsYTH-P74uJVz-UziKEMMqrmYeH--dZwEwLTD7Z5rnS8HPD1GDt8FhySXLjrKDCGeBG2dgo4HD3DNCRjDnONU.hk_0ZUHha82WP7NVj9EzOQ",
  "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJjb20uZmlzZXJ2LmNvbSIsImF1ZCI6IkZpc2VydiBHQlMiLCJUWVBFIjoiUkVGUkVTSCIsImV4cCI6MTY0NTg3MjcwMCwianRpIjoiaDlaWnR5cUJESWZKSmFFU2JrTi1vdyIsImlhdCI6MTY0NTY5OTkwMCwibmJmIjoxNjQ1Njk5NjAwLCJ2ZXJzaW9uIjoiMS4wIiwic3ViIjoicHJlcmFuYWF1cyJ9.GMFTfttx9ClDBViB8OshCJBMtEfSDisi_O75nYRUgd4",
  "ttl": 30
}
```

### Error Response Payload

```json
{
  "status": {
    "statusCode": 402,
    "message": "Bad Credential"
  },
  "data": {}
}
```

The table below provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`200`| Token not found | 
|`401`| Unauthorized |  
|`403`| Forbidden |
|`404`|  Not found |  
|`400`| Generic Error |