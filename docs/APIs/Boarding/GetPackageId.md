# Get Individual Package

This API is used to get individual package. Merchants needs to add session 
token received during login api call in the header of this API.


## Endpoint

GET `Externalboarding/secure/packages/{packageId}`

## Payload Example

### Request Payload

```
Path variable -  packageId : 136

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=Externalboarding/secure/packages/{packageId}).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `packageId` | *Path Variable* |  | M | package id |



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
                        "name": "SODEXO",
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
                        "name": "BAJAJ Finserv",
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

### Response
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `id` | *string* | 20 | M | Identification Number |




Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`401` |Token not found|  
|`200` |Success|
|`300` |Request Failure|
|`500` |Internal Server Error|
|`404` |Not Found|
|`502` |Request Timed Out|
