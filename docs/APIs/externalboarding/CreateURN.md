# Create URN

This API is used to create a unique reference number (URN) for each new application that is onboarded onto Fiserv platform.

## How it works
1. Merchant needs to use this unique value for all subsequent API requests where URN is a mandatory request parameter.
2. Merchant needs to create a URN for application before submitting any application request to Fiserv Boarding Platform.
3. This step is mandatory for boarding.


## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/create`

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
| Variable | Type | Length |  Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
| `appType` |	*Alphanumeric* |	8 |	M	| Fixed Value API |
| **KeySelection** |	 |	 | |   |
| `boardingType` | *Alphanumeric* |	20 |	M |	Type of merchant: NEW MID / ADD MID / ADD TID |
| **MerchantDetails** | |	 |  |	  |
| `businessName` |	*Alphanumeric* |	64 | M | Trade name of the Merchant. |
| `legalName` |	*Alphanumeric* |	64	| M	 | Legal name of the Merchant. |
| `institutionId` |	*Numeric* |	10 | O | Institution number assigned to the institution. |
| `countryCode` |	*Numeric* |	10 | O	| Country code where the institution belongs.  |


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


The table below provides the list of application's error code and its description.

| Error Code |  Description / Values |
| --------  | ------------------ |
|`200`| Token not found. | 
|`401`| Unauthorized | 
|`100`| Invalid request | 
|`702`| Unable to create merchant. | 
|`500`| Internal error, please contact application support team. | 
