# Pre-Authorization Completion


This API is used to send pre-authorization completion transaction request. Merchants will be required to add session token received during login API call in the header of this API.


## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/cloudpoidp/PosPush/standardNonOpiProcess`

## Payload Example

### Request Payload

```json
{
   "id":1656,
   "merchantDetails":{
      "ain":"2100000",
      "billerId":"14",
      "merchantId":"42298585549376",
      "terminalId":"85549376",
      "mrchCountryCode":"036",
      "siteId":"",
      "workStationId":""
   },
   "txnDetails":{
      "functionCode":"03",
      "customerRefNumber":"",
      "merchantRefNumber":"VinayAMEX111347112022031119911111431",
      "transactionId":"202211250040180",
      "reqDate":"21112022",
      "reqTime":"150155",
      "originalTranDate":"17112022",
      "originalTranTime":"",
      "authCode":"041232",
      "rrn":"232122006000",
      "tokenId":"",
      "invoiceNumber":"10",
      "batchNo":"",
      "amexSeNumber":"",
      "posEntryMode":"",
      "walletType":"",
      "walletId":"",
      "schemeId":"",
      "cardLastNumber":"1234",
      "primaryId":"",
      "customerName":"",
      "offlineFlag":"",
      "aTC":"",
      "tVR":"",
      "appLabel":"",
      "aID":"",
      "panSeqNo":"",
      "schemeTranInfo":"",
      "isInternalCall":"N",
      "authenticationMethod":null
   },
   "amounts":{
      "authAmount":"56.59",
      "mrchDiscountAmt":"",
      "convFee":"",
      "cgst":"",
      "igst":"",
      "sgst":"",
      "gst":"",
      "totalAmount":"56.59",
      "tranCurrency":"036",
      "tip":""
   },
   "additionalParams":{
      "udf1":"",
      "udf2":"",
      "callbackURL":"",
      "paramList":[
         {
            "param":"",
            "param_lit":""
         }
      ]
   }
}

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

##### The table below contains:- #####
- Mandatory fields required for a successful request
- Full request schemas are available in our  [API Explorer](../api/?type=post&path=/boardinggateway/cloudpoidp/PosPush/nonOpiProcessAmount)
- Identifies the required query parameters in the request message
- Identifies the required json properties in the request message.

### Request
| Variable | Type | Length | Mandatory / Optional /Conditional <br>(M / O / C) | Description / Values |
| -------- | ------- | -- | ----------------------------------------------- | ------------------ |
|`Merchant Info`|||||
|`billerId`|String|3|M|Biller Id provided by Fiserv.|
|`ain`|String |7|M|Acquirer institution number provided by Fiserv.|
|`siteId`|String|15|C|Merchant's MID reference (not required if MID is sent)|
|`workStationId`|String |8|C|Merchant's TID reference (not required if TID is sent)|
|`merchantId`|String |15|C|Merchant ID assigned|
|`terminalId`|String |8|C|Terminal ID where transaction to be pushed.|
|`mrchCountryCode`|String |3|M|Merchant Country Code (3-digit numeric value)|
|**Txn Info**|||||
|`functionCode`|String |2|M|00 - Sale | 
 | | |  |               |02 - Preauth |
 | | |  |               |03 - Preauth Completion|
 | | |  |               |04 - Refund|
 | | |  |               |05 - Void|
 | | |  |               |06 - TopUp (Incremental Preauth)|
 | | |  |               |11 - Transaction Status Check (Inquiry)|
 | | |  |               |12 - Settlement|
 | | |  |               |38 - Get Token|
|`merchantRefNumber`|String|50|M|Unique number for Sale, Pre-auth and Get Token.|
|`customerRefNumber`|String |20|O|Consumer Number |
|`transactionId`|String|20|M|Pass the same value from original transaction response.|
|`reqDate`|DDMMYYYY||M|Transaction Initiated date|
|`reqTime`|HHMMSS||M|Transaction Initiated time|
|`originalTranDate`|DDMMYYYY||M|Original transaction date|
|`originalTranTime`|HHMMSS||M|Original transaction time|
|`authCode`|String |6|M|Pass the same value from original transaction response.|
|`rrn`|String |20|M|Pass the same value from original transaction response.|
|`tokenId`|String|30|C|Token Id returned during initial auth / get token.|
|**Amounts**|||||
|`authAmount`|String|12|M|Bill Amount including decimal (Ex: “50.00” for $50 sale). Send 0.00 for inquiry txn and Get Token.|
|`mrchDiscountAmt`|String|10|N/A|discount given to card holder.|
|`convFee`|String |10|C|Convenience Fee including decimal (Ex: “5.00” for $5 fee) - To be sent if fee is charged.|
|`cgst`|String |10|C|Central GST Including decimal (Ex: “10.00” for $10 cgst) - To be sent if CGST is included in the total amount (Applicable only for India).|
|`igst`|String |10|C|Integrated GST Including decimal (Ex: “10.00” for $10 igst) - To be sent if IGST is included in the total amount (Applicable only for India).|
|`sgst`|String |10|C|State GST Including decimal (Ex: “10.00” for $10 igst) - To be sent if SGST is included in the total amount (Applicable only for India).|
|`gst`|String |10|C|GST - applicable except India|
|`totalAmount`|String |12|M|Total Amount (auth, fee, gsts) including decimal (Ex: “57.00” for $57 sale). Send 0.00 for inquiry txn and Get Token.|
|`tranCurrency`|String |3|M|Transaction Currency Code (3-digit numeric value)|
|**Additional Params**|||||
|`callbackURL`|String|100|O|Response URL, place holder for notification API call feature.|
|`param_lit`|Array||O|Biller can pass any additional details if required in arrary format as below,<br>"paramList": [<br> {<br>"param_lit": "param1 key",<br>"param"": "23"<br>},<br>{<br>"param_lit": "param 2 key",<br>"param": "54"<br>}<br>]|"
|`udf1`|String |100|O|User Defined Field|
|`udf2`|String|100|O|User Defined Field|

### Successful Response Payload

```json
{
   "merchantDetails":{
      "ain":"2100000",
      "billerId":"14",
      "merchantId":"42298585549376",
      "terminalId":"85549376",
      "mrchCountryCode":"036",
      "siteId":"",
      "workStationId":""
   },
   "txnStatus":{
      "respCode":"200",
      "response":"SUCCESS",
      "respMsg":"Transaction Success"
   },
   "txnDetails":{
      "functionCode":"03",
      "customerRefNumber":"",
      "merchantRefNumber":"",
      "transactionId":"",
      "reqDate":"21112022",
      "reqTime":"150155",
      "originalTranDate":"17112022",
      "originalTranTime":"",
      "authCode":"353319",
      "rrn":"000000000095",
      "tokenId":"",
      "invoiceNumber":"",
      "batchNo":"",
      "amexSeNumber":"",
      "posEntryMode":"",
      "walletType":"",
      "walletId":"",
      "schemeId":"",
      "cardLastNumber":"",
      "primaryId":"",
      "customerName":"",
      "offlineFlag":"",
      "aTC":"",
      "tVR":"",
      "appLabel":"",
      "aID":"",
      "panSeqNo":"",
      "schemeTranInfo":"",
      "isInternalCall":null,
      "authenticationMethod":null
   },
   "amounts":{
      "authAmount":"56.59",
      "mrchDiscountAmt":"",
      "convFee":"",
      "cgst":"",
      "igst":"",
      "sgst":"",
      "gst":"",
      "totalAmount":"56.59",
      "tranCurrency":"036",
      "tip":""
   },
   "dccInfo":{
      "dccIndicator":"",
      "dccCurrency":"",
      "dccAmount":"",
      "dccExchangeRate":""
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
| Variable | Type | Length | Mandatory / Optional /Conditional <br>(M / O / C) | Description / Values |
| -------- | ------- | -- | ----------------------------------------------- | ------------------ |
|`Merchant Info`|||||
|`billerId`|String |3|M|Same as request|
|`ain`|String|7|M|Same as request|
|`siteId`|String|15|C|Same as request|
|`workStationId`|String|8|C|Same as request|
|`merchantId`|String |15|C|Same as request|
|`terminalId`|String|8|C|Same as request|
|`mrchCountryCode`|String|3|M|Merchant Country Code (3-digit numeric value)|
|**Txn Status**|||||
|`respCode`|String|5|M|200/300/actual switch response|
|`response`|String|20|M|SUCCESS/FAILURE|
|`respMsg`|String|20|O|Error Message|
|**Txn Info**|||||
|`functionCode`|String|2|M|Same as request except Inquiry txn. For Inquiry txn Original txn function code will be returned.|
|`merchantRefNumber`|String|50|M|Same as request|
|`customerRefNumber`|String|20|O|Same as request|
|`transactionId`|String|20|M|Unique Id for the transaction.|
|`reqDate`|DDMMYYYY||M|Same as request|
|`reqTime`|HHMMSS||M|Same as request|
|`originalTranDate`|DDMMYYYY||M|Same as request|
|`originalTranTime`|HHMMSS||M|Same as request|
|`authCode`|String|6|O|Received from Issuer Host. Return the auth code received in response from Base24 for refund.|
|`rrn`|String|20|O|Received from Issuer Host. Return the auth code received in response from Base24 for refund.|
|`invoiceNumber`|String|20|O|Terminal Invoice Number|
|`batchNo`|String|3|O|Terminal Batch Number|
|`amexSeNumber`|String|10|C|Applicable for AMEX transaction.|
|`posEntryMode`|String|10|M|MANUAL / SWIPE / INSERT / CLSS / FALLBACK / CLSS_MSR / QRC|
|`walletType`|String|10|O|Wallet Type will be passed for QR txn.|
|`walletId`|String|5|O|Wallet Id will be passed for LPM txn.|
|`schemeId`|String|10|O|Scheme Name will be passed for Card txn.|
|`cardLastNumber`|String|4|O|Card Last 4 digits for Carded txn.|
|`primaryId`|String |20|O|Reference Number of the QR Request.|
|`customerName`|String |20|O|Cardholder Name|
|`offlineFlag`|String|1|O|Offline flag|
|`tokenId`|String|30|O|Token Id - for the merchant requires token PAN.|
|`aTC`|String|4|O|Application Txn Counter (EMV Tag 9F36)|
|`tVR`|String |10|O|Terminal Verification Result (EMV Tag - 95)|
|`appLabel`|String|32|O|Application Label (EMV tag - 50)|
|`aID`|String|14|O|Application Identifier (EMV tag - 84)|
|`panSeqNo`|String|2|O|PAN Sequence No (EMV Tag - 5F34)|
|`schemeTranInfo`|String|32|O|Refer Appendix A for the tag layout.|
|**Amounts**|||||
|`authAmount`|String|12|M|Same as Request|
|`mrchDiscountAmt`|String |10|O|discount given to card holder.|
|`convFee`|String |10|C|Same as Request|
|`cgst`|String |10|C|Same as Request|
|`igst`|String |10|C|Same as Request|
|`sgst`|String |10|C|Same as Request|
|`gst`|String|10|C|Same as Request|
|`tipAmount`|String |12|O|Tip Amount If applicable|
|`totalAmount`|String|12|M|Total Amount (auth, fee, gsts, tip) including decimal ((Ex: “57.00” for $57 sale).|
|`tranCurrency`|String|3|M|Same as Request|
|**DCC**|||||
|`dccIndicator`|String|1|M|0 – Non DCC <br> 1 – DCC|
|`dccCurrency`|String|3|C|DCC Currency|
|`dccAmount`|String|19|C|DCC Amount|
|`dccExchangeRate`|String|20|C|Currency exchange rate|


The table below provides the list of error codes and description for this application.

|  Error Code   |  Description / Values    | Comments |
|  -----------  | ---------------------- |----------|
| `200`| Success | Request is successfully processed. Merchant should go ahead with receipt generation. |
| `300`| Request Failure | Redirection error. Merchant should validate and retry with new request. |
| `401`| Token not valid or Token had not passed at all | User authentication error. Merchant should key a valid token during the transaction. |
 | `404`| Not Found | Server cannot find the requested resource. Contact Customer Support / Business Manager. |
| `502`| Request Timed Out | Server received an invalid gateway response Merchant should retry with new request. |


