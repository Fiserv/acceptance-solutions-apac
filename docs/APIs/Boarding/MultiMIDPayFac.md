# Multiple MID Payfac

This API is used to multiple mid payfac. Merchants needs to add session 
token received during login api call in the header of this API.


## Endpoint

GET `/Externalboarding/secure/newmid`

## Payload Example

### Request Payload

```json

{
"appURN": "1000007802",
"appType": "API",
"salesId": "BharatPEPFAC",
"channelCode": "Bharat_PE",
"institutionId":"47",
"osvFlagValue": "",
"merchantDetails": {
"businessName": "Test",
"legalName": "Test Merchant",
"businessType": "Sole Proprietor",
"registrationNo": "5678325544",
"dateIncorporated": "17-01-2022",
"websiteURL": "",
"communicationEmail": "test@gmail.com",
"merchantType": "Small",
"acceptanceType": "POSMOB",
"iciciMerchant": "No",
"newFundingAc": "No",
"legalAddress": {
"addressLine": "Hyderabad",
"addressLine2": "",
"addressLine3": "",
"city": "YELLAREDDY",
"state": "AP",
"pincode": "503122",
"country": "IN",
"mobileNo": "9440958263",
"phone1": "0",
"contactName": "Test Merchant"
},
"taxDetails": {
"taxidType": "PAN",
"taxidValue": "DGLPS4788D"
},
"gstNo": "114333211",
"gstMerchantStateCode": "AP",
"isdnFlag": "No"
},
"tradingLocations":[ {



"tradingName": "Test",
"locationNo": "56",
"tradingAddress": {
"addressLine": "Hyderabad",
"addressLine2": "",
"addressLine3": "",
"city": "Hyderabad",
"state": "AP",
"pincode": "500081",
"country": "IN",
"mobileNo": "9440958263",
"phone1": "0",
"contactName": "test name"
},
"packageId": "14872",
"autoSettlementTime": "",
"cpvGroupId": "",
"regionalcpvGroupid": "",
"commerceConnectReferenceMID": "",
"altmerchCode": "",
"sameLocation": "true",
"mid": "",
"parentmid": "",
"otpEnabled": "",
"terminals": [
{
"count": "1",
"preferedDate": "20220117",
"preferedTime": "1701175",
"discount": "",
"userInstruction1": "",
"userInstruction2": ""
}
]
}],
"principalDetails":[ {
"principalNo": "1",
"position": "Manager",
"title": "Mr",
"firstName": "Test principal",
"lastName": "s",
"middleName": "",
"gender": "Male",
"dateOfBirth": "04-04-1998",
"nationality": "",
"principalAddress": {
"addressLine": "Hyderabad",
"addressLine2": "",
"addressLine3": "",
"city": "Hyderabad",
"state": "TS",
"pincode": "500081",
"country": "IN",
"mobileNo": "9440958263",
"phone1": "0",
"contactName": "Test Principal"
},
"kycDetails": [{
"kycCategory": "POI",
"identityType": "PAN",
"identityValue": "DGLPS4788D",
"identitymetaName1": "",
"identitymetaValue1": ""
}]
}],
"businessSummary": {
"briefSummary": "summary",
"salessrNumber": "",
"mccCode": "5912",
"mccDescription": "electronics",
"totalTurnover": "100000",
"totalTurnoverPerMID": "10000",
"cardTurnover": "1000",
"avgTicketAmt": "1000",
"dccTurnoverPerMID": "1000",
"pgTurnover": "100000",
"pgTurnoverPerMID": "10000",
"avgEMITicketAmt": "",
"tranVolumeInternet": "1000",
"tranVolumeMoto": "1000",
"tranVolumeInStore": "1000",
"deliveryDays0": "1000",
"deliveryDays7": "1000",
"deliveryDays14": "1000",
"deliveryDays30": "1000",
"deliveryDaysOver30": "1000",
"tranTypeMagStrip": "0",
"tranTypeChip": "100",
"tranTypeKeyed": "0",
"creditSalesConsumer": "1000",
"creditSalesBusiness": "1000",
"firsReport": "",
"recurringTranFlag": "",
"refundPolicy": "",
"cardRefundDays": "",
"thirdPartyProcessorFlag": "",
"thirdPartyProcessorName": "",
"smallMerchant":"Y"
}
}

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/newmid``).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `appType` | *Path variable* | 10 |  | Application Type |


### Successful Response Payload

```json

{
  "status": {
    "statusCode": 200,
    "message": "Success"
  },
  "data": {
    "appurn": "Application URN",
    "leadsubgroupmid": "Lead Sub Group MID",
    "SGArray": [
      {
        "subgroupmId": "Sub Group MID",
        "merchantId": "Member MID",
        "submerchantId": "Submerchant ID",
        "terminals": [
          "Terminal ID 1",
          "Terminal ID 2"
        ]
      }
    ]
  }
}

```

### Response
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |





Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`100`| Invalid Request |
|`103`| Data Not Found.Please contact Application Support Team |
|`200`| Success |
|`302`| IO Exception |
|`404`| Not Found |
|`401`| Unauthorized |	
|`500`| Internal Error.Please contact Application Support Team |
|`505`| Internal server Error. Please contact Application Support Team |
|`708`| AppURN already submitted |
|`902`| AppURN is Mandatory |
|`903`| Application already Submitted |
|`904`| Json Processing Error |
|`905`| Json Parse Error |
|`906`| Json Mapping Error |
|`907`| Comments are empty |
|`908`| App URN not matching |
|`909`| Given Merchant Hierarchy Cannot handle via TAB. Please contact Application Support Team |
|`910`| Given Merchant Id Doesnt qualify for Add Outlet. Please contact Application Support Team |
|`911`| Given Merchant Super MID is Inactive. Please contact Application Support Team |
|`912`| One of MID in hierarchy is Inactive. Please contact Application Support Team |
|`913`| Please use member level Mid.Please contact Application Support Team |
|`914`| Ref MID should be 8 digits |
|`915`| Business Rule Exception |
|`916`| All Adress Types are not available for Ref MID.Please contact Application Suport Team |
|`917`| No Services avaiable for Ref MID. Please contact Application Support Team |
