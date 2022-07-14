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

POST `https://www.uat.fdmerchantservices.com/Externalboarding/secure/newmid`

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
|`appURN`|Alphanumeric|30|M|App URN retured as part of Create URN API|
|`appType`|Alphanumeric|8|M|Fixed Value 'API'|
|`salesId`|Alphanumeric|70|O|User Credential created for each partner|
|`channelCode`|Alphanumeric|10|O|Static Channel Code shared with each partner|
|`institutionId`|Numeric|10|O|Institution number assigned to the institution|
|`boardingType`|Alphanumeric|20|NA|Type of Merchant: New MID / Add MID / Add TID|
|`IS_ADD_LOCATION`|Alphanumeric|20|NA|Applicable if the merchant wants additional location|
|`IS_ADD_MID`|Alphanumeric|20|NA|Applicable if the merchant wants additional MID|
|`appChannel`|Alphanumeric|20|NA|Application channel|
|`osvFlagValue`|Alphanumeric|1|NA|Original Sent & Verified flag. Applicable for entities where documents are uploaded. For entities not uploading documents, keep this field as blank.|
|**merchantDetails**|-|||This is the object|
|`businessName`|Alphanumeric|22|M|Trade Name of the Merchant|
|`legalName`|Alphanumeric|35|M|Legal Name of the Merchant|
|`businessType`|Alphanumeric|50|M|Type of Business of the Merchant|
|`registrationNo`|Alphanumeric|100|O|Registration number of the Merchant|
|**taxDetails**|-|||This is the object|
|`taxidType`|Alphanumeric|50|M|Tax ID Type provided for the merchant|
|`taxidType`|Alphanumeric|50|M|For India - PAN|
|`taxidType`|Alphanumeric|50|M|For AU - ABN "" ""Tax ID Type provided for the merchant For India: Individual PAN for Individual/Soleprop merchants|
|`taxidValue`|Alphanumeric|100|M|PAN, ABN number of the Merchant|
|`dateIncorporated`|Alphanumeric|100|M|PAN, ABN number of the Merchant|
|`websiteURL`|Alphanumeric|100|M|PAN, ABN number of the Merchant|
|`communicationEmail`|Alphanumeric|100|M|PAN, ABN number of the Merchant|
|`merchantType`|Alphanumeric|100|M|PAN, ABN number of the Merchant|
|`acceptanceType`|Alphanumeric|100|M|PAN, ABN number of the Merchant|
|`iciciMerchant`|Numeric|8|M|YYYYMMDD|
|`newFundingAc`|Alphanumeric|100|NA|Eligible for ECOM Merchant|
|**legalAddress**|Alphanumeric|60|M|Communication Email of the Merchant|
|`addressLine`|Alphanumeric|20|M|Whether it is small merchant or Large merchant|
"|`addressLine2`|Alphanumeric|10|M|Static Value - 'POSMOB' for POS merchant Static Value: ''ECOM'' for ECOM merchant|"
|`addressLine3`|Alphanumeric|20|M|Applicable if the merchant has ICICI account|
|`city`|Alphanumeric|20|M|Applicable if the merchant wants the new settlement account|
|`state`|-|||This is the object|
|`pincode`|Alphanumeric|35|M|Address of the Merchant|
|`country`|Alphanumeric|35|O|Address of the Merchant|
|`mobileNo`|Alphanumeric|35|O|Address of the Merchant|
|`phone1`|Alphanumeric|25|M|City of the Merchant|
|`email`|Alphanumeric|25|M|State of the Merchant|
|`contactName`|Alphanumeric|8|M|Pincode of the Merchant|
|`gstNo`|Alphanumeric|25|M|Country of the Merchant|
|`gstMerchantStateCode`|Numeric|15|M|Mobile number of the Merchant|
|`isdnFlag`|Numeric|15|O|Phone number of the Merchant|
|**idDocDetails**|Numeric|30|O|Email of the Merchant|
|`entity`|Alphanumeric|35|M|Contact Name of the Merchant|
|`idType`|Alphanumeric|100|M|Mandatory for Large merchants|
|`idValue`|Alphanumeric|40|O|Mandatory for Large Partners|
|`docId`|Alphanumeric|20|NA|Isdn Flag|
|`categoryName`|-|||ID Doc Details section is a conditional tag and has to be mandatorily present if the user is uploding documents for a particular application. All documents uploaded under ""categoryInd"": ""E"" has to be included under merchantDetails.idDocDetails|
|`level`|Alphanumeric|20|NA|Static Value - 'Member'|
|`entity`|Alphanumeric|20|NA|Value of docType received as response of uploaded document|
|`idType`|Alphanumeric|20|NA||
|`idValue`|Alphanumeric|20|NA|Value of docID received as response of uploaded document|
|`docId`|Alphanumeric|20|NA|Value of categoryName received as response of uploaded document|
|`categoryName`|Numeric|20|NA|Value of level received as response of uploaded document|
|`level`|Alphanumeric|20|NA|Static Value - 'Member'|
|**geoLocation**|Alphanumeric|20|NA|Value of docType received as response of uploaded document|
|`latitude`|Alphanumeric|20|NA|Id Value|
|`longitude`|Alphanumeric|20|NA|Value of docID received as response of uploaded document|
|**tradingLocations**|Alphanumeric|20|NA|Value of categoryName received as response of uploaded document|
|`locationNo`|Numeric|20|NA|Value of level received as response of uploaded document|
|`tradingName`|-|||This is the object|
|**tradingAddress**|Numeric|20|NA|Lattitude of the Merchant|
|`addressLine`|Numeric|20|NA|Longitude of the Merchant|
|`addressLine2`|-|||"This section contains the trading location details of merchants that is being onboarded. A maximum upto 3 trading locations can be added under a single Application.|
|`addressLine3`|Numeric|2|M|Trading location number of the Merchant|
|`city`|Alphanumeric|22|M|Trade Name of the Merchant|
|`state`|-|||This is the object|
|`pincode`|Alphanumeric|35|M|Address of the Merchant|
|`country`|Alphanumeric|35|O|Address of the Merchant|
|`mobileNo`|Alphanumeric|35|O|Address of the Merchant|
|`phone1`|Alphanumeric|25|M|City of the Merchant|
|`email`|Alphanumeric|25|M|State of the Merchant|
|`ontactName`|Alphanumeric|8|M|Pincode of the Merchant|
|`packageId`|Alphanumeric|25|M|Country of the Merchant|
|`autoSettlementTime`|Numeric|15|M|Mobile number of the Merchant|
|`cpvGroupId`|Numeric|15|O|phone1 of the Merchant|
|`regionalcpvGroupid`|Numeric|30|NA|Email of the Merchant|
|`commerceConnectReferenceMID`|Alphanumeric|35|M|Contact name of the Merchant|
|**terminals**|Numeric|10|M|Package number assigned to the Merchant|
|`count`|Numeric|6|NA|HHMMSS|
|`preferedDate`|Alphanumeric|50|NA|Cpv groupid of the Merchant|
|`preferedTime`|Alphanumeric|50|NA|Regional cpv groupid of the Merchant|
|`discount`|Alphanumeric|8|NA|Commerce connect reference mid of the Merchant|
|`userInstruction1`|-|||This is the object|
|`userInstruction2`|Numeric|2|M|Count of terminals for the Merchant|
|**surchargeAmount**|Numeric|8|O|YYYYMMDD|
|`visaBase`|Numeric|6|O|HHMMSS|
|`visaPercent`|Numeric|3|NA|Discount of the Merchant|
|`mcBase`|Alphanumeric|100|NA|User Instruction1 of the Merchant|
|`mcPercent`|Alphanumeric|100|NA|User Instruction2 of the Merchant|
|`upiBase`|-|||This object not applicable for ISO. Surcharge values currently selected by Partner on MVSI in AU|
|`upiPercent`|Numeric|11|NA|For AU Only|
|`eftposBase`|Numeric|11|NA|For AU Only|
|`eftposPercent`|Numeric|11|NA|For AU Only|
|`amexBase`|Numeric|11|NA|For AU Only|
|`amexPercent`|Numeric|11|NA|For AU Only|
|`jcbBase`|Numeric|11|NA|For AU Only|
|`jcbPercent`|Numeric|11|NA|For AU Only|
|`dinersBase`|Numeric|11|NA|For AU Only|
|`dinersPercent`|Numeric|11|NA|For AU Only|
|`altmerchCode`|Numeric|11|NA|For AU Only|
|`sameLocation`|Numeric|11|NA|For AU Only|
|`mID`|Numeric|11|NA|For AU Only|
|`parentmid`|Numeric|11|NA|For AU Only|
|`otpEnabled`|Numeric|11|NA|For AU Only|
|**principalDetails**|Alphanumeric|20|NA|This is an optional field which has to be populated only if there is merchant MID or Dealer Code has to be captured at MID Level|
|`principalNo`|Alphanumeric|1|M|This flag has to be set to 'Y' if Partner wants multiple MIDs at the same location|
|`position`|Numeric|15|NA|This is the reference Member MID which needs to be given in case of ADD MID / ADD TID.|
|`title`|Numeric|15|NA|This is the SG (parent MID) of the reference MID which needs to be given in case of ADD MID & ADD TID|
|`firstName`|Alphanumeric|10|NA|Otp enabled for the merchant|
|`lastName`|-|||This section is used to capture details of Principal Owner for the said merchant. The same section can be repeated for multiple Principal Owners. We can have upto maximum of 2 Principal Owners per merchant|
|`middleName`|Alphanumeric|2|M|Principal number of the Merchant|
|`gender`|Alphanumeric|20|M|Position of the Merchant|
|`ddateOfBirth`|Alphanumeric|20|M|Title of the Merchant|
|**KYCDetails**|Alphanumeric|25|M|First Name mf the Merchant|
|`kYCCategory`|Alphanumeric|25|M|Last Name of the Merchant|
|`identityType`|Alphanumeric|25|O|Middle Name of the Oerchant|
|`identityType`|Alphanumeric|10|M|Gender of the Merchant|
|`identityType`|Numeric|8|M|YYYYMMDD|
|`identityType`|-|||This is the object|
|`identityValue`|-|||POI / POA of the Merchant|
|`identitymetaName1`|Alphanumeric|50|M|Type of KYC Document submitted|
|`identitymetaValue1`|Alphanumeric|50|M|For India - PAN / AADHAR|
|`nationality`|Alphanumeric|50|M|For ASEAN - Passport / Driving Licence / HKID or SGID or MYID|
|**principalAddress**|Alphanumeric|50|M|For AU - Passport/Driving Licence|
|`addressLine`|Alphanumeric|100|M|Value of the Kyc Document submitted|
|`addressLine2`|Alphanumeric|100|NA|Additional information pertaning to the KYC docuements submitted. For AU - Driving License State Code|
|`addressLine3`|Alphanumeric|100|NA|Additional information pertaning to the KYC docuements submitted. For AU - Value Driving License State Code|
|`city`|Alphanumeric|35|O|Nationality of the Merchant|
|`state`|-|||This is the object|
|`pincode`|Alphanumeric|35|M|Address  line of the Merchant|
|`country`|Alphanumeric|35|O|Address Line2 of the Merchant|
|`mobileNo`|Alphanumeric|35|O|Address Line3 of the Merchant|
|`phone 1`|Alphanumeric|25|M|City of the Merchant|
|`contactName`|Alphanumeric|25|M|State of the Merchant|
|`idDocDetails`|Alphanumeric|8|M|Pincode of the Merchant|
|`idDocDetails`|Alphanumeric|25|M|Country of the Merchant|
|`level`|Numeric|15|M|Mobile number of the Merchant|
|`mandatory`|Numeric|15|O|phone 1 of the Merchant|
|`entity`|Alphanumeric|35|M|Contact name of the Merchant|
|`idType`|-||NA|ID Doc Details section is a conditional tag and has to be mandatorily present if the user is uploding documents for a particular application|
|`idValue`|-||NA|All documents uploaded under ""categoryInd"": ""P"" has to be included under principalDetails.idDocDetails|
|`docId`|Alphanumeric|2|NA|Value of level received as response of uploaded document|
|`categoryName`|Alphanumeric|10|NA|Mandatory of the Merchant|
|**uboDetails**|Alphanumeric|20|NA|Static Value - 'Member'|
|`serialNo`|Alphanumeric|20|NA|Value of docType received as response of uploaded document|
|`title`|Alphanumeric|20|NA|Id value|
|`firstName`|-||NA|Value of docID received as response of uploaded document|
|`lastName`|Alphanumeric|30|NA|Value of categoryName received as response of uploaded document|
|`middleName`|-|||This section is used to capture details of Ultimate Benefeciary Owner for the said merchant. The same section can be repeated for multiple UBOs. We can have upto maximum of 5 UBOs per merchant.|
|`dateOfBirth`|Numeric|2|NA|Serial number of the Ultimate Benefeciary Owner|
|`shareholderPercentage`|Alphanumeric|20|NA|Title of the Ultimate Benefeciary Owner|
|`nationality`|Alphanumeric|25|NA|First name of the Ultimate Benefeciary Owner|
|**kycDetails**|Alphanumeric|25|NA|Last name of the Ultimate Benefeciary Owner|
|**kycCategory**|Alphanumeric|25|NA|Middle name of the Ultimate Benefeciary Owner|
|`identityType`|Numeric|10|NA|Format - YYYYMMDD|
|`identityType`|Numeric|8|NA|Shareholder percentage the Ultimate Benefeciary Owner|
|`identityType`|Alphanumeric|35|NA|Nationality of the Ultimate Benefeciary Owner|
|`identityType`|-|||This is the object|
|`identityValue`|-|||POI / POA of the Ultimate Benefeciary Owner|
|`identitymetaName1`|Alphanumeric|50|NA|Type of KYC Document submitted for UBO|
|`identitymetaName1`|Alphanumeric|50|NA|For India - PAN / AADHAR|
|`identitymetaValue1`|Alphanumeric|50|NA|For ASEAN - Passport / Driving Licence / HKID or SGID or MYID|
|`identitymetaValue1`|Alphanumeric|50|NA|For AU - Passport / Driving Licence|
|**uboAddress**|Alphanumeric|100|NA|Value of the Kyc Document submitted|
|`addressLine`|Alphanumeric|100|NA|Additional information pertaning to the KYC docuements submitted for UBO|
|`addressLine2`|Alphanumeric|100|NA|For AU - Driving License State Code|
|`addressLine3`|Alphanumeric|100|NA|Additional information pertaning to the KYC docuements submitted|
|`city`|Alphanumeric|100|NA|For AU - Value Driving License State Code"|
|`state`|-|||This is the object|
|`pincode`|Alphanumeric|35|NA|Address  of the Ultimate Benefeciary Owner|
|`country`|Alphanumeric|35|NA|Address Line2 Ultimate Benefeciary Owner|
|`mobileNo`|Alphanumeric|35|NA|Address Line3 Ultimate Benefeciary Owner|
|`phone1`|Alphanumeric|25|NA|City of the Ultimate Benefeciary Owner|
|`contactName`|Alphanumeric|25|NA|State of the Ultimate Benefeciary Owner|
|**bankDetails**|Alphanumeric|8|NA|Pincode of the Ultimate Benefeciary Owner|
|**uwaccountdetails**|Alphanumeric|25|NA|Country of the Ultimate Benefeciary Owner|
|`accountNo`|Numeric|15|NA|Mobile number of Ultimate Benefeciary Owner|
|`accountName`|Numeric|15|NA|phone 1 of the Ultimate Benefeciary Owner|
|`ifsc`|Alphanumeric|35|NA|Contact Name of Ultimate Benefeciary Owner|
|`bankName`|-|||This tag will contain the Bank account details of Partner/PayFac which needs to be configured at Fiserv End|
|`currency`|-|||UW Account details are primarily the actual merchant account which will be used while underwriting the merchant|
|`branch`|Numeric|100|NA|Account number of the Merchant|
|`bankAddress`|Alphanumeric|35|NA|Account name of the Merchant|
|`accType`|Alphanumeric|15|NA|Ifsc of the Merchant|
|**fundingaccountdetails**|Alphanumeric|80|NA|Bank name of the Merchant|
|`accountNo`|Alphanumeric|3|NA|Currency of the Merchant|
|`accountName`|Alphanumeric|500|NA|Branch of the Merchant|
|`ifsc`|Alphanumeric|500|NA|Bank address of the Merchant|
|`bankName`|Alphanumeric|30|NA|Acc Type of the Merchant|
|`currency`|-|||Funding account will the details of account to which Fiserv will process the funding on daily basis|
|`branch`|Numeric|100|NA|If different form UW details|
|`bankAddress`|Alphanumeric|35|NA|Account number of the Merchant|
|`accType`|Alphanumeric|15|NA|Ifsc of the Merchant|
|**collectionaccountdetails**|Alphanumeric|80|NA|Bank Name of the Cerchant|
|`accountNo`|Alphanumeric|3|NA|Currency of the Merchant|
|`accountName`|Alphanumeric|500|NA|Branch of the Merchant|
|`ifsc`|Alphanumeric|500|NA|Bank address of the Merchant|
|`bankName`|Alphanumeric|30|NA|Account Type of the Merchant|
|`currency`|-|||This section will have details of account which needs to be used for collection of charges. This account may or may not be the same as UW account/Funding account|
|`branch`|Numeric|100|NA|If different form UW details|
|`bankAddress`|Alphanumeric|35|NA|Account name of the Merchant|
|`accType`|Alphanumeric|15|NA|Ifsc of the Merchant|
|**submerchantDetails**|Alphanumeric|80|NA|Bank Name of the Cerchant|
|`submerchantID`|Alphanumeric|3|NA|Currency of the Merchant|
|`submerchantID`|Alphanumeric|500|NA|Branch of the Merchant|
|`submerchantID`|Alphanumeric|500|NA|Bank address of the Merchant|
|**businessSummary**|Alphanumeric|30|NA|Acc type of the Merchant|
|`briefSummary`|-|||This object is not applicable for ISO. This section is used to capture the sub Partner Details of the merchant|
|`salessrNumber`|Numeric|15|NA|"This is an optional field which the Single MID PayFacs can use to pass their own MID to Fiserv.|
|`mCCCode`|Numeric|15|NA|This field will be mandatory if the Channel level parameter for Payfac Provided SMID is set to Y.|
|`mCCDescription`|Numeric|15|NA|If the same is set to 'N', Boarding backend will generate its own MID for the merchant"|
|`totalTurnover`|-|||This section is used to capture the summary of the merchant|
|`totalTurnoverPerMID`|Alphanumeric|100|M|Brief summary of the Merchant|
|`cardTurnover`|Alphanumeric|100|NA|Sales number of the Merchant|
|`avgTicketAmt`|Numeric|20|M|MCC  number of the Merchant|
|`dccTurnoverPerMID`|Alphanumeric|200|M|MCC  description of the Merchant|
|`pgTurnover`|Numeric|20|M|Total  turnover number of the Merchant|
|`pgTurnoverPerMID`|Numeric|20|M|Total turnover per mid of the Merchant|
|`avgEMITicketAmt`|Numeric|20|O|Card turnover of the Merchant|
|`tranVolumeInternet`|Numeric|20|M|Avg ticket amt of the Merchant|
|`tranVolumeMoto`|Numeric|20|M|Dcc turnover per mid of the Merchant|
|`tranVolumeinStore`|Numeric|20|O|Pg  turnover of the Merchant|
|`deliveryDays0`|Numeric|20|O|Pg turnover per mid of the Merchant|
|`deliveryDays7`|Numeric|20|O|Avg emi ticket amt of the Merchant|
|`deliveryDays14`|Numeric|20|O|Tran volume internet of the Merchant|
|`deliveryDays30`|Numeric|20|O|Tran volume moto of the Merchant|
|`deliveryDaysOver30`|Numeric|20|M|Tran volume in store of the Merchant|
|`tranTypeMagStrip`|Numeric|20|M|Delivery Days0 of the Merchant|
|`tranTypeChip`|Numeric|20|M|Delivery Days7 of the Merchant|
|`tranTypeKeyed`|Numeric|20|M|Delivery Days14 of the Merchant|
|`creditSalesConsumer`|Numeric|20|M|Delivery Days30 of the Merchant|
|`creditSalesBusiness`|Numeric|20|M|Delivery Days Over30 of the Merchant|
|`firstReport`|Numeric|20|M|Tran type magstripe of the Merchant|
|`recurringTranFlag`|Numeric|20|M|Tran type chip of the Merchant|
|`refundPolicy`|Numeric|20|M|Tran type keyed of the Merchant|
|`cardRefundDays`|Numeric|20|M|Credit salesconsumer of the Merchant|
|`thirdPartyProcessorFlag`|Numeric|20|M|Credit salesbusiness of the Merchant|
|`thirdPartyProcessorName`|Alphanumeric|20|NA|First report of the Merchant|
|`smallMerchant`|Alphanumeric|20|NA|Recurring tran flag of the Merchant|
|`Refund Policy`|Alphanumeric|20|NA|Refund policy of the Merchant|
|`Card Refund Days`|Alphanumeric|20|NA|Card refund days of the Merchant|
|`ThirdParty Processor Flag`|Alphanumeric|20|NA|Thirdparty processor flag of the Merchant|
|`ThirdParty Processor Name`|Alphanumeric|40|NA|Thirdparty processor name of the Merchant|


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
