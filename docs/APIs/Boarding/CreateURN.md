# Create URN

This API is used to create URN. Merchants needs to add session 
token received during login api call in the header of this API,


## Endpoint

POST `/Externalboarding/secure/create`

## Payload Example

### Request Payload

```json
{
  "appType" : "API",
  "salesId" : "ecomuser",
  "channelCode" : "EAZYAPY_ECOM",
  "keySelection" : {
    "boardingType" : "NEWMID"
  },
  "merchantDetails" : {
    "businessName" : "ECOM",
    "legalName" : "ECOM"
  },
  "institutionId" : "47",
  "countryCode" : "IND"
}

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/create).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `merchantId` | *string* | 20 | M | Merchant ID |

### Successful Response Payload

```json
{
	"appURN": "1000007936",
	"appType": "API",
	"boardingType": null,
	"appChannel": null,
	"institutionId": "21",
	"salesId": "preranaaus",
	"status": "Saved",
	"statusDate": null,
	"keySelection": {
		"mccCode": null,
		"merchantGrade": null,
		"merchantType": null,
		"acceptanceType": null,
		"typeOfBusiness": null,
		"international": null,
		"iciciMerchant": null,
		"dcc": null,
		"fundingCurrency": null,
		"newFundingAc": null
	},
	"channelCode": "TestAUS",
	"osvFlagValue": null,
	"countryCode": "IND",
	"leadId": null,
	"merchantDetails": {
		"businessName": "PAYFAC",
		"legalName": "PAYFAC",
		"businessType": null,
		"registrationNo": null,
		"dateTrading": null,
		"dateIncorporated": null,
		"websiteURL": null,
		"communicationEmail": null,
		"legalAddress": null,
		"fundingMethod": null,
		"clientTariff": null,
		"postingTariff": null,
		"billingLevel": null,
		"gstNo": null,
		"isdnFlag": null,
		"gstMerchantStateCode": null,
		"merchantType": null,
		"acceptanceType": null,
		"iciciMerchant": null,
		"newFundingAc": null,
		"merchantGrade": null,
		"idDocDetails": null,
		"geoLocation": null,
		"taxDetails": null
	},
	"tradingLocations": null,
	"principalDetails": null,
	"bankDetails": null,
	"businessSummary": {
		"briefSummary": null,
		"mccCode": null,
		"mccDescription": null,
		"totalTurnover": null,
		"totalTurnoverPerMID": null,
		"dccTurnoverPerMID": null,
		"pgTurnover": null,
		"pgTurnoverPerMID": null,
		"cardTurnover": null,
		"avgTicketAmt": null,
		"avgEMITicketAmt": null,
		"tranVolumeInternet": null,
		"tranVolumeMoto": null,
		"tranVolumeInStore": null,
		"deliveryDays0": null,
		"deliveryDays7": null,
		"deliveryDays14": null,
		"deliveryDays30": null,
		"deliveryDaysOver30": null,
		"tranTypeMagStrip": null,
		"tranTypeChip": null,
		"tranTypeKeyed": null,
		"creditSalesConsumer": null,
		"creditSalesBusiness": null,
		"firsReport": null,
		"recurringTranFlag": null,
		"refundPolicy": null,
		"cardRefundDays": null,
		"thirdPartyProcessorFlag": null,
		"thirdPartyProcessorName": null,
		"smallMerchant": null
	},
	"uboDetails": null
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
| `merchantId` | *string* | 20 | M | Merchant ID |




Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`401` |Token not found|  
|`200` |Success|
|`300` |Request Failure|
|`500` |Internal Server Error|
|`404` |Not Found|
|`502` |Request Timed Out|
