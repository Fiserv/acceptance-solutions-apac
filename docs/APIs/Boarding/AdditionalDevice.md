# Additional Device

This API is used to additional device. Merchants needs to add session 
token received during login api call in the header of this API.


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

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/addtid).

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
 | **terminals** | - | - | - | This is the object | - | - | - | 
 | `count` | M | *Numeric* | 2 | Count of terminals for the Merchant | M | NA | NA | 
 | `preferedDate` | M | *Numeric* | 8 | YYYYMMDD | M | NA | NA | 
 | `preferedTime` | M | *Numeric* | 	 | 6 | HHMMSS | M | NA | NA | 
 | `discount` | O | *Numeric* | 3 | Discount of the Merchant | M | NA | NA | 
 | `userInstruction1` | O | *Alphanumeric* | 100 | userInstruction1 of the Merchant | O | NA | NA | 
 | `userInstruction2` | O | *Alphanumeric* | 100 | userInstruction2 of the Merchant | O | NA | NA | 
 | `surchargeAmount` | - | - | - | Surcharge values currently selected by Partner on MVSI in AU | This object not applicable for ISO | This object not applicable forSingleMID PFAC | This object not applicable for Multimid PFAC | 
 | `visaBase` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `visaPercent` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `mcBase` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `mcPercent` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `upiBase` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `upiPercent` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `eftposBase` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `eftposPercent` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `amexBase` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `amexPercent` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `jcbBase` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `jcbPercent` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `dinersBase` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `dinersPercent` | C | *Numeric* | 11 | For AU Only | NA | NA | NA | 
 | `altmerchCode` | O | *Alphanumeric* | 20 | This is an optional field which has to be populated only if there is merchant MID or Dealer Code has to be captured at MID Level | NA | NA | NA | 
 | `sameLocation` | C | *Alphanumeric* | 1 | This flag has to be set to `Y` if Partner wants multiple MIDs at the same location | NA | NA | NA | 
 | `mid` | C | *Numeric* | 15 | This is the reference Member MID which needs to be given in case of ADD MID/ ADD TID. | O | NA | NA | 
 | `parentmid` | C | *Numeric* | 	 | 15 | This is the SG (parent MID) of the reference MID which needs to be given in case of ADD MID & ADD TID | 	O	 | NA | NA | 
 | `otpEnabled` | O | *Alphanumeric* | 10 | Otp alpber naf the Oerchant | M | NA | NA | 
 | **principalDetails** | - | - | - | This section is used to capture details of Principal Owner for the said merchant. The same section can be repeated for multiple Principal Owners. We can have upto maximum of 2 Principal Owners per merchant. | - | - | - | 
 | `principalNo` | M | *Alphanumeric* | 2 | Principal number of the Merchant | M | NA | NA | 
 | `position` | M | *Alphanumeric* | 20 | Position of the Merchant | M | NA | NA | 
 | `title` | M | *Alphanumeric* | 20 | Title of the Merchant | M | NA | NA | 
 | `firstName` | M | *Alphanumeric* | 25 | First Name mf the Merchant | M | NA | NA | 
 | `lastName` | M | *Alphanumeric* | 25 | Last Name of the Merchant | M | NA | NA | 
 | `middleName` | O | *Alphanumeric* | 25 | Middle Name of the Oerchant | M | NA | NA | 
 | `gender` | M | *Alphanumeric* | 10 | Gender of the Merchant | M | NA | NA | 
 | `dateOfBirth` | M | *Numeric* | 8 | YYYYMMDD | M | NA | NA | 
 | **kycDetails** | - | - | - | This is the object | - | - | - | 
 | `kycCategory` | - | - | - | POI/POA of the Merchant | - | - | NA | 
 | `identityType` | M | *Alphanumeric* | 50 | "Type of KYC Document submitted. | M | NA | NA | 
 | `identityType` | M | *Alphanumeric* | 50 | For India - PAN/AADHAR | M | NA | NA | 
 | `identityType` | M | *Alphanumeric* | 50 | For ASEAN - Passport/Driving Licence/HKID or SGID or MYID | M | NA | NA | 
 | `identityType` | M | *Alphanumeric* | 50 | For AU - Passport/Driving Licence" | M | NA | NA | 
 | `identityValue` | M | *Alphanumeric* | 100 | Value of the Kyc Document submitted | M | NA | NA | 
 | `identitymetaName1` | C | *Alphanumeric* | 100 | "Additional information pertaning to the KYC docuements submitted. For AU - Driving License State Code" | NA | NA | NA | 
 | `identitymetaValue1` | C | *Alphanumeric* | 100 | "Additional information pertaning to the KYC docuements submitted. For AU - Value Driving License State Code" | NA | NA | NA | 
 | `nationality` | M | *Alphanumeric* | 35 | Nationality of the Merchant | M | NA | NA | 
 | **principalAddress** | - | - | - | This is the object | - | - | - | 
 | `addressLine` | M | *Alphanumeric* | 35 | Address line of the Merchant | M | NA | NA | 
 | `addressLine2` | O | *Alphanumeric* | 35 | addressLine2 of the Merchant | O | NA | NA | 
 | `addressLine3` | O | *Alphanumeric* | 35 | addressLine3 of the Merchant | O | NA | NA | 
 | `city` | M | *Alphanumeric* | 25 | City of the Merchant | M | NA | NA | 
 | `state` | M | *Alphanumeric* | 25 | State of the Merchant | M | NA | NA | 
 | `pincode` | M | *Alphanumeric* | 8 | Pincode of the Merchant | M | NA | NA | 
 | `country` | M | *Alphanumeric* | 25 | Country of the Merchant | M | NA | NA | 
 | `mobileNo` | M | *Numeric* | 15 | Mobile number of the Merchant | M | NA | NA | 
 | `phone1` | O | *Numeric* | 15 | phone1 of the Merchant | M | NA | NA | 
 | `contactName` | M | *Alphanumeric* | 35 | Contact name of the Merchant | M | NA | NA | 
 | **idDocDetails** | C | - | - | "ID Doc Details section is a conditional tag and has to be mandatorily present if the user is uploding documents for a particular application. | - | This object not applicable forSingleMID PFAC | This object not applicable for Multimid PFAC | 
 | **idDocDetails** | C | - | - | All documents uploaded under ""categoryInd"": ""P"" has to be included under principalDetails.idDocDetails" | - | This object not applicable forSingleMID PFAC | This object not applicable for Multimid PFAC | 
 | `entity` | C | - | - | Static Value - `Member` | M | NA | NA | 
 | `idType` | C | - | - | Value of docType received as response of uploaded document | M | NA | NA | 
 | `idValue` | C- | - | -M | NA | NA | 
 | `docId` | C | - | - | Value of docID received as response of uploaded document | M | NA | NA | 
 | `categoryName` | C | *Alphanumeric* | 30 | Value of categoryName received as response of uploaded document | M | NA | NA | 
 | `level` | C | *Alphanumeric* | 2 | Value of level received as response of uploaded document | M | NA | NA | 
 | `mandatory` | C | *Alphanumeric* | 10 | Mandatory of the Merchant | M | NA | NA | 
 | `entity` | C | - | - | Static Value - `Member` | M | NA | NA | 
 | `idType` | C | - | - | Value of docType received as response of uploaded document | M | NA | NA | 
 | `idValue` | C | - | - | - | M | NA | NA | 
 | `docId` | C | - | - | Value of docID received as response of uploaded document | M | NA | NA | 
 | `categoryName` | C | *Alphanumeric* | 30 | Value of categoryName received as response of uploaded document | M | NA | NA | 
 | `level` | C | *Alphanumeric* | 2 | Value of level received as response of uploaded document | M | NA | NA | 
 | `mandatory` | C | *Alphanumeric* | 10 | Mandatory of the Merchant | M | NA | NA | 
 | **uboDetails** | - | - | - | This section is used to capture details of Ultimate Benefeciary Owner for the said merchant. The same section can be repeated for multiple UBOs. We can have upto maximum of 5 UBOs per merchant. | - | - | This object not applicable for Multimid PFAC | 
 | `serialNo` | C | *Numeric* | 2 | Serial number of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `title` | C | *Alphanumeric* | 20 | Title of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `firstName` | C | *Alphanumeric* | 25 | First NAme of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `lastName` | C | *Alphanumeric* | 25 | Last NAme of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `middleName` | O | *Alphanumeric* | 25 | Middle NAme of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `dateOfBirth` | C | *Numeric* | 10 | Format - YYYYMMDD | M | NA | NA | 
 | `shareholderPercentage` | C | *Numeric* | 8 | Shareholder percentage the Ultimate Benefeciary Owner | M | NA | NA | 
 | `Nationality` | C | *Alphanumeric* | 35 | Nationality of the Ultimate Benefeciary Owner | M | NA | NA | 
 | **kycDetails** | C | - | - | This is the object | - | - | - | 
 | `kycCategory` | - | - | - | POI/POA of the Ultimate Benefeciary Owner | - | NA | NA | 
 | `identityType` | C | *Alphanumeric* | 50 | "Type of KYC Document submitted for UBO. | M | NA | NA | 
 | `identityType` | C | *Alphanumeric* | 50 | For India - PAN/AADHAR | M | NA | NA | 
 | `identityType` | C | *Alphanumeric* | 50 | For ASEAN - Passport/Driving Licence/HKID or SGID or MYID | M | NA | NA | 
 | `identityType` | C | *Alphanumeric* | 50 | For AU - Passport/Driving Licence" | M | NA | NA | 
 | `identityValue` | C | *Alphanumeric* | 100 | Value of the Kyc Document submitted | M | NA | NA | 
 | `identitymetaName1` | C | *Alphanumeric* | 100 | "AdditioNAl information pertaning to the KYC docuements submitted for UBO. | O | NA | NA | 
 | `identitymetaName1` | C | *Alphanumeric* | 100 | For AU - Driving License State Code" | O | NA | NA | 
 | `identitymetaValue1` | C | *Alphanumeric* | 100 | "AdditioNAl information pertaning to the KYC docuements submitted. | O | NA | NA | 
 | `identitymetaValue1` | C | *Alphanumeric* | 100 | For AU - Value Driving License State Code" | O | NA | NA | 
 | **uboAddress** | - | - | - | This is the object | - | NA | NA | 
 | `addressLine` | C | *Alphanumeric* | 35 | Address of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `addressLine2` | O | *Alphanumeric* | 35 | addressLine2 Ultimate Benefeciary Owner | O | NA | NA | 
 | `addressLine3` | O | *Alphanumeric* | 35 | addressLine3 Ultimate Benefeciary Owner | O | NA | NA | 
 | `city` | C | *Alphanumeric* | 25 | City of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `state` | C | *Alphanumeric* | 25 | State of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `pincode` | C | *Alphanumeric* | 8 | Pincode of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `country` | C | *Alphanumeric* | 25 | Country of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `mobileNo` | C | *Numeric* | 15 | Mobile number of Ultimate Benefeciary Owner | M | NA | NA | 
 | `phone1` | O | *Numeric* | 15 | phone1 of the Ultimate Benefeciary Owner | M | NA | NA | 
 | `contactName` | C | *Alphanumeric* | 35 | Contact Name of Ultimate Benefeciary Owner | M | NA | NA | 
 | **bankDetails** | - | - | - | This tag will contain the Bank account details of Partner/PayFac which needs to be configured at Fiserv End | - | This object is not applicable for SingleMid PFAC | This object not applicable for MultiMid PFAC | 
 | **uwaccountdetails** | - | - | - | UW Account details are primarily the actual merchant account which will be used while underwriting the merchant | - | - | - | 
 | `accountNo` | M | *Numeric* | 100 | Account number of the Merchant | M | NA | NA | 
 | `accountName` | M | *Alphanumeric* | 35 | Account name of the Merchant | M | NA | NA | 
 | `ifsc` | M | *Alphanumeric* | 15 | Ifsc of the Merchant | M | NA | NA | 
 | `bankName` | M | *Alphanumeric* | 80 | Bank name of the Merchant | M | NA | NA | 
 | `currency` | M | *Alphanumeric* | 3 | Currency of the Merchant | M | NA | NA | 
 | `branch` | O | *Alphanumeric* | 500 | Branch of the Merchant | M | NA | NA | 
 | `bankAddress` | M | *Alphanumeric* | 500 | Bank address of the Merchant | O | NA | NA | 
 | `accType` | M | *Alphanumeric* | 30 | Acc Type of the Merchant | M | NA | NA | 
 | **fundingaccountdetails** | C | - | - | "Funding account will the details of account to which Fiserv will process the funding on daily basis. | - | - | - | 
 | `fundingaccountdetails` | C | - | - | For PayFacs, this will be the PayFac account. | - | - | - | 
 | `fundingaccountdetails` | C | - | - | For Normal Partners, UW Account & Funding account both will be the same" | - | - | - | 
 | `accountNo` | C | *Numeric* | 100 | If different form UW details | NA | NA | NA | 
 | `accountName` | C | *Alphanumeric* | 35 | Account number of the Merchant | NA | NA | NA | 
 | `ifsc` | C | *Alphanumeric* | 15 | Ifsc of the Merchant | NA | NA | NA | 
 | `bankName` | C | *Alphanumeric* | 80 | Bank Name of the Cerchant | NA | NA | NA | 
 | `currency` | C | *Alphanumeric* | 3 | Currency of the Merchant | NA | NA | NA | 
 | `branch` | O | *Alphanumeric* | 500 | Branch of the Merchant | NA | NA | NA | 
 | `bankAddress` | C | *Alphanumeric* | 500 | Bank address of the Merchant | NA | NA | NA | 
 | `accType` | C | *Alphanumeric* | - | Account Type of the Merchant | NA | NA | NA | 
 | **collectionaccountdetails** | C | - | - | "This section will have details of account which needs to be used for collection of charges. This account may or may not be the same as UW account/Funding account." | - | - | - | 
 | `accountNo` | C | *Numeric* | 100 | If different form UW details | NA | NA | NA | 
  |  `accountName`  |  C  |  *Alphanumeric*  |  35  |  Account name of the Merchant  |  NA  |  NA  |  NA  |  
  |  `ifsc`  |  C  |  *Alphanumeric*  |  15  |  Ifsc of the Merchant  |  NA  |  NA  |  NA  |  
  |  `bankName`  |  C  |  *Alphanumeric*  |  80  |  Bank Name of the Cerchant  |  NA  |  NA  |  NA  |  
  |  `currency`  |  C  |  *Alphanumeric*  |  3  |  Currency of the Merchant  |  NA  |  NA  |  NA  |  
  |  `branch`  |  O  |  *Alphanumeric*  |  500  |  Branch of the Merchant  |  NA  |  NA  |  NA  |  
  |  `bankAddress`  |  C  |  *Alphanumeric*  |  500  |  Bank address of the Merchant  |  NA  |  NA  |  NA  |  
  |  `accType`  |  	C  |  *Alphanumeric*  |  30  |  Acc type of the Merchant  |  NA  |  NA  |  NA  |  
  |  **submerchantDetails**  |  -  |  -  |  -  |  This section is used to capture the sub Partner Details of the merchant  |  This object is not applicable for ISO   |  This object is not applicable for SingleMid PFAC  |  This object is not applicable for MultiMid PFAC  |  
  |  `submerchantID`  |  C  |  *Numeric*  |  15  |  "This is an optional field which the Single MID PayFacs can use to pass their own MID to Fiserv.  |  NA  |  NA  |  NA  |  
  |  `submerchantID`  |  C  |  *Numeric*  |  15  |  This field will be mandatory if the Channel level parameter for Payfac Provided SMID is set to Y.  |  NA  |  NA  |  NA  |  
  |  `submerchantID`  |  C  |  *Numeric*  |  15  |  If the same is set to `N', Boarding backend will generate its own MID for the merchant"  |  NA  |  NA  |  NA  |  
  |  **businessSummary**  |  -  |  -  |  -  |  This section is used to capture the summary of the merchant  |  -  |  -  |  -  |  
  |  `briefSummary`  |  M  |  *Alphanumeric*  |  100  |  Brief summary of the Merchant  |  M  |  NA  |  NA  |  
  |  `salessrNumber`  |  O  |  *Alphanumeric*  |  100  |  Sales number of the Merchant  |  O  |  NA  |  NA  |  
  |  `mccCode`  |  M  |  *Numeric*  |  20  |  Mcc number of the Merchant  |  M  |  NA  |  NA  |  
  |  `mccDescription`  |  M  |  *Alphanumeric*  |  200  |  Mcc description of the Merchant  |  M  |  NA  |  NA  |  
  |  `totalTurnover`  |  M  |  *Numeric*  |  20  |  Total turnover number of the Merchant  |  M  |  NA  |  NA  |  
  |  `totalTurnoverPerMID`  |  M  |  *Numeric*  |  20  |  Totalturnoverpermid of the Merchant  |  M  |  NA  |  NA  |  
  |  `cardTurnover`  |  M  |  *Numeric*  |  20  |  Card turnover of the Merchant  |  M  |  NA  |  NA  |  
  |  `avgTicketAmt`  |  M  |  *Numeric*  |  20  |  Avgticketamt of the Merchant  |  M  |  NA  |  NA  |  
  |  `dccTurnoverPerMID`  |  M  |  *Numeric*  |  20  |  Dccturnoverpermid of the Merchant  |  M  |  NA  |  NA  |  
  |  `pgTurnover`  |  M  |  *Numeric*  |  20  |  Pg turnover of the Merchant  |  M  |  NA  |  NA  |  
  |  `pgTurnoverPerMID`  |  M  |  *Numeric*  |  20  |  Pgturnoverpermid of the Merchant  |  M  |  NA  |  NA  |  
  |  `avgEMITicketAmt`  |  O  |  *Numeric*  |  20  |  Avgemiticketamt of the Merchant  |  M  |  NA  |  NA  |  
  |  `tranVolumeInternet`  |  M  |  *Numeric*  |  20  |  Tranvolume internet of the Merchant  |  M  |  NA  |  NA  |  
  |  `tranVolumeMoto`  |  M  |  *Numeric*  |  20  |  Tranvolume moto of the Merchant  |  M  |  NA  |  NA  |  
  |  `tranVolumeinStore`  |  M  |  *Numeric*  |  20  |  Tranvolume in store of the Merchant  |  M  |  NA  |  NA  |  
  |  `deliveryDays0`  |  M  |  *Numeric*  |  20  |  deliveryDays0 of the Merchant  |  M  |  NA  |  NA  |  
  |  `deliveryDays7`  |  M  |  *Numeric*  |  20  |  deliveryDays7 of the Merchant  |  M  |  NA  |  NA  |  
  |  `deliveryDays14`  |  M  |  *Numeric*  |  20  |  deliveryDays14 of the Merchant  |  M  |  NA  |  NA  |  
  |  `deliveryDays30`  |  M  |  *Numeric*  |  20  |  deliveryDays30 of the Merchant  |  M  |  NA  |  NA  |  
  |  `deliveryDaysOver30`  |  M  |  *Numeric*  |  20  |  deliveryDaysOver30 of the Merchant  |  M  |  NA  |  NA  |  
  |  `tranTypeMagStrip`  |  M  |  *Numeric*  |  20  |  Trantypemagstrip of the Merchant  |  M  |  NA  |  NA  |  
  |  `tranTypeChip`  |  M  |  *Numeric*  |  20  |  Trantypechip of the Merchant  |  M  |  NA  |  NA  |  
  |  `tranTypeKeyed`  |  M  |  *Numeric*  |  20  |  Trantypekeyed of the Merchant  |  M  |  NA  |  NA  |  
  |  `creditSalesConsumer`  |  M  |  *Numeric*  |  20  |  Creditsalesconsumer of the Merchant  |  M  |  NA  |  NA  |  
  |  `creditSalesBusiness`  |  M  |  *Numeric*  |  20  |  Creditsalesbusiness of the Merchant  |  M  |  NA  |  NA  |  
  |  `firsReport`  |  O  |  *Alphanumeric*  |  20  |  Firs report of the Merchant  |  NA  |  NA  |  NA  |  
  |  `recurringTranFlag`  |  O  |  *Alphanumeric*  |  20  |  Recurringtranflag of the Merchant  |  NA  |  NA  |  NA  |  
  |  `refundPolicy`  |  O  |  *Alphanumeric*  |  20  |  Refund policy of the Merchant  |  NA  |  NA  |  NA  |  
  |  `cardRefundDays`  |  O  |  *Alphanumeric*  |  20  |  Cardrefunddays of the Merchant  |  NA  |  NA  |  NA  |  
  |  `thirdPartyProcessorFlag`  |  O  |  *Alphanumeric*  |  20  |  Thirdpartyprocessorflag of the Merchant  |  M  |  NA  |  NA  |  
  |  `thirdPartyProcessorName`  |  O  |  *Alphanumeric*  |  40  |  Thirdpartyprocessorname of the Merchant  |  NA  |  NA  |  NA  |  
  |  `smallMerchant`  |  O  |  *Alphanumeric*  |  20  |  Applicable if the merchant is a Small Merchant  |  M  |  NA  |  NA  |


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