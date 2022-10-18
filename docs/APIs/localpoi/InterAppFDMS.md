# Inter-Application Integration
Inter-application Integration provides a seamless integration between the Fiserv payment application and the merchant application locally installed in android-based terminals. E.g. A biller can integrate with a payment application and complete the payment transaction.

Financial payment transactions that are supported by inter-application to billers include functions like Sale, Pre-Authorisation Sale, Pre-Authorisation Completion, Transaction Status Check, Installment Sale, Void, Refund, Adjust, Settlement and Offline Transactions.


## How it works
For a normal Sale request, the supported functionalities are listed below. 

- Card Transaction (navigating to direct card payment application) 

For digital transactions, the supported functionalities are listed below.

<table border="0">
  <tr>
    <th>Value Added Services</th>
    <th> Rest of APAC <br>(SG, HK, MY) </th>
     </tr>
    <tr>
    <td>WeChat</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Alipay</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>FPS</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>GrabPay</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>CUP QR (UnionPay QR)</td>
    <td align="center">&#10004;</td>
    </tr>
    </table>

  For a normal Sale request, the supported functionalities are listed below.
    
    
 <table border="0">
    <tr>
    <th>Transactions Supported</th>
    <th> Rest of APAC (SG, HK, MY)  </th>
     </tr>
    <tr>
    <td>Pre-Authorization Sale</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale cancellation</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale completion</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale completion / cancellation</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Sale</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Void</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Offline Sale</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Tip Adjustment</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Refund</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Pre-Authorization Sale completion offline</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Installment / EMI</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>Installment Sale Cancellation</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>MOTO Pre-Authorization</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>MOTO Pre-Authorization Cancellation</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>
    <td>MOTO Pre-Authorization completion</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>MOTO Pre-Authorization Completion / Cancellation</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>MOTO Sale</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>MOTO Sale Cancellation </td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>MOTO Refund</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Void Refund</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Cash Advance / Cash withdrawal</td>
    <td align="center"></td>
    </tr>
    <tr>   
    <td > Cash Only</td>
    <td align="center"></td>
    </tr>
    <tr>   
    <td>Purchase with Cashback</td>
    <td  align="center"></td>
    </tr>
    <tr>   
    <td>Settlement / Batch Upload</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>DCC (Dynamic Currency Conversion)</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Pre-Authorization Top-Up (Incremental Auth)</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Balance Inquiry</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Settlement report / Detail report</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Reprint</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Reprint Total</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>View History</td>
    <td align="center">&#10004;</td>
    </tr>
    <tr>   
    <td>Get Transaction Record</td>
    <td align="center">&#10004;</td>
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

### Pre-Authorization Sale Request
```
PreAuthMsg.Request request = new PreAuthMsg.Request();
request.setAppId("com.pax.fdms.base24");
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(222);
request.setUid("1234");//Unique id 
ITransAPI transAPI =TransAPIFactory.createTransAPI(MainActivity.this);boolean ret = transAPI.doTrans(request);

```
### Pre-Authorization Completion Request
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

### Pre-Authorization Void Request
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

### Pre-Authorization Void New Request
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

### Pre-Authorization Completion New Transaction Request
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

### Pre-Authorization Completion Void Request
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

### Pre-Authorization Completion Void New Request
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

### Pre-Authorization Topup Request
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
### Installment Request
```
InstallmentMsg.Request request = new InstallmentMsg.Request(); 
request.setAppId("com.pax.fdms.base24"); 
request.setPackageName("com.pax.fdms.base24"); 
request.setTotalTxnAmount(10000); 
ITransAPItransAPI=TransAPIFactory.createTransAPI(MainActivity.this);
boolean ret = transAPI.doTrans(request);

```

### Request
The table below identifies the required properties in the request message

| Variable |  Type | Length | Mandatory / Optional / Conditional <br> (M / O / C) | Description / Values |
| -------- | ------- | ------- |------------------ | ------------------ |
|` appId`|String|20|M|FAMS_BASE24 App ID.|
|`packageName`|String|20|M|FAMS_BASE24 App Package Name.|
|`tipAmount`|String|10|O|Transaction Tip Amount for sale.|
|`InvoiceNo`|String|6|M|6 digits invoicenumber for voiding a transaction.|
|`type`|String|2|M|Use type to indicate the print details
| | | | | 1- Current summary batch. |
| | | | |2- Current detail. |
| | | | | 3- Last settlement. |
|`totalTxnAmount`|String|10|M|Total Amount in decimals - "100.00".|
|`acquirerName`|String|20|M|Acquirer Name for settlement or print.|
|`staffId`|String|20|O|Optional field in an offline transaction.|
|`rText`|String|20|O|Optional field in an offline transaction.|
|`showDetail`|Boolean|5|O|Optional field for Void transaction and settlement.|
|`authCode`|String|8|M| Mandatory field for 
| | | | | . Pre-Authorization Cancellation, or |
| | | | | . Top-up transaction, or | 
| | | | | . Pre-Authorization Completion transaction.| 
|`uid`|String|8|O|Unique ID or each transaction.|
|`isPrint`|Boolean|2|O|To enable charge slip printing - Y or N.|
|`isQfpay`|Boolean|4|O|For sale transaction for transactions through Qfpay supported applications.|
|`newTotal`|Long|10|M|Updated total for the Adjustment Amount.|
|`isMicors`|Boolean|10|O|Micros enabled – an optional field for Oracle Payment Interface (OPI) applicable transactions.|
|`DeviceId`|String|10|O|Device ID – an optional field for Oracle Payment Interface (OPI) applicable transactions. |
|`requestId`|String|10|O|Request ID – an optional field for Oracle Payment Interface (OPI) applicable transactions. |
|`sequenceNum`|String|20|O|Sequence Number – an optional field for Oracle Payment Interface (OPI) applicable transactions.|



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

### Installment Response
```
InstallmentMsg.Response response = (InstallmentMsg.Response)
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
|`appId`|String|20||FAMS_BASE24 App Id.|
|`rspCode`|String|20|M|Description of the response code.|
|`issuerName`|String|20|M|Issuer name.|
|`acquirerName`|String|20|M|Acquirer name.|
|`transTime`|String|20|M|Transaction time.|
|`amount`|String|10|M|Transaction amount.|
|`appCode`|String|8|M|Approval code of the transaction.|
|`signature`|String|3|O|Signature data.|
|`referNo`|String|10|O|Reference Number.|
|`traceNo`|String|6|O|Trace Number (6-digit value). |
|`batchNo`|String|6|M| Batch Number (6-digit value). |
|`merchantName`|String|20|M|Merchant name.|
|`merchantId`|String|8|M| Merchant ID (15-digit value). |
|`cardNo`|String|16|M|Card Number.|
|`terminalId`|String|15|M| Terminal ID (8-digit value). |
|`saleTotal Amt`|String|10|O|Total sale amount.|
|`saleTotalNum`|String|10|O|Total sale number.|
|`saleVoidTotalAmt`|String|10|O|Total void sale amount.|
|`saleVoidTotalNum`|String|10|O|Total void  sale number.|
|`refundTotal Amt`|String|10|O|Total refund amount.|
|`refundTotalNum`|String|10|O|Total refund number.|
|`refundVoidTotalAmt`|String|10|O|Total void refund amount.|
|`refundVoidTotalNum`|String|10|O|Total void refund number.|
|`settleMsg`|String|2|O|Settlement message.|
|`cardholderName`|String|20|O|Cardholder name.|
|`tipAmount`|String|10|O|Transaction tip amount.|
|`enterMode`|String|1|O|Entry mode:(1-character value)|
| | | | | F=Fallback|
| | | | | S=Swipe |
| | | | | C= Insert |
| | | | | T=Contactless |
| | | | | M= Manual|
|`app`|String|5|O|EMV application label name.|
|`aid`|String|16|O| EMV application ID(16-digit value).|
|`tc`|String|16|O|EMV  transaction cryptogram (16-digit value).|
|`tvr`|String|10|O| EMV terminal  verification result(10-digit value).|
|`tsi`|String|4|O|EMV transaction status information (4-digit value). |
|`atc`|String|2|O|EMV Application transaction counter (2-digit value). |
|`localCurrCode`|String|3|O|Local currency code for DCC transactions.|
|`cardholderCode`|String|3|O|Cardholder currency code.For Dcc transactions.|
|`fxRate`|String|6|O|Exchange rate for Dcc transactions. |
|`foreignAmt`|String|10|O|Amount in cardholder’s home currency for DCC transaction.|
|`tenure`|String|3|O|Installment / EMI duration. If Installment / EMI transactions are included.|
|`productCode`|String|3|O|Product code for Installment / EMI transactions if these transactions when applicable.|
|`interestAmt`|String|10|O|Monthly installment / EMI interest amount.|
|`deviceId`|String|10|O|Device ID – an optional field for Oracle Payment Interface (OPI) applicable transactions. |
|`requestId`|String|10|O|For  OPI transaction.|
|`deviceSN`|String|10|O|Terminal device serial Number.|
|`flagNac`|Boolean|2|O|Flag NAC – an optional field for Oracle Payment Interface (OPI) applicable transactions. |
|`isMicros`|Boolean|2|O|Micros enabled – an optional field for Oracle Payment Interface (OPI) applicable transactions. |
|`token`|String|10|O|Micros Token value – an optional field for Oracle Payment Interface (OPI) applicable transactions.|
|`sequenceNum`|String|10|O|Sequence Number – an optional field for Oracle Payment Interface (OPI) applicable transactions.|
|`dccFlag`|Boolean|2|O|DCC Conversion flag - Yes or No. Response contains converted amount, exchange rate and margin fee.|
|`pinVerify`|Boolean|2|O|PIN will be validated when value is set = ‘True’.|
|`expDate`|String|4|O|Expiry Date.|
|`currency`|String|3|O|Currency code / currency that had been selected.|
|`signed`|Boolean|5|O|If the signature is captured, the value will be ‘True’ for this field.|
|`signedData`|String|5|O|The signature data field captured in the receipt.|
|`reservedData`|String|10|O|This is in json format, and it includes the ‘MTTokenIssuerID’ value – an optional field for Oracle Payment Interface (OPI) applicable transactions.|

The table below provides the list of application's error code and its description.

| Error Code |  Description / Values | Comments |
| --------  | ------------------ | ---------- |
|`00`|Transaction is approved / successful.|Request had been approved. Merchant should go ahead with receipt generation.|
|`01`|Cardholder to contact Issuing Bank|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`02`|Special condition, cardholder to contact Issuing Bank|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`03`| Invalid merchant|Contact Customer Support / Business Manager.|
|`04`|Pick-up card|Issuer Declined the transaction. Merchant should advise cardholder to use a different valid card for the transaction.|
|`05`|Do not honour, cardholder to contact Issuing bank|Issuer declined the transaction.Merchant should advise cardholder to use a different valid card for the transaction.|
|`06`|Error|Issuer declined the transaction. Merchant should advise cardholder to use a different valid card for the transaction.|
|`07`|Pick-up card, special condition|Issuer declined the transaction. Merchant should advise cardholder to use a different valid card for the transaction.|
|`08`| Honour with identification|Merchant should confirm cardholder's ID/verification.|
|`09`|Request in progress|Transaction request in progress, merchant should wait for transaction completion.|
|`10`|Partial approval|Contact Customer Support / Business Manager.|
|`11`|Approved(V.I.P)|Contact Customer Support / Business Manager.|
|`12`|Invalid Transaction|Issuer declined the transaction.Merchant should advise cardholder to use a different card for the transaction.|
|`13`|Invalid amount|Invalid amount or currency conversion field overflow. Merchant should enter a valid amount.|
|`14`|Invalid account|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`15`|No such issuer|Cannot verify PIN; for example, no PVV Contact Customer Support / Business Manager.|
|`19`|Re-enter transaction|Contact Customer Support / Business Manager.|
|`20`|Invalid response|Contact Customer Support / Business Manager.|
|`21`|Card not Initialized|Issuer declined the transaction.For CUP transaction – this means the card had not been activated. Merchant should advise cardholder to use a different card for the transaction.|
|`22`|Suspected malfunction|Issuer declined the transaction.Merchant should advise cardholder to use a different card for the transaction.|
|`25`| Unable to locate the original transaction|Contact Customer Support / Business Manager.|
|`30`|Invalid message format|Invalid message format received. Contact Customer Support / Business Manager.|
|`31`|Bank not supported|Merchant should advisent should advise cardholder to use a different card for the transaction.|
|`32`|Expired card, pick-up|Issuer declined the transaction.Merchant should advise cardholder to use a different card for the transaction.|
|`33`|Suspected fraud, pick-up|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`34`|Fraud|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`36`|Restricted card, pick-up|Issuer declined the transaction.Merchant should advise cardholder to use a different card for the transaction.|
|`38`|PIN tries exceeded|Issuer Decline. Merchants cardholder to use a different card for the transaction. Contact Customer Support|
|`39`|No credit account|Issuer Decline. Merchant should advise cardholder to use a different card for the transaction. |
|`40`|Function not supported|Requested function is not supported. Contact Customer Support / Business Manager.|
|`41`|Lost card,pick up|Lost card, contact Customer Support / Business Manager.|
|`42`|No universal account|Credit account does not exist at the issuing bank. Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`43`|Stolen card|Issuer Decline. Merchant should advise cardholder to use different card for transaction.|
|`45`|Fallback not allowed|Contact Customer Support / Business Manager|
|`51`|Insufficient funds|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`52`|No checking account|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`53`|No savings account|Issuer Decline. Merchant should advise cardholder to use different card for transaction.|
|`54`|Expired card|Issuer Decline. Merchant should advise cardholder to use different card for transaction.|
|`55`|Incorrect PIN|Issuer declined the transaction. Merchant should advise cardholder to retry with the correct PIN.|
|`56`|No card record|(Applicable for JCB transactions only) Bank offline please retry later or use another card.|
|`57`|Transaction not permitted to cardholder|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`58`|Transaction not permitted to terminal|Contact Customer Support / Business Manager.|
|`59`|Suspected Fraud|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`61`|Exceed withdrawal account limit|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`62`|Restricted card|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`63`|Security violation|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`64`|Original amount incorrect|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`65`|Exceeds withdrawal frequency limit|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`68`|Response received too late, reversal (unsupported)|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`75`|Allowable number of PIN tries exceeded|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`77`|Bank approval required|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction. (Decline reasons may vary for different schemes)|
|`78`|Bank approval required|Issuer declined the transaction.Merchant should advise cardholder to use a different card for the transaction. (Decline reasons may vary for different schemes)|
|`85`|Transaction not declined|Issuer has no reason to decline the transaction (Account Verification).|
|`90`|Cut-off in progress|Contact Customer Support / Business Manager.|
|`91`|Issuer or switch inoperative|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`92`|Routing Error|Contact Customer Support / Business Manager.|
|`94`|Duplicate Transaction|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`95`|Reconcile error|Contact Customer Support / Business Manager.|
|`96`|System Error|Contact Customer Support / Business Manager.|
|`99`|PIN Block error|Issuer Decline. Merchant should advise cardholder to use different card for transaction.|
