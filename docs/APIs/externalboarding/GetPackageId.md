# Get Individual Package

This API is used to fetch the package details list and its corresponding parameters based on the filter criteria provided in the request API.

## How it works
1. Merchant needs to use this API where in individual package details are to be retrieved by passing the package id in request parameter.
2. This step is optional for boarding.

## Endpoint

GET `https://www.uat.fdmerchantservices.com/Externalboarding/secure/packages/{packageId}`

## Payload Example

### Request Payload

```
Path variable -  packageId : 136

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=Externalboarding/secure/packages/{packageId}).

### Request
The below table identifies the required properties in the request message
| Variable |	Type |	Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- | ------------------ | ------------------ |
|`Package Id`|	String|	10	| M |	Package id|



### Successful Response Payload

```json
{
    "status": {
        "statusCode": 200,
        "message": "Success"
    },
    "data": {
        "id": "136",
        "name": "TID LG EmergingP090LM existing prod",
        "desc": "LG Sole properitor exsting prod with PC Additional TID",
        "shrtName": null,
        "level": null,
        "image": null,
        "cnrInd": null,
        "acceptanceType": "POSMOB",
        "isInternational": "No",
        "isDCC": "No",
        "msfTariff": "EmergingP090LM",
        "fundingCurrency": "NET_INR",
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
                        "name": "UPI",
                        "value": "Y",
                        "codeType": "Package VAS",
                        "applicableForFilter": true
                    },
                    {
                        "name": "EMI Profile",
                        "value": "Y",
                        "codeType": "Package VAS",
                        "applicableForFilter": true
                    },
                    {
                        "name": "PAYBACK",
                        "value": "Y",
                        "codeType": "Package VAS",
                        "applicableForFilter": true
                    },
                    {
                        "name": "POCKETS WALLET",
                        "value": "Y",
                        "codeType": "Package VAS",
                        "applicableForFilter": true
                    },
                    {
                        "name": "BHARATQR",
                        "value": "Y",
                        "codeType": "Package VAS",
                        "applicableForFilter": true
                    },
                    {
                        "name": "Google Pay",
                        "value": "Y",
                        "codeType": "Package VAS",
                        "applicableForFilter": true
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
                "category": "Funding Currency",
                "displayName": null,
                "attributeList": [
                    {
                        "name": "NET_INR",
                        "value": "NET_INR",
                        "codeType": "Funding Currency",
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
                "category": "Additional Parameters",
                "displayName": null,
                "attributeList": [
                    {
                        "name": "Charge Slip Type",
                        "value": "Physical Chargeslip",
                        "codeType": "Additional Parameters",
                        "applicableForFilter": false
                    }
                ]
            },
            {
                "category": "Terminal Type",
                "displayName": null,
                "attributeList": [
                    {
                        "name": "Normal WIFI",
                        "value": "Y",
                        "codeType": "Terminal Type",
                        "applicableForFilter": true
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
                        "name": "Rupay",
                        "value": "Y",
                        "codeType": "Package Schemes",
                        "applicableForFilter": true
                    },
                    {
                        "name": "DND",
                        "value": "Y",
                        "codeType": "Package Schemes",
                        "applicableForFilter": false
                    },
                    {
                        "name": "AMEX",
                        "value": "N",
                        "codeType": "Package Schemes",
                        "applicableForFilter": false
                    },
                    {
                        "name": "CUP",
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
                        "name": "Maestro",
                        "value": "Y",
                        "codeType": "Package Schemes",
                        "applicableForFilter": true
                    },
                    {
                        "name": "JCB",
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
                        "name": "Cash at POS Tariff",
                        "value": null,
                        "codeType": "Package Tariffs",
                        "applicableForFilter": false
                    },
                    {
                        "name": "MSF Tariff",
                        "value": "EmergingP090LM",
                        "codeType": "Package Tariffs",
                        "applicableForFilter": true
                    },
                    {
                        "name": "SOC Tariff",
                        "value": "2500 1st Month GPRS Rental 300",
                        "codeType": "Package Tariffs",
                        "applicableForFilter": true
                    },
                    {
                        "name": "MDR",
                        "value": "C090P090COR090IC000INC260D090",
                        "codeType": "Package Tariffs",
                        "applicableForFilter": false
                    }
                ]
            },
            {
                "category": "Additional Terminal Info",
                "displayName": null,
                "attributeList": [
                    {
                        "name": "ATS Remarks",
                        "value": "New",
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
                    }
                ]
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
The table below provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`103`| Data Not Found.Please contact Application Support Team |
|`105`| Given RM details not found |  
|`200`| Success |
|`400`| Terminal not in Proper Status |
|`401`| Unauthorized |
|`405`| HttpClientErrorException |  
|`700`| No record found for given AppURN and Sales Id |
|`900`|  Invalid AppURN |  
|`901`| AppURN Not Match |
|`902`| AppURN is Mandatory |
|`903`| Application already Submitted |  
|`904`| Json Processing Error |
|`905`|  Json Parse Error |  
|`906`| Json Mapping Error |
|`907`| Comments are empty |
|`908`| App URN not matching |
