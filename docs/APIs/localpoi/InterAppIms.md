# Inter-Application Integration

Inter-Application integration can facilitate processing of various payment transactions from Fiserv payment terminal.
E.g. Biller can integrate with payment app and complete the payment transaction.

Financial payment transactions supported by Interapp to biller: Sale, PreAuth Sale, PreAuth Completion, Transaction Status Check, EMI Sale, Void, Settlement, Bharat QR code generation

## How it works
-	In Normal Sale request will show the below options for sale 
-	Digital Transaction (will perform txn in mCommerce application only)
    -	Amazon QR
    -	Bharath QR
    -	UPI QR
    -	ICICI Fast Tag 
    -	Card Transaction (navigating to direct card payment application)

### Payload Examples

### Request Payload

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

| Variable | Type |     Length     | Mandatory / Optional / Conditional (M / O / C )  | Description / Values |
| -------- | -------- | -------------- | -----------------------| ------------------ |
| `functionCode` | String	| 2 | 00- Digital and Carded both |
|  | 	|  | 01-Sale(Sale,DCC) |
|  | 	|  | 02-Preauth Sale |
|  | 	|  | 03- Preauth Completion |
|  | 	|  | 04-Refund |
|  | 	|  | 05-Void |
|  | 	|  | 06-TIP |
|  | 	|  | 07-Cash@POS |
|  | 	|  | 08-EMI Sale |
|  | 	|  | 09-Loyality Earn,10-Loyality Burn |
|  | 	|  | 10-Loyality Burn |
|  | 	|  | 11-Settlement Transaction |
|  | 	|  | 12-Transaction status |
| `source` | String | 10 | O | TILL,Mobile,AVTM,etc |
| `totalTxnAmount(Auth+ConvFee + GTS )`| String | 10 | M | Total Amount including decimal |
| `convenienceFee`| String | 10 | O | Convenience Fee including decimal |
| `CGST` | String | 10 | O | GST Including decimal (GST) |
| `SGST` | String  | 10 | O | GST Including decimal (GST) |
| `billAmount`  | String | 10 | O (Mandotory for QR generation / Wallet Transactions | Bill amount including decimal |
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

| Variable |  Length  | Description / Values |
| -------- | ------------- | ------------------ |
| `functionCode`	| 2bytes | 00- Digital and Carded both,01-Sale(Sale,DCC),02-Preauth Sale,03- Preauth Completion,04-Refund,05-Void,06-TIP,07-Cash@POS,08-EMI Sale,09-Loyality Earn,10-Loyality Burn,11-Settlement Transaction,12-Transaction status |
| `source` | 10bytes | TILL,Mobile,AVTM,etc |
| `tipAamount` | 10 bytes | Length 10 including decimal |
| `totalTransactionAmount( Bill Amount + Convience Fee + GST )` | 10bytes | Length 10 including decimal |
| `fuelDiscountCashback` | 10bytes | Length 10 including decimal |
| `convenienceFee` | 10bytes | Length 10 including decimal |
| `CGST` | 10bytes | Length 10 including decimal |
| `SGST` | 10bytes | Length 10 including decimal |
| `billAmount` | 10bytes | Length 10 including decimal |
| `emiSpecificData` | 20bytes | Interesting rate,Processing fee,Tenure,etc |
| `merchaneReferenceNumber(MRN)`| 20bytes | same as request |
| `terminalInvoiceNumber` | 8bytes | Terminal Invoice Number |
| `currencySelection` | 3bytes | currency code/currency which been selected |
| `transactionId`| 10bytes | same as request |
| `customerName` | 25bytes | Customer name extracted from Card |
| `userDefinedFields` | 30bytes | same as request |
| `maskedCardNumber` | 21bytes | First Six digit & last four digit, Inbeetween number should be masked |
| `applicationVersionNumber` | 10bytes | This terminal version number |
| `Date&Time` | 20bytes | Host Date & Time |
| `ATID` | 8bytes | Aquirer TID |
| `AMID` | 15bytes | Aquirer MID |
| `aquirerName` | 20bytes | Aquirer Name |
| `responseCode` | 12bytes | Host Response code, it has response message |
| `batchNumber` | 6bytes | Terminal Batch Number |
| `cardType` | 10bytes | This will card type |
| `RRN` | 12bytes | RRN received from the host |
| `SE` | 10bytes |  Value would be populated incase of Amex txns |
| `emvSpecificData` | 256bytes | EMV data like TC,Application identifier , Application Name, TSL,etc |
| `dcc Indicator` | 1byte | DCC flag yes or no DCC : Sale , Void value as '1' |
| `emiFlag`| 1byte | EMI flag yes or no, YES : 1, NO :0 To be sent in OTC EMI Sale,EMI Void |
| `posEntryMode` | 3bytes |Magstipe,Chip,Contactless,Manual entry,etc |
| `pinVerified` | 3bytes | "Yes" when PIN was entered & "No" when pin was not prompt |
| `authCode` | 8bytes | Received from issue/host |
| `billerID` | 10bytes | same as request |
| `specificIndicator` | 3bytes |To be used for BBPS |
| `merchantUniqueNumber` | 20bytes | same as request |
| `theSameAsTerminalInvoiceNumber`| 20bytes | same as request |
| `suppressPrintChargeSlip` | 2bytes | "y" or "no" .. To suppress chargeslip prints for financial transactions |
| `EMI` | 20bytes | EMI details - emi flag is 1/10 EMI refernce number generated on 8 bytes |
| `consumerNumber`| 20bytes | CRN/Consumer number 20bytes (CRN : Mandatory) |
| `cardLastFourDigit` | 4bytes | Used for pre-auth completion & cancellation |
| `emailID` | 50bytes | Email ID on which Email needs to be received 50 bytes optional |
| `cardTxnMobile` | 3bytes | NA |
| `purchaseAmount` | 10bytes | Purchase Amount |
| `cashBackAmount` | 10bytes | Transaction cash amount |
| ` nacStatus` | 3bytes | Identify the network status	True -> private network False -> public network |
| `cardExpDate` | 4bytes | Transaction Card expire date |




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