# Void Transaction

This API is used to send void transaction request. Merchants will be required to add session 
token received during login API call in the header of this API.


## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/cloudpoidp/PosPush/standardNonOpiProcess`

## Payload Example

### Request Payload

```json
{
   "request":{
      "merchantDetails":{
         "ain":"2100000",
         "billerId":"14",
         "merchantId":"42298519014704",
         "terminalId":"19014704",
         "mrchCountryCode":"036"
      },
      "transactionDetails":{
         "functionCode":"05",
         "merchantRefNumber":"900000700012",
         "transactionId":"202211172224141",
         "reqDate":"17112022",
         "reqTime":"154900",
         "originalTranDate":"14022022",
         "originalTranTime":"133955",
         "authCode":"318861",
         "rrn":"232110980240",
         "tokenId":null,
         "isInternalCall":"Y",
         "invoiceNumber":"4"
      },
      "amounts":{
         "totalAmount":"3",
         "tranCurrency":"036",
         "authAmount":"100.00"
      }
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
|**Merchant Information**|||||
|`billerId`|String|3|M|Biller ID provided by Fiserv.|
|`ain`|String |7|M|Acquirer institution number provided by Fiserv.|
|`siteId`|String|15|C|Merchant's MID reference (not required if MID is sent)|
|`workStationId`|String |8|C|Merchant's TID reference (not required if TID is sent)|
|`merchantId`|String |15|C|Merchant ID assigned|
|`terminalId`|String |8|C|Terminal ID where transactions to be pushed.|
|`mrchCountryCode`|String |3|M|Merchant Country Code (3-digit numeric value)|
|**Transaction Information**|||||
|`functionCode`|String |2|M|00 - Sale | 
 | | |  |               |02 - Pre-authorization |
 | | |  |               |03 - Pre-authorization Completion|
 | | |  |               |04 - Refund|
 | | |  |               |05 - Void|
 | | |  |               |06 - Top Up (Incremental Pre-authorization)|
 | | |  |               |11 - Transaction Status Check (Inquiry)|
 | | |  |               |12 - Settlement|
 | | |  |               |38 - Get Token|
|`merchantRefNumber`|String|50|M|Unique number for Sale, Pre-authorization and Get Token.|
|`customerRefNumber`|String |20|O|Consumer Number |
|`transactionId`|String|20|M|Pass the same value from original transaction response.|
|`reqDate`|DDMMYYYY||M|Transaction Initiated date|
|`reqTime`|HHMMSS||M|Transaction Initiated time|
|`originalTranDate`|DDMMYYYY||M|Original transaction date|
|`originalTranTime`|HHMMSS||M|Original transaction time|
|`authCode`|String |6|M|Pass the same value from original transaction response.|
|`rrn`|String |20|M|Pass the same value from original transaction response.|
|`tokenId`|String|30|C|Token ID returned during initial authorization / get token.|
|**Amounts**|||||
|`authAmount`|String|12|M|Bill Amount including decimal (E.g: “50.00” for $50 sale). Send 0.00 for inquiry transaction and Get Token.|
|`mrchDiscountAmt`|String|10|N/A|Discount given to cardholder.|
|`convFee`|String |10|C|Convenience Fee including decimal (E.g: “5.00” for $5 fee) - To be sent if fee is charged.|
|`cgst`|String |10|C|Central GST Including decimal (E.g: “10.00” for $10 cgst) - To be sent if CGST is included in the total amount (Applicable only for India).|
|`igst`|String |10|C|Integrated GST Including decimal (E.g: “10.00” for $10 igst) - To be sent if IGST is included in the total amount (Applicable only for India).|
|`sgst`|String |10|C|State GST Including decimal (E.g: “10.00” for $10 sgst) - To be sent if SGST is included in the total amount (Applicable only for India).|
|`gst`|String |10|C|GST - applicable except India|
|`totalAmount`|String |12|M|Total Amount (auth, fee, gsts) including decimal (E.g: “57.00” for $57 sale). Send 0.00 for inquiry transaction and Get Token.|
|`tranCurrency`|String |3|M|Transaction Currency Code (3-digit numeric value)|
|**Additional Params**|||||
|`callbackURL`|String|100|O|Response URL, placeholder for notification API call feature.|
|`param_lit`|Array||O|Biller can pass any additional details if required in array format as below,<br>"paramList": [<br> {<br>"param_lit": "param1 key",<br>"param"": "23"<br>},<br>{<br>"param_lit": "param 2 key",<br>"param": "54"<br>}<br>]|"
|`udf1`|String |100|O|User Defined Field|
|`udf2`|String|100|O|User Defined Field|

### Successful Response Payload

```json
{
   "merchantDetails":{
      "ain":"2100000",
      "billerId":"14",
      "merchantId":"42298519014704",
      "terminalId":"19014704",
      "mrchCountryCode":"036",
      "siteId":"",
      "workStationId":""
   },
   "transactionStatus":{
      "respCode":"200",
      "response":"",
      "respMsg":"SUCCESS"
   },
   "transactionDetails":{
      "functionCode":"05",
      "customerRefNumber":"",
      "merchantRefNumber":"",
      "transactionId":"",
      "reqDate":"17112022",
      "reqTime":"154900",
      "originalTranDate":"14022022",
      "originalTranTime":"133955",
      "authCode":"",
      "rrn":"",
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
      "isInternalCall":null
   },
   "amounts":{
      "authAmount":"100.00",
      "mrchDiscountAmt":"",
      "convFee":"",
      "cgst":"",
      "igst":"",
      "sgst":"",
      "gst":"",
      "totalAmount":"3",
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
    "response": {
        "merchantDetails": {
            "ain": "",
            "billerId": "",
            "merchantId": "",
            "terminalId": "",
            "mrchCountryCode": "",
            "siteId": "",
            "workStationId": ""
        },
        "transactionStatus": {
            "respCode": "300",
            "response": "Failure:",
            "respMsg": "[Field Name: merchantId is mandatory, Field Name: terminalId is mandatory, Field Name: billerId is mandatory]"
        },
        "transactionDetails": {
            "functionCode": "",
            "customerRefNumber": "",
            "merchantRefNumber": "",
            "transactionId": "",
            "reqDate": "",
            "reqTime": "",
            "originalTranDate": "",
            "originalTranTime": "",
            "authCode": "",
            "rrn": "",
            "tokenId": "",
            "invoiceNumber": "",
            "batchNo": "",
            "amexSeNumber": "",
            "posEntryMode": "",
            "walletType": "",
            "walletId": "",
            "schemeId": "",
            "cardLastNumber": "",
            "primaryId": "",
            "customerName": "",
            "offlineFlag": "",
            "aTC": "",
            "tVR": "",
            "appLabel": "",
            "aID": "",
            "panSeqNo": "",
            "schemeTranInfo": "",
            "isInternalCall": null,
            "authenticationMethod": null
        },
        "amounts": {
            "authAmount": "",
            "mrchDiscountAmt": "",
            "convFee": "",
            "cgst": "",
            "igst": "",
            "sgst": "",
            "gst": "",{
    "response": {
        "merchantDetails": {
            "ain": "",
            "billerId": "",
            "merchantId": "",
            "terminalId": "",
            "mrchCountryCode": "",
            "siteId": "",
            "workStationId": ""
        },
        "transactionStatus": {
            "respCode": "300",
            "response": "Failure:",
            "respMsg": "[Field Name: terminalId should be not exceed length :8]"
        },
        "transactionDetails": {
            "functionCode": "",
            "customerRefNumber": "",
            "merchantRefNumber": "",
            "transactionId": "",
            "reqDate": "",
            "reqTime": "",
            "originalTranDate": "",
            "originalTranTime": "",
            "authCode": "",
            "rrn": "",
            "tokenId": "",
            "invoiceNumber": "",
            "batchNo": "",
            "amexSeNumber": "",
            "posEntryMode": "",
            "walletType": "",
            "walletId": "",
            "schemeId": "",
            "cardLastNumber": "",
            "primaryId": "",
            "customerName": "",
            "offlineFlag": "",
            "aTC": "",
            "tVR": "",
            "appLabel": "",
            "aID": "",
            "panSeqNo": "",
            "schemeTranInfo": "",
            "isInternalCall": null,
            "authenticationMethod": null
        },
        "amounts": {
            "authAmount": "",
            "mrchDiscountAmt": "",
            "convFee": "",
            "cgst": "",
            "igst": "",
            "sgst": "",
            "gst": "",
            "totalAmount": "",
            "tranCurrency": "",
            "tip": ""
        },
        "dccInfo": {
            "dccIndicator": "",
            "dccCurrency": "",
            "dccAmount": "",
            "dccExchangeRate": ""
        }
    }
}

            "totalAmount": "",
            "tranCurrency": "",
            "tip": ""
        },
        "dccInfo": {
            "dccIndicator": "",
            "dccCurrency": "",
            "dccAmount": "",
            "dccExchangeRate": ""
        }
    }
}

{
    "response": {
        "merchantDetails": {
            "ain": "",
            "billerId": "",
            "merchantId": "",
            "terminalId": "",
            "mrchCountryCode": "",
            "siteId": "",
            "workStationId": ""
        },
        "transactionStatus": {
            "respCode": "300",
            "response": "Failure:",
            "respMsg": "[Field Name: terminalId should be not exceed length :8]"
        },
        "transactionDetails": {
            "functionCode": "",
            "customerRefNumber": "",
            "merchantRefNumber": "",
            "transactionId": "",
            "reqDate": "",
            "reqTime": "",
            "originalTranDate": "",
            "originalTranTime": "",
            "authCode": "",
            "rrn": "",
            "tokenId": "",
            "invoiceNumber": "",
            "batchNo": "",
            "amexSeNumber": "",
            "posEntryMode": "",
            "walletType": "",
            "walletId": "",
            "schemeId": "",
            "cardLastNumber": "",
            "primaryId": "",
            "customerName": "",
            "offlineFlag": "",
            "aTC": "",
            "tVR": "",
            "appLabel": "",
            "aID": "",
            "panSeqNo": "",
            "schemeTranInfo": "",
            "isInternalCall": null,
            "authenticationMethod": null
        },
        "amounts": {
            "authAmount": "",
            "mrchDiscountAmt": "",
            "convFee": "",
            "cgst": "",
            "igst": "",
            "sgst": "",
            "gst": "",
            "totalAmount": "",
            "tranCurrency": "",
            "tip": ""
        },
        "dccInfo": {
            "dccIndicator": "",
            "dccCurrency": "",
            "dccAmount": "",
            "dccExchangeRate": ""
        }
    }
}


```

### Response
| Variable | Type | Length | Mandatory / Optional /Conditional <br>(M / O / C) | Description / Values |
| -------- | ------- | -- | ----------------------------------------------- | ------------------ |
|**Merchant Information**|||||
|`billerId`|String |3|M|Same value as request table.<br>Biller ID provided by Fiserv.|
|`ain`|String|7|M|Same value as request table.<br>Acquirer institution number provided by Fiserv.|
|`siteId`|String|15|C|Same value as request table.<br>Merchant's MID reference (not required if MID is sent)|
|`workStationId`|String|8|C|Same value as request table.<br>Merchant's TID reference (not required if TID is sent)|
|`merchantId`|String |15|C|Same value as request table.<br>Merchant ID assigned|
|`terminalId`|String|8|C|Same value as request table.<br>Terminal ID where transactions to be pushed.|
|`mrchCountryCode`|String|3|M|Same value as request table.<br>Merchant Country Code (3-digit numeric value)|
|**Transaction Status**|||||
|`respCode`|String|5|M|200 / 300 / Actual Response from switch|
|`response`|String|20|M|Success / Failure|
|`respMsg`|String|20|O|Error Message|
|**Transaction Information**|||||
|`functionCode`|String|2|M|Same as request except Inquiry transactions. <br>For Inquiry transactions original transaction function code will be returned.|
|`merchantRefNumber`|String|50|M|Unique number for Sale, Pre-authorization and Get Token.|
|`customerRefNumber`|String|20|O|Consumer Number|
|`transactionId`|String|20|M|Unique ID for the transactions.|
|`reqDate`|DDMMYYYY||M|Same value as request table. Transaction initiated date|
|`reqTime`|HHMMSS||M|Same value as request table. Transaction initiated time|
|`originalTranDate`|DDMMYYYY||M|Same value as request table. Original transaction date|
|`originalTranTime`|HHMMSS||M|Same value as request table. Original transaction time|
|`authCode`|String|6|O|Bill Amount including decimal (E.g: “50.00” for $50 sale).<br>Send 0.00 for inquiry transactions and Get Token.|
|`rrn`|String|20|O|Received from the Issuer Host. Return the authorization code received in response from Fiserv switch (Base 24) for refund.|
|`invoiceNumber`|String|20|O|Terminal Invoice Number|
|`batchNo`|String|3|O|Terminal Batch Number|
|`amexSeNumber`|String|10|C|Applicable for AMEX transactions.|
|`posEntryMode`|String|10|M|MANUAL / SWIPE / INSERT / CLSS / FALLBACK / CLSS_MSR / QRC|
|`walletType`|String|10|O|Wallet type will be passed for QR transactions.|
|`walletId`|String|5|O|Wallet ID will be passed for local payment method(LPM) transactions.|
|`schemeId`|String|10|O|Scheme Name will be passed for the Card transactions.|
|`cardLastNumber`|String|4|O|Last 4-digits of the Card used in the  transactions.|
|`primaryId`|String |20|O|Reference number of the QR request.|
|`customerName`|String |20|O|Cardholder Name|
|`offlineFlag`|String|1|O|Offline flag|
|`tokenId`|String|30|O|Token ID returned during initial authorization / get token.|
|`aTC`|String|4|O|Application Transaction Counter (EMV Tag 9F36)|
|`tVR`|String |10|O|Terminal Verification Result (EMV Tag - 95)|
|`appLabel`|String|32|O|Application Label (EMV tag - 50)|
|`aID`|String|14|O|Application Identifier (EMV tag - 84)|
|`panSeqNo`|String|2|O|PAN Sequence No (EMV Tag - 5F34)|
|`schemeTranInfo`|String|32|O|Refer Appendix A for the tag layout.|
|**Amounts**|||||
|`authAmount`|String|12|M|Total Amount (auth, fee, gsts) including decimal<br> (E.g: “57.00” for $57 sale). Send 0.00 for inquiry transactions and Get Token.|
|`mrchDiscountAmt`|String |10|O|Discount given to cardholder.|
|`convFee`|String |10|O|Convenience Fee including decimal<br>(E.g: “5.00” for $5 fee) - To be sent if fee is charged.|
|`cgst`|String |10|O|Same value as request table. Central GST Including decimal (E.g: “10.00” for $10 cgst)<br> - To be sent if CGST is included in the total amount (Applicable only for India).|
|`igst`|String |10|O|Same value as request table. Integrated GST Including decimal (E.g: “10.00” for $10 igst)<br> - To be sent if IGST is included in the total amount (Applicable only for India).|
|`sgst`|String |10|O|Same value as request table. State GST Including decimal (E.g: “10.00” for $10 sgst)<br>- To be sent if SGST is included in the total amount (Applicable only for India).|
|`gst`|String|10|O|Same value as request table. Same value as request table <br>GST - applicable except India|
|`tipAmount`|String |12|O|Tip amount if applicable|
|`totalAmount`|String|12|M|Total amount (auth, fee, gsts) including decimal<br>(E.g: “57.00” for $57 sale). Send 0.00 for inquiry transactions and Get Token.|
|`tranCurrency`|String|3|M|Same as Request|
|**DCC**|||||
|`dccIndicator`|String|1|M|0 – Non-DCC <br> 1 – DCC|
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



