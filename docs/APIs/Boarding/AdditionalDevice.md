# Additional Device

This API is used to additional device. Merchants needs to add session 
token received during login api call in the header of this API,


## Endpoint

POST `/Externalboarding/secure/addtid`

## Payload Example

### Request Payload

```json

{
  "appURN": "1000008465",
  "appType": "Tab",
  "boardingType": "ADDLTID",
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
    "newFundingAc": null
  },
  "channelCode": "ISO Channel1",
  "osvFlagValue": null,
  "cardedUncarded": "No",
  "countryCode": "IND",
  "leadId": null,
  "merchantDetails": {
    "businessName": null,
    "legalName": "ezetap provisioning testing",
    "businessType": "Sole Proprietor",
    "registrationNo": null,
    "dateTrading": null,
    "dateIncorporated": null,
    "websiteURL": null,
    "communicationEmail": "Prerana.kumbhar@firstdata.com",
    "legalAddress": {
      "addressLine": "Near central fire briged, Ganj peth",
      "addressLine2": ",, opposite kamble lane,",
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
    "postingTariff": "NET_INR",
    "billingLevel": "01",
    "gstNo": "27AAOFN4566A1Z6",
    "isdnFlag": null,
    "gstMerchantStateCode": null,
    "merchantType": "LG",
    "acceptanceType": "POSMOB",
    "iciciMerchant": "No",
    "newFundingAc": null,
    "merchantGrade": "EO",
    "idDocDetails": [
      {
        "entity": "Member",
        "idType": "Capture the Merchant Store Photos",
        "idValue": "",
        "docId": "dbab41ff030c49dc9cdc562f8e640e21",
        "categoryName": "LOCATION PHOTOS",
        "level": "1",
        "mandatory": "Y"
      },
      {
        "entity": "Member",
        "idType": "MITC Document Page 1",
        "idValue": "",
        "docId": "7771684880c3440a8d69ebe936c8178e",
        "categoryName": "MITC",
        "level": "1",
        "mandatory": "Y"
      },
      {
        "entity": "Member",
        "idType": "MITC Document Page 2",
        "idValue": "",
        "docId": "85a0203e2ba84e3ebfc4158665862f00",
        "categoryName": "MITC",
        "level": "2",
        "mandatory": "Y"
      },
      {
        "entity": "Member",
        "idType": "socDocument",
        "idValue": "",
        "docId": "b00d608f1cf14bd8bfc80fc32e9e2284",
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
      "taxidValue": null
    }
  },
  "tradingLocations": [
    {
      "locationNo": 1,
      "tradingName": "ezetap provisioning te",
      "tradingAddress": {
        "addressLine": "Near central fire briged, Ganj peth",
        "addressLine2": ",, opposite kamble lane,",
        "addressLine3": null,
        "city": "PUN-PUNE",
        "state": "MAH",
        "pincode": "411042",
        "country": null,
        "phone1": "8358353553",
        "phone2": "",
        "contactName": "Test",
        "mobileNo": null,
        "email": null
      },
      "packageId": 1056,
      "packageName": "Industry Type Additional TID Normal GPRS with fuel",
      "packageDescription": "Industry Type Additional TID Normal GPRS with fuel",
      "memberType": "POS",
      "tariff": "RetailP185LM",
      "amexTariff": "Amex Miscellane",
      "merchantGrade": "EO",
      "acqProfile": "Domestic",
      "msfProfile": "C120P185COR220IC000INC260D090",
      "mid": "470000099000154",
      "leadsubgroupmid": "470000056000250",
      "subgroupmid": "470000056000251",
      "otpEnabled": true,
      "feePlans": [
        {
          "serviceName": "UPI",
          "feePlan": "Y"
        },
        {
          "serviceName": "BHARATQR",
          "feePlan": "Y"
        },
        {
          "serviceName": "Email / SMS Invoicing",
          "feePlan": "Y"
        },
        {
          "serviceName": "BBPS",
          "feePlan": "ICICI-2015"
        },
        {
          "serviceName": "AEPS",
          "feePlan": "4-1001"
        },
        {
          "serviceName": "MicroATM SARVATRA",
          "feePlan": "1101"
        },
        {
          "serviceName": "FDConnect",
          "feePlan": "Y"
        },
        {
          "serviceName": "UPICashWithdraw",
          "feePlan": "U-9003"
        },
        {
          "serviceName": "Mobikwik",
          "feePlan": "1001"
        },
        {
          "serviceName": "AmazonPay",
          "feePlan": "Amazon1"
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
      "terminals": [
        {
          "terminalType": "GPRS",
          "terminalModel": "Verifone Vx680 (W BC) GPRS GSM",
          "batteryFlag": "Y",
          "count": 1,
          "currencyCode": null,
          "templateId": null,
          "socScheme": null,
          "services": [
            {
              "serviceName": "AMEX",
              "serviceValue": "N"
            }
          ],
          "withBiller": null,
          "billingSolProvider": null,
          "preferedDate": "03-07-2022",
          "preferedTime": "12:27",
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
      "sameLocation": null
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
      "nationality": null,
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
          "identityType": "",
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
      ]
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
      "nationality": null,
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
          "identityType": "",
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
      "accType": null
    }
  },
  "businessSummary": {
    "briefSummary": null,
    "mccCode": "5999",
    "mccDescription": "Miscellaneous and Specialty Retail Stores",
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
        "message": "Success"
    },
    "isAcvSuccess": null,
    "data": {
        "appUrn": "1000008469",
        "lsg": "51675948",
        "sgArray": [
            {
                "subgroupmId": "51672434",
                "merchantId": "95515434",
                "submerchantId": "00267746",
                "terminals": null
            }
        ]
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


Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`100`| Invalid Request |
|`103`| Data Not Found.Please contact Application Support Team |
|`200`| Sucess |
|`302`| IOException |
|`404`| Not Found |
|`401`| Unauthorized |
|`500`| Internal Error.Please contact Application Support Team |
|`505`| Internal Error.Please contact Application Support Team |
|`708`| AppURN already submitted |
|`902`| AppURN is mandatory |
|`903`| Application already Submitted |
|`904`| Json Processing Error |
|`905`| Json Parse Error |
|`906`| Json Mapping Error |
|`907`| Comments are empty |
|`908`| App URN not matching |
|`909`| Given Merchant Hierarchy Cannot handle via TAB. Please contact Application Support Team |
|`910`| Given Merchant Id Doesnt qualify for Add Outlet. Please contact Application Support Team |
|`911`| Given Merchant Super MID is InActive. Please contact Application Support Team |
|`912`| One of MID in hierarchy is InActive. Please contact Application Support Team |
|`913`| Please use member level Mid.Please contact Application Support Team |
|`914`| Ref MID should be 8 digits |
|`915`| Business Rule Exception |
|`916`| All Adress Types are not available for Ref MID.Please contact Application Suport Team |
|`917`| No Services avaiable for Ref MID. Please contact Application Support Team |