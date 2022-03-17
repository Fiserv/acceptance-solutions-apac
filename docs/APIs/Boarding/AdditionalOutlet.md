# Additional Outlet

This API is used to additional outlet. Merchants needs to add session 
token received during login api call in the header of this API,


## Endpoint

POST `/Externalboarding/secure/addmid`

## Payload Example

### Request Payload

```json

{
  "appURN": "1000008471",
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

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/addmid).

### Request
| FieldName | FieldType | Data Type | Length | Description/Values | ISO/Direct Merchant | SMPFAC | MMPFAC |
| -------- | :-------: | :--: | :------------: | :--: | :------------:| :------------:| ------------------ |
 | `appURN` | M | *Alphanumeric* | 30 | App URN retured as part of Create URN API | M | NA | NA | 
 | `appType` | M | *Alphanumeric* |  | 8 | Fixed Value "API" | M | NA | NA | 
 | `salesId` | M | *Alphanumeric* |  | 70 | User Credential created for each partner | M | NA | NA | 
 | `channelCode` | C | *Alphanumeric* | 10 | Static Channel Code shared with each partner | M | NA | NA | 
 | `institutionId` | C | *Numeric* | 10 | Institution number assigned to the institution | M | NA | NA | 
 | `boardingType` | O | *Alphanumeric* | 20 | Type of Merchant: NEWMID/ADDMID/ADDTID | M | NA | NA | 
 | `IS_ADD_LOCATION` | O | *Alphanumeric* | 20 | Applicable if the merchant wants additional location | M | NA | NA | 
 | `IS_ADD_MID` | O | *Alphanumeric* | 20 | Applicable if the merchant wants additional MID | M | NA | NA |
 | `appChannel` | O | *AlphanuMeric* | 20 | | M | NA | NA | 
 | `osvFlagValue` | O | *AlphanuMeric* | 1 | Original Seen & Verified flag.| M | NA | NA | 
 | **MerchantDetails** | - | - |  - | This is the object | - | - | - | 			
 | `businessName` | M | *AlphanuMeric* | 22 | Trade Name of the Merchant | M | NA | NA | 
 | `legalName` | M | *AlphanuMeric* | 35 | Legal Name of the Merchant | M | NA | NA | 
 | `businessType` | M | *AlphanuMeric* | 50 | Type of Business of the Merchant | M | NA | NA | 
 | `registrationNo` | M | *AlphanuMeric* | 100 | Registration number of the Merchant | M | NA | NA | 
| **taxDetails** | - | - | - | This is the object | - | - | - | 			
 | `taxidType` | M | *AlphanuMeric* | 50 | "Tax ID Type provided for the Merchant. | M | NA | NA | 
 | `taxidType` | M | *AlphanuMeric* | 50 | For India - PAN | M | NA | NA | 
 | `taxidType` | M | *AlphanuMeric* | 50 | Individual PAN for Individual/Soleprop Merchants | M | NA | NA | 
 | `taxidValue` | M | *AlphanuMeric* | 100 | PAN, ABN nuMber of the Merchant | M | NA | NA | 
 | `taxidValue` | M | *AlphanuMeric* | 100 | PAN, ABN nuMber of the Merchant | M | NA | NA | 
 | `taxidValue` | M | *AlphanuMeric* | 100 | PAN, ABN nuMber of the Merchant | M | NA | NA | 
 | `taxidValue` | M | *AlphanuMeric* | 100 | PAN, ABN nuMber of the Merchant | M | NA | NA | 
 | `taxidValue` | M | *AlphanuMeric* | 100 | PAN, ABN nuMber of the Merchant | M | NA | NA | 
 | `taxidValue` | M | *AlphanuMeric* | 100 | PAN, ABN nuMber of the Merchant | M | NA | NA | 
 | `dateIncorporated` | M | *Numeric* | 8 | YYYYMMDD | M | NA | NA | 
 | `websiteURL` | C | *Alphanumeric* | 100 | Eligible for ECOM Merchant | M | NA | NA | 
 | `communicationEmail` | M | *AlphanuMeric* | 60 | Communication Email of the Merchant | M | NA | NA | 
 | `merchantType` | M | *Alphanumeric* | 20 | Whether it is small merchant or Large merchant | M | NA | NA | 
 | `acceptanceType` | M | *Alphanumeric* | 10 | Static Value - POSMOB /ECOM | M | NA | NA | 
 | `iciciMerchant` | M | *Alphanumeric* | 20 | Applicable if the merchant has ICICI account | M | NA | NA | 
 | `newFundingAc` | M | *Alphanumeric* | 20 | Applicable if the merchant wants the new settlement account | NA | NA | NA | 
 | **legalAddress** | - | - | - | This is the object | - | - | - | 		
 | `addressLine` | M | *Alphanumeric* | 35 | Address of the Merchant | M | NA | NA | 
 | `addressLine2` | O | *Alphanumeric* | 35 | Address of the Merchant | O | NA | NA | 
 | `addressLine3` | O | *Alphanumeric* | 35 | Address of the Merchant | O | NA | NA | 
 | `city` | M | *Alphanumeric* | 25 | City of the Merchant | M | NA | NA | 
 | `state | M | *Alphanumeric* | 	 | 25 | State of the Merchant | M | NA | NA | 
 | `pincode` | M | *Alphanumeric* | 8 | Pincode of the Merchant | M | NA | NA | 
 | `country` | M | *Alphanumeric* | 25 | Country of the Merchant | M | NA | NA | 
 | `mobileNo` | M | *Numeric* | 15 | Mobile number of the Merchant | M | NA | NA | 
 | `phone1` | O | *Numeric* | 15 | Phone number of the Merchant | M | NA | NA | 
 | `email` | O | *Numeric* | 30 | Email of the Merchant | M | NA | NA | 
 | `contactName` | M | *Alphanumeric* | 35 | Contact Name of the Merchant | M | NA | NA | 
 | `gstNo` | C | *Alphanumeric* | 100 | Mandatory for Large merchants | NA | NA | NA | 
 | `gstMerchantStateCode` | O | *Alphanumeric* | 40 | Mandatory for Large Partners | NA | NA | NA | 
 | `isdnFlag` | C | *Alphanumeric* | 20 | |  M | NA | NA | 
  | **idDocDetails** | - | - | - | *"ID Doc Details section is a conditional tag and has to be mandatorily present if the user is uploding documents for a particular application. All documents uploaded under ""categoryInd"": ""E"" has to be included under merchantDetails.idDocDetails"* | This object not applicable forSingleMID PFAC | - | This object not applicable for Multimid PFAC | 
 | `entity` | C | *Alphanumeric* | - | Static Value - `Member` | M | NA | NA | 
 | `idType` | C | *Alphanumeric* | - | Value of docType received as response of uploaded document | M | NA | NA | 
 | `idValue` | C | *Alphanumeric* | - | - | M | NA | NA | 
 | `docId` | C | *Alphanumeric* | - | Value of docID received as response of uploaded document | M | NA | NA | 
 | `categoryName` | C | *Alphanumeric* | - | Value of category | NA | me received as response of uploaded document | M | NA | NA | 
 | `level` | C | *Numeric* | - | Value of level received as response of uploaded document | M | NA | NA | 
 | `mandatory` | C | *Alphanumeric* | - | - | M | NA | NA | 
 | `entity` | C | *Alphanumeric* | - | Static Value - `Member` | M | NA | NA | 
 | `idType` | C | *Alphanumeric* | 	 | - | 	 | Value of docType received as response of uploaded document | M | NA | NA | 
 | `idValue` | C | *Alphanumeric* | - | - | M | NA | NA | 
 | `docId` | C | *Alphanumeric* | - | Value of docID received as response of uploaded document | M | NA | NA | 
 | `categoryName` | C | *Alphanumeric* | - | Value of category | NA | me received as response of uploaded document | M | NA | NA | 
 | `level` | C | *Numeric* | - | Value of level received as response of uploaded document | M | NA | NA | 
 | `mandatory` | C | *Alphanumeric* | - | - | M | NA | NA | 
 | **geoLocation** | - | - | - | This is the object | - | - | This object not applicable for Multimid PFAC | 
 | `latitude` | O | *Numeric* | 20 | Lattitude of the Merchant | M | NA | NA | 
 | `longitude` | O | *Numeric* | 20 | Longitude of the Merchant | M | NA | NA | 
 | **tradingLocations** | - | - | - | "This section contains the trading location details of merchants that is being onboarded. A maximum upto 3 trading locations can be added under a single Application. | - | - | - | 
 | **tradingLocations** | - | - | - | The entire trading location section needs to be repeated for multiple trading locations." | - | - | - | 
 | `locationNo` | M | *Numeric* | 2 | Trading location number of the Merchant | M | NA | NA | 
 | `tradingName` | M | *Alphanumeric* | 22 | Trade Name of the Merchant | M | NA | NA | 
 | **tradingAddress** | - | - | - | This is the object | - | - | - | 
 | `addressLine` | M | *Alphanumeric* | 35 | Address of the Merchant | - | NA | NA | 
 | `addressLine2` | O | *Alphanumeric* | 35 | Address of the Merchant | M | NA | NA | 
 | `addressLine3` | O | *Alphanumeric* | 35 | Address of the Merchant | O | NA | NA | 
 | `city` | M | *Alphanumeric* | 25 | City of the Merchant | O | NA | NA | 
 | `state` | M | *Alphanumeric* | 25 | State of the Merchant | M | NA | NA | 
 | `pincode` | M | *Alphanumeric* | 8 | Pincode of the Merchant | M | NA | NA | 
 | `country` | M | *Alphanumeric* | 25 | Country of the Merchant | M | NA | NA | 
 | `mobileNo` | M | *Numeric* | 15 | Mobile number of the Merchant | M | NA | NA | 
 | `phone1` | O | *Numeric* | 15 | phone1 of the Merchant | M | NA | NA | 
 | `email` | O | *Numeric* | 30 | Email of the Merchant | M | NA | NA | 
 | `contactName` | M | *Alphanumeric* | 35 | Contact Name of the Merchant | M | NA | NA | 
 | `packageId` | M | *Numeric* | 10 | Package number assigned to the Merchant | M | NA | NA | 
 | `autoSettlementTime` | O | *Numeric* | 6 | HHMMSS | M | NA | NA | 
 | `cpvGroupId` | O | *Alphanumeric* | 50 | Cpvgroupid of the Merchant | NA | NA | NA | 
 | `regionalcpvGroupid` | O | *Alphanumeric* | 50 | Regionalcpv groupid of the Merchant | O | NA | NA | 
 | `commerceConnectReferenceMID` | O | *Alphanumeric* | 8 | Commerceconnectreferencemid of the Merchant | O | NA | NA |
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
|`200`| Success |
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
