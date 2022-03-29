# Sale with Local Payment Method

This API is used to send a sale request for card transactions. Merchants needs to add the session token received during Login  API call in the header field of this API.

## Endpoint

POST `/boardinggateway/cloudpoi/PosPush/nonOpiProcessAmount`

## Payload Example

### Request Payload

```json
	{
	  "ain": "4700000",
	  "functionCode": "00",
	  "merchantId": "470000095488827",
	  "terminalId": "33878692",
	  "customerRefNumber": "33333333333",
	  "merchantRefNumber": "Guru415",
	  "billerId": "22",
	  "convFee": "43",
	  "cgst": "12",
	  "igst": "23",
	  "sgst": "55",
	  "totalAmount": "10",
	  "tranCurrency": "356",
	  "reqDate": "22022022",
	  "reqTime": "161900",
	  "authAmount": "111",
	  "tranDate": "",
	  "tranTime": "",
	  "invoiceNumber": "",
	  "cardLastNumber": "",
	  "callbackURL": "",
	  "mrchCountryCode": "366",
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
The table below contains the mandatory fields:
Required for a successful Sale request
Required query parameters in the request message
Required json properties
Merchants can access the full request schemas in our API Explorer[API Explorer](../api/?type=post&path=/boardinggateway/cloudpoi/PosPush/nonOpiProcessAmount).

The below table identifies the required json properties in the request message.
### Request
| Variable | Type | Length |  Mandatory / Optional/ Conditional (M / O / C) | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
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
| `merchantRefNumber` | *string* | 14 | M (BOCM – 50) | Unique number for each transaction. Inquiry transaction should have same MRN of original txn |
| `customerRefNumber` | *string* | 20 | O | Consumer Number |
| `authAmount` | *string* | 19 | M | Bill Amount including decimal (E.g. 50.00 for $50 sale). Send 0.00 for inquiry txn. |
| `convFee` | *string* | 10 | C (To be sent if fee is charged) | Convenience Fee including decimal (E.g. 5.00 for $5 fee) |
|| `cgst` | *string* | 10 | C (if CGST is included in the total amount)  | Central GST Including decimal (E.g. 10.00 for $10 cgst) |
| `igst` | *string* | 10 | C (if IGST is included in the total amount) | State GST Including decimal (E.g. 10.00 for $10 igst) |
| `sgst` | *string* | 10 | C (if SGST is included in the total amount)  | State GST Including decimal (E.g. 100.00 for $10 sgst) |
| `totalAmount` | *string* | 19 | M | Total Amount (auth, fee, gsts) including decimal ((E.g. 57.00 for $57 sale). |
| `tranCurrency` | *string* | 03 | M | Transaction Currency Code (3-digit numeric value) |
| `reqDate` | *Date* | DDMMYYYY | M | Transaction initiated date |
| `reqTime` | *Timestamp* | HHMMSS | M | Transaction initiated time |
| `tranDate` | *Date* | DDMMYYYY | C  |Original transaction date |
| `tranTime` | *Timestamp* | HHMMSS | C | Original transaction time |
| `cardLastNumber` | *string* | 04 | C (if included pre auth Completion)  | Last 4 digits of Card Number  |
| `cardBin` | *string* | 06 | C (if included refund) | First 6 digits of the Card, used in the original (sale) transaction |
| `callbackURL` | *string* | 100 | O | Response URL, place holder for notification API call feature |
| `mrchCountryCode` | *string* | 03 | M | Merchant Country Code (3-digit numeric value) |
| `tranType` | *string* | 50 | O | Transaction Description |
| `rrn` | *string* | 20 | C (It is applicable for Refund and optional for Inquiry txn) | Must pass the same value received in original transaction response |
| `emiTenure` | *string* | 02 | C (if included EMI transactions) | EMI duration |
| `paramList` | *array* | NA | O | Biller can pass any additional details if required in arrary format "paramList": [{"param_lit": "param1 key","param": "23"}] |
| `udf1` | *string* | 100 | O | User Defined Field |
| `udf2` | *string* | 100 | O | User Defined Field |

### Successful Response Payload

```json

{
    "functionCode": "00",
    "source": null,
    "billingAmount": null,
    "invoiceNumber": "202251211",
    "customerMobile": null,
    "billingCurrency": "INR",
    "transactionId": "202202250834781",
    "customerName": null,
    "respCode": "200",
    "response": "SUCCESS",
    "cardType": null,
    "rrn": null,
    "authCode": null,
    "merchantId": "470000095488827",
    "terminalId": "33878692",
    "respMsg": "Transaction Success",
    "amexSeNumber": "",
    "emiTenure": "",
    "emiInterestRate": "",
    "emiProcessingFee": "0",
    "emiDiscAmt": "0.08",
    "dccIndicator": "0",
    "dccExchangeRate": "",
    "offlineFlag": "N",
    "cardLastNumber": "",
    "totalAmount": "10.00",
    "merchantRefNumber": "Guru415",
    "customerRefNumber": "33333333333",
    "emiFlag": "",
    "cardNumber": null,
    "expDate": "",
    "posEntryMode": "",
    "walletType": "W0",
    "primaryId": "Guru415",
    "custId": "220225121129",
    "emiPerMonth": "0",
    "tranDate": "22022022",
    "tranTime": "",
    "cardBin": null,
    "tipAmount": null,
    "settlementDetails": "",
    "walletId": "W0"
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
| -------- | ------- | -- | ------------ | ------------------ |
| `merchantId` | *string* | 20 | M | Merchant ID |
| `transactionId` | *string* | 20 | M | Unique ID (Biller tran details table) |
| `functionCode` | *string* | 02 | M | Same as request |
| `invoiceNumber` | *string* | 20 | O | Terminal Invoice Number |
| `cardLastNumber` | *string* | 4 | C (if required for Pre-auth) | Last 4 Digits of Card Number |
| `totalAmount` | *string* | 19 | M | Total Amount (auth, fee, gsts, tip) including decimal (E.g. 57.00 for $57 sale) |
| `tipAmount` | *string* | 10 | C (if Tip is included) | Tip Amount including decimal (E.g. 7.00 for $7 tip)|
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
