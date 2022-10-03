# Inter-Application Integration
Inter-application Integration provides a seamless integration between the Fiserv payment application and the merchant application locally installed in android-based terminals.
E.g. A biller can integrate with a payment application and complete the payment transaction.

Financial payment transactions that are supported by inter-application to billers include functions like Sale, Pre-Authorisation Sale, Pre-Authorisation Completion, Transaction Status Check,Installment/EMI Sale, Void, Settlement and Bharat QR code generation.

## How it works
For a normal Sale request, the supported functionalities are listed below. 

- Card Transaction (navigating to direct card payment application) 

For digital transactions, the supported functionalities are listed below.

<table width="120%" border="1">
  <tr>
    <th>Value Added Services</th>
    <th> Rest of APAC <br>(SG, HK, MY) </th>
     </tr>
    <tr>
    <td>WeChat</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Alipay</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>FPS</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>GrabPay</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>CUP QR (UnionPay QR)</td>
    <td align="center">.</td>
    </tr>
    </table>

  For a normal Sale request, the supported functionalities are listed below.
    
    
 <table border="1">
    <tr>
    <th>Transactions Supported</th>
    <th> Rest of APAC (SG, HK, MY)  </th>
     </tr>
    <tr>
    <td>Pre-Authorization Sale</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale cancellation</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale completion</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale completion / cancellation</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Sale</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Void</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Offline Sale</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Tip Adjustment</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Refund</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale completion offline</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Installment / EMI</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>Installment Sale Cancellation</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>MOTO Pre-Authorization</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>MOTO Pre-Authorization Cancellation</td>
    <td align="center">.</td>
    </tr>
    <tr>
    <td>MOTO Pre-Authorization completion</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>MOTO Pre-Authorization Completion / Cancellation</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>MOTO Sale</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>MOTO Sale Cancellation </td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>MOTO Refund</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Void Refund</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Cash Advance / Cash withdrawal</td>
    <td></td>
    </tr>
    <tr>   
    <td>Cash Only</td>
    <td></td>
    </tr>
    <tr>   
    <td>Purchase with Cashback</td>
    <td></td>
    </tr>
    <tr>   
    <td>Settlement / Batch Upload</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>DCC (Dynamic Currency Conversion)</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Pre-Authorization Top-Up (Incremental Auth)</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Balance Inquiry</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Settlement report / Detail report</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Reprint</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Reprint Total</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>View History</td>
    <td align="center">.</td>
    </tr>
    <tr>   
    <td>Get Transaction Record</td>
    <td align="center">.</td>
    </tr>
    </tr>
    </table>
   



 

### Payload Examples - Request

### Sale Request
```
SaleMsg.Request request = new SaleMsg.Request(); 
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24");
request.setTotalTxnAmount(10000);
request.setUid("1234");
//Unique id request.setIsQfpay(false);  //use for Qfpay,the default value is false
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### PreAuth Sale Request
```
PreAuthMsg.Request request = new PreAuthMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(222);
request.setUid("1234");//Unique id 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);boolean ret = transAPI.doTrans(request);

```
### PreAuth Completion Request
```
PreAuthCompMsg.Request request = new PreAuthCompMsg.Request(); 
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24");
request.setTotalTxnAmount(10000);
request.setUid("1234");//Unique id request.setTerminalInvoiceNo(1);
//orig invoice no request.setAuthCode("123456");//orig approve code request.setScheme("CUP");
//choose the scheme(CUP,JCB/DINERS/AMEX,V/M/DCC) 
request.setLast4DigitCardNo("0010");//last 4 digits card number request.setIssuer("CUP");
//choose the issuer(CUP,MASTER,VISA,JCB) 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);boolean ret = transAPI.doTrans(request);

```

### Refund Request
```
RefundMsg.Request request = new RefundMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(10000);
request.setUid("1234");//Unique id 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```
### Void Request
```
VoidMsg.Request request = new VoidMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax. fdms.base24");
request.setTerminalInvoiceNo(1);
request.setUid("1234");//Unique id request.setShowDetail(false);
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### Offline Request
```
OfflineMsg.Request request = new OfflineMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24");
request.setTotalTxnAmount(10000);
request.setStaffid("12301ATR2562-BLR-SIN")；
request.setRtext("TR2562 BLR-SIN");
request.setUid("1234");//Unique id 
ITransAPI transAPI = TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### Adjust Request
```
AdjustMsg.Request request = new AdjustMsg.Request();
request.setAppId("com.pax. fdms.base24");
request.setPackageName("com.pax.fdms.base24"); 
request.setTerminalInvoiceNo(1); 
request.setNewTotal(100);
request.setUid("1234");//Unique id 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### PreAuth Void Request
```
PreAuthVoidMsg.Request request = new PreAuthVoidMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24");
request.setTotalTxnAmount(10000);
request.setTerminalInvoiceNo(1);
//orig invoice no request.setAuthCode("123456");//orig approve code 
request.setLast4DigitCardNo("0010");//last 4 digits card numbre
request.setIssuer("CUP");//choose the issuer(CUP,MASTER,VISA,JCB) 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### PreAuth Void New Request
```
PreAuthVoidNewMsg.Request request = new PreAuthVoidNewMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24");
request.setTotalTxnAmount(10000);
request.setPreAuthID1("123456");
//preAuth ID1 request.setPreAuthID2("654321");//preAuth ID2 
ITransAPI transAPI =TransAPIFactory.createT
PreAuthVoidNewMsg.Request request = new PreAuthVoidNewMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24");
request.setTotalTxnAmount(10000); 
request.setPreAuthID1("123456");
//preAuth ID1 request.setPreAuthID2("654321");//preAuth ID2 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### PreAuth Completion New Transaction Request
```
PreAuthCompMsg.Request request = new PreAuthCompMsg.Request(); 
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24");
request.setTotalTxnAmount(10000); 
request.setUid("1234");//Unique id
request.setPreAuthID1("123456");//preAuth ID1 request.setPreAuthID2("654321");//preAuth ID2
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);boolean ret = transAPI.doTrans(request);
PreAuthCompMsg.Request request = new PreAuthCompMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(10000); 
request.setUid("1234");//Unique id
request.setPreAuthID1("123456");//preAuth ID1 
request.setPreAuthID2("654321");//preAuth ID2 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);boolean ret = transAPI.doTrans(request);

```

### PreAuth Completion Void Request
```
PreAuthCompVoidMsg.Request request = new PreAuthCompVoidMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setUid("1234");//Unique id request.setTerminalInvoiceNo(1);
//orig invoice no request.setPackageName("com.pax.fdms.base24");
 ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);
PreAuthCompVoidMsg.Request request = new PreAuthCompVoidMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setUid("1234");//Unique id 
request.setTerminalInvoiceNo(1);//orig invoice no 
request.setPackageName("com.pax.fdms.base24"); 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);boolean ret = transAPI.doTrans(request);
PreAuthCompVoidMsg.Request request = new PreAuthCompVoidMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setUid("1234");//Unique id 
request.setTerminalInvoiceNo(1);//orig invoice no request.setPackageName("com.pax.fdms.base24"); 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### PreAuth Completion Void New Request
```
PreAuthCompVoidNewMsg.Request request = new PreAuthCompVoidNewMsg.Request(); 
request.setAppId("com.pax.fdms.base24"); 
request.setUid("1234");//Unique id ，Optional 
request.setTotalTxnAmount(10000); 
request.setPreAuthID1("123456");//preAuth ID1 
request.setPreAuthID2("654321");//preAuth ID2 
request.setPackageName("com.pax.fdms.base24");
ITransAPI transAPI =TransAPIFactory.reateTransAPI(MainActivity.this);
PreAuthCompVoidNewMsg.Request request = new PreAuthCompVoidNewMsg.Request(); 
request.setAppId("com.pax.fdms.base24"); 
request.setUid("1234");//Unique id ，Optional 
request.setTotalTxnAmount(10000);
request.setPreAuthID1("123456");//preAuth ID1 
request.setPreAuthID2("654321");//preAuth ID2 
request.setPackageName("com.pax.fdms.base24"); 
ITransAPI transAPI =TransAPIFactory.create TransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### Settlement Transaction Request
```
SettleMsg.Request request = new SettleMsg.Request(); 
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24"); 
request.setAcqName("FDMS-CUP");
request.setPrint(false);
request.setShowDetail(false);
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);
SettleMsg.Request request = new SettleMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24"); 
request.setAcqName("FDMS-CUP"); 
request.setPrint(false);
request.setShowDetail(false);
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### PreAuth Topup Msg Request
```
preauthTopUpMsg.Request request = new PreauthTopUpMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(10000); 
request.setUid("1234");//Unique id request.setTerminalInvoiceNo(1);//orig invoice no 
request.setAuthCode("123456");//orig approve code 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

preauthTopUpMsg.Request request = new PreauthTopUpMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(10000);
request.setUid("1234");//Unique id request.setTerminalInvoiceNo(1);
//orig invoice no request.setAuthCode("123456");
//orig approve code 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);
preauthTopUpMsg.Request request = new PreauthTopUpMsg.Request();
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(10000); 
request.setUid("1234");//Unique id 
request.setTerminalInvoiceNo(1);//orig invoice no 
request.setAuthCode("123456");//orig approve code 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```
### Instalment Transaction Request
```
InstalmentMsg.Request request = new InstalmentMsg.Request(); 
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(10000); 
ITransAPItransAPI=TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### Request
The table below identifies the required properties in the request message

| Variable |  Type | Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- |------------------ | ------------------ |
|` appId`|String|20|M|FAMS_BASE24 App ID|
|`packageName`|String|20|M|FAMS_BASE24 App Package Name|
|`tipAmount`|String|10|O|Transaction Tip Amount for sale|
|`InvoiceNo`|String|6|M|6 digits invoicenumber for void transaction|
|`type`|String|2|M|Use type to indicate the print details
| | | | | 1- Current summary batch |
| | | | |2- Current detail |
| | | | | 3- Last settlement |
|`totalTxnAmount`|String|10|M|Total Amount in decimals - "100.00"|
|`acquirerName`|String|20|M|Acquirer Name for settlement or print|
|`staffId`|String|20|O|Option for offline transaction|
|`rText`|String|20|O|Option for offline transaction|
|`showDetail`|Boolean|5|O|Option for void and settle|
|`authCode`|String|8|M|Use for Preauth cancel/ Top up / Preauth Completion transaction|
|`uid`|String|8|O|Unique id for each transaction|
|`isPrint`|Boolean|2|O|Chargeslip - Print or Not|
|`isQfpay`|Boolean|4|O|For sale transaction,used for Qfpay|
|`newTotal`|Long|10|M|New Total for Adjustment Amount|
|`isMicors`|Boolean|10|O|For OPI Transaction|
|`DeviceId`|String|10|O|For OPI Transaction|
|`requestId`|String|10|O|For OPI Transaction|
|`sequenceNum`|String|20|O|For OPI Transaction|



### Response in Payload
### Sale Response
```
SaleMsg.Response response = (SaleMsg.Response) transAPI.onResult(requestCode, resultCode, data);
if (resultCode == RESULT_OK && response != null) { 
if (response.getRspCode() == 0) { 
    String respMsg = response.getRspMsg();
    String merchantName = response.getMerchantName(); 
    String merchantId = response.getMerchantId(); 
    String appId = response.getAppId(); 
    String acuquirerName = response.getAcquirerName(); 
    String issuerName = response.getIssuerName();
    long batchNo = response.getBatchNo(); 
    long traceNo = response.getTraceNo();
    SaleMsg.Response response = (SaleMsg.Response) transAPI.onResult(requestCode, resultCode, data);
    if (resultCode == RESULT_OK && response != null) { 
        if (response.getRspCode() == 0) { 
            String respMsg = response.getRspMsg(); 
            String merchantName = response.getMerchantName(); 
            String merchantId = response.getMerchantId(); 
            String appId = response.getAppId(); 
            String acuquirerName = response.getAcquirerName(); 
            String issuerName = response.getIssuerName(); 
            long batchNo = response.getBatchNo(); 
            long traceNo = response.getTraceNo();
            String amount = response.getAmount ();
            String appCode = response.getAppCode();
            String refNo = response.getRefNo();
            String cardNo = response.getCardNo();
            String tipAmount = response.getTipAmount();
            String app = response.getApp();
            String aid = response.getAid();
            String tc = response.getTc();
            String tvr = response.getTvr();
            String tsi = response.getTsi();
            String atc = response.getAtc();
            String enterMode = response.getEnterMode();
            String localCurrCode = response.getLocalCurrCode();
            String cardholderCode = response.getCardholderCode();
            String fxRate = response.getFxRate();
            String foreignAmt = response.getDccTransAmt();
            String expDate = response.getExpDate();
            String currency = response.getCurrency();
            boolean dccFlag = response.isDccFlag();
            boolean pinVerify = response.isPinVerify();
            boolean signatureVer = response.isSignatureVer();
            String signData = response.getSignData();
            } else {
            Log.d("response", response.getRspMsg());
            }
            } else {
            Log.d("response", "transaction failed");
            }

```

### Settlement Response
```
SettleMsg.Response responseList = (SettleMsg.Response)
transAPI.onResult(requestCode, resultCode, data);
if (resultCode == RESULT_OK && responseList != null) {
List<GetTotalMsg.Response> responses =
responseList.getAllResponses();
String responseMsg = responseList.getRspMsg();
String appId = responseList.getAppId();
if (responses!=null && responses.size() != 0) {
for (GetTotalMsg.Response response : responses) {
String merchantName = response.getMerchantName();
String merchantId = response.getMerchantId();
String acquirerName = response.getAcquirerName();
long batchNo = response.getBatchNo();
long saleTotalAmt = response.getSaleTotalAmt();
long saleTotalNum = response.getSaleTotalNum();
long saleVoidTotalAmt = response.getSaleVoidTotalAmt();
long saleVoidTotalNum = response.getSaleVoidTotalNum();
long refundTotalAmt = response.getRefundTotalAmt();
long refundVoidTotalAmt = response.getRefundVoidTotalAmt();
long refundVoidTotalNum = response.getRefundVoidTotalNum();
String settleMsg = response.getSettleMsg();
int rspCode = response.getRspCode();
String rspMsg = response.getRspMsg()；
}
} else {
Log.d("response", responseList.getRspMsg());
}
} else {
Log.d("response", "transaction failed");
}

```

### Instalment Response
```
InstalmentMsg.Response response = (InstalmentMsg.Response)
transAPI.onResult(requestCode, resultCode, data);
if (resultCode == RESULT_OK && response != null) {
if (response.getRspCode() == 0) {
String respMsg = response.getRspMsg();
String merchantName = response.getMerchantName();
String merchantId = response.getMerchantId();
String appId = response.getAppId();
String acuquirerName = response.getAcquirerName();
String issuerName = response.getIssuerName();
long batchNo = response.getBatchNo();
long traceNo = response.getTraceNo();
String amount = response.getAmount ();
String authCode = response.getAppCode();
String refNo = response.getRefNo();
String cardNo = response.getCardNo();
String tenure = response.getTenure();
String productCode = response.getProductCode();
String insterestAmt = response.getInterestAmt();
String monthlyAmt = response.getEmiPerMonth();
String expDate = response.getExpDate();
String currency = response.getCurrency();
boolean dccFlag = response.isDccFlag();
boolean pinVerify = response.isPinVerify();
boolean signatureVer = response.isSignatureVer();
String signData = response.getSignData();
} else {
Log.d("response", response.getRspMsg());
}
} else {
Log.d("response", "transaction failed");
}

```

### Response
The below table identifies the required properties in the response message

| Variable |	Type |	Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- | ------------------ | ------------------ |
|`appId`|String|20||FAMS_BASE24 App Id|
|`rspCode`|String|20|M|Description of the response code|
|`issuerName`|String|20|M|Issuer name|
|`acquirerName`|String|20|M|Acquirer name|
|`refNo`|String|10|M|Reference No|
|`transTime`|String|20|M|Transaction time|
|`amount`|String|10|M|Transaction amount|
|`appCode`|String|8|M|Approval code of the transaction|
|`signature`|String|3|O|Signature data|
|`referNo`|String|10|O|Reference  No|
|`traceNo`|String|6|O|6 digits  trace number|
|`batchNo`|String|6|M|6 digits batch number|
|`merchantName`|String|20|M|Merchant name|
|`merchantId`|String|8|M| 15 digits Merchant ID|
|`cardNo`|String|16|M|Card  No|
|`terminalId`|String|15|M|8 digits Terminal ID|
|`saleTotal Amt`|String|10|O|Total sale amount|
|`saleTotalNum`|String|10|O|Total sale number|
|`saleVoidTotalAmt`|String|10|O|Total void sale amount|
|`saleVoidTotalNum`|String|10|O|Total void  sale number|
|`refundTotal Amt`|String|10|O|Total refund amount|
|`refundTotalNum`|String|10|O|Total refund number|
|`refundVoidTotalAmt`|String|10|O|Total void refund amount|
|`refundVoidTotalNum`|String|10|O|Total void refund number|
|`settleMsg`|String|2|O|Settlement message|
|`cardholderName`|String|20|O|Cardholder name|
|`tipAmount`|String|10|O|Transaction tip amount|
|`enterMode`|String|1|O|1 digits entry mode:|
| | | | | “F”- Fallback|
| | | | | “S” - Swipe |
| | | | | “C” - Insert |
| | | | |“T”- Contactless |
| | | | | “M” - Manual|
|`app`|String|5|O|EMV application label name|
|`aid`|String|16|O|16 digits EMV application ID|
|`tc`|String|16|O|16 digits EMV  transaction cryptogram|
|`tvr`|String|10|O|10  digits EMV terminal  verification result|
|`tsi`|String|4|O|4 digits EMV transaction status information|
|`atc`|String|2|O|2 digits EMV Application transaction counter |
|`localCurrCode`|String|3|O|Local currency code.For Dcc txn|
|`cardholderCode`|String|3|O|Cardholder currency code.For Dcc  txn|
|`fxRate`|String|6|O|Rate.For Dcc txn|
|`foreignAmt`|String|10|O|Cardholder currency Amount.For Dcc txn|
|`tenure`|String|3|O|For instalment txn|
|`productCode`|String|3|O|For instalment txn|
|`interestAmt`|String|10|O|For instalment txn.For instalment String monthly Amt|
|`deviceId`|String|10|O|For  OPI transaction|
|`requestId`|String|10|O|For  OPI transaction|
|`deviceSN`|String|10|O|Serial Number|
|`flagNac`|Boolean|2|O|For  OPI transaction|
|`isMicros`|Boolean|2|O|To enable Micros solution|
|`token`|String|10|O|For OPI,MT token|
|`sequenceNum`|String|10|O|For  OPI transaction|
|`dccFlag`|Boolean|2|O|If it is Dcc transaction,it is 'True'|
|`pinVerify`|Boolean|2|O|Pin entered,it is 'TRUE'|
|`expDate`|String|4|O|Expiry Date|
|`currency`|String|3|O|Currency code|
|`signed`|Boolean|5|O|If have signature,it is 'TRUE'|
|`signedData`|String|5|O|The data in receipt|
|`reservedData`|String|10|O|For OPI , the value is json format which includes “MTTokenIssuerID""|

The table below provides the list of application's error code and its description.

| ErrorCode |  Description / Values | Comments |
| --------  | ------------------ | ---------- |
|`00`|Approved or completed successfully|Merchant should go ahead with reciept generation|
|`01`|Refer to card issuer, Cardholder to contact Issuing Bank|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`02`|Refer to card issuer, special condition|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`03`| Invalid merchant|Contact Customer Support / Business Manager|
|`04`|Pick-up card|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`05`|Do not honour, Cardholder to contact Issuing bank|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`06`|Error|Contact Customer Support / Business Manager|
|`07`|Pick-up card, special condition|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`08`| Honour with identification|Merchant should Confirm cardholder ID/verification|
|`09`|Request in progress|Merchant should Wait for transaction completion|
|`10`|Approved, partial|Contact Customer Support / Business Manager|
|`11`|Approved, VIP|Contact Customer Support / Business Manager|
|`12`|Invalid transaction|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`13`|Invalid amount|Merchant should key valid amount|
|`14`|Invalid card number|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`15`|No such issuer|Contact Customer Support / Business Manager|
|`19`|Re - enter transaction|Contact Customer Support / Business Manager|
|`20`|Invalid response|Contact Customer Support / Business Manager|
|`21`|Card Not Initialized|Issuer Decline. Card is not activated (for CUP)|
|`22`|Suspected malfunction|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`25`| Unable to locate Original Transaction|Contact Customer Support / Business Manager|
|`30`|Format Error|Contact Customer Support / Business Manager|
|`31`|Bank not supported|Contact Customer Support / Business Manager|
|`32`|Expired card, pick-up|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`33`|Suspected fraud, pick-up|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`34`|Fraud|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`36`|Restricted card, pick-up|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`38`|PIN tries exceeded|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`39`|No credit account|Issuer Decline. No money/Debit card (Visa only)|
|`40`|Function not supported|Contact Customer Support / Business Manager|
|`41`|Lost card|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`42`|No universal account|Small bank not international (Only JCB)|
|`43`|Stolen card|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`45`|Fallback not allowed|Contact Customer Support / Business Manager|
|`51`|Not sufficient funds|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`52`|No check account|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`53`|No savings account|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`54`|Expired card|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`55`|Incorrect PIN|Issuer Decline. Merchant should advise cardholder to key correct pin for transaction|
|`56`|No card record|Bank is offline / Retry later(Only for JCB)|
|`57`|Transaction not permitted to cardholder|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`58`|Transaction not permitted to terminal|Contact Customer Support / Business Manager|
|`59`|Suspected fraud|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`61`|Exceeds withdrawal limit|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`62`|Restricted card|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`63`|Security violation|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`64`|Original amount incorrect|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`65`|Exceeds withdrawal frequency|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`68`|Issuer Response Timed-out|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`75`|PIN tries exceeded|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`77`|Intervene, bank approval required|Visa, MC and JCB has different meaning. But overall, it is decline.|
|`78`|Intervene, bank approval required|Visa, MC and JCB has different meaning. But overall, it is decline.|
|`85`|Not declined|AVS with zero amount|
|`90`|Cut-off in progress|Contact Customer Support / Business Manager|
|`91`|Issuer or switch inoperative|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`92`|Routing Error|Contact Customer Support / Business Manager|
|`94`|Duplicate Transaction|Issuer Decline. Merchant should advise cardholder to use different card for transaction|
|`95`|Reconcile error|Contact Customer Support / Business Manager|
|`96`|System Error|Contact Customer Support / Business Manager|
|`99`|PIN Block error|Issuer Decline. Merchant should advise cardholder to use different card for transaction|