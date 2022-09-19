# Application Status Inquiry

This API is used to fetch the latest status of any boarding application for merchants.

## How it works
1. Merchant needs to use this API by keying the Application URN in request Message.
2. Merchant has to trigger this API post submitting a particular boarding application.


## Endpoint

GET `https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/appstatus/{appUrn}`

## Payload Example

### Request Payload

```json
Path Variable - appUrn : 1000007294

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/appstatus/{appUrn}).

### Request
| Field Name |	Type |	Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- | ------------------ | ------------------ |
| `appURN` | Alphanumeric | 30 | M | App URN retured as part of Create URN API |

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

The table below provides the list of application's error code and its description.
| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`100`| Invalid Request |
|`103`| Data Not Found.Please contact Application Support Team |  
|`200`| Success |
|`400`| Generic Error |
|`401`| Unauthorized |
|`500`| Internal Error. Please contact Application Support Team |  

