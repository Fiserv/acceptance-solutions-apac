# Additional Device

This API is used to submit the application details for additional device for an existing merchant.

## How it works
1. Merchant needs to use this common API for Additional Device for ISOs, ISVs & Payment Facilitators.
2. Merchant has to trigger this API post Create URN API. Below APIs can be optionally used to contribute to the data to be 
   submitted as part  of New Partner Application Submit API.
    - Get Packages
    - Get Document Matrix
    - Upload Document

## Endpoint

POST `https://www.uat.fdmerchantservices.com/Externalboarding/secure/addtid`

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

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/addtid).

### Request
 | Field Name |	Type |	Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- | ------------------ | ------------------ |
|`App URN`|	Alphanumeric|	30|	M|	App URN retured as part of Create URN API|
|`App Type`|	Alphanumeric|	8|	M|	Fixed Value 'API'|
|`Sales Id`|	Alphanumeric|	70|	O|	User Credential created for each partner|
|`channel Code`|	Alphanumeric|	10|	O|	Static Channel Code shared with each partner|
|`Institution Id`|	Numeric	|10|	O|	Institution number assigned to the institution|
|`Boarding Type`|	Alphanumeric|	20|	NA |	Type of Merchant: NEWMID/ADDMID/ADDTID|
|`IS_ADD_LOCATION`|	Alphanumeric|	20|	NA |	Applicable if the merchant wants additional location|
|`IS_ADD_MID`|	Alphanumeric|	20|	NA	|Applicable if the merchant wants additional MID|
|`App Channel`|	Alphanumeric|	20	|NA|Application channel|
|`Osv Flag Value`|	Alphanumeric|	1|	NA |	Original Sent & Verified flag. Applicable for entities where documents are uploaded. For entities not uploading documents, keep this field as blank.|
| **MerchantDetails** | - | - |  - | This is the object |
|`Business Name`|	Alphanumeric	|22|	M	|Trade Name of the Merchant|
|`Legal Name`|	Alphanumeric |	35	 |M	|Legal Name of the Merchant|
|`Business Type`|	Alphanumeric|	50	|M|	Type of Business of the Merchant|
|`Registration No`|	Alphanumeric|	100	|O	|Registration number of the Merchant
 **Tax Details** | - | - |  - | This is the object |
 |`Taxid Type`|	Alphanumeric	|50	|M|	"Tax ID Type provided for the merchant.|
|`Taxid Type`|	Alphanumeric|	50|	M|	For India - PAN|
|`Taxid Type`|	Alphanumeric|	50	|M|	For AU - ABN **Tax ID Type provided for the merchant For India: Individual PAN for Individual/Soleprop merchants**|
|`Taxid Value`|	Alphanumeric|	100	|M|	PAN, ABN number of the Merchant
|`Taxid Value`|	Alphanumeric|	100|	M|	PAN, ABN number of the Merchant|
|`Taxid Value`|	Alphanumeric|	100|	M|	PAN, ABN number of the Merchant|
|`Taxid Value`|	Alphanumeric|	100|	M|	PAN, ABN number of the Merchant|
|`Taxid Value`|	Alphanumeric|	100|	M|	PAN, ABN number of the Merchant|
|`Taxid Value`|	Alphanumeric|	100|	M|	PAN, ABN number of the Merchant|
|`Date Incorporated`|	Numeric	|8	|O|	YYYYMMDD|
|`Website URL`|	Alphanumeric|	100	|C|	Eligible for ECOM Merchant|
|`Communication Email`|	Alphanumeric|	60|	O|	Communication Email of the Merchant|
|`Merchant Type`|	Alphanumeric|	20|	O|	Whether it is small merchant or Large merchant|
|`Acceptance Type`|	Alphanumeric|	10|	M|	"Static Value - 'POSMOB' for POS merchant Static Value: ''ECOM'' for ECOM merchant"|
|`ICICI Merchant`|	Alphanumeric|	20|	NA|	Applicable if the merchant has ICICI account|
|`New Funding Ac`|	Alphanumeric|	20|	NA|	Applicable if the merchant wants the new settlement account|
| **Legal Address** | - | - |  - | This is the object |
 |`Address Line`|	Alphanumeric|	35|	M|	Address of the Merchant|
|`Address Line2`|	Alphanumeric|	35|	M	|Address of the Merchant|
|`Address Line3`|	Alphanumeric|	35	|M	|Address of the Merchant|
|`City`|	Alphanumeric|	25|	M|	City of the Merchant|
|`State`|	Alphanumeric|	25|	M|	State of the Merchant|
|`Pin code`|	Alphanumeric|	8	|M	|Pincode of the Merchant|
|`Country`|	Alphanumeric|	25|	M	|Country of the Merchant|
|`Mobile No`|	Numeric|	15|	O|	Mobile number of the Merchant|
|`Phone1`|	Numeric	|15|	O	|Phone number of the Merchant|
|`Email`	| AlphaNumeric|	30	|O|	Email of the Merchant|
|`Contact Name`|	Alphanumeric|	35|	O|	Contact Name of the Merchant|
|`Gst No`|	Alphanumeric|	100	|NA	|Mandatory for Large merchants|
|`Gst Merchant State Code`| 	Alphanumeric|	40	|NA|	Mandatory for Large Partners|
|`Isdn Flag`|	Alphanumeric	|20|	NA|	Isdn Flag|
|**Id Doc Details**|- | - |  - |		ID Doc Details section is a conditional tag and has to be mandatorily present if the user is uploding documents for a particular application. All documents uploaded under **categoryInd: E** has to be included under merchantDetails.idDocDetails|
|`Entity`|	Alphanumeric|	20|	NA|	Static Value - 'Member'|
|`Id Type`|	Alphanumeric|	20|	NA |	Value of docType received as response of uploaded document|
|`Id Value`|	Alphanumeric|	20|	NA|	
|`Doc Id`|	Alphanumeric|	20|	NA|	Value of docID received as response of uploaded document|
|`Category Name`|	Alphanumeric|	20	|NA|	Value of categoryName received as response of uploaded document|
|`Level`|	Numeric|	20|	NA |	Value of level received as response of uploaded document|
|`Entity`|	Alphanumeric|	20|	NA |	Static Value - 'Member'|
|`Id Type`|	Alphanumeric|	20|	NA |	Value of docType received as response of uploaded document|
|`Id Value`|	Alphanumeric|	20|	NA	 |Id Value|
|`Doc Id`|	Alphanumeric|	20|	NA|	Value of docID received as response of uploaded document|
|`Category Name`|	Alphanumeric|	20|	NA |	Value of categoryName received as response of uploaded document|
|`Level`|	Numeric|	20|	NA|	Value of level received as response of uploaded document|
| **Geo Location** | - | - |  - | This is the object |
|`Latitude`|	Numeric|	20|	O|	Lattitude of the Merchant
|`Longitude`|	Numeric|	20|	O	|Longitude of the Merchant
| **Trading Locations** |	- | - |  - |	"This section contains the trading location details of merchants that is being onboarded. A maximum upto 3 trading locations can be added under a single Application.|
|`Location No`|	Numeric|2|	M	|Trading location number of the Merchant|
|`Trading Name`|	Alphanumeric|	22|	M	|Trade Name of the Merchant|
|Trading Locations|		- | - |  - |	"This section contains the trading location details of merchants that is being onboarded. A maximum upto 3 trading locations can be added under a single Application.|
|`Location No`|	Numeric|2|	M	|Trading location number of the Merchant|
|`Trading Name`|	Alphanumeric|	22|	M	|Trade Name of the Merchant|
| **Trading Address** | - | - |  - | This is the object |
|`Address Line`|	Alphanumeric|	35|	M|	Address of the Merchant|
|`Address Line2`|	Alphanumeric|	35|	M|	Address of the Merchant|
|`Address Line3`|	Alphanumeric|	35|	M|	Address of the Merchant|
|`City`|	Alphanumeric|	25|	M|	City of the Merchant|
|`State`|	Alphanumeric|	25|	M	|State of the Merchant|
|`Pincode`|	Alphanumeric|	8	|M	|Pincode of the Merchant|
|`Country`|	Alphanumeric|	25|	M|	Country of the Merchant|
|`Mobile NO`|oNumeric	|15|	O	|Mobile number of the Merchant|
|`Phone1`|	Numeric	|15|	O|	phone1 of the Merchant|
|`Email`|	Numeric	|30|	O	|Email of the Merchant|
|`ContactName`|	Alphanumeric|	35|	O|	Contact name of the Merchant|
|`Package Id`|	Numeric|	10	|M|	Package number assigned to the Merchant|
|`AutoSettlement`| Time	Numeric	|6|NA|	HHMMSS|
|`Cpv GroupId`|	Alphanumeric	|50|NA	|Cpv groupid of the Merchant|
|`Regional cpv Groupid`|	Alphanumeric|	50	|NA|	Regional cpv groupid of the Merchant|
|`Commerce Connect Reference MID`|	Alphanumeric	|8|	NA|	Commerce connect reference mid of the Merchant|
| **Terminals** | - | - |  - | This is the object |
|`Count`|	Numeric	|2	|O|	Count of terminals for the Merchant|
|`prefered Date`|	Numeric|	8|	O|	YYYYMMDD|
|`prefered Time`|	Numeric	|6|	O	|HHMMSS|
|`Discount`|	Numeric	|3	|NA|	Discount of the Merchant|
|`User Instruction1`|	Alphanumeric|	100|	NA|	User Instruction1 of the Merchant|
|`User Instruction2`|	Alphanumeric|	100|	NA|	User Instruction2 of the Merchant|
| **Surcharge Amount** | - | - |  - | This object not applicable for ISO. Surcharge values currently selected by Partner on MVSI in AU |
|`Visa Base`|	Numeric|	11|	NA	|For AU Only|
|`Visa Percent`|	Numeric|	11|	NA	|For AU Only|
|`Mc  Base`|	Numeric	|11|	NA	|For AU Only|
|`Mc  Percent`|	Numeric|	11|	NA	|For AU Only|
|`Upi Base`|	Numeric	|11|	NA|	|For AU Only|
|`Upi Percent`|	Numeric|	11	|NA	|For AU Only|
|`Eftpos Base`|	Numeric|	11|	NA	|For AU Only|
|`Eftpos Percent`|	Numeric|	11	|NA	|For AU Only|
|`Amex Base`|	Numeric	|11	| NA	|For AU Only|
|`Amex Percent`|	Numeric|	11 |	NA	|For AU Only|
|`Jcb Base`|	Numeric	|11|	NA	|For AU Only|
|`Jcb Percent`|	Numeric|	11	|NA	|For AU Only|
|`Diners Base`|	Numeric	|11	|NA	|For AU Only|
|`Diners Percent`|	Numeric|	11|NA	|For AU Only|
|`Alt merchCode`|	Alphanumeric	|20	|NA	|This is an optional field which has to be populated only if there is merchant MID or Dealer Code has to be captured at MID Level|
|`Same Location`|	Alphanumeric	|1	|NA	|This flag has to be set to 'Y' if Partner wants multiple MIDs at the same location|
|`MID`|	Numeric|	15|	NA	|This is the reference Member MID which needs to be given in case of ADD MID/ ADD TID.|
|`Parent mid`|	Numeric	|15	|NA	|This is the SG (parent MID) of the reference MID which needs to be given in case of ADD MID & ADD TID|
|`Otp Enabled`|	Alphanumeric	|10|	NA|	Otp enabled for the merchant|
 **Principal Details** | - | - |  - | This section is used to capture details of Principal Owner for the said merchant. The same section can be repeated for multiple Principal Owners. We can have upto maximum of 2 Principal Owners per merchant |
 |`Principal No`|	Alphanumeric|	2|	M|	Principal number of the Merchant|
|`Position`|	Alphanumeric|	20	|O|	Position of the Merchant|
|`Title`|	Alphanumeric|	20	|O|	Title of the Merchant|
|`First Name`|	Alphanumeric	|25	|M|	First Name mf the Merchant|
|`Last Name	`|Alphanumeric|	25|	M|	Last Name of the Merchant|
|`Middle Name`|	Alphanumeric|	25|	O|	Middle Name of the Oerchant|
|`Gender`|	Alphanumeric|	10	|O	|Gender of the Merchant|
|`date Of Birth`|	Numeric|	8|	M|	YYYYMMDD|
| **KYC Details** | - | - |  - | This is the object |
|*KYC Details* | - | - |  - | POI/POA of the Merchant |
|`Identity Type`|	Alphanumeric|	50	|O	|Type of KYC Document submitted|
|`Identity Type`|	Alphanumeric|	50	|O|	For India - PAN/AADHAR|
|`Identity Type`|	Alphanumeric|	50	|O|	For ASEAN - Passport/Driving Licence/HKID or SGID or MYID|
|`Identity Type`|	Alphanumeric|	50	|O|	For AU - Passport/Driving Licence|
|`Identity Value`|	Alphanumeric|	100	|O|	Value of the Kyc Document submitted|
|`Identity metaName1`|	Alphanumeric|	100|	O	|Additional information pertaning to the KYC docuements submitted. For AU - Driving License State Code|
|`Identity metaValue1`|	Alphanumeric |	100	|O|	Additional information pertaning to the KYC docuements submitted. For AU - Value Driving License State Code|
|`Nationality`|	Alphanumeric	|35|	O|	Nationality of the Merchant|
|`Identity metaName1`|	Alphanumeric|	100|	NA|	Additional information pertaning to the KYC docuements submitted for UBO|
|`Identity metaName1`|	Alphanumeric|	100	|NA|	For AU - Driving License State Code|
|`Identity metaValue1`|	Alphanumeric|	100|	NA|	Additional information pertaning to the KYC docuements submitted|
|`Identity metaValue1`|	Alphanumeric|	100|	NA|	For AU - Value Driving License State Code|
| **Principal Address** | - | - |  - | This is the object |
|`Address Line`|	Alphanumeric|	35|M|	Address  line of the Merchant|
|`Address Line2`|	Alphanumeric|	35|	M|	Address Line2 of the Merchant|
|`Address Line3`|	Alphanumeric|	35|	M|	Address Line3 of the Merchant|
|`City`|	Alphanumeric|	25|	M	|City of the Merchant|
|`State`|	Alphanumeric|	25|	M|	State of the Merchant|
|`Pincode`|	Alphanumeric|	8|	M|	Pincode of the Merchant|
|`Country`|	Alphanumeric|	25|	M|	Country of the Merchant|
|`MobileNo`|	Numeric|	15|	O|	Mobile number of the Merchant|
|`Phone 1`|	Numeric|	15|	M|	phone 1 of the Merchant|
|`Contact Name`|	Alphanumeric|	35|	O|	Contact name of the Merchant|
| `Id DocDetailss` | - | - |  NA | ID Doc Details section is a conditional tag and has to be mandatorily present if the user is uploding documents for a particular application |
| `Id DocDetails` | - | - |  NA | All documents uploaded under ""categoryInd"": ""P"" has to be included under principalDetails.idDocDetails |
|`Level`|	Alphanumeric|	2|	NA	|Value of level received as response of uploaded document|
|`Mandatory`|	Alphanumeric|	10|	NA	|Mandatory of the Merchant|
|`Entity`|	Alphanumeric|	20|	NA|	Static Value - 'Member'|
|`Id Type`|	Alphanumeric|	20|	NA|	Value of docType received as response of uploaded document|
|`Id Value`|	Alphanumeric|	20|	NA|	Id value|
|`Doc Id`|	-|-|-|NA	|Value of docID received as response of uploaded document|
|`CategoryName` |	Alphanumeric|	30	|NA	|Value of categoryName received as response of uploaded document|
| **Ubo Details** | - | - |  - | This section is used to capture details of Ultimate Benefeciary Owner for the said merchant. The same section can be repeated for multiple UBOs. We can have upto maximum of 5 UBOs per merchant |
|`Serial No`|	Numeric|	2|	C|	Serial number of the Ultimate Benefeciary Owner|
|`Title`|	Alphanumeric|	20|	C	|Title of the Ultimate Benefeciary Owner|
|`First Name`|	Alphanumeric|	25	|C	|First name of the Ultimate Benefeciary Owner|
|`Last Name`|	Alphanumeric|	25|	C	|Last name of the Ultimate Benefeciary Owner|
|`Middle Name`|	Alphanumeric|	25|	C	|Middle name of the Ultimate Benefeciary Owner|
|`Date Of Birth`|	Numeric	|10|	C|	Format - YYYYMMDD|
|`Shareholder Percentage`|	Numeric	|8|	C|	Shareholder percentage the Ultimate Benefeciary Owner|
|`Nationality`|	Alphanumeric|	35|	C|	Nationality of the Ultimate Benefeciary Owner|
| **Ubo Address** | - | - |  - | This is the object |
|`Address Line`|	Alphanumeric|	35	|C|	Address  of the Ultimate Benefeciary Owner|
|`Address Line2`|	Alphanumeric|	35	|C|	Address Line2 Ultimate Benefeciary Owner|
|`Address Line3`|	Alphanumeric|	35|	C	|Address Line3 Ultimate Benefeciary Owner
|`City`|	Alphanumeric|	25|	C	|City of the Ultimate Benefeciary Owner|
|`State`|	Alphanumeric|	25	|C	|State of the Ultimate Benefeciary Owner|
|`Pincode`|	Alphanumeric|	8|	C|	Pincode of the Ultimate Benefeciary Owner|
|`Country`|	Alphanumeric|	25|	C|	Country of the Ultimate Benefeciary Owner|
|`Mobile No`|	Numeric|	15|	C|	Mobile number of Ultimate Benefeciary Owner|
|`Phone 1`|	Numeric	|15|	C|	phone 1 of the Ultimate Benefeciary Owner|
|`Contact Name`|	Alphanumeric|	35|	C|	Contact Name of Ultimate Benefeciary Owner|
| **Bank Details** | - | - |  - | This tag will contain the Bank account details of Partner/PayFac which needs to be configured at Fiserv End |
| **UW account details** | - | - |  - | UW Account details are primarily the actual merchant account which will be used while underwriting the merchant |
|`Account No`|	Numeric|	100|NA	|Account number of the Merchant|
|`Account Name`|	Alphanumeric|	35|	NA|	Account name of the Merchant|
|`Ifsc`|	Alphanumeric|	15|	NA|	Ifsc of the Merchant|
|`Bank Name`|	Alphanumeric|	80|	NA	|Bank name of the Merchant|
|`Currency`|	Alphanumeric|	3|	NA	|Currency of the Merchant|
|`Branch`|	Alphanumeric|	500|	NA|	Branch of the Merchant|
|`Bank Address`|	Alphanumeric|	500|	NA|	Bank address of the Merchant|
|`Acc Type`|	Alphanumeric|	30	|NA	|Acc Type of the Merchant|
| **Funding accountdetails** | - | - |  - | Funding account will the details of account to which Fiserv will process the funding on daily basis |
|`Account No`|	Numeric|	100	|NA	|If different form UW details|
|`Account Name`|	Alphanumeric|	35|	NA|	Account number of the Merchant|
|`Ifsc`|	Alphanumeric|	15|	NA|	Ifsc of the Merchant|
|`Bank Name`|	Alphanumeric	|80	|NA|	Bank Name of the Cerchant|
|`Currency`|	Alphanumeric|	3|	NA	|Currency of the Merchant|
|`Branch`|	Alphanumeric|	500	|NA	|Branch of the Merchant|
|`Bank Address`|	Alphanumeric|	500|	NA|	Bank address of the Merchant|
|`Acc Type`|	Alphanumeric|	30|	NA	|Account Type of the Merchant|
| **Collection accountdetails** | - | - |  - | This section will have details of account which needs to be used for collection of charges. This account may or may not be the same as UW account/Funding account |
|`Account No`|	Numeric|	100|	NA|	If different form UW details|
|`Account Name`|	Alphanumeric|	35|	NA|	Account name of the Merchant|
|`Ifsc`|	Alphanumeric|	15|	NA|	Ifsc of the Merchant|
|`Bank Name`|	Alphanumeric|	80|	NA|	Bank Name of the Cerchant|
|`Currency`|	Alphanumeric|	3|	NA	|Currency of the Merchant|
|`Branch`|	Alphanumeric|	500|	NA|	Branch of the Merchant|
|`Bank Address`|	Alphanumeric	|500|	NA|	Bank address of the Merchant|
|`Acc Type`|	Alphanumeric|	30|	NA|	Acc type of the Merchant|
 **Sub merchantDetails** | - | - |  - | This object is not applicable for ISO. This section is used to capture the sub Partner Details of the merchant |
|`Sub merchantID`|	Numeric	|15	|NA|	"This is an optional field which the Single MID PayFacs can use to pass their own MID to Fiserv.|
|`Sub merchantID`|	Numeric	|15	|NA	|This field will be mandatory if the Channel level parameter for Payfac Provided SMID is set to Y.|
|`Sub merchantID`|	Numeric	|15	|NA|	If the same is set to 'N', Boarding backend will generate its own MID for the merchant"|
| **Business Summary** | - | - |  - | This section is used to capture the summary of the merchant |
|`Brief Summary`|	Alphanumeric|	100|	O|	Brief summary of the Merchant|
|`Salessr Number`|	Alphanumeric|	100|	O|	Sales number of the Merchant|
|`MCC Code`|	Numeric	|20	|M	|MCC  number of the Merchant|
|`MCC Description`|	Alphanumeric|	200|	O|	MCC  description of the Merchant|
|`Total Turnover`|	Numeric|	20	|O|	Total  turnover number of the Merchant|
|`Total Turnover Per MID`|	Numeric	|20	|O	|Total turnover per mid of the Merchant|
|`Card Turnover`|	Numeric|	20	|O	|Card turnover of the Merchant|
|`Avg Ticket Amt`| 	Numeric|	20|	O|	Avg ticket amt of the Merchant|
|`Dcc Turnover Per MID`| 	Numeric |	20|	O|	Dcc turnover per mid of the Merchant
|`Pg Turnover`|	Numeric	|20|	O|	Pg  turnover of the Merchant|
|`Pg Turnover Per MID`| 	Numeric	|20|	O	|Pg turnover per mid of the Merchant|
|`Avg EMI Ticket Amt`| Numeric|	20|	O	|Avg emi ticket amt of the Merchant|
|`Tran VolumeInternet`|	Numeric	|20|	M	|Tran volume internet of the Merchant|
|`Tran VolumeMoto`|	Numeric	|20	|M|	Tran volume moto of the Merchant|
|`Tran VolumeinStore`|	Numeric|	20|	M|	Tran volume in store of the Merchant|
|`Delivery Days0`|	Numeric|	20|	M|	Delivery Days0 of the Merchant|
|`Delivery Days7`|	Numeric|	20|	M|	Delivery Days7 of the Merchant|
|`Delivery Days14`|	Numeric|	20|	M|	Delivery Days14 of the Merchant|
|`Delivery Days30`|	Numeric|	20|	M|	Delivery Days30 of the Merchant|
|`Delivery Days Over30`|	Numeric|	20	|M|	Delivery Days Over30 of the Merchant|
|`Tran TypeMagStrip`|	Numeric|	20|	O|	Tran type magstripe of the Merchant|
|`Tran Type Chip`|	Numeric|	20|	O	|Tran type chip of the Merchant|
|`Tran Type Keyed`|	Numeric|	20|O	|Tran type keyed of the Merchant|
|`Credit SalesConsumer`|	Numeric	|20|	M|	Credit salesconsumer of the Merchant|
|`Credit SalesBusiness`|	Numeric|	20|	M	|Credit salesbusiness of the Merchant|
|`First Report`|	Alphanumeric|	20|	NA	|First report of the Merchant|
|`Recurring Tran Flag`|	Alphanumeric|	20|	NA|	Recurring tran flag of the Merchant|
|`Refund Policy`|	Alphanumeric|	20|	NA|	Refund policy of the Merchant|
|`Card Refund Days`|	Alphanumeric|	20|	NA|	Card refund days of the Merchant|
|`ThirdParty Processor`| Flag	|Alphanumeric|	20|	NA|	Thirdparty processor flag of the Merchant|
|`ThirdParty Processor`| Name	|Alphanumeric	|40	|NA	|Thirdparty processor name of the Merchant|
|`Small Merchant`|	Alphanumeric|	20|	NA|	Applicable if the merchant is a Small Merchant|

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