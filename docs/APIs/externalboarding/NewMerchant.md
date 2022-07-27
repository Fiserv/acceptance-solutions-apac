# New Merchant

This API is used to submit the boarding application for new merchants.

## How it works
1. Merchant needs to use this API to actually submit the boarding application for the new merchant.
2. This step is mandatory for boarding.
3. Merchant has to trigger this API post Create URN API. Below APIs can be optionally used to contribute to the data to be submitted
   as part  of New Partner Application Submit API.
    - Get Packages
    - Get Document Matrix
    - Upload Document

## Endpoint

POST `https://www.uat.fdmerchantservices.com/Externalboarding/secure/newmid`

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

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/newmid``).

### Request
| Field Name | Type | Length | Mandatory / Optional / Conditional (M / O / C ) | Description/Values | 
| -------- | :-------: | :--: | :------------: | :--: | 
 |`appURN`|Alphanumeric|30|M|App URN retured as part of Create URN API|
|`appType`|Alphanumeric|8|M|Fixed Value 'API'|
|`salesId`|Alphanumeric|70|M|User Credential created for each partner|
|`channelCode`|Alphanumeric|10|M|Static Channel Code shared with each partner|
|`institutionId`|Numeric|10|M|Institution number assigned to the institution|
|`boardingType`|Alphanumeric|20|M|Type of Merchant: New MID/Add MID/Add TID|
|`IS_ADD_LOCATION`|Alphanumeric|20|M|Applicable if the merchant wants additional location|
|`IS_ADD_MID`|Alphanumeric|20|M|Applicable if the merchant wants additional MID|
|`appChannel`|Alphanumeric|20|M|Application channel|
|`osvFlagValue`|Alphanumeric|1|M|Original Sent & Verified flag. Applicable for entities where documents are uploaded. For entities not uploading documents, keep this field as blank.|
|**merchantDetails**|-|||This is the object|
|`businessName`|Alphanumeric|22|M|Trade Name of the Merchant|
|`legalName`|Alphanumeric|35|M|Legal Name of the Merchant|
|`businessType`|Alphanumeric|50|M|Type of Business of the Merchant|
|`registrationNo`|Alphanumeric|100|M|Registration number of the Merchant|
|**taxDetails**|-|||This is the object|
|`taxidType`|Alphanumeric|50|M|Tax ID Type provided for the merchant.
| | | | | For India - PAN |
| | | | | For AU - ABN |
|`taxidValue`|Alphanumeric|50|M|Tax ID Value provided for the merchant.
| | | | | For India - Individual PAN for Individual/Soleprop merchants|
| | | | | Corporate PAN for other type pf merchants
| | | | | For AU - ABN Value|
|`dateIncorporated`|Numeric|8|M|YYYYMMDD|
|`websiteURL`|Alphanumeric|100|M|Eligible for ECOM Merchant|
|`communicationEmail`|Alphanumeric|60|M|Communication Email of the Merchant|
|`merchantType`|Alphanumeric|20|M|Whether it is small merchant or Large merchant|
|`acceptanceType`|Alphanumeric|10|M|Static Value - ''POSMOB'' for POS merchant|
| | | | | Static Value - ''ECOM'' for ECOM merchant|
|`iciciMerchant`|Alphanumeric|20|M|Applicable if the merchant has ICICI account|
|`newFundingAc`|Alphanumeric|20|NA|Applicable if the merchant wants the new settlement account|
|**legalAddress**|-|||This is the object|
|`addressLine`|Alphanumeric|35|M|Address of the Merchant|
|`addressLine2`|Alphanumeric|35|O|Address of the Merchant|
|`addressLine3`|Alphanumeric|35|O|Address of the Merchant|
|`city`|Alphanumeric|25|M|City of the Merchant|
|`state`|Alphanumeric|25|M|State of the Merchant|
|`pincode`|Alphanumeric|8|M|Pincode of the Merchant|
|`country`|Alphanumeric|25|M|Country of the Merchant|
|`mobileNo`|Numeric|15|M|Mobile number of the Merchant|
|`phone1`|Numeric|15|M|Phone number of the Merchant|
|`email`|Numeric|30|M|Email of the Merchant|
|`contactName`|Alphanumeric|35|M|Contact Name of the Merchant|
|`gstNo`|Alphanumeric|100|NA|Mandatory for Large merchants|
|`gstMerchantStateCode`|Alphanumeric|40|NA|Mandatory for Large Partners|
|`isdnFlag`|Alphanumeric|20|M|Isdn Flag|
|**idDocDetails**|-|||ID Doc Details section is a conditional tag and should be mandatory for a user uploding documents in an application. All documents uploaded under "categoryInd": "E" has to be included under merchantDetails - idDocDetails|
|`entity`|Alphanumeric|20|M|Static Value - 'Member'|
|`idType`|Alphanumeric|20|M|Value of docType received as response of uploaded document|
|`idValue`|Alphanumeric|20|M|Id Value|
|`docId`|Alphanumeric|20|M|Value of docID received as response of uploaded document|
|`categoryName`|Alphanumeric|20|M|Value of categoryName received as response of uploaded document|
|`level`|Numeric|20|M|Value of level received as response of uploaded document|
|`entity`|Alphanumeric|20|M|Static Value - 'Member'|
|`idType`|Alphanumeric|20|M|Value of docType received as response of uploaded document|
|`idValue`|Alphanumeric|20|M|Id Value|
|`docId`|Alphanumeric|20|M|Value of docID received as response of uploaded document|
|`categoryName`|Alphanumeric|20|M|Value of categoryName received as response of uploaded document|
|`level`|Numeric|20|M|Value of level received as response of uploaded document|
|**geoLocation**|-|||This is the object|
|`latitude`|Numeric|20|M|Latitude of the Merchant|
|`longitude`|Numeric|20|M|Longitude of the Merchant|
|**tradingLocations**|-|||This section contains the trading location details of merchants that is being onboarded. A maximum upto 3 trading locations can be added under a single Application.|
|`locationNo`|Numeric|2|M|Trading location number of the Merchant|
|`tradingName`|Alphanumeric|22|M|Trade Name of the Merchant|
|**tradingAddress**|-|||This is the object|
|`addressLine`|Alphanumeric|35||Address of the Merchant|
|`addressLine2`|Alphanumeric|35|M|Address of the Merchant|
|`addressLine3`|Alphanumeric|35|O|Address of the Merchant|
|`city`|Alphanumeric|25|O|City of the Merchant|
|`state`|Alphanumeric|25|M|State of the Merchant|
|`pincode`|Alphanumeric|8|M|Pincode of the Merchant|
|`country`|Alphanumeric|25|M|Country of the Merchant|
|`mobileNo`|Numeric|15|M|Mobile number of the Merchant|
|`phone1`|Numeric|15|M|phone1 of the Merchant|
|`email`|Numeric|30|M|Email of the Merchant|
|`contactName`|Alphanumeric|35|M|Contact name of the Merchant|
|`packageId`|Numeric|10|M|Package number assigned to the Merchant|
|`autoSettlementTime`|Numeric|6|M|HHMMSS|
|`cpvGroupId`|Alphanumeric|50|NA|Cpv groupid of the Merchant|
|`regionalcpvGroupid`|Alphanumeric|50|O|Regional cpv groupid of the Merchant|
|`commerceConnectReferenceMID`|Alphanumeric|8|O|Commerce connect reference mid of the Merchant|
|`terminals`|-|||This is the object|
|`count`|Numeric|2|M|Count of terminals for the Merchant|
|`preferedDate`|Numeric|8|M|YYYYMMDD|
|`preferedTime`|Numeric|6|M|HHMMSS|
|`discount`|Numeric|3|M|Discount of the Merchant|
|`userInstruction1`|Alphanumeric|100|O|User Instruction1 of the Merchant|
|`userInstruction2`|Alphanumeric|100|O|User Instruction2 of the Merchant|
|**surchargeAmount***|-|||This object is not applicable for ISO. Surcharge values currently selected by Partner on MVSI in AU|
|`visaBase`|Numeric|11|NA|For AU Only|
|`visaPercent`|Numeric|11|NA|For AU Only|
|`mcBase`|Numeric|11|NA|For AU Only|
|`mcPercent`|Numeric|11|NA|For AU Only|
|`upiBase`|Numeric|11|NA|For AU Only|
|`upiPercent`|Numeric|11|NA|For AU Only|
|`eftposBase`|Numeric|11|NA|For AU Only|
|`eftposPercent`|Numeric|11|NA|For AU Only|
|`amexBase`|Numeric|11|NA|For AU Only|
|`amexPercent`|Numeric|11|NA|For AU Only|
|`jcbBase`|Numeric|11|NA|For AU Only|
|`jcbPercent`|Numeric|11|NA|For AU Only|
|`dinersBase`|Numeric|11|NA|For AU Only|
|`dinersPercent`|Numeric|11|NA|For AU Only|
|`altmerchCode`|Alphanumeric|20|NA|This is an optional field which has to be populated only if there is merchant MID or Dealer Code has to be captured at MID Level|
|`sameLocation`|Alphanumeric|1|NA|This flag has to be set to 'Y' if Partner wants multiple MIDs at the same location|
|`mid`|Numeric|15|O|This is the reference Member MID which needs to be given in case of ADD MID/ ADD TID.|
|`parentmid`|Numeric|15|O|This is the SG (parent MID) of the reference MID which needs to be given in case of ADD MID & ADD TID|
|`otpEnabled`|Alphanumeric|10|M|Otp enabled for the merchant|
|**principalDetails**|-|||This section is used to capture details of Principal Owner for the said merchant. The same section can be repeated for multiple Principal Owners. We can have upto maximum of 2 Principal Owners per merchant|
|`principalNo`|Alphanumeric|2|M|Principal number of the Merchant|
|`position`|Alphanumeric|20|M|Position of the Merchant|
|`title`|Alphanumeric|20|M|Title of the Merchant|
|`firstName`|Alphanumeric|25|M|First Name mf the Merchant|
|`lastName`|Alphanumeric|25|M|Last Name of the Merchant|
|`middleName`|Alphanumeric|25|M|Middle Name of the Oerchant|
|`gender`|Alphanumeric|10|M|Gender of the Merchant|
|`dateOfBirth`|Numeric|8|M|YYYYMMDD|
|**kycDetails**|-|||This is the object|
|`kycCategory`||||POI/POA of the Merchant|
|`identityType`|Alphanumeric|50|M|Type of KYC Document submitted.
| | | | | For India - PAN/AADHAR|
| | | |  |For ASEAN - Passport/Driving Licence/HKID or SGID or MYID |
| | | | |For AU - Passport/Driving Licence|
|`identityValue`|Alphanumeric|50|M|Value of the Kyc Document submitted|
|`identitymetaName1`|Alphanumeric|100|NA|Additional information pertaning to the KYC documents submitted. For AU - Driving License State Code|
|`identitymetaValue1`|Alphanumeric|100|NA|Additional information pertaning to the KYC documents submitted. For AU - Value Driving License State Code|
|`nationality`|Alphanumeric|35|M|Nationality of the Merchant|
|**principalAddress**|-|||This is the object|
|`addressLine`|Alphanumeric|35|M|Address  line of the Merchant|
|`addressLine2`|Alphanumeric|35|O|Address Line2 of the Merchant|
|`addressLine3`|Alphanumeric|35|O|Address Line3 of the Merchant|
|`city`|Alphanumeric|25|M|City of the Merchant|
|`state`|Alphanumeric|25|M|State of the Merchant|
|`pincode`|Alphanumeric|8|M|Pincode of the Merchant|
|`country`|Alphanumeric|25|M|Country of the Merchant|
|`mobileNo`|Numeric|15|M|Mobile number of the Merchant|
|`phone1`|Numeric|15|M|phone 1 of the Merchant|
|`contactName`|Alphanumeric|35|M|Contact name of the Merchant|
|**idDocDetails**|-||C|ID Doc Details section is a conditional tag and should be mandatory for a user uploding documents in an application. All documents uploaded under "categoryInd": "P" has to be included under principalDetails - idDocDetails|
|`level`|Alphanumeric|2|M|Value of level received as response of uploaded document|
|`mandatory`|Alphanumeric|10|M|Mandatory of the Merchant|
|`entity`|Alphanumeric|20|M|Static Value - 'Member'|
|`idType`|Alphanumeric|20|M|Value of docType received as response of uploaded document|
|`idValue`|Alphanumeric|20|M|Id value|
|`docId`|-||M|Value of docID received as response of uploaded document|
|`categoryName`|Alphanumeric|30|M|Value of categoryName received as response of uploaded document|
|**uboDetails**|-|||This section is used to capture details of Ultimate Benefeciary Owner for the said merchant. The same section can be repeated for multiple UBOs. We can have upto maximum of 5 UBOs per merchant.|
|`serialNo`|Numeric|2|M|Serial number of the Ultimate Benefeciary Owner|
|`title`|Alphanumeric|20|M|Title of the Ultimate Benefeciary Owner|
|`firstName`|Alphanumeric|25|M|First name of the Ultimate Benefeciary Owner|
|`lastName`|Alphanumeric|25|M|Last name of the Ultimate Benefeciary Owner|
|`middleName`|Alphanumeric|25|M|Middle name of the Ultimate Benefeciary Owner|
|`dateOfBirth`|Numeric|10|M|Format - YYYYMMDD|
|`shareholderPercentage`|Numeric|8|M|Shareholder percentage the Ultimate Benefeciary Owner|
|`nationality`|Alphanumeric|35|M|Nationality of the Ultimate Benefeciary Owner|
|**kycDetails**|-|||This is the object|
|`kycCategory`|-||M|POI/POA of the Ultimate Benefeciary Owner|
|`identityType`|Alphanumeric|50|M|Type of KYC Document submitted for UBO.
| | | | |For India - PAN/AADHAR |
| | | | |For ASEAN - Passport/Driving Licence/HKID or SGID or MYID |
| | | | |For AU - Passport/Driving Licence|
|`identityValue`|Alphanumeric|50|M|Value of the Kyc Document submitted|
|`identitymetaName1`|Alphanumeric|50|M|Additional information pertaning to the KYC documents submitted for UBO.
| | | | |For AU - Driving License State Code|
|`identitymetaValue1`|Alphanumeric|50|M|Additional information pertaning to the KYC documents submitted.
| | | | |For AU - Value Driving License State Code|
|**uboAddress**|-|||This is the object|
|`addressLine`|Alphanumeric|35|M|Address  of the Ultimate Benefeciary Owner|
|`addressLine2`|Alphanumeric|35|O|Address Line2 Ultimate Benefeciary Owner|
|`addressLine3`|Alphanumeric|35|O|Address Line3 Ultimate Benefeciary Owner|
|`city`|Alphanumeric|25|M|City of the Ultimate Benefeciary Owner|
|`state`|Alphanumeric|25|M|State of the Ultimate Benefeciary Owner|
|`pincode`|Alphanumeric|8|M|Pincode of the Ultimate Benefeciary Owner|
|`country`|Alphanumeric|25|M|Country of the Ultimate Benefeciary Owner|
|`mobileNo`|Numeric|15|M|Mobile number of Ultimate Benefeciary Owner|
|`phone1`|Numeric|15|M|phone 1 of the Ultimate Benefeciary Owner|
|`contactName`|Alphanumeric|35|M|Contact Name of Ultimate Benefeciary Owner|
|**bankDetails**|-|||This tag will contain the Bank account details of Partner/PayFac which needs to be configured at Fiserv End|
|**uwaccountdetails**|-|||UW Account details are primarily the actual merchant account which will be used while underwriting the merchant|
|`accountNo`|Numeric|100|M|Account number of the Merchant|
|`accountName`|Alphanumeric|35|M|Account name of the Merchant|
|`ifsc`|Alphanumeric|15|M|Ifsc of the Merchant|
|`bankName`|Alphanumeric|80|M|Bank name of the Merchant|
|`currency`|Alphanumeric|3|M|Currency of the Merchant|
|`branch`|Alphanumeric|500|M|Branch of the Merchant|
|`bankAddress`|Alphanumeric|500|O|Bank address of the Merchant|
|`accType`|Alphanumeric|30|M|Acc Type of the Merchant|
|**fundingaccountdetails**|-|||Funding account will have the details of account to which Fiserv will process the funding on daily basis|
|`accountNo`|Numeric|100|NA|If different from UW details|
|`accountName`|Alphanumeric|35|NA|Account number of the Merchant|
|`ifsc`|Alphanumeric|15|NA|Ifsc of the Merchant|
|`bankName`|Alphanumeric|80|NA|Bank Name of the Cerchant|
|`currency`|Alphanumeric|3|NA|Currency of the Merchant|
|`branch`|Alphanumeric|500|NA|Branch of the Merchant|
|`bankAddress`|Alphanumeric|500|NA|Bank address of the Merchant|
|`accType`|Alphanumeric|30|NA|Account Type of the Merchant|
|`collectionaccountdetails`|-|||This section will have details of account which needs to be used for collection of charges. This account may or may not be the same as UW account/Funding account|
|`accountNo`|Numeric|100|NA|If different form UW details|
|`accountName`|Alphanumeric|35|NA|Account name of the Merchant|
|`ifsc`|Alphanumeric|15|NA|Ifsc of the Merchant|
|`bankName`|Alphanumeric|80|NA|Bank Name of the Cerchant|
|`currency`|Alphanumeric|3|NA|Currency of the Merchant|
|`branch`|Alphanumeric|500|NA|Branch of the Merchant|
|`bankAddress`|Alphanumeric|500|NA|Bank address of the Merchant|
|`accType`|Alphanumeric|30|NA|Acc type of the Merchant|
|**submerchantDetails**|-|||This object is not applicable for ISO. This section is used to capture the sub Partner Details of the merchant|
|`submerchantID`|Numeric|15|NA|This is an optional field where the Single MID PayFacs can use to pass their own MID to Fiserv.|
|`submerchantID`|Numeric|15|NA|This field will be mandatory if the Channel level parameter for Payfac provided SMID is set to Y.|
|`submerchantID`|Numeric|15|NA|If the same is set to 'N', boarding backend will generate its own MID for the merchant|
|**businessSummary**|-|||This section is used to capture the summary of the merchant|
|`briefSummary`|Alphanumeric|100|M|Brief summary of the Merchant|
|`salessrNumber`|Alphanumeric|100|O|Sales number of the Merchant|
|`mccCode`|Numeric|20|M|MCC  number of the Merchant|
|`mccDescription`|Alphanumeric|200|M|MCC  description of the Merchant|
|`totalTurnover`|Numeric|20|M|Total  turnover number of the Merchant|
|`totalTurnoverPerMID`|Numeric|20|M|Total turnover per mid of the Merchant|
|`cardTurnover`|Numeric|20|M|Card turnover of the Merchant|
|`avgTicketAmt`|Numeric|20|M|Avg ticket amt of the Merchant|
|`dccTurnoverPerMID`|Numeric|20|M|Dcc turnover per mid of the Merchant|
|`pgTurnover`|Numeric|20|M|Pg  turnover of the Merchant|
|`pgTurnoverPerMID`|Numeric|20|M|Pg turnover per mid of the Merchant|
|`avgEMITicketAmt`|Numeric|20|M|Avg emi ticket amt of the Merchant|
|`tranVolumeInternet`|Numeric|20|M|Tran volume internet of the Merchant|
|`tranVolumeMoto`|Numeric|20|M|Tran volume moto of the Merchant|
|`tranVolumeinStore`|Numeric|20|M|Tran volume in store of the Merchant|
|`deliveryDays0`|Numeric|20|M|Delivery Days0 of the Merchant|
|`deliveryDays7`|Numeric|20|M|Delivery Days7 of the Merchant|
|`deliveryDays14`|Numeric|20|M|Delivery Days14 of the Merchant|
|`deliveryDays30`|Numeric|20|M|Delivery Days30 of the Merchant|
|`deliveryDaysOver30`|Numeric|20|M|Delivery Days Over30 of the Merchant|
|`tranTypeMagStrip`|Numeric|20|M|Tran type magstripe of the Merchant|
|`tranTypeChip`|Numeric|20|M|Tran type chip of the Merchant|
|`tranTypeKeyed`|Numeric|20|M|Tran type keyed of the Merchant|
|`creditSalesConsumer`|Numeric|20|M|Credit sales consumer of the Merchant|
|`creditSalesBusiness`|Numeric|20|M|Credit sales business of the Merchant|
|`firsReport`|Alphanumeric|20|NA|First report of the Merchant|
|`recurringTranFlag`|Alphanumeric|20|NA|Recurring tran flag of the Merchant|
|`refundPolicy`|Alphanumeric|20|NA|Refund policy of the Merchant|
|`cardRefundDays`|Alphanumeric|20|NA|Card refund days of the Merchant|
|`thirdPartyProcessorFlag`|Alphanumeric|20|M|Thirdparty processor flag of the Merchant|
|`thirdPartyProcessorName`|Alphanumeric|40|NA|Thirdparty processor name of the Merchant|
|`smallMerchant`|Alphanumeric|20|M|Applicable if the merchant is a Small Merchant|

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

The table below provides the list of application's error code and its description.

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