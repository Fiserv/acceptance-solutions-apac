# Get Package List

This API is used to fetch the package details list and its corresponding parameters based on the filter criteria provided in the request API.

## How it works
1. Merchant needs to use this API where in multiple packages are assigned to the partner.
2. This step is optional for boarding.

## Endpoint

GET `https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/packages`

## Payload Example

### Request Payload

```json

{
  "appType": "API",
  "mccCode": "5813",
  "merchantType": "SM",
  "acceptanceType": "POSMOB",
  "typeOfBusiness": "SOLPROR",
  "international": "No",
  "iciciMerchant": "No",
  "dcc": "Yes",
  "fundingCurrency": "NET_AUD",
  "boardingType": "NEWMID",
  "merchantGrade": "NA",
  "newFundingAc": ""
}

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/packages).

### Request
| Variable | Type | Length |  Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
|`appType`|Alphanumeric|8|M|Fixed Value API.|
|`salesId`|Alphanumeric|70|M|User Credential created for each partner.|
|`channelCode`|Alphanumeric|10|M|Static channel code shared with each partner.|
|`mccCode`|Numeric|20|M|Unique value assigned for each industry.|
|`merchantType`|Alphanumeric|20|M|Type of merchant whether Small or Large Merchant.|
|`acceptanceType`|Alphanumeric|10|M|Static Value: 'ECOM' / 'POSMOB'|
|`typeOfBusiness`|Alphanumeric|50|M|Type of business means Sole Proprieter, Individual etc.|
|`international`|Alphanumeric|3|O|Applicable if the merchant supports international Card Transactions.|
|`iciciMerchant`|Alphanumeric|20|O|Applicable if the merchant is ICICI current bank account holder.|
|`dcc`|Alphanumeric|3|O|If enabled for foreign rate currency, the value returned should be captured as either Y / N.|
|`fundingCurrency`|Alphanumeric|8|M|The currency settled to the merchant NET_INR, NET_USD, NET_AUD etc|
|`boardingType`|Alphanumeric|20|M|Type of merchant: New MID / Add MID / Add TID|
|`merchantGrade`|Alphanumeric|40|M|The grade of the merchant decided as per the turnover.|



### Successful Response Payload

```json
[
{
"id": "15001",
"name": "Test Package AU 1_NEWMID",
"desc": "Package Name",
"shrtName": null,
"level": null,
"image": null,
"cnrInd": null,
"acceptanceType": "POSMOB",
"isInternational": "No",
"isDCC": "Yes",
"msfTariff": "Tiered I/C",
"fundingCurrency": "NET_AUD",
"preferential": "N",
"otpEnabled": true,
"sbPackageDesc": null,
"sbInstrumentsDesc": null,
"sbVASDesc": null,
"sbTerminalTypeDesc": null,
"sbPricingDesc": null,
"attributes": [
{
"category": "Package VAS",
"displayName": null,
"attributeList": [
{
"name": "Charge Slip Type",
"value": "E",
"codeType": "Package VAS",
"applicableForFilter": true
},
{
"name": "FDConnect",
"value": "Y",
"codeType": "Package VAS",
"applicableForFilter": true
},
{
"name": "Project Call Type",
"value": "ISO",
"codeType": "Package VAS",
"applicableForFilter": false
},
{
"name": "MVV Indicator",
"value": "Y",
"codeType": "Package VAS",
"applicableForFilter": false
},
{
"name": "Email / SMS Invoicing",
"value": "Y",
"codeType": "Package VAS",
"applicableForFilter": true
}
]
},
{
"category": "Additional Peripherals",
"displayName": null,
"attributeList": [
{
"name": "Peripharal2",
"value": "Peripheral 2",
"codeType": "Additional Peripherals",
"applicableForFilter": false
},
{
"name": "Peripharal4",
"value": "Peripheral 4",
"codeType": "Additional Peripherals",
"applicableForFilter": false
},
{
"name": "Peripharal3",
"value": "Peripheral 3",
"codeType": "Additional Peripherals",
"applicableForFilter": false
},
{
"name": "Peripharal5",
"value": "Peripheral 5",
"codeType": "Additional Peripherals",
"applicableForFilter": false
},
{
"name": "Peripharal1",
"value": "Peripheral 1",
"codeType": "Additional Peripherals",
"applicableForFilter": false
}
]
},
{
"category": "Package Currency Acceptance",
"displayName": null,
"attributeList": [
{
"name": "DCC",
"value": "Y",
"codeType": "Package Currency Acceptance",
"applicableForFilter": false
},
{
"name": "DCC PARTNER",
"value": "openFxFuture",
"codeType": "Package Currency Acceptance",
"applicableForFilter": false
},
{
"name": "International",
"value": "N",
"codeType": "Package Currency Acceptance",
"applicableForFilter": false
}
]
},
{
"category": "Package Acceptance",
"displayName": null,
"attributeList": [
{
"name": "POSMOB",
"value": "Y",
"codeType": "Package Acceptance",
"applicableForFilter": false
}
]
},
{
"category": "Package Info",
"displayName": null,
"attributeList": [
{
"name": "KET MERCHANT TAGING",
"value": "Key Merchant Tagging",
"codeType": "Package Info",
"applicableForFilter": false
},
{
"name": "Package ID",
"value": "477",
"codeType": "Package Info",
"applicableForFilter": false
},
{
"name": "Package Level",
"value": "NEWMID",
"codeType": "Package Info",
"applicableForFilter": false
},
{
"name": "Package Name",
"value": "Test Package AU 1",
"codeType": "Package Info",
"applicableForFilter": false
},
{
"name": "Number of Terminals",
"value": "10",
"codeType": "Package Info",
"applicableForFilter": false
},
{
"name": "Package Description",
"value": "NAB Test Package",
"codeType": "Package Info",
"applicableForFilter": false
},
{
"name": "Preferrential?",
"value": "Y",
"codeType": "Package Info",
"applicableForFilter": false
}
]
},
{
"category": "Package Schemes",
"displayName": null,
"attributeList": [
{
"name": "Master",
"value": "Y",
"codeType": "Package Schemes",
"applicableForFilter": true
},
{
"name": "AMEX",
"value": "Y",
"codeType": "Package Schemes",
"applicableForFilter": false
},
{
"name": "DND",
"value": "Y",
"codeType": "Package Schemes",
"applicableForFilter": false
},
{
"name": "VISA",
"value": "Y",
"codeType": "Package Schemes",
"applicableForFilter": true
},
{
"name": "CUP",
"value": "Y",
"codeType": "Package Schemes",
"applicableForFilter": false
}
]
},
{
"category": "Package Tariffs",
"displayName": null,
"attributeList": [
{
"name": "MDR",
"value": "Visa@X%,MC@X%,CUP@X% & EFTPOS@X%",
"codeType": "Package Tariffs",
"applicableForFilter": false
},
{
"name": "MSF Tariff",
"value": "Tiered I/C",
"codeType": "Package Tariffs",
"applicableForFilter": true
}
]
},
{
"category": "Additional Terminal Info",
"displayName": null,
"attributeList": [
{
"name": "Terminal Instruction 2",
"value": "Terminal Instruction3",
"codeType": "Additional Terminal Info",
"applicableForFilter": false
}
]
},
{
"category": "Package Card Types",
"displayName": null,
"attributeList": [
{
"name": "DEBIT",
"value": "Y",
"codeType": "Package Card Types",
"applicableForFilter": false
},
{
"name": "PREPAID",
"value": "Y",
"codeType": "Package Card Types",
"applicableForFilter": false
},
{
"name": "CREDIT",
"value": "Y",
"codeType": "Package Card Types",
"applicableForFilter": false
},
{
"name": "OFFUS",
"value": "Y",
"codeType": "Package Card Types",
"applicableForFilter": false
}
]
}
]
}
]
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
|`103`| Data not found, please contact application support team |
|`105`| Given RM details not found. |
|`200`| Success |
|`400`| Terminal not in proper status.  |
|`401`| Unauthorized |
|`405`| Http client error exception |
|`700`| No record found for given App URN and Sales ID. |
|`900`| Invalid App URN |
|`901`| App URN not match |
|`902`| App URN is a mandatory value. |
|`903`| Application had already submitted. |
|`904`| JSON Processing Error |
|`905`| JSON Parse Error |
|`906`| JSON Mapping Error |
|`907`| Comment field empty. |
|`908`| App URN does not match. |
