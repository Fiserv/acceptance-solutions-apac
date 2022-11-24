# Additional Outlet

This API is used to submit the application details for additional trading location for an existing merchant.

## How it works
1. Payment Facilitators needs to use this API to board their sub-merchants under Payment Facilitator master MID created on Fiserv Platform.
2. Merchant has to trigger this API post Create URN API. Below APIs can be optionally used to contribute to the data to be submitted 
   as part of New Partner Application Submit API.
    - Get Packages
    - Get Document Matrix
    - Upload Document


## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/addmid`

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

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/addmid).

### Request
| Field Name | Type | Length | Mandatory / Optional / Conditional (M / O / C ) | Description / Values | 
| -------- | ------- | -- | ------------ | -- | 
|`appURN`|Alphanumeric|30|M|App URN retured as part of Create URN API.|
|`appType`|Alphanumeric|8|M|Fixed Value API |
|`salesId`|Alphanumeric|70|M|User Credential created for each partner.|
|`channelCode`|Alphanumeric|10|C|Static Channel Code shared with each partner.|
|`institutionId`|Numeric|10|C|Institution number assigned to the institution.|
|`boardingType`|Alphanumeric|20|O|Type of Merchant: New MID / Add MID / Add TID|
|`IS_ADD_LOCATION`|Alphanumeric|20|O|Applicable if the merchant wants additional location.|
|`IS_ADD_MID`|Alphanumeric|20|O|Applicable if the merchant wants additional MID.|
|`appChannel`|Alphanumeric|20|O|Application channel|
|`osvFlagValue`|Alphanumeric|1|O|Original Sent & Verified flag. Applicable for entities where documents are uploaded. For entities not uploading documents, keep this field as blank.|
|**merchantDetails**|||||
|`businessName`|Alphanumeric|22|M|Trade Name of the Merchant.|
|`legalName`|Alphanumeric|35|M|Legal Name of the Merchant.|
|`businessType`|Alphanumeric|50|M|Type of Business of the Merchant.|
|`registrationNo`|Alphanumeric|100|M|Registration number of the Merchant.|
|`taxDetails`|-||||
|`taxidType`|Alphanumeric|50|M|Tax ID Type provided for the merchant.
| | | | | For India - PAN |
| | | | | For AU - ABN |
|`taxidValue`|Alphanumeric|50|M|Tax ID Value provided for the merchant. |
| | | | | For India - Individual PAN for Individual / Soleprop merchants
| | | | | Corporate PAN for other type of merchants |
| | | | | For AU - ABN Value|
|`dateIncorporated`|Alphanumeric|50|M|YYYYMMDD|
|`websiteURL`|Alphanumeric|100|M|Eligible for ECOM Merchant.|
|`communicationEmail`|Alphanumeric|100|M|Communication Email of the Merchant.|
|`merchantType`|Alphanumeric|100|M|Whether it is small merchant or Large merchant|
|`acceptanceType`|Alphanumeric|100|M|Static Value - ''POSMOB'' for POS merchant.|
| | | | | Static Value - ''ECOM'' for ECOM merchant|
|`iciciMerchant`|Alphanumeric|100|M|Applicable if the merchant has ICICI account.|
|`newFundingAc`|Alphanumeric|100|M|Applicable if the merchant wants the new settlement account.|
|**legalAddress**|||||
|`addressLine`|Alphanumeric|100|C|Address of the Merchant.|
|`addressLine2`|Alphanumeric|60|M|Address of the Merchant.|
|`addressLine3`|Alphanumeric|20|M|Address of the Merchant.|
|`city`|Alphanumeric|10|M|City of the Merchant.|
|`state`|Alphanumeric|20|M|State of the Merchant.|
|`pincode`|Alphanumeric|20|M|Pincode of the Merchant.|
|`country`|-|||Country of the Merchant.|
|`mobileNo`|Alphanumeric|35|M|Mobile number of the Merchant.|
|`phone1`|Alphanumeric|35|O|Phone number of the Merchant.|
|`email`|Alphanumeric|35|O|Email of the Merchant.|
|`contactName`|Alphanumeric|25|M|Contact Name of the Merchant.|
|`gstNo`|Alphanumeric|25|M|Mandatory for Large merchants.|
|`gstMerchantStateCode`|Alphanumeric|8|M|Mandatory for Large Partners.|
|`isdnFlag`|Alphanumeric|25|M|Isdn Flag|
|**idDocDetails**|Numeric|15|M|ID Doc Details section is a conditional tag and should be mandatory for a user uploding documents in an application. All documents uploaded under "categoryInd": "E" has to be included under merchantDetails - idDocDetails|
|`entity`|Numeric|15|O|Static Value - 'Member'|
|`idType`|Numeric|30|O|Value of docType received as response of uploaded document.|
|`idValue`|Alphanumeric|35|M|Id Value|
|`docId`|Alphanumeric|100|C|Value of docID received as response of uploaded document.|
|`categoryName`|Alphanumeric|40|O|Value of categoryName received as response of uploaded document.|
|`level`|Alphanumeric|20|C|Value of level received as response of uploaded document.|
|`entity`|-|||Static Value - 'Member'|
|`idType`|Alphanumeric|20|C|Value of docType received as response of uploaded document.|
|`idValue`|Alphanumeric|20|C|Id Value|
|`docId`|Alphanumeric|20|C|Value of docID received as response of uploaded document.|
|`categoryName`|Alphanumeric|20|C|Value of categoryName received as response of uploaded document.|
|`level`|Alphanumeric|20|C|Value of level received as response of uploaded document.|
|**geoLocation**|||||
|`latitude`|Alphanumeric|20|C|Latitude of the Merchant.|
|`longitude`|Alphanumeric|20|C|Longitude of the Merchant.|
|**tradingLocations**|Alphanumeric|20|C|This section contains the trading location details of merchants that is being onboarded. A maximum upto 3 trading locations can be added under a single Application.|
|`locationNo`|Alphanumeric|20|C|Trading location number of the Merchant.|
|`tradingName`|Alphanumeric|20|C|Trade Name of the Merchant.|
|**tradingAddress**|||||
|`addressLine`|-|||Address of the Merchant.|
|`addressLine2`|Numeric|20|O|Address of the Merchant.|
|`addressLine3`|Numeric|20|O|Address of the Merchant.|
|`city`|-|||City of the Merchant.|
|`state`|Numeric|2|M|State of the Merchant.|
|`pincode`|Alphanumeric|22|M|Pincode of the Merchant.|
|`country`|-|||Country of the Merchant.|
|`mobileNo`|Alphanumeric|35|M|Mobile number of the Merchant.|
|`phone1`|Alphanumeric|35|O|phone1 of the Merchant.|
|`email`|Alphanumeric|35|O|Email of the Merchant.|
|`contactName`|Alphanumeric|25|M|Contact name of the Merchant.|
|`packageId`|Alphanumeric|25|M|Package number assigned to the Merchant|
|`autoSettlementTime`|Alphanumeric|8|M|HHMMSS|
|`cpvGroupId`|Alphanumeric|25|M|Cpv groupid of the Merchant.|
|`regionalcpvGroupid`|Numeric|15|M|Regional cpv groupid of the Merchant.|
|`commerceConnectReferenceMID`|Numeric|15|O|Commerce connect reference mid of the Merchant.|
|**terminals**|||||
|`count`|Alphanumeric|35|M|Count of terminals for the Merchant.|
|`preferedDate`|Numeric|10|M|YYYYMMDD|
|`preferedTime`|Numeric|6|O|HHMMSS|
|`discount`|Alphanumeric|50|O|Discount of the Merchant.|
|`userInstruction1`|Alphanumeric|50|O|User Instruction 1 of the Merchant.|
|`userInstruction2`|Alphanumeric|8|O|User Instruction 2 of the Merchant.|
|**surchargeAmount**|-|||This object is not applicable for ISO. Surcharge values currently selected by Partner on MVSI in AU|
|`visaBase`|Numeric|2|M|For AU Only.|
|`visaPercent`|Numeric|8|M|For AU Only.|
|`mcBase`|Numeric|6|M|For AU Only.|
|`mcPercent`|Numeric|3|O|For AU Only.|
|`upiBase`|Alphanumeric|100|O|For AU Only.|
|`upiPercent`|Alphanumeric|100|O|For AU Only.|
|`eftposBase`|-|||For AU Only.|
|`eftposPercent`|Numeric|11|C|For AU Only.|
|`amexBase`|Numeric|11|C|For AU Only.|
|`amexPercent`|Numeric|11|C|For AU Only.|
|`jcbBase`|Numeric|11|C|For AU Only.|
|`jcbPercent`|Numeric|11|C|For AU Only.|
|`dinersBase`|Numeric|11|C|For AU Only.|
|`dinersPercent`|Numeric|11|C|For AU Only.|
|`altmerchCode`|Numeric|11|C|This is an optional field which has to be populated only if there is merchant MID or Dealer Code has to be captured at MID Level.|
|`sameLocation`|Numeric|11|C|This flag has to be set to 'Y' if Partner wants multiple MIDs at the same location.|
|`mid`|Numeric|11|C|This is the reference Member MID which needs to be given in case of ADD MID / ADD TID.|
|`parentmid`|Numeric|11|C|This is the SG (parent MID) of the reference MID which needs to be given in case of ADD MID & ADD TID.|
|`otpEnabled`|Numeric|11|C|Otp enabled for the merchant.|
|**principalDetails**|Numeric|11|C|This section is used to capture details of Principal Owner for the said merchant. The same section can be repeated for multiple Principal Owners. We can have upto maximum of 2 Principal Owners per merchant.|
|`principalNo`|Numeric|11|C|Principal number of the Merchant.|
|`position`|Alphanumeric|20|O|Position of the Merchant.|
|`title`|Alphanumeric|1|C|Title of the Merchant.|
|`firstName`|Numeric|15|C|First Name mf the Merchant.|
|`lastName`|Numeric|15|C|Last Name of the Merchant.|
|`middleName`|Alphanumeric|10|O|Middle Name of the Merchant.|
|`gender`|-|||Gender of the Merchant.|
|`dateOfBirth`|Alphanumeric|2|M|YYYYMMDD|
|**kycDetails**|||||
|`kycCategory`|Alphanumeric|20|M|POI / POA of the Merchant.|
|`identityType`|Alphanumeric|25|M|Type of KYC Document submitted.
| | | | | For India - PAN/AADHAR |
| | | | | For ASEAN - Passport / Driving Licence / HKID or SGID or MYID |
| | | | | For AU - Passport / Driving Licence|
|`identityValue`|Alphanumeric|25|M|Value of the KYC Document submitted.|
|`identitymetaName1`|Alphanumeric|25|O|Additional information pertaning to the KYC documents submitted. For AU - Driving License State Code.|
|`identitymetaValue1`|Alphanumeric|10|M|Additional information pertaning to the KYC documents submitted. For AU - Value Driving License State Code.|
|`nationality`|Numeric|8|M|Nationality of the Merchant.|
|**principalAddress**|||||
|`addressLine`|-|||Address  line of the Merchant.|
|`addressLine2`|Alphanumeric|50|M|Address Line 2 of the Merchant.|
|`addressLine3`|Alphanumeric|50|M|Address Line 3 of the Merchant.|
|`city`|Alphanumeric|50|M|City of the Merchant.|
|`state`|Alphanumeric|50|M|State of the Merchant.|
|`pincode`|Alphanumeric|100|M|Pincode of the Merchant.|
|`country`|Alphanumeric|100|C|Country of the Merchant.|
|`mobileNo`|Alphanumeric|100|C|Mobile number of the Merchant.|
|`phone1`|Alphanumeric|35|M|phone 1 of the Merchant.|
|`contactName`|-|||Contact name of the Merchant.|
|**idDocDetails**|Alphanumeric|35|M|ID Doc Details section is a conditional tag and should be mandatory for a user uploding documents in an application. All documents uploaded under "categoryInd": "P" has to be included under principalDetails - idDocDetails|
|`level`|Alphanumeric|35|O|Value of level received as response of uploaded document.|
|`mandatory`|Alphanumeric|25|M|Mandatory of the Merchant.|
|`entity`|Alphanumeric|25|M|Static Value - 'Member'|
|`idType`|Alphanumeric|8|M|Value of docType received as response of uploaded document.|
|`idValue`|Alphanumeric|25|M|Id value|
|`docId`|Numeric|15|M|Value of docID received as response of uploaded document.|
|`categoryName`|Numeric|15|O|Value of categoryName received as response of uploaded document.|
|**uboDetails**|Alphanumeric|35|M|This section is used to capture details of Ultimate Benefeciary Owner for the said merchant. The same section can be repeated for multiple UBOs. We can have upto maximum of 5 UBOs per merchant.|
|`serialNo`|-||C|Serial number of the Ultimate Benefeciary Owner.|
|`title`|-||C|Title of the Ultimate Benefeciary Owner.|
|`firstName`|Alphanumeric|2|C|First name of the Ultimate Benefeciary Owner.|
|`lastName`|Alphanumeric|10|C|Last name of the Ultimate Benefeciary Owner.|
|`middleName`|Alphanumeric|20|C|Middle name of the Ultimate Benefeciary Owner.|
|`dateOfBirth`|Alphanumeric|20|C|Format - YYYYMMDD|
|`shareholderPercentage`|Alphanumeric|20|C|Shareholder percentage the Ultimate Benefeciary Owner.|
|`nationality`|-||C|Nationality of the Ultimate Benefeciary Owner.|
|**kycDetails**|||||
|`kycCategory`|-|||POI / POA of the Ultimate Benefeciary Owner.|
|`identityType`|Numeric|2|C|Type of KYC Document submitted for UBO.
| | | | |For India - PAN / AADHAR |
| | | | |For ASEAN - Passport / Driving Licence / HKID or SGID or MYID |
| | | | |For AU - Passport / Driving Licence|
|`identityValue`|Alphanumeric|20|C|Value of the KYC Document submitted.|
|`identitymetaName1`|Alphanumeric|25|C|Additional information pertaning to the KYC documents submitted for UBO.
| | | | | For AU - Driving License State Code|
|`identitymetaValue1`|Alphanumeric|25|C|Additional information pertaning to the KYC docuements submitted.
| | | | | For AU - Value Driving License State Code|
|`uboAddress`|||||
|`addressLine`|Numeric|10|C|Address  of the Ultimate Benefeciary Owner.|
|`addressLine2`|Numeric|8|C|Address Line 2 Ultimate Benefeciary Owner.|
|`addressLine3`|Alphanumeric|35|C|Address Line 3 Ultimate Benefeciary Owner.|
|`city`|-|||City of the Ultimate Benefeciary Owner.|
|`state`|-|||State of the Ultimate Benefeciary Owner.|
|`pincode`|Alphanumeric|50|C|Pincode of the Ultimate Benefeciary Owner.|
|`country`|Alphanumeric|50|C|Country of the Ultimate Benefeciary Owner.|
|`mobileNo`|Alphanumeric|50|C|Mobile number of Ultimate Benefeciary Owner.|
|`phone1`|Alphanumeric|50|C|phone 1 of the Ultimate Benefeciary Owner.|
|`contactName`|Alphanumeric|100|C|Contact Name of Ultimate Benefeciary Owner.|
|**bankDetails**|Alphanumeric|100|C|This tag will contain the Bank account details of Partner/PayFac which needs to be configured at Fiserv End.|
|**uwaccountdetails**|Alphanumeric|100|C|UW Account details are primarily the actual merchant account which will be used while underwriting the merchant.|
|`accountNo`|Alphanumeric|100|C|Account number of the Merchant.|
|`accountName`|Alphanumeric|100|C|Account name of the Merchant.|
|`ifsc`|-|||Ifsc of the Merchant.|
|`bankName`|Alphanumeric|35|C|Bank name of the Merchant.|
|`currency`|Alphanumeric|35|O|Currency of the Merchant.|
|`branch`|Alphanumeric|35|O|Branch of the Merchant.|
|`bankAddress`|Alphanumeric|25|C|Bank address of the Merchant.|
|`accType`|Alphanumeric|25|C|Acc Type of the Merchant.|
|**fundingaccountdetails**|Alphanumeric|8|C|Funding account will have the details of account to which Fiserv will process the funding on daily basis.|
|`accountNo`|Alphanumeric|25|C|If different from UW details.|
|`accountName`|Numeric|15|C|Account name of the Merchant.|
|`ifsc`|Numeric|15|O|Ifsc of the Merchant.|
|`bankName`|Alphanumeric|35|C|Bank Name of the Merchant.|
|`currency`|-|||Currency of the Merchant.|
|`branch`|-|||Branch of the Merchant.|
|`bankAddress`|Numeric|100|M|Bank address of the Merchant.|
|`accType`|Alphanumeric|35|M|Account Type of the Merchant.|
|`collectionaccountdetails`|Alphanumeric|15|M|This section will have details of account which needs to be used for collection of charges. This account may or may not be the same as UW account/Funding account.|
|`accountNo`|Alphanumeric|80|M|If different form UW details.|
|`accountName`|Alphanumeric|3|M|Account name of the Merchant.|
|`ifsc`|Alphanumeric|500|O|Ifsc of the Merchant.|
|`bankName`|Alphanumeric|500|M|Bank Name of the Merchant.|
|`currency`|Alphanumeric|30|M|Currency of the Merchant.|
|`branch`|-|||Branch of the Merchant.|
|`bankAddress`|Numeric|100|C|Bank address of the Merchant.|
|`accType`|Alphanumeric|35|C|Acc type of the Merchant.|
|**submerchantDetails**|Alphanumeric|15|C|This object is not applicable for ISO. This section is used to capture the sub Partner Details of the Merchant.|
|`submerchantID`|Alphanumeric|80|C|This is an optional field where the Single MID PayFacs can use to pass their own MID to Fiserv.|
|`submerchantID`|Alphanumeric|3|C|This field will be mandatory if the Channel level parameter for Payfac provided SMID is set to Y.|
|`submerchantID`|Alphanumeric|500|O|If the same is set to 'N', boarding backend will generate its own MID for the merchant.|
|**businessSummary**|Alphanumeric|500|C|This section is used to capture the summary of the Merchant.|
|`briefSummary`|Alphanumeric|30|C|Brief summary of the Merchant.|
|`salessrNumber`|-|||Sales number of the Merchant.|
|`mccCode`|Numeric|100|C|MCC  number of the Merchant.|
|`mccDescription`|Alphanumeric|35|C|MCC  description of the Merchant.|
|`totalTurnover`|Alphanumeric|15|C|Total  turnover number of the Merchant.|
|`totalTurnoverPerMID`|Alphanumeric|80|C|Total turnover per mid of the Merchant.|
|`cardTurnover`|Alphanumeric|3|C|Card turnover of the Merchant.|
|`avgTicketAmt`|Alphanumeric|500|O|Avg ticket amt of the Merchant.|
|`dccTurnoverPerMID`|Alphanumeric|500|C|Dcc turnover per mid of the Merchant.|
|`pgTurnover`|Alphanumeric|30|C|Pg  turnover of the Merchant.|
|`pgTurnoverPerMID`|-|||Pg turnover per mid of the Merchant.|
|`avgEMITicketAmt`|Numeric|15|C|Avg emi ticket amt of the Merchant.|
|`tranVolumeInternet`|Numeric|15|C|Tran volume internet of the Merchant.|
|`tranVolumeMoto`|Numeric|15|C|Tran volume moto of the Merchant.|
|`tranVolumeinStore`|-|||Tran volume in store of the Merchant.|
|`deliveryDays0`|Alphanumeric|100|M|Delivery Days 0 of the Merchant.|
|`deliveryDays7`|Alphanumeric|100|O|Delivery Days 7 of the Merchant.|
|`deliveryDays14`|Numeric|20|M|Delivery Days 14 of the Merchant.|
|`deliveryDays30`|Alphanumeric|200|M|Delivery Days 30 of the Merchant.|
|`deliveryDaysOver30`|Numeric|20|M|Delivery Days Over 30 of the Merchant.|
|`tranTypeMagStrip`|Numeric|20|M|Tran type magstripe of the Merchant.|
|`tranTypeChip`|Numeric|20|M|Tran type chip of the Merchant.|
|`tranTypeKeyed`|Numeric|20|M|Tran type keyed of the Merchant.|
|`creditSalesConsumer`|Numeric|20|M|Credit sales consumer of the Merchant.|
|`creditSalesBusiness`|Numeric|20|M|Credit sales business of the Merchant.|
|`firsReport`|Numeric|20|M|First report of the Merchant.|
|`recurringTranFlag`|Numeric|20|O|Recurring tran flag of the Merchant.|
|`refundPolicy`|Numeric|20|M|Refund policy of the Merchant.|
|`cardRefundDays`|Numeric|20|M|Card refund days of the Merchant.|
|`thirdPartyProcessorFlag`|Numeric|20|M|Thirdparty processor flag of the Merchant.|
|`thirdPartyProcessorName`|Numeric|20|M|Thirdparty processor name of the Merchant.|
|`smallMerchant`|Numeric|20|M|Applicable if the merchant is a Small Merchant.|
|`deliveryDays14`|Numeric|20|M|Delivery Days 14 of the Merchant.|
|`deliveryDays30`|Numeric|20|M|Delivery Days 30 of the Merchant.|
|`deliveryDaysOver30`|Numeric|20|M|Delivery Days Over 30 of the Merchant.|
|`tranTypeMagStrip`|Numeric|20|M|Tran type magstripe of the Merchant.|
|`tranTypeChip`|Numeric|20|M|Tran type chip of the Merchant.|
|`tranTypeKeyed`|Numeric|20|M|Tran type keyed of the Merchant.|
|`creditSalesConsumer`|Numeric|20|M|Credit sales consumer of the Merchant.|
|`creditSalesBusiness`|Numeric|20|M|Credit sales business of the Merchant.|
|`firsReport`|Alphanumeric|20|O|First report of the Merchant.|
|`recurringTranFlag`|Alphanumeric|20|O|Recurring tran flag of the Merchant.|
|`refundPolicy`|Alphanumeric|20|O|Refund policy of the Merchant.|
|`cardRefundDays`|Alphanumeric|20|O|Card refund days of the Merchant.|
|`thirdPartyProcessorFlag`|Alphanumeric|20|O|Thirdparty processor flag of the Merchant.|
|`thirdPartyProcessorName`|Alphanumeric|40|O|Thirdparty processor name of the Merchant.|
|`smallMerchant`|Alphanumeric|20|O|Applicable if the merchant is a Small Merchant.|

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

The table below provides the list of application's error code and its description.

| Error Code |  Description / Values |
| --------  | ------------------ |
|`100`| Invalid Request |
|`103`| Data not found, please contact Application Support Team. |
|`200`| Success |
|`302`| IO Exception |
|`404`| Not Found |
|`401`| Unauthorized |
|`500`| Internal Error, please contact Application Support Team. |
|`505`| Internal Error, Please contact Application Support Team. |
|`708`| App URN already submitted. |
|`902`| App URN is mandatory. |
|`903`| Application already Submitted. |
|`904`| JSON Processing Error |
|`905`| JSON Parse Error |
|`906`| JSON Mapping Error |
|`907`| Comments are empty. |
|`908`| App URN is not matching. |
|`909`| Given Merchant Hierarchy Cannot handle via TAB. Please contact Application Support Team. |
|`910`| Given Merchant Id Doesnt qualify for Add Outlet. Please contact Application Support Team. |
|`911`| Given Merchant Super MID is InActive. Please contact Application Support Team. |
|`912`| One of MID in hierarchy is InActive. Please contact Application Support Team.|
|`913`| Please use member level Mid. Please contact Application Support Team. |
|`914`| Ref MID should be 8 digits. |
|`915`| Business Rule Exception |
|`916`| All Adress Types are not available for Ref MID. Please contact Application Suport Team. |
|`917`| No Services avaiable for Ref MID. Please contact Application Support Team. |
