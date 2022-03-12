# Single MID Payfac

This API is used to single mid payfac. Merchants needs to add session 
token received during login api call in the header of this API.


## Endpoint

GET `/Externalboarding/secure/newmid`

## Payload Example

### Request Payload

```json
{
  "appURN" : "1000008135",
  "appType" : "API",
  "salesId" : "sumupuser",
  "channelCode" : "SumUp_Australia",
  "merchantDetails" : {
    "businessName" : "AU Fiserv",
    "legalName" : "AU Fiserv",
    "businessType" : "Private Limited",
    "registrationNo" : "BR00902100",
    "dateIncorporated" : "06-04-2016",
    "websiteURL" : "www.fisau.com",
    "communicationEmail" : "fisau@gmail.com",
    "legalAddress" : {
      "addressLine" : "626",
      "addressLine2" : "38",
      "addressLine3" : "New South Wales",
      "city" : "Ingebirah",
      "state" : "NSW",
      "pincode" : "442001",
      "country" : "Australia",
      "mobileNo" : "7387864253",
      "phone1" : "7387864253",
      "email" : "guru@gmail.com",
      "contactName" : "Taj"
    },
    "geoLocation" : {
      "latitude" : "18.5336116",
      "longitude" : "73.9504918"
    },
    "merchantType" : "SM",
    "acceptanceType" : "ECOM",
    "taxDetails" : {
      "taxidType" : "businessPan",
      "taxidValue" : "AAECK1088P"
    }
  },
  "tradingLocations" : [ {
    "locationNo" : "1",
    "tradingName" : "AU Test Merchant",
    "tradingAddress" : {
      "addressLine" : "101",
      "addressLine2" : "85 Scenic Road",
      "addressLine3" : "New South Wales",
      "city" : "85 Scenic Road",
      "state" : "NSW",
      "pincode" : "411052",
      "country" : "Australia",
      "mobileNo" : "7387864253",
      "phone1" : "7387864253",
      "email" : "fisau@gmail.com",
      "contactName" : "Lala"
    },
    "packageId" : "15002",
    "terminals" : [ {
      "count" : 1,
      "preferedDate" : "11-03-2021",
      "preferedTime" : "19:24",
      "surchargeAmount" : {
        "visaBase" : "0",
        "visaPercent" : "0",
        "mcBase" : "0",
        "mcPercent" : "0",
        "upiBase" : "0",
        "upiPercent" : "0",
        "eftposBase" : "0",
        "eftposPercent" : "0.00",
        "amexBase" : "0",
        "amexPercent" : "0",
        "jcbBase" : "0",
        "jcbPercent" : "0",
        "dinersBase" : "0",
        "dinersPercent" : "0"
      }
    } ]
  } ],
  "principalDetails" : [ {
    "principalNo" : "1",
    "position" : "Owner",
    "title" : "Mr",
    "firstName" : "Lala",
    "lastName" : "Rao",
    "middleName" : "R",
    "gender" : "Male",
    "dateOfBirth" : "23-04-1987",
    "nationality" : "Australian",
    "principalAddress" : {
      "addressLine" : "626",
      "addressLine2" : "38",
      "addressLine3" : "address line 3",
      "city" : "Buraja",
      "state" : "NSW",
      "pincode" : "442001",
      "country" : "Australia",
      "mobileNo" : "7387864253",
      "phone1" : "7387864253",
      "contactName" : "Lala"
    },
    "kycDetails" : [ {
      "kycCategory" : "Individual POA 1 KYC",
      "identityType" : "aadhar",
      "identityValue" : "000000001200",
      "identitymetaName1" : "Guru",
      "identitymetaValue1" : "Vvv"
    } ]
  } ],
  "businessSummary" : {
    "briefSummary" : "Trading and Hotels",
    "salessrNumber" : "10981",
    "mccCode" : "7011",
    "mccDescription" : "Bars, Cocktail Lounges, Discotheques, etc",
    "totalTurnover" : "0",
    "totalTurnoverPerMID" : "0",
    "cardTurnover" : "100",
    "avgTicketAmt" : "100",
    "dccTurnoverPerMID" : "0",
    "pgTurnover" : "100",
    "pgTurnoverPerMID" : "100",
    "avgEMITicketAmt" : "0",
    "tranVolumeInternet" : "0",
    "tranVolumeMoto" : "100",
    "tranVolumeInStore" : "0",
    "deliveryDays0" : "100",
    "deliveryDays7" : "0",
    "deliveryDays14" : "0",
    "deliveryDays30" : "0",
    "deliveryDaysOver30" : "0",
    "tranTypeMagStrip" : "0",
    "tranTypeChip" : "0",
    "tranTypeKeyed" : "100",
    "creditSalesConsumer" : "100",
    "creditSalesBusiness" : "0"
  },
  "uboDetails" : [ {
    "serialNo" : "1",
    "title" : "Mr",
    "firstName" : "Steve",
    "lastName" : "Smith",
    "middleName" : "DG",
    "dateOfBirth" : "19-04-1987",
    "shareholderPercentage" : "100",
    "nationality" : "Australian",
    "kycDetails" : [ {
      "kycCategory" : "Individual POA 1 KYC",
      "identityType" : "aadhar",
      "identityValue" : "000000001200",
      "identitymetaName1" : "Vinay",
      "identitymetaValue1" : "Vvv"
    } ],
    "uboAddress" : {
      "addressLine" : "626",
      "addressLine2" : "38",
      "addressLine3" : "address line 3",
      "city" : "Buraja",
      "state" : "NSW",
      "pincode" : "411052",
      "country" : "Australia",
      "mobileNo" : "7387864253",
      "phone1" : "7387864253",
      "contactName" : "Lala"
    }
  } ],
  "institutionId" : "21",
  "countryCode" : "AU"
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
|`401` |Token not found|  
|`200` |Success|
|`300` |Request Failure|
|`500` |Internal Server Error|
|`404` |Not Found|
|`502` |Request Timed Out|
