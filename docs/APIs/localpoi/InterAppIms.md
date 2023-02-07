# Inter-Application Integration

Inter-application Integration provides a seamless integration between the Fiserv payment application and the merchant application locally installed in android-based terminals.
E.g. A biller can integrate with a payment application and complete the payment transaction.

Financial payment transactions that are supported by inter-application to billers include functions like Sale, Pre-Authorisation Sale, Pre-Authorisation Completion, Transaction Status Check,Installment/EMI Sale, Void, Settlement and Bharat QR code generation.

For card transactions, the supported functionalities are listed below.

  <table width="120%" border="0">
  <tr>
    <th>Transactions Supported</th>
    <th>India</th>
    <th>Australia</th>
  </tr>
  <tr>
    <td>Pre-Authorization Sale</td>
     <td align="center">&#10004;</td>
     <td align="center">&#10004;</td>
 </tr>
   <tr>
    <td>Pre-Authorization Sale cancellation</td>
    <td></td>
     <td align="center">&#10004;</td>
</tr>
   <tr>
    <td>Pre-Authorization Sale completion</td>
     <td align="center">&#10004;</td>
      <td align="center">&#10004;</td>
  </tr>
   <tr>
    <td>Pre-Authorization Sale completion cancellation</td>
    <td></td>
    <td></td>
  </tr>
    <tr>
    <td>Sale</td>
     <td align="center">&#10004;</td>
    <td align="center">&#10004;</td>
 </tr>
  <tr>
    <td>Void </td>
     <td align="center">&#10004;</td>
     <td align="center">&#10004;</td>
</tr>
  <tr>
    <td>Offline Sale</td>
    <td></td>
     <td align="center">&#10004;</td>
</tr>
  <tr>
    <td>Tip Adjustment</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Refund</td>
    <td></td>
     <td align="center">&#10004;</td>
 </tr>
  <tr>
    <td>Pre-Authorization completion Offline</td>
    <td></td>
     <td align="center">&#10004;</td>
</tr>
  <tr>
    <td>Installment / EMI Sale</td>
     <td align="center">&#10004;</td>
  <td></td>
  </tr>
  <tr>
    <td>Installment Sale Cancellation</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Void Refund</td>
    <td></td>
     <td align="center">&#10004;</td>
</tr>
  <tr>
    <td>Cash Advance / Cash withdrawal</td>
     <td align="center">&#10004;</td>
     <td></td>
  </tr>
  <tr>
    <td>Cash Only</td>
     <td align="center">&#10004;</td>
     <td align="center">&#10004;</td>
 </tr>
  
  <tr>
    <td>Purchase with Cashback</td>
     <td align="center">&#10004;</td>
    <td align="center">&#10004;</td>
</tr>
  <tr>
    <td>Settlement / Batch Upload</td>
     <td align="center">&#10004;</td>
     <td align="center">&#10004;</td>
</tr>
  <tr>
    <td>DCC (Dynamic Currency Conversion)</td>
     <td align="center">&#10004;</td>
     <td></td>
  </tr>
  <tr>
    <td>Pre-Authorization Top-Up (Incremental Auth)</td>
     <td align="center">&#10004;</td>
     <td align="center">&#10004;</td>
 </tr>
   <tr>
    <td>Balance Inquiry</td>
     <td align="center">&#10004;</td>
  <td></td>
  </tr>
   <tr>
    <td>Settlement report / Detail report</td>
     <td align="center">&#10004;</td>
     <td align="center">&#10004;</td>
  </tr>
  </table>
  
 For digital transactions, the supported functionalities are listed below.
<table width="130%"border="0">
  <tr>
    <th>Value Added Services</th>
    <th>India</th>
  </tr>
  <tr>
    <td>BBPS (Bharat Bill Pay)</td>
     <td align="center">&#10004;</td>
   
  </tr>
   <tr>
    <td>UPI QR</td>
     <td align="center">&#10004;</td>
   
  </tr>
   <tr>
    <td>Bharat QR</td>
     <td align="center">&#10004;</td>
    
  </tr>
   <tr>
    <td>FASTag</td>
     <td align="center">&#10004;</td>
    
  </tr>
     <tr>
    <td>MobiKwik</td>
     <td align="center">&#10004;</td>
     
  </tr>
</table>

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

### Pre-Authorisation Sale Request
```
Base24Request request = new Base24Request();
request.setFunctionCode(Base24Constant.TYPE_PREAUTH_SALE);
request.setTotalTxnAmount("12300"); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```

### Pre-Authorisation Completion Request
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
### Cash & Point of Sale Request
```
Base24Request request = new Base24Request();
request.setFunctionCode(Base24Constant.TYPE_CASH); 
JSONObject requestParams = new JSONObject();
requestParams.put("base24Request", request.toString());
MSApi.getInstance().doPayment(context, 123, requestParams);

```
### Installment/ EMI Sale Request
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
### Bharat Bill Pay (BBPS) Sale Request
```
JSONObject requestParams = new JSONObject();
requestParams.put("transaction_type","BBPS"); 
MSApi.getInstance().doBBPSTransaction(context, 123, requestParams);

```
### ICICI FASTag Sale Request
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

| Variable | Type | Length | Mandatory / Optional / Conditional (M / O / C)  | Description / Values |
| -------- | -------- | ----- | ------------------------------------------------------| ------------------------- |
|`functionCode`|String|2| M|01 = Sale ( Sale, DCC ) |
| | | | | 02 = Pre-Authorization |
| | | | | 03 = Pre-Authorization Completion |
| | | | | 04 = Refund |
| | | | | 05 = Void |
| | | | | 06 = TIP | 
| | | | | 07 = Cash @ POS |
| | | | | 08 = Installment/EMI Sale |
| | | | | 11 = Settlement Transaction|
| | | | | 12 = Transaction status |
| | | | | 13 = UPI QR  Generation | 
| | | | | 14 = UPI QR Last Transaction Status|
| | | | | 15 = Bharat QR  Generation |
| | | | | 16 = Bharat  QR Last Transaction Status |
| | | | | 17 = Google Pay Wallet |
| | | | | 18 = Tone Tag Wallet |
| | | | | 19 = Non-carded Transactions |
|`source`|String|10|O|APOS (Android Point of Sale), Mobile, ECR (Electronic Cash Register), ATVM (Automatic Vending Machine).|
|`totalTxnAmount`|String|10|M|Total Amount including (Auth + ConvFee+ GST) in decimals - "100.00".|
| `CGST` | *string* | 10 | C | Central GST Including decimal (E.g. 10.00 for $10 CGST). If CGST is included in the total amount. |
| `IGST` | *string* | 10 | C | Integrated GST Including decimal (E.g. 10.00 for $10 IGST). If IGST is included in the total amount. |
| `SGST` | *string* | 10 | C | State GST Including decimal (E.g. 100.00 for $10 SGST). If SGST is included in the total amount. |
|`billAmount`|String|10|O |Bill  amount  including decimal  (Mandatory for QR generation / Wallet Transactions).|
|`merchantReferenceNumber`|String|14|M|Unique merchant number for reconcilation - Value to be populated in statement in FT Number.|
|`emiReferenceNumber`|String|8|O |EMI reference number generated on mobile (Mandatory for EMI Transaction).|
|`consumerNumber`|String|20|O|Consumer number ( CRN ) - Value to be populated in statement in session id.|
|`currencySelection`|String|3|O|Currency code / currency that had been selected.|
|`userDefinedFields`|String|30|O|CRN + UDF - Value to be populated in statement in session ID.|
|`terminalInvoiceNumber`|String|8|O |Used for Pre-authorization completion & cancellation transaction (Mandatory field for VConversion flag - Yes or No. Response contains converted amount, exchange rate and margin fee. |
|`se`|String|10|O|Value would be populated incase of Amex transactions.|
|`printChargeslip`|String|1|O| To enable charge slip printing - Y or N ( Default mode = Y ).|
|`cardLastFourDigit`|String|4|O| Last 4 digits of Card Number. To be included for Pre-Authorization completion and cancellation transaction. |
|`maskedCardNumber`|String|21|M|First 6 digit and last 4 digit. The numbers in between should be masked.|
|`emailID`|String|50|O|Email ID of the email that needs to be received. This is an optional 50 bytes variable.
|`applicationVersionNumber`|String|10|M|Version number of terminal application used.|
|`aTID`|String|8|M|Acquirer TID (Terminal ID)|
|`aMID`|String|15|M|Acquirer MID (Merchant ID)|
|`authCode`|String|8|M|Used for Pre-authorization completion & cancellation transaction.|
|`billerID`|String|10|O|Biller ID received |
|`dccFlag`|String|1|O| DCC Conversion flag - Y or N|


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
| -------- | ------- | ------- | -------------------------------------------------------| ------------------------- 
|`functionCode`|String|2| M|01 = Sale ( Sale, DCC )|
| | | | | 02 = Pre-Authorization |
| | | | | 03 = Pre-Authorization Completion |
| | | | | 04 = Refund |
| | | | | 05 = Void |
| | | | | 06 = TIP | 
| | | | | 07 = Cash @ POS |
| | | | | 08 = Installment/EMI Sale |
| | | | | 11 = Settlement Transaction |
| | | | | 12 = Transaction status |
| | | | | 13 = UPI QR  Generation | 
| | | | | 14 = UPI QR Last Transaction Status |
| | | | | 15 = Bharat QR  Generation |
| | | | | 16 = Bharat  QR Last Transaction Status|
| | | | | 17 = Google Pay Wallet |
| | | | | 18 = Tone Tag Wallet |
| | | | | 19 = Non-carded Transactions |
|`source`|String|10|O|APOS, Mobile, ECR (Electronic Cash Register), ATVM (Automatic Vending Machine).|
|`tipAmount`|String|10|O|Tip Amount entered during the transaction.|
|`totalTxnAmount `|String|10|M|Total Amount including (Auth + ConvFee+ GST) in decimals.|
|`fuelDiscountCashback `|String|10|O|Fuel discount cashback amount during the transaction.|
|`convenienceFee `|String|10|O|Convenience  Fee including decimal.|
|`cGST`|String|10|O|GST Including decimal ( GST ).|
|`sGST`|String|10|O|GST Including decimal ( GST ).|
|`billAmount`|String|10|O|Bill  amount  including decimal.|
|`merchantReferenceNumber`|String|20|M||Unique merchant number for reconcilation - Value to be populated in statement in FT Number.|
|`terminalInvoiceNumber`|String|8|M|Used for Pre-authorization completion & cancellation transaction (Mandatory field for Void transaction).|
|`currencySelection`|String|3|O|Currency code/currency which been selected.|
|`transactionID`|String|10|M|Same as request.|
|`customerName`|String|25|O|Customer name extracted from Card.|
|`userDefinedFields`|String|30|O|CRN + UDF - Value to be populated in statement in session ID.|
|`maskedCardNumber`|String|21|M|First 6 digit and last 4 digit. The numbers in between should be masked.|
|`applicationVersionNumber`|String|10|M|Version number of terminal application used.|
|`date & Time`|Timestamp|20|M|Host Date & Time|
|`aTID`|String|8|M|Acquirer TID (Terminal ID)|
|`aMID`|String|15|M|Acquirer MID (Merchant ID)|
|`acquirerName`|String|20|M|Acquirer Name|
|`responseCode`|String|12|M|Host Response code, it has response message.|
|`batchNumber`|String|6|M|Terminal Batch Number|
|`cardType`|String|10|M|Type of card.|
|`rrn`|String|12|M|The same value received in the original transaction response needs to be submitted across.|
|`se`|String|10|O|Value would be populated incase of Amex transactions.|
|`emv`|String|256|O|EMV data like TC , Application identifier, Application Name, TSI, etc.|
|`emiFlag`|String|1|O|To be sent in for Over the Counter (OTC)<br> transactions such as:<br> - Installment / EMI Sale <br>- Installment / EMI Void <br>Flag is defined as:<br>0 = Non-EMI (Non-installment / Non-EMI)<br> 1 = EMI (Installment / EMI).|
|`posEntryMode`|String|3|O|Magstripe, Chip, Contactless, Manual entry, etc.|
|`pinVerified`|String|3|O|Yes= when PIN was entered <br> No = when pin was not prompted.|
|`authCode`|String|8|M|Used for Pre-authorization completion & cancellation transaction.|
|`billerID`|String|10|O|Biller ID received.|
|`SspecificIndicator `|String|3|O|To be used for BBPS (Bharat Bill Payment System).|
|`merchantUniqueNumber`|String|20|O|Same as request. |
|`suppressPrintChargeslip `|String|2|O|To suppress charge slip printing for financial transactions, to be set as “Yes” or “No”.|
|`emi`|String|20|O|Installment / EMI details<br> - Installment / EMI flag is 1/0 .<br> - Installment / EMI reference number<br> generated is 8 bytes.<br> - Tenure, discount amount, product amount,<br> Installment / EMI amount per month.|
|`consumerNumber`|String|20|M|Consumer number ( CRN ) The value that is populated in statement of the session ID.|
|`cardLastFourDigit`|String|4|O| Last 4 digits of Card Number. To be included for Pre-Authorization completion and cancellation transaction. |
|`emailID`|String|50|O|Email ID of the email that needs to be received. This is an optional 50 bytes variable. |
|`cardTxnMode`|String|3|O|Transaction Mode|
|`purchaseAmount `|String|10|O|Purchase amount|
|`cashBackAmount`|String|10|O| Transaction cash back amount|
|`nacStatus `|String|3|O|Identifies the network status <br> - True = private network <br> - False = public network.|
|`cardExpDate`|String|4|O|Transaction card expiry date|
|`dccFlag`|String|1|O| DCC Conversion flag - Y or N|
|`printChargeslip`|String|1|O| To enable charge slip printing - Y or N ( Default mode = Y ).|


The table below provides the list of application's error code and its description.

| Error Code |  Description / Values | Comments |
| --------  | ------------------ | ----------- |
|`00`|Approved Balances|Merchant should proceed with reciept generation.|
|`01`|Place Call|Contact Customer Support / Business Manager.|
|`02`|Over Floor Limit|Contact Customer Support / Business Manager.|
|`03`|Merchant Not on File|Contact Customer Support / Business Manager|.
|`12`|Invalid Transaction|Issuer declined the transaction. Merchant should advise cardholder to use a  different card for the  transaction.|
|`14`|Invalid Account|Issuer declined the transaction. Merchant should advise cardholder to use a  different card for the  transaction.|
|`19`|Retry Transaction|Contact Customer Support / Business Manager.|
|`25`|CAF Not Found|Contact Customer Support / Business Manager.|
|`30`|Invalid msg format|Contact Customer Support / Business Manager.|
|`31`|Card Not Supported|Contact Customer Support / Business Manager.|
|`41`|Lost or Stolen Card|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`43`|CAF Status 3, stolen card|Issuer declined the transaction. Merchant should advise cardholder to use a  different card for the transaction.|
|`51`|Pin Tries Exceeded|Issuer declined the transaction. The number of tries using PIN had exceeded. Merchant should advise cardholder to use a different card for the transaction.|
|`54`|Expired Card|Issuer declined the transaction. Merchant should advise cardholder to use a different valid card for the transaction.|
|`55`|Incorrect Pin|Issuer declined the transaction. Merchant should advise cardholder to retry with the correct PIN.|
|`58`|Transaction not allowed|Issuer declined the transaction. Merchant should advise cardholder to use a  different card for the  transaction.|
|`91`|Authorization Attempt Timed out|Contact Customer Support / Business Manager.|
