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

