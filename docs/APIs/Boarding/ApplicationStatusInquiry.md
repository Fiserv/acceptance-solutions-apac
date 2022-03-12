# Application Status Inquiry

This API is used to application status inquiry. Merchants needs to add session 
token received during login api call in the header of this API.


## Endpoint

GET `/Externalboarding/secure/appstatus/{appUrn}`

## Payload Example

### Request Payload

```json
Path Variable - appUrn : 1000007294

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/appstatus/{appUrn}).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `appURN` | *path Variable* | 10 | M | Application URN |

### Successful Response Payload

```json
{
	"appURN": "1000007294",
	"appType": "NEW",
	"appChannel": "TAB",
	"institutionId": "47",
	"salesId": "SureshBC",
	"status": null,
	"statusDate": null,
	"reason": null,
	"businessName": "test",
	"legalName": "test",
	"businessType": "Sole Proprietor",
	"submittedDate": 1643977173000,
	"createdDate": null,
	"lastUpdatedDate": null,
	"countofBacktoSales": "0",
	"mccCode": "5813",
	"merchantGrade": "EA",
	"merchantType": null,
	"acceptanceType": "POSMOB",
	"typeOfBusiness": "Sole Proprietor",
	"international": null,
	"iciciMerchant": "No",
	"dcc": null,
	"fundingCurrency": null,
	"channelCode": null,
	"boardingType": null,
	"newFundingAc": null,
	"institutionCode": null,
	"terminalId": "33917151",
	"mid": "96000842",
	"atsJobSheet": "",
	"preInstall": "false",
	"bcInstall": "false",
	"selfInstallStatus": "Initiate self install"
}
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
| `appURN` | *string* | 20 | M | Applicaiton URN |




Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`401` |Token not found|  
|`200` |Success|
|`300` |Request Failure|
|`500` |Internal Server Error|
|`404` |Not Found|
|`502` |Request Timed Out|
