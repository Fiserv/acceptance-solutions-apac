# Interapp

Interapp is an integration between two applications present in the same device. E.g. Biller can integrate with payment app and complete the payment transaction.

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
request. setSuppressPrintChargeSlips("y"); //can be “y” or “n” request. setMrn("merchant_random_ref_no"); 
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

### PreAuth Completition Request
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
### EMI sale Request
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
### Transaction status Request
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
### QR Directly Request
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
requestParams.put("transaction_type",“BBPS”); 
MSApi.getInstance().doBBPSTransaction(context, 123, requestParams);

```
### ICICI Fast tag Sale Request
```
JSONObject requestParams = new JSONObject();
requestParams.put("transaction_amount", “100”);
requestParams.put("vehicle_number", “TN10AB0001”);
requestParams.put("mrn", “23423423”);
requestParams.put("sap_code", “2323”);
MSApi.getInstance().doFastagTransaction(context, 123, requestParams);

```
### Request
```
The below table identifies the required properties in the request message

```
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




Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`0`|	SUCC |
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