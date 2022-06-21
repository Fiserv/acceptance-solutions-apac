# Create URN

This API is used to create URN. Merchants needs to add session token received during login API call in the header of this API.


## Endpoint

POST `https://www.uat.fdmerchantservices.com/Externalboarding/secure/create`

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

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/create).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `appType` |	*Alphanumeric* |	8 |	M	| Fixed Value 'API' |
| **KeySelection** |	 |	 | |	This is the object |
| `boardingType` | *Alphanumeric* |	20 |	M |	Type of Merchant: NEWMID/ADDMID/ADDTID |
| **MerchantDetails** | |	 |  |	This is the object |
| `businessName` |	*Alphanumeric* |	64 | M | Trade Name of the Merchant |
| `legalName` |	*Alphanumeric* |	64	| M	 | Legal Name of the Merchant |
| `institutionId` |	*Numeric* |	10 | O | Institution number assigned to the institution |
| `countryCode` |	*Numeric* |	10 | O	| Country code where the institution belongs  |


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




THe table below provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`200`| Token not found | 
|`401`| Unauthorized | 
|`100`| Invalid Request | 
|`702`| Unable to create merchant | 
|`500`| Internal Error, Please contact application support team | 
