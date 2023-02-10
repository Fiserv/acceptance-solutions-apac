# Installment / EMI Sale Transaction

This API is used to send Installment / EMI Sale transaction request. Merchants will be required to add session 
token received during login API call in the header of this API,


## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/cloudpoidp/PosPush/nonOpiProcessAmount`

## Payload Example

### Request Payload

```json
{
  "ain": "4700000",
  "functionCode": "08",
  "merchantId": "470000095241203",
  "terminalId": "33533344",
  "customerRefNumber": "1051104367",
  "merchantRefNumber": "Guru526",
  "billerId": "809",
  "convFee": "50",
  "cgst": "76",
  "igst": "84",
  "sgst": "72",
  "totalAmount": "250",
  "tranCurrency": "849",
  "reqDate": "28022022",
  "reqTime": "095300",
  "authAmount": "12345678",
  "tranDate": "",
  "tranTime": "",
  "invoiceNumber": "",
  "cardLastNumber": "",
  "callbackURL": "",
  "mrchCountryCode": "356",
  "tranType": "",
  "rrn": "",
  "emiTenure": "3",
  "udf1": "",
  "udf2": "",
  "paramList": [
    {
      "param_lit": "param1 key",
      "param": ""
    }, 
    {
      "param_lit": "param 2 key",
      "param": ""
    }
  ]
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
| `merchantId` | *string* | 15 | M | Merchant ID assigned |
| `ain` | *string* | 07 | M | Acquirer institution number |
| `functionCode` | *string* | 02 | M | E.g. |
|  |  |  |  | 00 - Sale  - Digital and Card |
|  |  |  |  | 01 - Sale - Card|
|  |  |  |  | 02 - Pre-authorization|
|  |  |  |  | 03 - Pre-authorization Completion |
|  |  |  |  | 04 - Refund |
|  |  |  |  | 05 - Void |
|  |  |  |  | 06 - Top Up (Incremental Pre-authorization) |
|  |  |  |  | 11 - Transaction Status Check (Inquiry) |
|  |  |  |  | 12 - Settlement|
| `terminalId` | *string* | 07 | M | Terminal ID |
| `billerId` | *string* | 03 | M | Biller ID provided by Fiserv. |
| `merchantRefNumber` | *string* | 14 | M | Unique number for Sale, Pre-authorization and Get Token. |
| `customerRefNumber` | *string* | 20 | O | Customer's Reference Number |
| `authAmount` | *string* | 19 | M | Bill Amount including decimal (E.g: “50.00” for $50 sale).<br>Send 0.00 for inquiry transactions and Get Token. |
| `convFee` | *string* | 10 | C | Convenience Fee including decimal.<br>(E.g: “5.00” for $5 fee) - To be sent if fee is charged. |
| `CGST` | *string* | 10 | C | Central GST Including decimal (E.g: “10.00” for $10 cgst)<br>- To be sent if CGST is included in the total amount (Applicable only for India). |
| `IGST` | *string* | 10 | C | Integrated GST Including decimal (E.g: “10.00” for $10 igst)<br> - To be sent if IGST is included in the total amount (Applicable only for India). |
| `SGST` | *string* | 10 | C | State GST Including decimal (E.g: “10.00” for $10 sgst)<br>  - To be sent if SGST is included in the total amount (Applicable only for India). |
| `totalAmount` | *string* | 19 | M | Total Amount (auth, fee, gsts) including decimal (E.g. 57.00 for $57 sale).Send 0.00 for inquiry transaction and Get Token. |
| `tranCurrency` | *string* | 03 | M | Transaction Currency Code (3-digit numeric value) |
| `reqDate` | *Date* | DDMMYYYY | M | Transaction initiated date |
| `reqTime` | *Timestamp* | HHMMSS | M | Transaction initiated time |
| `tranDate` | *Date* | DDMMYYYY | C  |Original transaction date |
| `tranTime` | *Timestamp* | HHMMSS | C | Transaction Time |
| `cardLastNumber` | *string* | 04 | C | Last 4 digits of Card Number. To be included for Pre-authorization completion transactions.  |
| `cardBin` | *string* | 06 | C | First 6 digits of the Card, used in the original (sale) transaction. To be included for Refund transactions. |
| `callbackURL` | *string* | 100 | O | Response URL, placeholder for notification API call feature. |
| `mrchCountryCode` | *string* | 03 | M | Merchant Country Code (3-digit numeric value) |
| `tranType` | *string* | 50 | O | Transaction Description |
| `rrn` | *string* | 20 | C | The same value received in the original transaction response needs to be submitted across. |
| `emiTenure` | *string* | 02 | C | Installment / EMI duration. If Installment / EMI transactions are included. |
| `paramList` | *array* | NA | O | Biller can pass any additional details if required in array format "paramList": [{"param_lit": "param1 key","param": "23"}]. |
| `udf1` | *string* | 100 | O | User Defined Field |
| `udf2` | *string* | 100 | O | User Defined Field |

### Successful Response Payload

```json
{
    "functionCode": "08",
    "source": null,
    "billingAmount": null,
    "invoiceNumber": "22",
    "customerMobile": null,
    "billingCurrency": "INR",
    "transactionId": "202202280728139",
    "customerName": null,
    "respCode": "200",
    "response": "SUCCESS",
    "cardType": null,
    "rrn": "000000000075",
    "authCode": "006264",
    "merchantId": "470000095241203",
    "terminalId": "33533344",
    "respMsg": "Transaction Success",
    "amexSeNumber": "",
    "emiTenure": "03",
    "emiInterestRate": "13.00",
    "emiProcessingFee": "10",
    "emiDiscAmt": "0",
    "dccIndicator": "0",
    "dccExchangeRate": "",
    "offlineFlag": "N",
    "cardLastNumber": "0042",
    "totalAmount": "250.00",
    "merchantRefNumber": "Guru526",
    "customerRefNumber": "1051104367",
    "emiFlag": "1",
    "cardNumber": "541333****0042",
    "expDate": "4912",
    "posEntryMode": "CLSS",
    "walletType": "",
    "primaryId": "",
    "custId": "",
    "emiPerMonth": "85.14",
    "tranDate": "28022022",
    "tranTime": "",
    "cardBin": null,
    "tipAmount": null,
    "settlementDetails": "TILL",
    "walletId": ""
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
|**Merchant Information**|||||
|`billerId`|String |3|M|Same value as request table.<br>Biller ID provided by Fiserv.|
|`ain`|String|7|M|Same value as request table.<br>Acquirer institution number provided by Fiserv.|
|`siteId`|String|15|C|Same value as request table.<br>Merchant's MID reference (not required if MID is sent)|
|`workStationId`|String|8|C|Same value as request table.<br>Merchant's TID reference (not required if TID is sent)|
|`merchantId`|String |15|C|Same value as request table.<br> Merchant ID assigned|
|`terminalId`|String|8|C|Same value as request table.<br> Terminal ID where transactions to be pushed.|
|`mrchCountryCode`|String|3|M|Same value as request table.<br>Merchant Country Code (3-digit numeric value)|
|**Transaction Status**|||||
|`respCode`|String|5|M|200 / 300 / actual switch response|
|`response`|String|20|M|SUCCESS / FAILURE|
|`respMsg`|String|20|O|Error Message|
|**Transaction Information**|||||
|`functionCode`|String |2|M|02 - Pre-authorization | 
 | | |  |               |03 - Pre-authorization Completion|
 | | |  |               |06 - Top Up (Incremental Pre-authorization)|
|`merchantRefNumber`|String|50|M|Unique number for Sale, Pre-authorization and Get Token.|
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
|`amexSeNumber`|String|10|C|Applicable for AMEX transactions.|
|`posEntryMode`|String|10|M|MANUAL / SWIPE / INSERT / CLSS / FALLBACK / CLSS_MSR / QRC|
|`walletType`|String|10|O|Wallet Type will be passed for QR transactions.|
|`walletId`|String|5|O|Wallet ID will be passed for LPM transactions.|
|`schemeId`|String|10|O|Scheme Name will be passed for Card transactions.|
|`cardLastNumber`|String|4|O|Card Last 4 digits for Carded transactions.|
|`primaryId`|String |20|O|Reference Number of the QR Request.|
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
|`authAmount`|String|12|M|Same value as request table.<br>Bill Amount including decimal (E.g: “50.00” for $50 sale).<br>Send 0.00 for inquiry transactions and Get Token.|
|`mrchDiscountAmt`|String |10|O|Same value as request table. Discount given to cardholder|
|`convFee`|String |10|C|Same value as request table. Convenience Fee including decimal<br> (E.g: “5.00” for $5 fee) - To be sent if fee is charged.|
|`cgst`|String |10|C|Same value as request table. Central GST Including decimal (E.g: “10.00” for $10 cgst)<br> - To be sent if CGST is included in the total amount (Applicable only for India).|
|`igst`|String |10|C|Same value as request table. Integrated GST Including decimal (E.g: “10.00” for $10 igst)<br> - To be sent if IGST is included in the total amount (Applicable only for India).|
|`sgst`|String |10|C|Same value as request table. State GST Including decimal (E.g: “10.00” for $10 sgst)<br> - To be sent if SGST is included in the total amount (Applicable only for India).|
|`gst`|String|10|C|Same as Request|
|`tipAmount`|String |12|O|Tip Amount If applicable|
|`totalAmount`|String|12|M|Total Amount (auth, fee, gsts) including decimal<br> (E.g: “57.00” for $57 sale). Send 0.00 for inquiry transactions and Get Token.|
|`tranCurrency`|String|3|M|Same value as request table. Transaction Currency Code (3-digit numeric value)|
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
| `401`| Token not valid or Token had not passed at all | User authentication error. Merchant should key a valid token during the transactions. |
 | `404`| Not Found | Server cannot find the requested resource. Contact Customer Support / Business Manager. |
| `502`| Request Timed Out | Server received an invalid gateway response Merchant should retry with new request. |
