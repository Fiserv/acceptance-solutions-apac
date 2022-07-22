# Inter-Application Integration

Inter Application Integration provides a seamless integration between the Fiserv payment application and the merchant application locally installed in android-based terminals.
E.g. A biller can integrate with a payment application and complete the payment transaction.

Financial payment transactions that are supported by inter application to billers include functions like Sale, Pre-Authorisation Sale, Pre-Authorisation Completion, Transaction Status Check, EMI Sale, Void, Settlement and Bharat QR code generation.


## How it works
-	Digital transactions from the Fiserv's proprietary mCommerce application supported by the payment terminal includes :-
    -	Amazon QR
    -	Bharath QR
    -	UPI QR
    -	ICICI Fast Tag 
    -	Card Transaction (navigating to direct card payment application)
- For a normal Sale request, the supported functionalities are listed below.

### Payload Examples - Request

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
| -------- | -------- | ----- | ------------------------------------------------------| ------------------------- |
|`functionCode`|String|2| M|01 - Sale ( Sale, DCC ) |
| `Print Charge Slip` | String | 1 | O | Y or N ( Default - Y ) |
| | | | | 02 - Preauth Sale |
| | | | | 03 - Preauth Completion |
| | | | | 04 - Refund |
| | | | | 05 - Void |
| | | | | 06 - TIP | 
| | | | | 07 - Cash @ POS |
| | | | | 08 - EMI Sale |
| | | | | 11- Settlement Transaction |
| | | | | 12- Transaction status |
| | | | | 13 - UPI QR  Generation | 
| | | | | 14- UPI QR Last Transaction Status |
| | | | | 15 - Bharat QR  Generation |
| | | | | 16-  Bharat  QR Last Transaction Status |
| | | | | 17- Wallet Google Pay |
| | | | | 18- Tone Tag wallet |
| | | | | 19- Noncarded |
|`source`|String|10|O|APOS, Mobile, ECR (Electronic Cash Register), ATVM (Automatic Vending Machine)|
|`totalTxnAmount (  Auth + ConvFee+ GST) `|String|10|M|Total Amount including decimal|
|`convenienceFee `|String|10|O|Convenience  Fee including decimal|
|`cGST`|String|10|O|GST Including decimal ( GST )|
|`sGST`|String|10|O|GST Including decimal ( GST )|
|`billAmount`|String|10|O |Bill  amount  including decimal  (Mandatory for QR generation / Wallet Transactions)|
|`merchantReferenceNumber(MRN)`|String|14|M|Unique merchant number for reconcilation - Value to be populated in statement in FT Number|
|`emiReferenceNumber(ERN)`|String|8|O |EMI reference number generated on mobile (Mandatory for EMI Transaction)|
|`consumerNumber`|String|20|O|Consumer number ( CRN ) - Value to be populated in statement in session id|
|`currencySelection`|String|3|O|Currency|
|`userDefinedFields`|String|30|O|CRN + UDF - Value to be populated in statement in session id|
|`terminalInvoiceNumber`|String|8|O |Used for Preauth completion & cancellation transaction (Mandatory for Void transaction)|
|`cardLastFourDigit`|String|4|O|Used for Preauth completion & cancellation transaction|
|`authCode`|String|8|O|Used for Preauth completion & cancellation transaction|
|`emailID`|String|50|O|Email ID on which email needs to be received|
|`billerID`|String|10|O|Biller ID received |
|`dCCFlag `|String|1|O|DCC Conversion flag  Yes or No  |
|`printChargeslip`|String|1|O|Y or N ( Default - Y ) |


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
| -------- | ------- | ------- | -------------------------------------------------------| ------------------------- |
|`functionCode`|String|2|M|01 - Sale ( Sale, DCC )|
| | | | | 02 - Preauth Sale |
| | | | | 03 - Preauth Completion |
| | | | | 04 - Refund |
| | | | | 05 - Void |
| | | | | 06 - TIP | 
| | | | | 07 - Cash @ POS |
| | | | | 08 - EMI Sale |
| | | | | 11- Settlement Transaction |
| | | | | 12- Transaction status |
| | | | | 13 - UPI QR  Generation |
| | | | | 14-  UPI QR Last Transaction Status |
| | | | | 15 - Bharat QR  Generation |
| | | | | 16-  Bharat  QR Last Transaction Status 
| | | | | 17- Wallet Google Pay |
| | | | | 18- Tone Tag wallet |
| | | | | 19- Noncarded |
|`source`|String|10|O|APOS, Mobile, ECR (Electronic Cash Register), ATVM (Automatic Vending Machine)|
|`tipAmount`|String|10|O|Tip Amount entered during the transaction|
|`totalTxnAmount (  Auth + ConvFee+ GST) `|String|10|M|Total Amount including decimal|
|`fuelDiscountCashback `|String|10|O|Fuel discount cashback amount during the transaction|
|`convenienceFee `|String|10|O|Convenience  Fee including decimal|
|`cGST`|String|10|O|GST Including decimal ( GST )|
|`sGST`|String|10|O|GST Including decimal ( GST )|
|`billAmount`|String|10|O|Bill  amount  including decimal|
|`merchantReferenceNumber(MRN)`|String|20|M|Same as request|
|`terminalInvoiceNumber`|String|8|M|Terminal Invoice Number|
|`currencySelection`|String|3|O|Currency code/currency which been selected|
|`transactioID`|String|10|M|Same as request|
|`customerName`|String|25|O|Customer name extracted from Card|
|`userDefinedFields`|String|30|O|Same as request|
|`maskedCardNumber`|String|21|M|First Six digit & last four digit. In between number should be masked|
|`applicationVersionNumber`|String|10|M|This is terminal application version number|
|`date & Time`|Timestamp|20|M|Host Date & Time|
|`aTID`|String|8|M|Acquirer TID|
|`aMID`|String|15|M|Acquirer MID|
|`acquirerName`|String|20|M|Acquirer Name|
|`responseCode`|String|12|M|Host Response code, it has response message|
|`batchNumber`|String|6|M|Terminal Batch Number|
|`cardType`|String|10|M|Type of card|
|`rrn`|String|12|M|RRN received from host|
|`se`|String|10|O|Value would be populated incase of Amex txns|
|`emv`|String|256|O|EMV data like TC , Application identifier, Application Name, TSI, etc.|
|`emiFlag`|String|1|O|EMI  flag  yes or no,  YES :1 , NO : 0 To be sent in OTC .EMI Sale, EMI Void|
|`posEntryMode`|String|3|O|Magstripe,Chip, Contactless, Manual entry, etc.|
|`pinVerified`|String|3|O|"Yes" when PIN was entered & "No" when pin was not prompt|
|`authCode`|String|8|M|Received from Issuer/host|
|`billerID`|String|10|O|Same as request|
|`SspecificIndicator `|String|3|O|To be used for BBPS |
|`merchantUniqueNumber`|String|20|O|Same as request |
|`suppressPrintChargeslip `|String|2|O|“Yes” or “No”  -To suppress chargeslip prints for financial transactions|
|`emi`|String|20|O|EMI details – emi flag is 1/0  .EMI reference number generated is 8 bytes.Tenure, discount amount, product amount, EMI per month|
|`consumerNumber`|String|20|M|Consumer number ( CRN ) - Value to be populated in statement in session id|
|`cardLastFourDigit`|String|4|O|Used for pre-auth completion & cancellation transaction|
|`emailID`|String|50|O|Email ID on which Email needs to be received 50 bytes optional|
|`cardTxnMode`|String|3|O|Txn Mode|
|`purchaseAmount `|String|10|O|Purchase amount |
|`cashBackAmount`|String|10|O| Transaction cash back amount|
|`nacStatus `|String|3|O|Identify the network status .True-> private network .False -> public network|
|`cardExpDate`|String|4|O|Transaction card expire date|
|`dccFlag`|String|1|O|DCC Conversion flag  Yes or No. Response is converted amount, exchange rate and margin fee|


The table below provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`00`|Approved Balances|
|`01`|Place Call|
|`02`|Over Floor Limit|
|`03`|Merchant Not on File|
|`12`|Invalid Transaction|
|`14`|Invalid Account|
|`19`|Retry Transaction|
|`25`|CAF Not Found|
|`30`|Invalid msg format|
|`31`|Card Not Supported|
|`41`|Lost or Stolen Card|
|`43`|CAF Status 3, stolen card|
|`51`|Pin Tries Exceeded|
|`54`|Expired Card|
|`55`|Incorrect Pin|
|`58`|Transaction not allowed|
|`91`|Auth Timed out|