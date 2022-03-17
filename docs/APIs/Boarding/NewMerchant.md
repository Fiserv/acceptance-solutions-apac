# New Merchant

This API is used to new merchant. Merchants needs to add session 
token received during login api call in the header of this API.


## Endpoint

POST `/Externalboarding/secure/newmid`

## Payload Example

### Request Payload

```json

{
  "IS_ADD_LOCATION" : "",
  "IS_ADD_MID" : "",
  "appChannel" : "A12",
  "appType" : "API",
  "appURN" : "1000007494",
  "channelCode" : "Bharat_PE",
  "salesId" : "BharatPEPFAC",
  "bankDetails" : {
    "accType" : "Current",
    "accountName" : "Vinay Trading",
    "accountNo" : "04881132001324",
    "bankName" : "ORIENTAL BANK OF COMMERCE",
    "branch" : "",
    "currency" : "INR",
    "ifsc" : "ORBC0100488"
  },
  "boardingType" : "NEWMID",
  "businessSummary" : {
    "avgEMITicketAmt" : "0",
    "avgTicketAmt" : "100",
    "briefSummary" : "Trading",
    "cardTurnover" : "100",
    "creditSalesBusiness" : "0",
    "creditSalesConsumer" : "100",
    "dccTurnoverPerMID" : "0",
    "deliveryDays0" : "100",
    "deliveryDays14" : "0",
    "deliveryDays30" : "0",
    "deliveryDays7" : "0",
    "deliveryDaysOver30" : "0",
    "firsReport" : "Weekly",
    "mccCode" : "5411",
    "mccDescription" : "Bars, Cocktail Lounges, Discotheques, etc.",
    "pgTurnover" : "100",
    "pgTurnoverPerMID" : "100",
    "recurringTranFlag" : "Yes",
    "smallMerchant" : "Y",
    "thirdPartyProcessorFlag" : "No",
    "totalTurnover" : "0",
    "totalTurnoverPerMID" : "0",
    "tranTypeChip" : "0",
    "tranTypeKeyed" : "100",
    "tranTypeMagStrip" : "0",
    "tranVolumeInternet" : "100",
    "tranVolumeInStore" : "0",
    "tranVolumeMoto" : "0"
  },
  "institutionId" : "47",
  "isSocOtpActivated" : true,
  "keySelection" : {
    "acceptanceType" : "POSMOB",
    "dcc" : "Yes",
    "fundingCurrency" : "NET_INR",
    "iciciMerchant" : "No",
    "international" : "Yes",
    "mccCode" : "5411",
    "merchantGrade" : "PA",
    "merchantType" : "SM",
    "typeOfBusiness" : "PVTLTD"
  },
  "merchantDetails" : {
    "acceptanceType" : "POSMOB",
    "businessName" : "Vinay",
    "businessType" : "PVTLTD",
    "communicationEmail" : "vinay@gmail.com",
    "dateIncorporated" : "09-09-2011",
    "fundingMethod" : "NEFT",
    "geoLocation" : {
      "latitude" : "18.5334233",
      "longitude" : "73.9508064"
    },
    "iciciMerchant" : "No",
    "idDocDetails" : [ {
      "categoryInd" : "NO",
      "categoryName" : "Entity POA KYC",
      "docId" : "5c6b33009c414b87b27f9e164aae2b0a",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "BankStmtPassbookSol Proprietor",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Other",
      "docId" : "41ed67e87c9941338976f6715cf6a360",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "Small Merchant Declaration",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Entity POI KYC",
      "docId" : "b428179abdc9447b9fc4fc449a2077ce",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "Certi issued by ANCHAL SAMITI MEMBER",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Other",
      "docId" : "a1cdf97f60b54045a1265abb8f865f90",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "GSTN Declaration",
      "idValue" : "NO",
      "level" : "2",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Other",
      "docId" : "d7a39bb216a0446a991b336e8ce9bdc4",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "Other supporting document",
      "idValue" : "NO",
      "level" : "6",
      "mandatory" : "N"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Funding Proof",
      "docId" : "dfc6fd4f07054ce69c7ac3dba176a436",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "cheque",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Funding Proof",
      "docId" : "23bb9a8660e84e0da05049c9cc6ebe35",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "nachDocument",
      "idValue" : "NO",
      "level" : "2",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "LOCATION PHOTOS",
      "docId" : "ba629ab6d04347b6b6266d4cc5ae25c8",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "Capture the Merchant Store Photos",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "MITC",
      "docId" : "de6ee88d4cca4983afb0e4e975e78102",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "MITC Document Page 1",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "MITC",
      "docId" : "2659ee15355a4bf5a87b1682c598a5d0",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "MITC Document Page 2",
      "idValue" : "NO",
      "level" : "2",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Other Documents",
      "docId" : "5e861a05ce194486b6f8470204d59339",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "Cross Sell Product Consent",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "N"
    } ],
    "isdnFlag" : "No",
    "legalAddress" : {
      "addressLine" : "Kharadi",
      "addressLine2" : "",
      "addressLine3" : "",
      "city" : "PUNE",
      "contactName" : "Jems",
      "email" : "test@gmail.com",
      "phone1" : "9426855672",
      "phone2" : "9426855672",
      "pincode" : "411014",
      "state" : "MAH"
    },
    "legalName" : "Vinay",
    "merchantGrade" : "PA",
    "merchantType" : "SM",
    "postingTariff" : "NET_INR",
    "registrationNo" : "BR00992011",
    "taxDetails" : {
      "taxidType" : "businessPan",
      "taxidValue" : "AECPK1099Q"
    },
    "websiteURL" : "www.amazon.com"
  },
  "osvFlagValue" : "Y",
  "principalDetails" : [ {
    "dateOfBirth" : "09-08-1988",
    "firstName" : "Jems",
    "idDocDetails" : [ {
      "categoryInd" : "NO",
      "categoryName" : "Individual POA 1 KYC",
      "docId" : "55ae52673b004bc0a551b18b8a94d8fe",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "aadhaar",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    }, {
      "categoryInd" : "NO",
      "categoryName" : "Individual POI 1 KYC",
      "docId" : "d4ceb654a76e4da19be27da78edb7c05",
      "documentLevelGroup" : "",
      "documentLevelId" : "",
      "entity" : "Member",
      "idType" : "individualPan",
      "idValue" : "NO",
      "level" : "1",
      "mandatory" : "Y"
    } ],
    "kycDetails" : [ {
      "identityType" : "aadhaar",
      "identityValue" : "",
      "kycCategory" : "Individual POA 1 KYC"
    }, {
      "identityType" : "individualPan",
      "identityValue" : "ABCDE1234F",
      "kycCategory" : "Individual POI 1 KYC"
    } ],
    "lastName" : "Dsouza",
    "middleName" : "",
    "nationality" : "Indian",
    "position" : "Owner",
    "principalAddress" : {
      "addressLine" : "Keshavnagar",
      "addressLine2" : "",
      "addressLine3" : "",
      "city" : "PUNE",
      "contactName" : "Jems",
      "country" : "India",
      "phone1" : "9426855672",
      "phone2" : "",
      "pincode" : "411036",
      "state" : "MAH"
    },
    "principalNo" : 1,
    "title" : "Mr"
  } ],
  "SalesId" : "BharatPEPFAC",
  "tradingLocations" : [ {
    "acqProfile" : "International",
    "amexTariff" : "Amex Restaurant",
    "cardedUncarded" : "Uncarded",
    "cpvGroupId" : "",
    "feePlans" : [ {
      "feePlan" : "20",
      "serviceName" : "BBPS"
    }, {
      "feePlan" : "Y",
      "serviceName" : "AmazonPay"
    }, {
      "feePlan" : "2002",
      "serviceName" : "UPICashWithdraw"
    }, {
      "feePlan" : "SR00901022",
      "serviceName" : "Sales Lead SR Number"
    } ],
    "leadsubgroupmid" : "",
    "locationNo" : 1,
    "memberType" : "POS",
    "merchantGrade" : "PA",
    "mid" : "",
    "msfProfile" : "C200P200COR220IC000INC260D090",
    "otpEnabled" : true,
    "packageId" : 14872,
    "regionalCpvGroupId" : "",
    "serviceTaxCertificate" : "Monthly",
    "subgroupmid" : "",
    "tariff" : "RetailP185SM",
    "terminals" : [ {
      "batteryFlag" : "N",
      "count" : 1,
      "discount" : 0,
      "preferedDate" : "11-16-2021",
      "preferedTime" : "13:16",
      "services" : [ {
        "serviceName" : "DCC",
        "serviceValue" : "Y"
      } ],
      "socScheme" : "Test_1st_Month_2500",
      "terminalModel" : "APOS",
      "terminalType" : "APOS",
      "userInstruction1" : "",
      "userInstruction2" : ""
    } ],
    "tradingAddress" : {
      "addressLine" : "Kharadi",
      "addressLine2" : "",
      "addressLine3" : "",
      "city" : "PUNE",
      "contactName" : "Jems",
      "email" : "test@gmail.com",
      "phone1" : "9426855672",
      "phone2" : "9426855672",
      "pincode" : "411014",
      "state" : "MAH"
    },
    "tradingName" : "Test"
  } ],
  "uboDetails" : [ {
    "dateOfBirth" : "09-08-1988",
    "firstName" : "Jems",
    "idDocDetails" : [ {
      "categoryName" : "UBO POA KYC",
      "docId" : "55ae52673b004bc0a551b18b8a94d8fe",
      "idType" : "aadhaar",
      "idValue" : "NO"
    }, {
      "categoryName" : "UBO POI KYC",
      "docId" : "d4ceb654a76e4da19be27da78edb7c05",
      "idType" : "individualPan",
      "idValue" : "NO"
    } ],
    "kycDetails" : [ {
      "identityType" : "aadhaar",
      "identityValue" : "",
      "kycCategory" : "Individual POA 1 KYC"
    }, {
      "identityType" : "individualPan",
      "identityValue" : "ABCDE1234F",
      "kycCategory" : "Individual POI 1 KYC"
    } ],
    "lastName" : "Dsouza",
    "middleName" : "",
    "nationality" : "Indian",
    "serialNo" : 1,
    "shareholderPercentage" : 100,
    "title" : "Mr",
    "uboAddress" : {
      "addressLine" : "Keshavnagar",
      "addressLine2" : "",
      "addressLine3" : "",
      "city" : "PUNE",
      "country" : "India",
      "phone1" : "9426855672",
      "phone2" : "",
      "pincode" : "411036",
      "state" : "MAH"
    }
  } ]
}


```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/newmid``).

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