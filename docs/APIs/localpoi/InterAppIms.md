# Inter-Application Integration

Inter-Application integration can facilitate processing of various payment transactions from Fiserv payment terminal.
E.g. Biller can integrate with payment app and complete the payment transaction.

Financial payment transactions supported by Interapp to biller: Sale, PreAuth Sale, PreAuth Completion, Transaction Status Check, EMI Sale, Void, Settlement, Bharat QR code generation

## How it works
-	Digital transactions from Fiserv’s proprietary mCommerce application supported by the payment terminal includes :-
    -	Amazon QR
    -	Bharath QR
    -	UPI QR
    -	ICICI Fast Tag 
    -	Card Transaction (navigating to direct card payment application)
- For a normal Sale request, the supported functionalities are listed below.

### Sale Request
```
Base24Request request = new Base24Request(); 
request.setFunctionCode(Base24Constant.TYPE_SALE); 
request.setTotalTxnAmount("12300");
request.setBillAmount("10000");//new features request.setConvenienceFee("2000"); 
request.setCustomerNum("customer_random_ref_no"); 
request.setUserDefinedFields("panudf"); 
request.setcGST("150"); 
request.setsGST("150");  
request. setSuppressPrintChargeSlips("y"); //can be "y" or "n" request. setMrn("merchant_random_ref_no"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

``` 

### PreAuth Sale Request
```
Base24Request request = new Base24Request();
request.setFunctionCode(Base24Constant.TYPE_PREAUTH_SALE);
request.setTotalTxnAmount("12300"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```

### PreAuth Completion Request
```
Base24Request request = new Base24Request();
request.setFunctionCode(Base24Constant.TYPE_PREAUTH_COMPLETIN);
request.setTotalTxnAmount(“12000”); 
request.setTerminalInvoiceNo("01"); 
request.setAuthCode("123456"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```


### Refund Request
```
Base24Request request = new Base24Request();
request.setFunctionCode(Base24Constant.TYPE_REFUND); 
request.setTotalTxnAmount("10000"); request.setTerminalInvoiceNo("1"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### Void Request
```
Base24Request request = new Base24Request();
request.setFunctionCode(Base24Constant.TYPE_VOID);
request.setTerminalInvoiceNo("1"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### Tip Request
```
Base24Request request = new Base24Request(); 
request.setFunctionCode(Base24Constant.TYPE_TIP); 
request.setConvenienceFee("1200");
request.setTerminalInvoiceNo("1"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### Cash & POS Request
```
Base24Request request = new Base24Request();
request.setFunctionCode(Base24Constant.TYPE_CASH); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### EMI Sale Request
```
Base24Request request = new Base24Request(); 
request.setFunctionCode(Base24Constant.TYPE_EMI_SALE);
request.setTotalTxnAmount("12300"); 
request.setTenure("3"); // 3, 6, 9, 12, 18, 24 -> Those values are able to enter 
request.setEmiSchemeID("1234567890"); // All 10 Digit number 
request.setDiscountAmount("0"); // Always Zero 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### Settlement Request
```
Base24Request request = new Base24Request(); 
request.setFunctionCode(Base24Constant.TYPE_SETTLEMENT); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### Transaction Status Request
```
Base24Request request = new Base24Request(); 
request.setFunctionCode(Base24Constant.TYPE_TRANS_STATUS);
request.setTerminalInvoiceNo("1"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### NAC Request
```
Base24Request request = new Base24Request(); 
request.setFunctionCode(Base24Constant.NAC); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### QR Direct Request
```
JSONObject requestParams = new JSONObject();
requestParams.put("transaction_amount",“12000”); 
requestParams.put("transaction_type",“qr type”);  // bharat_qr / upi_qr / amazon_qr
requestParams.put("mrn",“merchant reference number”);
MSApi.getInstance().doQRCodeTransaction(context, 123, requestParams);

```
### UPI Transaction Request
```
JSONObject requestParams = new JSONObject();
requestParams.put("transaction_amount",“12000”); 
requestParams.put("vpa",“vpa upi id”);  // enter ur UPI ID
requestParams.put("transaction_type",“vpa”);
MSApi.getInstance().doUpiTransaction(context,123, requestParams);

```
### BBPS Sale Request
```
JSONObject requestParams = new JSONObject();
requestParams.put("transaction_type","BBPS"); 
MSApi.getInstance().doBBPSTransaction(context, 123, requestParams);

```
### ICICI Fast Tag Sale Request
```
JSONObject requestParams = new JSONObject();
requestParams.put("transaction_amount", “100”);
requestParams.put("vehicle_number", “TN10AB0001”);
requestParams.put("mrn", "23423423");
requestParams.put("sap_code", "2323");
MSApi.getInstance().doFastagTransaction(context, 123, requestParams);

```
### Request

The table below identifies the required properties in the request message

| Variable | Type |     Length     | Mandatory / Optional / Conditional (M / O / C)  |     Description / Values      |
| -------- | -------- | -------------- | -----------------------| ------------------------- |
| `functionCode` | String	| 2 | 00- Digital and Carded both |
|  | 	|  | 01-Sale( Sale , DCC ) |
|  | 	|  | 02-Preauth Sale |
|  | 	|  | 03- Preauth Completion |
|  | 	|  | 04-Refund |
|  | 	|  | 05-Void |
|  | 	|  | 06-TIP |
|  | 	|  | 07-Cash@POS |
|  | 	|  | 08-EMI Sale |
|  | 	|  | 09-Loyality Earned |
|  | 	|  | 10-Loyality Redeemed |
|  | 	|  | 11-Settlement Transaction |
|  | 	|  | 12-Transaction status |
|  | 	|  | 13 - UPI QR  Generation |
|  | 	|  | 14- UPI QR Last Transaction Status |
|  | 	|  | 15 - Bharat QR  Generation  |
|  | 	|  | 16-  Bharat  QR Last Transaction Status  |
|  | 	|  | 17- Wallet Google Pay |
|  | 	|  | 18- Tone Tag wallet  |
|  | 	|  | 19- Noncarded  |
| `source` | String | 10 | O | TILL, Mobile, AVTM, etc |
| `totalTxnAmount( Auth+ConvFee + GTS )`| String | 10 | M | Total Amount including decimal |
| `convenienceFee`| String | 10 | O | Convenience Fee including decimal |
| `CGST` | String | 10 | O | GST Including decimal (GST) |
| `SGST` | String  | 10 | O | GST Including decimal (GST) |
| `billAmount`  | String | 10 | O ( Mandatory for QR generation / Wallet Transactions | Bill amount including decimal |
| `merchantReferenceNumber(MRN)` | String | 20 | M | Unique merchant number generated on mobile |
| `EMIReferenceNumber(ERN)` | String | 8 | O ( Mandatory for EMI transaction ) | EMI reference number generated on mobile |
| `consumeNumber` | String | 20 | O | consume number (CRN) |
| `currencySelection` | String | 3 | O | NA |
| `userDefinedFields` | String | 30 | O | PAN + UDF |
| `terminalInvoiceNumber` | String | 8 | O ( Mandatory for void Transaction ) | Used for Preauth completion & cancelletion |
| `cardLastFourDigit` | String | 4 | O | Used for preauth completion & cancelletion |
| `authCode` | String | 8 | O | Used for preauth completion & cancelletion |
| `emailId` | String | 50 | O | Email ID on which Email needs to be received |
| `billerId` | String | 10 | O | Biller ID received |
| `DCC flag` | String | 1 | O | DCC conversion flag yes or no |
| `UDF 1` | String| 10 | O | UDF1 |
| `UDF 2`  | String| 10 | O | UDF2 |
| `printChargeSlip` | String | 1 | O | Y o N ( Default - Y ) |

### Response in Payload
```
NOTE: This is used for all transaction requests to receive the response. 
➔ In your activity.java,  
@Override
protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    super.onActivityResult(requestCode, resultCode, data);
    if (requestCode == 123) {
        if (resultCode == RESULT_OK) {
            String response = data.getStringExtra("response");
            //see all non-null fields of response, use response.toString();
        }
    }
}

```
### Response

The table below identifies the required properties in the response message

| Variable | Type |     Length     | Mandatory / Optional / Conditional (M / O / C)  |     Description / Values      |
| -------- | -------- | -------------- | -----------------------| ------------------------- |
| `functionCode` | String	| 2 | 00- Digital and Carded both |
|  | 	|  | 01-Sale( Sale , DCC ) |
|  | 	|  | 02-Preauth Sale |
|  | 	|  | 03- Preauth Completion |
|  | 	|  | 04-Refund |
|  | 	|  | 05-Void |
|  | 	|  | 06-TIP |
|  | 	|  | 07-Cash@POS |
|  | 	|  | 08-EMI Sale |
|  | 	|  | 09-Loyality Earn |
|  | 	|  | 10-Loyality Burn |
|  | 	|  | 11-Settlement Transaction |
|  | 	|  | 12-Transaction status |
|  | 	|  | 13 - UPI QR  Generation |
|  | 	|  | 14- UPI QR Last Transaction Status |
|  | 	|  | 15 - Bharat QR  Generation  |
|  | 	|  | 16-  Bharat  QR Last Transaction Status  |
|  | 	|  | 17- Wallet Google Pay |
|  | 	|  | 18- Tone Tag wallet  |
|  | 	|  | 19- Noncarded  |
|`source` | String | 10 | O | TILL, Mobile, AVTM, etc |
|`TIP amoun`t	|String	|10|O|	Length 10 including decimal |
|"Total Transaction amount (  Bill  Amount + Convenience Fee +  GST ) |	String|	10|	M	|Length 10 including decimal|
|Fuel  |Discount | Cashback |	String	|10|	O	|Length 10 including decimal|
|`Convenience Fee`|	String|	10|	O|	Length 10 including decimal|
|`CGST` |	String	|10	|O|	Length 10 including decimal|
|`SGST`|	String	|10	|O	|Length 10 including decimal|
|`Bill  amount`|	String|	10|	O|	Length 10 including decimal|
|`EMI specific data`|	String|	20|	O|	Interest rate,  Processing fee, Tenure,  etc.|
|`Merchant  Reference  Number (MRN)`|	String|	20	|M|	Merchant Reference Number
|`Terminal  Invoice  number`|	String|	8|	M|	Terminal Invoice Number|
|`Currency selection`	|String|	3|O|	Currency code/currency which been selected|
|`Transaction ID`	|String|	10|	M|	Transaction ID|
|`Customer name` |	String|	25|	O|	Customer name extracted from Card|
|`User defined fields`|	String|	30	|O|	custom filed|
|`Masked Card Number`	|String	|21|	M|	First Six digit & last four digit. In between number should be masked|
|`Application Version Number`|	String|	10	|M	|This is terminal application version number|
|`Date & Time`|	String|	20|	M|	Host Date & Time|
|`ATID`|	String|	8	|M|	Acquirer TID|
|`AMID`	|String|	15|	M|	Acquirer MID|
|`Acquirer Name`|	String|	20|	M	|Acquirer Name|
|`Response code`|	String|	12|	M|	Host Response code, it has response message|
|`Batch Number`|	String|	6|	M|Terminal Batch Number|
|`Card Type`|	String|	10|	M|	Type of card|
|`RRN`|	String|	12	|M	|RRN received from host|
|`SE`	|String	|10|	O|	Value would be populated incase of Amex txns|
|`EMV specific Data`|	String|	256|	O|	EMV data like TC , Application identifier, Application Name, TSI, etc.|
|`DCC Indicator`	|String|	1|	O|	"DCC  flag  yes or no DCC : Sale , Void value as '1'"|
|`EMI flag`|	String|	1	|O	|"EMI  flag  yes or no,  YES :1 , NO : 0 To be sent in OTC EMI Sale, EMI Void"|
|`Pos Entry Mode`	|String|	3|	O|	Magstipe,Chip, Contactless, Manual entry, etc.|
|`Pin Verified`	|String	|3	|O	|"Yes" when PIN was entered & "No" when pin was not prompt|
|`Auth Code`|	String|	8|	M	|Received from Issuer/host|
|`Biller Id` |	String	|10|	O	|Biller Id|
|`Specific Indicator` |	String|	3|	O|	To be used for BBPS |
|`Merchant Unique Number`	|String	|20|	O|	Merchant Unique Number|
|`Terminal Invoice Number`|	String	|20|	O	|Terminal Invoice Number| 
|`Suppress Print Charge Slip` |	String|	2|	O|“Yes” or “No”  -To suppress chargeslip prints for financial transactions|
|`EMI`|	String|	20|	O|	"EMI details – emi flag is 1/0 |EMI reference number generated is 8 bytesTenure, discount amount, product amount, EMI per month"
|`Consumer Number`|	String|	20|	M|	"CRN / Consumer number 20 bytes "
|`Card Last four digit`|	String|	4|	O|	Used for pre-auth completion & cancellation transaction
|`Email ID`	|String	|50	|O|	Email ID on which Email needs to be received 50 bytes optional|
|`Card Txn mode`|	String	|3|	O|	Txn Mode|
|`Purchase amount` |	String|	10|	O|	Purchase amount| 
|`Cash back amount`|	String|	10|	O|	 Transaction cash back amount|
|`NAC Status` |	String|	3|	O|	"Identify the network status True -> private network False -> public network"|
|` Exp Date`	|String|	4|	O	|Transaction card expire date|
|`DCC Yes/NO / flag` |	String|	10|	O	|DCC Conversion flag  Yes or No & the response converted amount, exchange rate and marginfee|



The table below provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`0`|	SUCCESS |
|`1`|	ERR_TIMEOUT |
|`2`|	ERR_CONNECT |
|`3`|	ERR_SEND |
|`4`|	ERR_RECV |
|`5`|	ERR_PACK |
|`6`|	ERR_UNPACK |
|`7`|	ERR_PACKET |
|`8`|	ERR_MAC |
|`9`|	ERR_PROC_CODE |
|`10`|	ERR_MSG |
|`11`|	ERR_TRANS_AMT |
|`12`|	ERR_TRACE_NO |
|`13`|	ERR_TERM_ID |
|`14`|	ERR_MERCH_ID |
|`15`|	ERR_NO_TRANS |
|`16`|	ERR_NO_ORIG_TRANS |
|`17`|	ERR_HAS_VOIDED |
|`18`|	ERR_VOID_UNSUPPORTED |
|`19`|	ERR_COMM_CHANNEL |
|`20`|	ERR_HOST_REJECT |
|`21`|	ERR_ABORTED |
|`22`|	ERR_USER_CANCEL |
|`23`|	ERR_NEED_SETTLE_NOW |
|`24`|	ERR_NEED_SETTLE_LATER |
|`25`|	ERR_NO_FREE_SPACE |
|`26`|	ERR_NOT_SUPPORT_TRANS |
|`27`|	ERR_CARD_NO |
|`28`|	ERR_PASSWORD |
|`29`|	ERR_PARAM |
|`31`|	ERR_BATCH_UP_NOT_COMPLETED |
|`33`|	ERR_AMOUNT |
|`34`|	ERR_CARD_DENIED |
|`36`|	ERR_ADJUST_UNSUPPORTED 
|`37`|	ERR_CARD_UNSUPPORTED |
|`38`|	ERR_CARD_EXPIRED |
|`39`|	ERR_CARD_INVALID |
|`40`|	ERR_UNSUPPORTED_FUNC |
|`47`|	ERR_NO_MATCH_ACQUIRER |
|`48`|	ERR_ADJUST_LIMIT |
|`49`|	ERR_NO_INSTALLMNET_DATA |
|`50`|	ERR_INVALID_QR_CODE |
|`51`|	ERR_MOTO_PREAUTH_COMP_UNSUPPORTED |
|`52`|	ERR_PRINT |
|`54`|	ERR_ABORTED_DISPLAY |
|`55`|	ERR_DECLINED |
|`59`|	CLSS_USE_CONTACT |
|`60`|	ERR_NO_RECORD |
|`66`|	ERR_UNEXPECTED |
|`204`|	ERR_REPEATED_UID |