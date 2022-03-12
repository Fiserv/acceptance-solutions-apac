# Additional Device

This API is used to additional device. Merchants needs to add session 
token received during login api call in the header of this API,


## Endpoint

POST `/Externalboarding/secure/addtid`

## Payload Example

### Request Payload

```json
{
  "appURN": "1000008471f",
  "appType": "Tab",
  "boardingType": "ADDLMID",
  "appChannel": "A12",
  "institutionId": "47",
  "salesId": "SureshBC",
  "status": null,
  "statusDate": null,
  "keySelection": {
    "mccCode": "5999",
    "merchantGrade": "EO",
    "merchantType": "LG",
    "acceptanceType": "POSMOB",
    "typeOfBusiness": "SOLPROR",
    "international": "No",
    "iciciMerchant": "No",
    "dcc": "No",
    "fundingCurrency": "NET_INR",
    "newFundingAc": "No"
  },
  "channelCode": "ISO Channel1",
  "osvFlagValue": "Y",
  "cardedUncarded": "Yes",
  "countryCode": "IND",
  "leadId": null,
  "merchantDetails": {
    "businessName": "Tets",
    "legalName": "ezetap provisioning testing",
    "businessType": "Sole Proprietor",
    "registrationNo": "829282",
    "dateTrading": null,
    "dateIncorporated": "25-03-2000",
    "websiteURL": "",
    "communicationEmail": "Prerana.kumbhar@firstdata.com",
    "legalAddress": {
      "addressLine": "Near central fire briged, Ganj peth",
      "addressLine2": ",, opposite kamble lane,",
      "addressLine3": "",
      "city": "PUN-PUNE",
      "state": "MAH",
      "pincode": "411042",
      "country": null,
      "phone1": "8358353553",
      "phone2": "",
      "contactName": "Test",
      "mobileNo": null,
      "email": "prerana.kumbhar@firstdata.com"
    },
    "fundingMethod": "NEFT",
    "clientTariff": null,
    "postingTariff": "NET_INR",
    "billingLevel": "01",
    "gstNo": "27AAOFN4566A1Z6",
    "isdnFlag": null,
    "gstMerchantStateCode": "27",
    "merchantType": "LG",
    "acceptanceType": "POSMOB",
    "iciciMerchant": "No",
    "newFundingAc": "No",
    "merchantGrade": "EO",
    "idDocDetails": [
      {
        "entity": "Member",
        "idType": "Capture the Merchant Store Photos",
        "idValue": "",
        "docId": "37ea3324bea6404bbc23a3bf78f4d238",
        "categoryName": "LOCATION PHOTOS",
        "level": "1",
        "mandatory": "Y"
      },
      {
        "entity": "Member",
        "idType": "MITC Document Page 1",
        "idValue": "",
        "docId": "cad26f43ff4c4956b30b2230727df1d2",
        "categoryName": "MITC",
        "level": "1",
        "mandatory": "Y"
      },
      {
        "entity": "Member",
        "idType": "MITC Document Page 2",
        "idValue": "",
        "docId": "e28aea1da58c41c6b37c137e379f1ce1",
        "categoryName": "MITC",
        "level": "2",
        "mandatory": "Y"
      },
      {
        "entity": "Member",
        "idType": "socDocument",
        "idValue": "",
        "docId": "073e4a4c5c9b4311895f0a0527b04dbd",
        "categoryName": "SOC",
        "level": "1",
        "mandatory": "Y"
      }
    ],
    "geoLocation": {
      "latitude": "12.9403189",
      "longitude": "77.7303295"
    },
    "taxDetails": {
      "taxidType": "businessPan",
      "taxidValue": "AAOFN4566A"
    }
  },
  "tradingLocations": [
    {
      "locationNo": 1,
      "tradingName": "jhcjgjcg",
      "tradingAddress": {
        "addressLine": "Near central fire briged, Ganj peth",
        "addressLine2": ",, opposite kamble lane,",
        "addressLine3": "",
        "city": "PUN-PUNE",
        "state": "MAH",
        "pincode": "411042",
        "country": null,
        "phone1": "8358353553",
        "phone2": "",
        "contactName": "Test",
        "mobileNo": null,
        "email": "prerana.kumbhar@firstdata.com"
      },
      "packageId": 1771,
      "packageName": "Add Indi Base Merchant - Add MID",
      "packageDescription": "Add Indi Base Merchant - Add MID",
      "memberType": "POS",
      "tariff": null,
      "amexTariff": "Amex Miscellane",
      "merchantGrade": "EO",
      "acqProfile": "International",
      "msfProfile": null,
      "mid": "470000099000154",
      "leadsubgroupmid": "470000056000250",
      "subgroupmid": "470000056000251",
      "otpEnabled": false,
      "feePlans": [
        {
          "serviceName": "Cashback",
          "feePlan": "0075"
        },
        {
          "serviceName": "UPI",
          "feePlan": "Y"
        },
        {
          "serviceName": "BHARATQR",
          "feePlan": "Y"
        },
        {
          "serviceName": "TONETAG POD",
          "feePlan": "Y"
        },
        {
          "serviceName": "Charge Slip Type",
          "feePlan": "P"
        },
        {
          "serviceName": "Debit plus pin",
          "feePlan": "Y"
        },
        {
          "serviceName": "BILLING SOLUTION",
          "feePlan": "Intuition"
        },
        {
          "serviceName": "Razor Netbanking",
          "feePlan": "Y"
        },
        {
          "serviceName": "Instant Settlement",
          "feePlan": "1"
        },
        {
          "serviceName": "Integrator_PMS solution",
          "feePlan": "MICROS PMS"
        },
        {
          "serviceName": "Auto Settlement Time",
          "feePlan": "Y"
        },
        {
          "serviceName": "Chargeslip Table ID",
          "feePlan": "TableCh"
        },
        {
          "serviceName": "Ocean UI User Group",
          "feePlan": "GroupCh"
        },
        {
          "serviceName": "Theme ID",
          "feePlan": "ThemeCh"
        }
      ],
      "autoSettlementTime": null,
      "cpvGroupId": "",
      "regionalcpvGroupid": null,
      "commerceConnectReferenceMID": null,
			"isMsfTariffOverride":null,
      "terminals": [
        {
          "terminalType": "APOS",
          "terminalModel": "APOS",
          "batteryFlag": "N",
          "count": 1,
          "currencyCode": null,
          "templateId": null,
          "socScheme": null,
          "services": [
            {
              "serviceName": "AMEX",
              "serviceValue": "N"
            },
            {
              "serviceName": "DCC",
              "serviceValue": "Y"
            }
          ],
          "withBiller": "Yes",
          "billingSolProvider": "Intuition",
          "preferedDate": "03-07-2022",
          "preferedTime": "15:09",
          "discount": "0",
          "tdrPlan": null,
          "userInstruction1": "",
          "userInstruction2": "",
          "cpvGroupId": null
        }
      ],
      "amcFee": null,
      "cardedUncarded": "Uncarded",
      "altmerchCode": null,
      "sameLocation": "false"
    }
  ],
  "principalDetails": [
    {
      "principalNo": 1,
      "position": "Owner",
      "title": "Mr",
      "firstName": "Manan",
      "lastName": "Gupta",
      "middleName": "",
      "gender": null,
      "dateOfBirth": "04-05-1985",
      "nationality": "INDIAN",
      "principalAddress": {
        "addressLine": "Keshavnagar",
        "addressLine2": "",
        "addressLine3": "",
        "city": "PUN-PUNE",
        "state": "MAH",
        "pincode": "411036",
        "country": "India",
        "phone1": "9426855672",
        "phone2": "",
        "contactName": "Manan",
        "mobileNo": null,
        "email": null
      },
      "idDocDetails": null,
      "kycDetails": [
        {
          "kycCategory": "Individual POA1 KYC",
          "identityType": "aadhaar",
          "identityValue": "000000006746",
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
      ]
    },
    {
      "principalNo": 2,
      "position": "Owner",
      "title": "Mr",
      "firstName": "Manan",
      "lastName": "Gupta",
      "middleName": "",
      "gender": null,
      "dateOfBirth": "04-05-1985",
      "nationality": "INDIAN",
      "principalAddress": {
        "addressLine": "Keshavnagar",
        "addressLine2": "",
        "addressLine3": "",
        "city": "PUN-PUNE",
        "state": "MAH",
        "pincode": "411036",
        "country": "India",
        "phone1": "9426855672",
        "phone2": "",
        "contactName": "Manan",
        "mobileNo": null,
        "email": null
      },
      "idDocDetails": null,
      "kycDetails": [
        {
          "kycCategory": "Individual POA2 KYC",
          "identityType": "aadhaar",
          "identityValue": "000000007546",
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
      ]
    }
  ],
  "bankDetails": {
    "fundingAccountDetails": null,
    "collectionAccountDetails": null,
    "uwAccountDetails": {
      "accountNo": "12231000013575757",
      "accountName": "test",
      "ifsc": "JANA0000012",
      "bankName": "JANASEVA SAHAKARI BANK LIMITED",
      "branch": "CAMP",
      "currency": "INR",
      "accType": "Savings"
    }
  },
  "businessSummary": {
    "briefSummary": "test",
    "mccCode": "5999",
    "mccDescription": "Miscellaneous and Specialty Retail Stores",
    "totalTurnover": "0",
    "totalTurnoverPerMID": "0",
    "dccTurnoverPerMID": "0",
    "pgTurnover": "25",
    "pgTurnoverPerMID": "5",
    "cardTurnover": "2525",
    "avgTicketAmt": "25",
    "avgEMITicketAmt": "0",
    "tranVolumeInternet": "0",
    "tranVolumeMoto": "0",
    "tranVolumeInStore": "100",
    "deliveryDays0": "100",
    "deliveryDays7": "0",
    "deliveryDays14": "0",
    "deliveryDays30": "0",
    "deliveryDaysOver30": "0",
    "tranTypeMagStrip": "0",
    "tranTypeChip": "100",
    "tranTypeKeyed": "0",
    "creditSalesConsumer": "0",
    "creditSalesBusiness": "100",
    "firsReport": "Not Required",
    "recurringTranFlag": "No",
    "refundPolicy": null,
    "cardRefundDays": null,
    "thirdPartyProcessorFlag": "No",
    "thirdPartyProcessorName": null,
    "smallMerchant": "Y"
  },
  "uboDetails": null
}

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/addtid).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `merchantId` | *string* | 20 | M | Merchant ID |

### Successful Response Payload

```json
{
  "status": {
    "statusCode": 200,
    "message": "SUCCESS"
  }
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
