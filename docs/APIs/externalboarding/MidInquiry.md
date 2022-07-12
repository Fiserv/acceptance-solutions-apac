# Mid Inquiry

This API is used to fetch the details of existing MID which merchants would have boarded in past.

## How it works
1. Merchant needs to use this API predominantly while boarding Additional Trading Location or Additional Device on existing MID.
2. API should be used before submitting Additional Trading Location or Additional Device Application request.


## Endpoint

GET `https://www.uat.fdmerchantservices.com/Externalboarding/secure/refmid/{appType}/{refmid}`

## Payload Example

### Request Payload

```json
Path variabe : 
                example:
                /ADDLTID/99000154
                /ADDLMID/99000745
```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/refmid/{appType}/{refmid}`).

### Request

| Variable | Type      | Length |  Mandatory / Optional/ Conditional (M / O / C) | Description / Values |
| -------- | ----------- | -- | ------------ | ------------------ |
|`appType`|Alphanumeric|8|M|Fixed Value **API**|
|`refMid`|Numeric|8|M|MID generated for the new application needs to be passed for generating Add MID & Add TID|




### Successful Response Payload

```json

{
  "appURN": null,
  "appType": null,
  "boardingType": null,
  "appChannel": null,
  "institutionId": null,
  "salesId": null,
  "channelCode": null,
  "osvFlagValue": null,
  "merchantGrade": null,
  "typeOfBusiness": null,
  "merchantDetails": {
    "businessName": null,
    "legalName": "ezetap provisioning testing",
    "businessType": "Sole proprietor",
    "registrationNo": null,
    "dateIncorporated": null,
    "websiteURL": null,
    "communicationEmail": "prerana.kumbhar@Fiserv.com",
    "legalAddress": {
      "addressLine": "Near central fire briged, Ganj peth,, opposite kamble lane, ",
      "addressLine2": null,
      "addressLine3": null,
      "city": "PUN-PUNE",
      "state": "MAH",
      "pincode": "411042",
      "country": null,
      "phone1": "8358353553",
      "phone2": null,
      "contactName": "Test",
      "mobileNo": null,
      "email": null
    },
    "fundingMethod": "NEFT",
    "clientTariff": null,
    "postingTariff": "NETINR",
    "billingLevel": "MID",
    "gstNo": "06AXVPM0608G1ZD",
    "isdnFlag": null,
    "gstMerchantStateCode": null,
    "idDocDetails": null,
    "geoLocation": null,
    "merchantGrade": null,
    "iciciMerchant": null,
    "newFundingAc": null,
    "taxDetails": {
      "taxidType": "businessPan",
      "taxidValue": null
    },
    "merchantType": null,
    "acceptanceType": null,
    "dcc": null,
    "international": null,
    "fundingCurrency": null
  },
  "submerchantDetails": null,
  "tradingLocations": [
    {
      "locationNo": 1,
      "tradingName": "ezetap provisioning te",
      "tradingAddress": {
        "addressLine": "test, , ",
        "addressLine2": null,
        "addressLine3": null,
        "city": "MUM-MUMBAI",
        "state": "MAH",
        "pincode": "400606",
        "country": null,
        "phone1": "8600433238",
        "phone2": "8600433238",
        "contactName": "Prerana",
        "mobileNo": null,
        "email": null
      },
      "sameLocation": false,
      "otpEnabled": false,
      "mid": "470000099000154",
      "leadsubgroupmid": "470000056000250",
      "subgroupmid": "470000056000251",
      "packageId": 0,
      "packageName": null,
      "packageDescription": null,
      "memberType": "POSMOB",
      "tariff": "RetailP185LM",
      "amexTariff": null,
      "merchantGrade": "EO",
      "acqProfile": null,
      "feePlans": null,
      "terminals": [],
      "msfProfile": "C120P185COR220IC000INC260D090",
      "cardedUncarded": null,
      "autoSettlementTime": null,
      "regionalCpvGroupId": null,
      "cpvGroupId": null,
      "commerceConnectReferenceMID": null,
      "altmerchCode": null,
      "isMsfTariffOverride": null,
      "packageOverride": null
    }
  ],
  "principalDetails": [
    {
      "principalNo": 1,
      "position": "Owner",
      "title": "Mr",
      "firstName": "Manan",
      "lastName": "Gupta",
      "middleName": null,
      "gender": null,
      "dateOfBirth": "04/05/1985",
      "principalAddress": {
        "addressLine": "Keshavnagar",
        "addressLine2": null,
        "addressLine3": null,
        "city": "PUN-PUNE",
        "state": "MAH",
        "pincode": "411036",
        "country": null,
        "phone1": "9426855672",
        "phone2": null,
        "contactName": "Manan",
        "mobileNo": null,
        "email": null
      },
      "idDocDetails": null,
      "kycDetails": [
        {
          "kycCategory": "Individual POA1 KYC",
          "identityType": "aadhar",
          "identityValue": "",
          "identitymetaName1": null,
          "identitymetaValue1": null
        },
        {
          "kycCategory": "Individual POI1 KYC",
          "identityType": "individualPan",
          "identityValue": "ABCDE1234F",
          "identitymetaName1": null,
          "identitymetaValue1": null
        }
      ],
      "nationality": null
    },
    {
      "principalNo": 2,
      "position": "Owner",
      "title": "Mr",
      "firstName": "Manan",
      "lastName": "Gupta",
      "middleName": null,
      "gender": null,
      "dateOfBirth": "04/05/1985",
      "principalAddress": {
        "addressLine": "Keshavnagar",
        "addressLine2": null,
        "addressLine3": null,
        "city": "PUN-PUNE",
        "state": "MAH",
        "pincode": "411036",
        "country": null,
        "phone1": "9426855672",
        "phone2": null,
        "contactName": "Manan",
        "mobileNo": null,
        "email": null
      },
      "idDocDetails": null,
      "kycDetails": [
        {
          "kycCategory": "Individual POA2 KYC",
          "identityType": "aadhar",
          "identityValue": "",
          "identitymetaName1": null,
          "identitymetaValue1": null
        },
        {
          "kycCategory": "Individual POI2 KYC",
          "identityType": "individualPan",
          "identityValue": "ABCDE1234F",
          "identitymetaName1": null,
          "identitymetaValue1": null
        }
      ],
      "nationality": null
    }
  ],
  "uboDetails": null,
  "bankDetails": {
    "accountNo": "12231000013575757",
    "accountName": "test",
    "ifsc": "JANA0000012",
    "bankName": "JANASEVA SAHAKARI BANK LIMITED",
    "branch": "",
    "currency": null,
    "accType": null,
    "fundingAccountDetails": null,
    "collectionAccountDetails": null,
    "uwAccountDetails": null
  },
  "businessSummary": {
    "briefSummary": null,
    "mccCode": "5999",
    "mccDescription": "Miscellaneous & spec",
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
  "keySelection": null,
  "preapproval_id": null,
  "countryCode": null
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
|`200`| Success |
|`400`| Generic Error |
|`401`| Unauthorized |
|`403`| Forbidden |  
|`500`| Not Found |
