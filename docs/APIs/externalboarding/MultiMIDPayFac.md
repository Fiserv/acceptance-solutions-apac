# Multiple MID Payfac

This API is used to submit the boarding application for new multi MID Payfac merchants.

## How it works
1. Merchant needs to use this API to actually submit the boarding application for the new multi MID Payfac merchants.
2. Merchant has to trigger this API post Create URN API. Below APIs can be optionally used to contribute to the data to be submitted 
   as part of New Partner Application Submit API.
    - Get Packages
    - Get Document Matrix
    - Upload Document

## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/newmid`

## Payload Example

### Request Payload

```json

{
"appURN": "1000007802",
"appType": "API",
"salesId": "BharatPEPFAC",
"channelCode": "Bharat_PE",
"institutionId":"47",
"osvFlagValue": "",
"merchantDetails": {
"businessName": "Test",
"legalName": "Test Merchant",
"businessType": "Sole Proprietor",
"registrationNo": "5678325544",
"dateIncorporated": "17-01-2022",
"websiteURL": "",
"communicationEmail": "test@gmail.com",
"merchantType": "Small",
"acceptanceType": "POSMOB",
"iciciMerchant": "No",
"newFundingAc": "No",
"legalAddress": {
"addressLine": "Hyderabad",
"addressLine2": "",
"addressLine3": "",
"city": "YELLAREDDY",
"state": "AP",
"pincode": "503122",
"country": "IN",
"mobileNo": "9440958263",
"phone1": "0",
"contactName": "Test Merchant"
},
"taxDetails": {
"taxidType": "PAN",
"taxidValue": "DGLPS4788D"
},
"gstNo": "114333211",
"gstMerchantStateCode": "AP",
"isdnFlag": "No"
},
"tradingLocations":[ {



"tradingName": "Test",
"locationNo": "56",
"tradingAddress": {
"addressLine": "Hyderabad",
"addressLine2": "",
"addressLine3": "",
"city": "Hyderabad",
"state": "AP",
"pincode": "500081",
"country": "IN",
"mobileNo": "9440958263",
"phone1": "0",
"contactName": "test name"
},
"packageId": "14872",
"autoSettlementTime": "",
"cpvGroupId": "",
"regionalcpvGroupid": "",
"commerceConnectReferenceMID": "",
"altmerchCode": "",
"sameLocation": "true",
"mid": "",
"parentmid": "",
"otpEnabled": "",
"terminals": [
{
"count": "1",
"preferedDate": "20220117",
"preferedTime": "1701175",
"discount": "",
"userInstruction1": "",
"userInstruction2": ""
}
]
}],
"principalDetails":[ {
"principalNo": "1",
"position": "Manager",
"title": "Mr",
"firstName": "Test principal",
"lastName": "s",
"middleName": "",
"gender": "Male",
"dateOfBirth": "04-04-1998",
"nationality": "",
"principalAddress": {
"addressLine": "Hyderabad",
"addressLine2": "",
"addressLine3": "",
"city": "Hyderabad",
"state": "TS",
"pincode": "500081",
"country": "IN",
"mobileNo": "9440958263",
"phone1": "0",
"contactName": "Test Principal"
},
"kycDetails": [{
"kycCategory": "POI",
"identityType": "PAN",
"identityValue": "DGLPS4788D",
"identitymetaName1": "",
"identitymetaValue1": ""
}]
}],
"businessSummary": {
"briefSummary": "summary",
"salessrNumber": "",
"mccCode": "5912",
"mccDescription": "electronics",
"totalTurnover": "100000",
"totalTurnoverPerMID": "10000",
"cardTurnover": "1000",
"avgTicketAmt": "1000",
"dccTurnoverPerMID": "1000",
"pgTurnover": "100000",
"pgTurnoverPerMID": "10000",
"avgEMITicketAmt": "",
"tranVolumeInternet": "1000",
"tranVolumeMoto": "1000",
"tranVolumeInStore": "1000",
"deliveryDays0": "1000",
"deliveryDays7": "1000",
"deliveryDays14": "1000",
"deliveryDays30": "1000",
"deliveryDaysOver30": "1000",
"tranTypeMagStrip": "0",
"tranTypeChip": "100",
"tranTypeKeyed": "0",
"creditSalesConsumer": "1000",
"creditSalesBusiness": "1000",
"firsReport": "",
"recurringTranFlag": "",
"refundPolicy": "",
"cardRefundDays": "",
"thirdPartyProcessorFlag": "",
"thirdPartyProcessorName": "",
"smallMerchant":"Y"
}
}

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/Externalboarding/secure/newmid``).

### Request
| Field Name |	Type |	Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- | ------------------ | ------------------ |
|`appURN`|Alphanumeric|30|M|App URN retured as part of Create URN API. |
|`appType`|Alphanumeric|8|M|Fixed Value API.|
|`salesId`|Alphanumeric|70|O|User Credential created for each partner.|
|`channelCode`|Alphanumeric|10|O|Static Channel Code shared with each partner.|
|`institutionId`|Numeric|10|O|Institution number assigned to the institution.|
|`boardingType`|Alphanumeric|20|NA|Type of Merchant: New MID / Add MID / Add TID|
|`IS_ADD_LOCATION`|Alphanumeric|20|NA|Applicable if the merchant wants additional location.|
|`IS_ADD_MID`|Alphanumeric|20|NA|Applicable if the merchant wants additional MID.|
|`appChannel`|Alphanumeric|20|NA|Application channel|
|`osvFlagValue`|Alphanumeric|1|NA|Original Sent & Verified flag. Applicable for entities where documents are uploaded. For entities not uploading documents, keep this field as blank.|
|`merchantDetails`|||||
|`businessName`|Alphanumeric|22|M|Trade Name of the Merchant.|
|`legalName`|Alphanumeric|35|M|Legal Name of the Merchant.|
|`businessType`|Alphanumeric|50|M|Type of Business of the Merchant.|
|`registrationNo`|Alphanumeric|100|O|Registration number of the Merchant.|
|`taxDetails`|||||
|`taxidType`|Alphanumeric|50|M|Tax ID Type provided for the merchant.|
|`taxidType`|Alphanumeric|50|M|For India - PAN|
|`taxidType`|Alphanumeric|50|M|For AU - ABN.Tax ID Type provided for the merchant For India - Individual PAN for Individual/Soleprop merchants.
|
|`taxidValue`|Alphanumeric|100|M|PAN, ABN number of the Merchant.|
|`dateIncorporated`|Alphanumeric|100|M|YYYYMMDD|
|`websiteURL`|Alphanumeric|100|M|Eligible for ECOM Merchant.|
|`communicationEmail`|Alphanumeric|100|M|Communication Email of the Merchant.|
|`merchantType`|Alphanumeric|100|M|Whether it is small merchant or Large merchant.|
|`acceptanceType`|Alphanumeric|100|M|Static Value - ''POSMOB'' for POS merchant
| | | | |Static Value - ''ECOM'' for ECOM merchant|
|`iciciMerchant`|Numeric|8|M|Applicable if the merchant has ICICI account.|
|`newFundingAc`|Alphanumeric|100|NA|Applicable if the merchant wants the new settlement account.|
|**legalAddress**||| | |
|`addressLine`|Alphanumeric|35|M|Address of the Merchant.|
|`addressLine2`|Alphanumeric|35|M|Address of the Merchant.|
|`addressLine3`|Alphanumeric|35|M|Address of the Merchant.|
|`city`|Alphanumeric|25|M|City of the Merchant.|
|`state`|Alphanumeric|25|M|State of the Merchant.|
|`pincode`|Alphanumeric|8|M|Pincode of the Merchant.|
|`country`|Alphanumeric|25|M|Country of the Merchant.|
|`mobileNo`|Numeric|15|O|Mobile number of the Merchant.|
|`phone1`|Numeric|15|O|Phone number of the Merchant.|
|`email`|Numeric|30|O|Email of the Merchant.|
|`contactName`|Alphanumeric|35|O|Contact Name of the Merchant.|
|`gstNo`|Alphanumeric|100|NA|Mandatory for Large merchants.|
|`gstMerchantStateCode`|Alphanumeric|40|NA|Mandatory for Large Partners.|
|`isdnFlag`|Alphanumeric|20|NA|Isdn Flag|
|`idDocDetails`|-|||ID Doc Details section is a conditional tag and should be mandatory for a user uploding documents in an application. All documents uploaded under "categoryInd": "E" has to be included under merchantDetails - idDocDetails.|
|`entity`|Alphanumeric|20|NA|Static Value - 'Member'|
|`idType`|Alphanumeric|20|NA|Value of docType received as response of Uploaded document.|
|`idValue`|Alphanumeric|20|NA|Id value|
|`docId`|Alphanumeric|20|NA|Value of docID received as response of Uploaded document.|
|`categoryName`|Alphanumeric|20|NA|Value of categoryName received as response of Uploaded document.|
|`level`|Numeric|20|NA|Value of level received as response of Uploaded document.|
|`entity`|Alphanumeric|20|NA|Static Value - 'Member'|
|`idType`|Alphanumeric|20|NA|Value of docType received as response of Uploaded document.|
|`idValue`|Alphanumeric|20|NA|Id Value|
|`docId`|Alphanumeric|20|NA|Value of docID received as response of Uploaded document.|
|`categoryName`|Alphanumeric|20|NA|Value of categoryName received as response of Uploaded document.|
|`level`|Numeric|20|NA|Value of level received as response of Uploaded document.|
|**geoLocation**|||||
|`latitude`|Numeric|20|O|Latitude of the Merchant.|
|`longitude`|Numeric|20|O|Longitude of the Merchant.|
|**tradingLocations**|-|||This section contains the trading location details of merchants that is being onboarded. A maximum upto 3 trading locations can be added under a single Application.|
|`locationNo`|Numeric|2|M|Trading location number of the Merchant.|
|`tradingName`|Alphanumeric|22|M|Trade Name of the Merchant.|
|**tradingAddress**|||||
|`addressLine`|Alphanumeric|35|M|Address of the Merchant.|
|`addressLine2`|Alphanumeric|35|M|Address of the Merchant.|
|`addressLine3`|Alphanumeric|35|M|Address of the Merchant.|
|`city`|Alphanumeric|25|M|City of the Merchant.|
|`state`|Alphanumeric|25|M|State of the Merchant.|
|`pincode`|Alphanumeric|8|M|Pincode of the Merchant.|
|`country`|Alphanumeric|25|M|Country of the Merchant.|
|`mobileNo`|Numeric|15|O|Mobile number of the Merchant.|
|`phone1`|Numeric|15|O|phone1 of the Merchant.|
|`email`|Numeric|30|O|Email of the Merchant.|
|`contactName`|Alphanumeric|35|O|Contact name of the Merchant.|
|`packageId`|Numeric|10|M|Package number assigned to the Merchant|
|`autoSettlementTime`|Numeric|6|NA|HHMMSS|
|`cpvGroupId`|Alphanumeric|50|NA|Cpv groupid of the Merchant.|
|`regionalcpvGroupid`|Alphanumeric|50|NA|Regional cpv groupid of the Merchant.|
|`commerceConnectReferenceMID`|Alphanumeric|8|NA|Commerce connect reference mid of the Merchant..|
|**terminals**|||||
|`count`|Numeric|2|O|Count of terminals for the Merchant.|
|`preferedDate`|Numeric|8|O|YYYYMMDD|
|`preferedTime`|Numeric|6|O|HHMMSS|
|`discount`|Numeric|3|NA|Discount of the Merchant.|
|`userInstruction1`|Alphanumeric|100|NA|User Instruction 1 of the Merchant.|
|`userInstruction2`|Alphanumeric|100|NA|User Instruction 2 of the Merchant.|
|**surchargeAmount**|-|||This object is not applicable for ISO. Surcharge values currently selected by Partner on MVSI in AU.|
|`visaBase`|Numeric|11|NA|For AU Only.|
|`visaPercent`|Numeric|11|NA|For AU Only.|
|`mcBase`|Numeric|11|NA|For AU Only.|
|`mcPercent`|Numeric|11|NA|For AU Only.|
|`upiBase`|Numeric|11|NA|For AU Only.|
|`upiPercent`|Numeric|11|NA|For AU Only.|
|`eftposBase`|Numeric|11|NA|For AU Only.|
|`eftposPercent`|Numeric|11|NA|For AU Only.|
|`amexBase`|Numeric|11|NA|For AU Only.|
|`amexPercent`|Numeric|11|NA|For AU Only.|
|`jcbBase`|Numeric|11|NA|For AU Only.|
|`jcbPercent`|Numeric|11|NA|For AU Only.|
|`dinersBase`|Numeric|11|NA|For AU Only.|
|`dinersPercent`|Numeric|11|NA|For AU Only.|
|`altmerchCode`|Alphanumeric|20|NA|This is an optional field which has to be populated only if there is merchant MID or Dealer Code has to be captured at MID Level.|
|`sameLocation`|Alphanumeric|1|NA|This flag has to be set to 'Y' if Partner wants multiple MIDs at the same location.|
|`mID`|Numeric|15|NA|This is the reference Member MID which needs to be given in case of ADD MID/ ADD TID.|
|`parentmid`|Numeric|15|NA|This is the SG (parent MID) of the reference MID which needs to be given in case of ADD MID & ADD TID.|
|`otpEnabled`|Alphanumeric|10|NA|Otp enabled for the merchant.|
|**principalDetails**|-|||This section is used to capture details of Principal Owner for the said merchant. The same section can be repeated for multiple Principal Owners. We can have upto maximum of 2 Principal Owners per merchant.|
|`principalNo`|Alphanumeric|2|M|Principal number of the Merchant.|
|`position`|Alphanumeric|20|O|Position of the Merchant.|
|`title`|Alphanumeric|20|O|Title of the Merchant.|
|`firstName`|Alphanumeric|25|M|First Name of the Merchant.|
|`lastName`|Alphanumeric|25|M|Last Name of the Merchant.|
|`middleName`|Alphanumeric|25|O|Middle Name of the Merchant.|
|`gender`|Alphanumeric|10|O|Gender of the Merchant.|
|`ddateOfBirth`|Numeric|8|M|YYYYMMDD|
|**KYCDetails**|||||
|`kYCCategory`|-|||POI/POA of the Merchant.|
|`identityType`|Alphanumeric|50|O|Type of KYC Document submitted.|
|`identityType`|Alphanumeric|50|O|For India - PAN / AADHAR.|
|`identityType`|Alphanumeric|50|O|For ASEAN - Passport / Driving Licence / HKID or SGID or MYID.|
|`identityType`|Alphanumeric|50|O|For AU - Passport / Driving Licence.|
|`identityValue`|Alphanumeric|100|O|Value of the KYC Document submitted.|
|`identitymetaName1`|Alphanumeric|100|O|Additional information pertaning to the KYC documents submitted. For AU - Driving License State Code.|
|`identitymetaValue1`|Alphanumeric|100|O|Additional information pertaning to the KYC documents submitted. For AU - Value Driving License State Code.|
|`nationality`|Alphanumeric|35|O|Nationality of the Merchant.|
|**principalAddress**|||||
|`addressLine`|Alphanumeric|35|M|Address  line of the Merchant.|
|`addressLine2`|Alphanumeric|35|M|Address Line 2 of the Merchant.|
|`addressLine3`|Alphanumeric|35|M|Address Line 3 of the Merchant.|
|`city`|Alphanumeric|25|M|City of the Merchant.|
|`state`|Alphanumeric|25|M|State of the Merchant.|
|`pincode`|Alphanumeric|8|M|Pincode of the Merchant.|
|`country`|Alphanumeric|25|M|Country of the Merchant.|
|`mobileNo`|Numeric|15|O|Mobile number of the Merchant.|
|`phone 1`|Numeric|15|M|phone 1 of the Merchant.|
|`contactName`|Alphanumeric|35|O|Contact name of the Merchant.|
|`idDocDetails`|-||NA|ID Doc Details section is a conditional tag and should be mandatory for a user uploding documents in an application. All documents uploaded under "categoryInd": "P" has to be included under principalDetails - idDocDetails|
|`level`|Alphanumeric|2|NA|Value of level received as response of Uploaded document.|
|`mandatory`|Alphanumeric|10|NA|Mandatory of the Merchant.|
|`entity`|Alphanumeric|20|NA|Static Value - 'Member'|
|`idType`|Alphanumeric|20|NA|Value of docType received as response of Uploaded document.|
|`idValue`|Alphanumeric|20|NA|Id value|
|`docId`|-||NA|Value of docID received as response of Uploaded document.|
|`categoryName`|Alphanumeric|30|NA|Value of categoryName received as response of Uploaded document.|
|**uboDetails**|-|||This section is used to capture details of Ultimate Benefeciary Owner for the said merchant. The same section can be repeated for multiple UBOs. We can have upto maximum of 5 UBOs per merchant.|
|`serialNo`|Numeric|2|C|Serial number of the Ultimate Benefeciary Owner.|
|`title`|Alphanumeric|20|C|Title of the Ultimate Benefeciary Owner.|
|`firstName`|Alphanumeric|25|C|First name of the Ultimate Benefeciary Owner.|
|`lastName`|Alphanumeric|25|C|Last name of the Ultimate Benefeciary Owner.|
|`middleName`|Alphanumeric|25|C|Middle name of the Ultimate Benefeciary Owner.|
|`dateOfBirth`|Numeric|10|C|Format - YYYYMMDD|
|`shareholderPercentage`|Numeric|8|C|Shareholder percentage the Ultimate Benefeciary Owner.|
|`nationality`|Alphanumeric|35|C|Nationality of the Ultimate Benefeciary Owner.|
|**kycDetails**|||||
|**kycCategory**|-|||POI/POA of the Ultimate Benefeciary Owner.|
|`identityType`|Alphanumeric|50|C|Type of KYC Document submitted for UBO.|
|`identityType`|Alphanumeric|50|C|For India - PAN / AADHAR|
|`identityType`|Alphanumeric|50|C|For ASEAN - Passport / Driving Licence / HKID or SGID or MYID|
|`identityType`|Alphanumeric|50|C|For AU - Passport / Driving Licence|
|`identityValue`|Alphanumeric|100|C|Value of the KYC Document submitted.|
|`identitymetaName1`|Alphanumeric|100|NA|Additional information pertaning to the KYC documents submitted for UBO. For AU - Driving License State Code.|
|`identitymetaValue1`|Alphanumeric|100|NA|Additional information pertaning to the KYC docuements submitted. For AU - Value Driving License State Code.|
|**uboAddress**|||||
|`addressLine`|Alphanumeric|35|C|Address  of the Ultimate Benefeciary Owner.|
|`addressLine2`|Alphanumeric|35|C|Address Line2 Ultimate Benefeciary Owner.|
|`addressLine3`|Alphanumeric|35|C|Address Line3 Ultimate Benefeciary Owner.|
|`city`|Alphanumeric|25|C|City of the Ultimate Benefeciary Owner.|
|`state`|Alphanumeric|25|C|State of the Ultimate Benefeciary Owner.|
|`pincode`|Alphanumeric|8|C|Pincode of the Ultimate Benefeciary Owner.|
|`country`|Alphanumeric|25|C|Country of the Ultimate Benefeciary Owner.|
|`mobileNo`|Numeric|15|C|Mobile number of Ultimate Benefeciary Owner.|
|`phone1`|Numeric|15|C|phone 1 of the Ultimate Benefeciary Owner.|
|`contactName`|Alphanumeric|35|C|Contact Name of Ultimate Benefeciary Owner.|
|**bankDetails**|-|||This tag will contain the Bank account details of Partner/PayFac which needs to be configured at Fiserv End.|
|**uwaccountdetails**|-|||UW Account details are primarily the actual merchant account which will be used while underwriting the merchant.|
|`accountNo`|Numeric|100|NA|Account number of the Merchant.|
|`accountName`|Alphanumeric|35|NA|Account name of the Merchant.|
|`ifsc`|Alphanumeric|15|NA|Ifsc of the Merchant.|
|`bankName`|Alphanumeric|80|NA|Bank name of the Merchant.|
|`currency`|Alphanumeric|3|NA|Currency of the Merchant.|
|`branch`|Alphanumeric|500|NA|Branch of the Merchant.|
|`bankAddress`|Alphanumeric|500|NA|Bank address of the Merchant.|
|`accType`|Alphanumeric|30|NA|Acc Type of the Merchant.|
|**fundingaccountdetails**|-|||Funding account will have the details of account to which Fiserv will process the funding on daily basis.|
|`accountNo`|Numeric|100|NA|If different form UW details.|
|`accountName`|Alphanumeric|35|NA|Account name of the Merchant.|
|`ifsc`|Alphanumeric|15|NA|Ifsc of the Merchant.|
|`bankName`|Alphanumeric|80|NA|Bank Name of the Merchant.|
|`currency`|Alphanumeric|3|NA|Currency of the Merchant.|
|`branch`|Alphanumeric|500|NA|Branch of the Merchant.|
|`bankAddress`|Alphanumeric|500|NA|Bank address of the Merchant.|
|`accType`|Alphanumeric|30|NA|Account Type of the Merchant.|
|**collectionaccountdetails**|-|||This section will have details of account which needs to be used for collection of charges. This account may or may not be the same as UW account/Funding account.|
|`accountNo`|Numeric|100|NA|If different form UW details.|
|`accountName`|Alphanumeric|35|NA|Account name of the Merchant.|
|`ifsc`|Alphanumeric|15|NA|Ifsc of the Merchant.|
|`bankName`|Alphanumeric|80|NA|Bank Name of the Merchant.|
|`currency`|Alphanumeric|3|NA|Currency of the Merchant.|
|`branch`|Alphanumeric|500|NA|Branch of the Merchant.|
|`bankAddress`|Alphanumeric|500|NA|Bank address of the Merchant.|
|`accType`|Alphanumeric|30|NA|Acc type of the Merchant.|
|**submerchantDetails**|-|||This object is not applicable for ISO. This section is used to capture the sub Partner Details of the Merchant.|
|`submerchantID`|Numeric|15|NA|This is an optional field where the Single MID PayFacs can use to pass their own MID to Fiserv.|
|`submerchantID`|Numeric|15|NA|This field will be mandatory if the Channel level parameter for Payfac provided SMID is set to Y.|
|`submerchantID`|Numeric|15|NA|If the same is set to 'N', boarding backend will generate its own MID for the merchant.|
|**businessSummary**|-|||This section is used to capture the summary of the Merchant.|
|`briefSummary`|Alphanumeric|100|O|Brief summary of the Merchant.|
|`salessrNumber`|Alphanumeric|100|O|Sales number of the Merchant.|
|`mCCCode`|Numeric|20|M|MCC  number of the Merchant.|
|`mCCDescription`|Alphanumeric|200|O|MCC  description of the Merchant.|
|`totalTurnover`|Numeric|20|O|Total  turnover number of the Merchant.|
|`totalTurnoverPerMID`|Numeric|20|O|Total turnover per mid of the Merchant.|
|`cardTurnover`|Numeric|20|O|Card turnover of the Merchant.|
|`avgTicketAmt`|Numeric|20|O|Avg ticket amt of the Merchant.|
|`dccTurnoverPerMID`|Numeric|20|O|Dcc turnover per mid of the Merchant.|
|`pgTurnover`|Numeric|20|O|Pg  turnover of the Merchant.|
|`pgTurnoverPerMID`|Numeric|20|O|Pg turnover per mid of the Merchant.|
|`avgEMITicketAmt`|Numeric|20|O|Avg emi ticket amt of the Merchant.|
|`tranVolumeInternet`|Numeric|20|M|Tran volume internet of the Merchant.|
|`tranVolumeMoto`|Numeric|20|M|Tran volume moto of the Merchant.|
|`tranVolumeinStore`|Numeric|20|M|Tran volume in store of the Merchant.|
|`deliveryDays0`|Numeric|20|M|Delivery Days 0 of the Merchant.|
|`deliveryDays7`|Numeric|20|M|Delivery Days 7 of the Merchant.|
|`deliveryDays14`|Numeric|20|M|Delivery Days 14 of the Merchant.|
|`deliveryDays30`|Numeric|20|M|Delivery Days 30 of the Merchant.|
|`deliveryDaysOver30`|Numeric|20|M|Delivery Days Over 30 of the Merchant.|
|`tranTypeMagStrip`|Numeric|20|O|Tran type magstripe of the Merchant.|
|`tranTypeChip`|Numeric|20|O|Tran type chip of the Merchant.|
|`tranTypeKeyed`|Numeric|20|O|Tran type keyed of the Merchant.|
|`creditSalesConsumer`|Numeric|20|M|Credit sales consumer of the Merchant.|
|`creditSalesBusiness`|Numeric|20|M|Credit sales business of the Merchant.|
|`firstReport`|Alphanumeric|20|NA|First report of the Merchant.|
|`recurringTranFlag`|Alphanumeric|20|NA|Recurring tran flag of the Merchant.|
|`refundPolicy`|Alphanumeric|20|NA|Refund policy of the Merchant.|
|`cardRefundDays`|Alphanumeric|20|NA|Card refund days of the Merchant.|
|`thirdPartyProcessorFlag`|Alphanumeric|20|NA|Thirdparty processor flag of the Merchant.|
|`thirdPartyProcessorName`|Alphanumeric|40|NA|Thirdparty processor name of the Merchant.|
|`smallMerchant`|Alphanumeric|20|NA|Applicable if the merchant is a Small Merchant.|


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

| Error Code |  Description / Values |
| --------  | ------------------ |
|`100`| Invalid Request |
|`103`| Data not found, please contact application support team. |
|`200`| Success |
|`302`| IO Exception |
|`404`| Not Found |
|`401`| Unauthorized |	
|`500`| Internal Error, please contact application support team. |
|`505`| Internal server Error, please contact application support team. |
|`708`| App URN had already submitted. |
|`902`| App URN is a mandatory value. |
|`903`| Application already submitted. |
|`904`| JSON Processing Error |
|`905`| JSON Parse Error |
|`906`| JSON Mapping Error |
|`907`| Comment field empty. |
|`908`| App URN does not match. |
|`909`| Given Merchant Hierarchy Cannot handle via TAB. Please contact Application Support Team. |
|`910`| Given Merchant Id Doesnt qualify for Add Outlet. Please contact Application Support Team. |
|`911`| Given Merchant Super MID is Inactive. Please contact Application Support Team. |
|`912`| One of MID in hierarchy is Inactive. Please contact Application Support Team. |
|`913`| Please use member level Mid. Please contact Application Support Team .|
|`914`| Ref MID should be 8 digits. |
|`915`| Business Rule Exception |
|`916`| All Adress Types are not available for Ref MID. Please contact Application Suport Team. |
|`917`| No Services avaiable for Ref MID. Please contact Application Support Team. |
