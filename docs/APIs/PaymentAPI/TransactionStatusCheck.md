# Transaction Inquiry

This API is used to send transaction inquiry request. Merchants will be required to add session 
token received during login API call in the header of this API.


## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/cloudpoidp/PosPush/nonOpiProcessAmount`

## Payload Example

### Request Payload

```json
{
"ain": "4700000",
"functionCode": "11",
"merchantId": "470000095241203",
"terminalId": "33533344",
"customerRefNumber": "",
"merchantRefNumber": "GURU513",
"billerId": "124",
"convFee": "",
"cgst": "",
"igst": "",
"sgst": "",
"totalAmount": "200",
"authCode": "",
"tranCurrency": "840",
"reqDate": "16022022",
"reqTime": "172200",
"authAmount": "12345678900",
"tranDate": "27022022",
"tranTime": " ",
"invoiceNumber": "",
"cardLastNumber": "",
"callbackURL": "",
"mrchCountryCode": "356",
"tranType": "",
"rrn": "",
"emiRefNumber": "",
"emiTenure": "",
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
| Variable | Type | Length |  Mandatory / Optional/ Conditional <br>(M / O / C) | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
| `merchantId` | *string* | 15 | M | Merchant ID assigned |
| `ain` | *string* | 07 | M | Acquirer institution number |
| `functionCode` | *string* | 02 | M | E.g. |
|  |  |  |  | 00 = Sale  - Digital and Card |
|  |  |  |  | 01 = Sale - Card|
|  |  |  |  | 02 = Pre-Authorization |
|  |  |  |  | 03 = Pre-Authorization Completion |
|  |  |  |  | 04 = Refund|
|  |  |  |  | 12 = Settlement |
|  |  |  |  | 11 = Transaction Status Check (Inquiry) |
|  |  |  |  | 05 = Void |
|  |  |  |  | 04 = Refund |
| `terminalId` | *string* | 07 | M | Terminal ID |
| `billerId` | *string* | 03 | M | Biller ID provided by Fiserv. |
| `merchantRefNumber` | *string* | 14 | M | Unique number for each transaction. Inquiry transaction should have same MRN of original transaction. For BOCM pass the value as (50 bytes). |
| `customerRefNumber` | *string* | 20 | O | Customer's Reference Number |
| `authAmount` | *string* | 19 | M | Bill amount including decimal (E.g. 50.00 for $50 sale). Send 0.00 for inquiry transaction. |
| `convFee` | *string* | 10 | C| Convenience Fee including decimal (E.g. 5.00 for $5 fee). To be sent if fee is charged. |
| `CGST` | *string* | 10 | C | Central GST Including decimal (E.g. 10.00 for $10 CGST). If CGST is included in the total amount. |
| `IGST` | *string* | 10 | C | Integrated GST Including decimal (E.g. 10.00 for $10 IGST). If IGST is included in the total amount. |
| `SGST` | *string* | 10 | C | State GST Including decimal (E.g. 100.00 for $10 SGST). If SGST is included in the total amount. |
| `totalAmount` | *string* | 19 | M | Total Amount (auth, fee, gsts) including decimal (E.g. 57.00 for $57 sale). |
| `tranCurrency` | *string* | 03 | M | Transaction Currency Code (3-digit numeric value) |
| `reqDate` | *Date* | DDMMYYYY | M | Transaction initiated date |
| `reqTime` | *Timestamp* | HHMMSS | M | Transaction initiated time |
| `tranDate` | *Date* | DDMMYYYY | C  |Original transaction date |
| `tranTime` | *Timestamp* | HHMMSS | C | Transaction Time |
| `cardLastNumber` | *string* | 04 | C | Last 4 digits of Card Number. To be included for Pre-Authorization completion transaction. |
| `cardBin` | *string* | 06 | C | First 6 digits of the Card, used in the original (sale) transaction. To be included for Refund transaction. |
| `callbackURL` | *string* | 100 | O | Response URL, placeholder for notification API call feature. |
| `mrchCountryCode` | *string* | 03 | M | Merchant Country Code (3-digit numeric value). |
| `tranType` | *string* | 50 | O | Transaction Description. |
| `rrn` | *string* | 20 | C  | The same value received in original transaction response needs to be submitted across. |
| `emiTenure` | *string* | 02 | C | Installment / EMI duration. If Installment / EMI transactions are included. |
| `paramList` | *array* | NA | O | Biller can pass any additional details if required in array format "paramList": [{"param_lit": "param1 key","param": "23"}]. |
| `udf1` | *string* | 100 | O | User Defined Field |
| `udf2` | *string* | 100 | O | User Defined Field |

### Successful Response Payload

```json
{
    "functionCode": "11",
    "source": null,
    "billingAmount": null,
    "invoiceNumber": "18",
    "customerMobile": null,
    "billingCurrency": "INR",
    "transactionId": "202202274190781",
    "customerName": null,
    "respCode": "200",
    "response": "SUCCESS",
    "cardType": null,
    "rrn": "000000000045",
    "authCode": "180024",
    "merchantId": "470000095241203",
    "terminalId": "33533344",
    "respMsg": "Transaction Success",
    "amexSeNumber": "",
    "emiTenure": "",
    "emiInterestRate": "",
    "emiProcessingFee": "0",
    "emiDiscAmt": "0",
    "dccIndicator": "0",
    "dccExchangeRate": "",
    "offlineFlag": "N",
    "cardLastNumber": "0010",
    "totalAmount": "25.00",
    "merchantRefNumber": "GURU513",
    "customerRefNumber": "7777777",
    "emiFlag": "0",
    "cardNumber": "476173****0010",
    "expDate": "2212",
    "posEntryMode": "INSERT",
    "walletType": "",
    "primaryId": "",
    "custId": "",
    "emiPerMonth": "0",
    "tranDate": "27022022",
    "tranTime": " ",
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
| Variable | Type | Length |   Mandatory / Optional/ Conditional <br> (M / O / C)  | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
| `merchantId` | *string* | 20 | M | Merchant ID. |
| `transactionId` | *string* | 20 | M | Unique ID (Biller tran details table). |
| `functionCode` | *string* | 02 | M | Same as request. |
| `invoiceNumber` | *string* | 20 | O | Terminal Invoice Number. |
| `cardLastNumber` | *string* | 4 | C | Last 4 Digits of Card Number. To be included for Pre-Authorization completion transaction. |
| `totalAmount` | *string* | 19 | M | Total Amount (auth, fee, gsts, tip) including decimal (E.g. 57.00 for $57 sale). |
| `tipAmount` | *string* | 10 | C | Last 4 Digits of Card Number. To be included for PreAuth completion transaction. |
| `merchantRefNumber` | *string* | 14 | M | Merchant Reference Number. |
| `customerRefNumber` | *string* | 20 | 0 | Customer's Reference Number. |
| `respCode` | *string* | 05 | M | 200 / 300 / actual switch response. |
| `response` | *string* | 20 | M | SUCCESS / FAILURE. |
| `respMsg` | *string* | 20 | O | Error Message. |
| `authCode` | *string* | 06 | C  | Received from Issuer Host. |
| `rrn` | *string* | 20 | C | Received from Issuer Host. |
| `cardBin` | *string* | 06 | O | First 6 digits of the Card, used in the original (sale) transaction. To be included for Refund transaction. |
| `dccIndicator` | *string* | 01 | M | 0 = Non DCC transaction, 1 = DCC transaction. |
| `billingCurrency` | *string* | 03 | C | DCC currency code. |
| `billingAmount` | *string* | 19 | C | DCC amount. |
| `dccExchangeRate` | *string* | 20 | M | Currency exchange rate. |
| `amexSeNumber` | *string* | 10 | C | Applicable for AMEX transaction. |
| `emiFlag` | *string* | 01 | M | 0 = Non-EMI (Non-Installment) 1 = EMI (Installment). |
| `emiTenure` | *string* | 02 | C | Installment / EMI duration. If Installment / EMI transactions are included. |
| `emiInterestRate` | *string* | 10 | C | Applicable for Installment / EMI transaction. |
| `emiProcessingFee` | *string* | 10 | C | Applicable for Installment / EMI transaction. |
| `emiDiscAmt` | *string* | 10 | C | Applicable for Installment / EMI transaction. |
| `emiPerMonth` | *string* | 10 | C | Applicable for Installment / EMI transaction. |
| `cardNumber` | *string* | 19 | O | Card Number. |
| `expDate` | *string* | 4 | O | Expiry date of the card. |
| `posEntryMode` | *string* | 10 | M | MANUAL / SWIPE / INSERT / CLSS / FALLBACK / CLSS_MSR / QRC. |
| `walletType` | *string* | 10 | C  | Type of wallet used such as UPI, Amazon Pay etc. |
| `primaryId` | *string* | 20 | C | Reference Number of the QR Request. |
| `custId` | *string* | 35 | O | Customer’s Identifier, Vehicle Number for FASTag VPA for UPI QR. |
| `walletId` | *string* | 05 | O | Unique wallet ID associated with each wallet. |
| `Source` | *string* | 20 | O | Transaction Initiated source. |
| `customerMobile` | *string* | 20 | O | Customer's Mobile Number. |
| `customerName` | *string* | 20 | O | Cardholder's Name. |
| `cardType` | *string* | 5 | O | Card Type. |
| `offlineFlag` | *string* | 01 | O | Offline Flag. |
| `tranDate` | *date* | DDMMYYYY | O | Transaction Date. |
| `tranTime` | *string* | HHMMSS | O | Transaction Time. |
| `settlementDetails` | *string* | 2000 | O | Set settlement Details. |


The table below provides the list of error codes and description for this application.

| Error Code |  Description / Values | Comments |
| --------  | ---------------------- |----------|
| `200`| Success | Request is successfully processed. Merchant should go ahead with receipt generation. |
| `300`| Request Failure | Redirection error. Merchant should validate and retry with new request. |
| `401`| Token not valid or Token had not passed at all | User authentication error. Merchant should key a valid token during the transaction. |
 | `404`| Not Found | Server cannot find the requested resource. Contact Customer Support / Business Manager. |
| `502`| Request Timed Out | Server received an invalid gateway response while working as a gateway to get the response needed to handle the request. Merchant should retry with new request. |

