# Process Amount

This API is used to send refund transaction request. Merchants needs to add session 
token received during login api call in the header of this API and encrypt the payload using the 
encryption key provided before sending it to gateway. 


## Endpoint

POST `/boardinggateway/cloudpoi/PosPush/nonOpiProcessAmount`

## Payload Example

### Request Payload

```json
{
"ain": "4700000",
"functionCode": "01",
"merchantId": "470000050790214",
"terminalId": "62850698",
"merchantRefNumber": "REVAMRNSALE140208",
"customerRefNumber": "REVASALE140208",
"billerId": "011",
"convFee": "1.00",
"cardBin": "",
"cgst": "",
"igst": "",
"sgst": "0.50",
"totalAmount": "3.50",
"tranCurrency": "356",
"reqDate": "14022022",
"reqTime": "133955",
"authAmount": "2.00",
"tranDate": "",
"tranTime": "",
"invoiceNumber": "",
"authCode":"",
"cardLastNumber": "",
"callbackURL": "",
"mrchCountryCode": "356",
"tranType": "sale",
"rrn": "",
"emiTenure": "",
"udf1": "23133",
"udf2": "21313"
}
```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=post&path=/boardinggateway/cloudpoi/PosPush/nonOpiProcessAmount).

The below table identifies the required query parameters in the request message.

The below table identifies the required json properties in the request message.
### Request
| Variable | Type | Length |  Mandatory / Optional/ Conditional (M / O / C) | Description / Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `merchantId` | *string* | 15 | M | Merchant ID assigned |
| `ain` | *string* | 07 | M | Acquirer institution number |
| `functionCode` | *string* | 02 | M | Examples: |
|  |  |  |  | 00 = Sale  - Digital and Card|
|  |  |  |  | 01 = Sale - Card|
|  |  |  |  | 02 = Preauth|
|  |  |  |  | 03 = Preauth Completion|
|  |  |  |  | 04 = Refund|
|  |  |  |  | 12 = Settlement|
|  |  |  |  | 11 = Transaction Status Check (Inquiry)
|  |  |  |  | 05 = Void|
|  |  |  |  | 04 = Refund|
| `terminalId` | *string* | 07 | M | Terminal ID |
| `billerId` | *string* | 03 | M | Biller Id provided by Fiserv |
| `merchantRefNumber` | *string* | 14 | M | Unique number for each transaction. Inquiry transaction should have same MRN of original txn |
|  |  | (BOCM – 50) |  | |
| `customerRefNumber` | *string* | 20 | O | Consumer Number |
| `authAmount` | *string* | 19 | M | Bill Amount including decimal (E.g. 50.00 for $50 sale). Send 0.00 for inquiry txn. |
| `convFee` | *string* | 10 | C | Convenience Fee including decimal (E.g. 5.00 for $5 fee) |
|  | |  | (To be sent if fee is charged) |  |
| `cgst` | *string* | 10 | C  | Central GST Including decimal (E.g. 10.00 for $10 cgst) |
|  | |  | (if CGST is included in the total amount) |  |
| `igst` | *string* | 10 | C  | State GST Including decimal (E.g. 10.00 for $10 igst) |
|  | | | | (if IGST is included in the total amount) |  |
| `sgst` | *string* | 10 | C  | State GST Including decimal (E.g. 100.00 for $10 sgst) |
|  | |  | | (if SGST is included in the total amount) |  |
| `totalAmount` | *string* | 19 | M | Total Amount (auth, fee, gsts) including decimal ((E.g. 57.00 for $57 sale). |
| `tranCurrency` | *string* | 03 | M | Transaction Currency Code (3-digit numeric value) |
| `reqDate` | *Date* | DDMMYYYY | M | Transaction initiated date |
| `reqTime` | *Timestamp* | HHMMSS | M | Transaction initiated time |
| `tranDate` | *Date* | DDMMYYYY | C  |Original transaction date |
| `tranTime` | *Timestamp* | HHMMSS | C | Original transaction time |
| `cardLastNumber` | *string* | 04 | C  | Last 4 digits ....  |
 | | | | (if included pre auth Completion) |  |
| `cardBin` | *string* | 06 | C  | First 6 digits .... of the Card, used in the original (sale) transaction |
 | | | | (if included refund) |   |
| `callbackURL` | *string* | 100 | O | Response URL, place holder for notification API call feature |
| `mrchCountryCode` | *string* | 03 | M | Merchant Country Code (3-digit numeric value) |
| `tranType` | *string* | 50 | O | Transaction Description |
| `rrn` | *string* | 20 | C | Must pass the same value received in original transaction response |
 | | | | (It is applicable for Refund and optional for Inquiry txn) |  |
| `emiTenure` | *string* | 02 | C  | EMI duration |
 | | | | (if included EMI transactions) |  |
| `paramList` | *array* | NA | O | Biller can pass any additional details if required in arrary format "paramList": [{"param_lit": "param1 key","param": "23"}] |
| `udf1` | *string* | 100 | O | User Defined Field |
| `udf2` | *string* | 100 | O | User Defined Field |

### Successful Response Payload

```json
{
"functionCode": "01",
"source": null,
"billingAmount": null,
"invoiceNumber": "9",
"customerMobile": null,
"billingCurrency": "INR",
"transactionId": "202202144565809",
"customerName": null,
"respCode": "200",
"response": "SUCCESS",
"cardType": null,
"rrn": "204518008073",
"authCode": "181414",
"merchantId": "470000050790214",
"terminalId": "62850698",
"respMsg": "Transaction Success",
"amexSeNumber": "",
"emiTenure": "",
"emiInterestRate": "",
"emiProcessingFee": "",
"emiDiscAmt": "",
"dccIndicator": "0",
"dccExchangeRate": "",
"offlineFlag": "N",
"cardLastNumber": "0157",
"totalAmount": "3.55",
"merchantRefNumber": "REVAMRNSALE140208",
"customerRefNumber": "REVASALE140208",
"emiFlag": "0",
"cardNumber": "6083 ****0157",
"expDate": "2612",
"posEntryMode": "CLSS",
"walletType": "",
"primaryId": "",
"custId": "",
"emiPerMonth": "",
"tranDate": "14022022",
"tranTime": "",
"cardBin": null,
"tipAmount": "0.05",
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
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `merchantId` | *string* | 20 | M | Merchant ID |
| `transactionId` | *string* | 20 | M | Unique Id (Biller tran details table) |
| `functionCode` | *string* | 02 | M | Same as request |
| `invoiceNumber` | *string* | 20 | O | Terminal Invoice Number |
| `cardLastNumber` | *string* | 4 | C | Last 4 Digits of Card Number |
|  | | |  (if required for Pre-auth) | |
| `totalAmount` | *string* | 19 | M | Total Amount (auth, fee, gsts, tip) including decimal (E.g. 57.00 for $57 sale) |
| `tipAmount` | *string* | 10 | C  | Tip Amount including decimal (E.g. 7.00 for $7 tip)|
|  | | |  (if Tip is included) | |
| `merchantRefNumber` | *string* | 14 | M | Merchant Reference Number |
| `customerRefNumber` | *string* | 20 | 0 | Custmer Reference Number |
| `respCode` | *string* | 05 | M | 200 / 300 / actual switch response |
| `response` | *string* | 20 | M | SUCCESS / FAILURE |
| `respMsg` | *string* | 20 | O | Error Message |
| `authCode` | *string* | 06 | C  | Received from Issuer Host |
| `rrn` | *string* | 20 | C | Received from Issuer Host |
| `cardBin` | *string* | 06 | O | Card Bin |
| `dccIndicator` | *string* | 01 | M | 0 – Non DCC, 1 – DCC  |
| `billingCurrency` | *string* | 03 | C | DCC currency code |
| `billingAmount` | *string* | 19 | C | DCC amount |
| `dccExchangeRate` | *string* | 20 | M | Currency exchange rate |
| `amexSeNumber` | *string* | 10 | C | Applicable for AMEX transaction |
| `emiFlag` | *string* | 01 | M | 0 – Non-EMI 1 - EMI |
| `emiTenure` | *string* | 02 | C | Applicable for EMI transaction |
| `emiInterestRate` | *string* | 10 | C | Applicable for EMI transaction |
| `emiProcessingFee` | *string* | 10 | C | Applicable for EMI transaction |
| `emiDiscAmt` | *string* | 10 | C | Applicable for EMI transaction |
| `emiPerMonth` | *string* | 10 | C | Applicable for EMI transaction |
| `cardNumber` | *string* | 19 | O | Card Number |
| `expDate` | *string* | 4 | O |  |
| `posEntryMode` | *string* | 10 | M | MANUAL / SWIPE / INSERT / CLSS / FALLBACK / CLSS_MSR / QRC |
| `walletType` | *string* | 10 | C  | Type of wallet used such as UPI, Amazon Pay LPM name |
| `primaryId` | *string* | 20 | C | Reference Number of the QR Request |
| `custId` | *string* | 35 | O | Customer identifier,Vehicle number for fasttag VPA for UPI QR |
| `walletId` | *string* | 05 | O | Unique wallet ID associated with each wallet |
| `Source` | *string* | 20 | O | Transaction Initiated source |
| `customerMobile` | *string* | 20 | O | Customer Mobile Number |
| `customerName` | *string* | 20 | O | Cardholder Name |
| `cardType` | *string* | 5 | O | Card Type |
| `offlineFlag` | *string* | 01 | O | offline flag |
| `tranDate` | *date* | DDMMYYYY | O | transaction date |
| `tranTime` | *string* | HHMMS | O | transaction time |
| `settlementDetails` | *string* | 2000 | O | set settlement Details |




Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`401` |Token not found|  
|`200` |Success|
|`300` |Request Failure|
|`500` |Internal Server Error|
|`404` |Not Found|
|`502` |Request Timed Out|
