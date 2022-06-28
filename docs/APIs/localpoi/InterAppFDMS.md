# Inter-Application Integration
Inter-Application integration can facilitate processing of various payment transactions from Fiserv payment terminal.
E.g. Biller can integrate with payment app and complete the payment transaction.

Financial payment transactions supported by Interapp to biller: Sale, Void, Refund, Offline, Adjust, PreAuth, PreAuth Void, PreAuth Complete, PreAuth Complete Void, Settlement.

## How it works
•	In Normal Sale request will show the below options for sale 
        o	Card Transaction (navigating to direct card payment application)

### Payload Examples

### Request Payload

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
The below table identifies the required properties in the request message

| Variable |  Type | Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- |------------------ | ------------------ |
| `appId`	 | String |  20 | M	| FAMS_BASE24 App ID |
| `packageName`	| String | 20	 |	M | FAMS_BASE24 App Package Name |
| `tipAmount`  | String	| 10 |  O |	Transaction Tip Amount for sale |
| `InvoiceNo`  | String | 6|	M	| 6digitsinvoicenumberforvoidtransaction |
| `type`  |	String | 2 |	M |	Use type to indicate the printdetails |
| `totalTxnAmount`  | String | 10 | M |	Transaction amount |
| `acquirerName` | String  | 20 | M	|	Acquirer Name for settlement or print |
| `staffId`  | String | 20	| 	O |	max20 characters ( opt ) for offline |
| `rText`  | String  | 20	| 	O | max20 characters ( opt ) for offline |
| `showDetail` | Boolean | 5  |	O |	For void and settle |
| `authCode` |	String	|  8 |	M  | Use for preauth cancel/topUp/comp |
| `uid` | String | 8 | O 	| Uniqueid for each transaction |
| `isPrint` | Boolean | 2 | O 	| Print |
| `isQfpay` | Boolean  | 4 | O | For sale transaction,use for Qfpay |
| `newTotal` | Long	 |  10 |M	 | New Total for Adjust |
| `isMicors` | Boolean | 10 | O | For OPI Transaction Source |
| `deviceId` | String |	 10 | O	 | For OPI Transaction |
| `grequestId` | String	| 10 | O | For OPI Transaction |
| `sequenceNum` | String | 20 |	O 	 |For OPI Transaction |



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
| `App Id` |	String	 | 20 |	M	 | FAMS_BASE24 App ID |
| `Rsp Msg` |	String	 | 20 |	M	 | Description of the response code |
|`Intrsp Code` |	String |	4 |	O |	Response code |
| `Issuer Name` |	String	| 20 |	M  | Issuer name |
|  `Acquirer Name` |	String | 20 | M	| Acquirer name |
| `Ref  No` |	String | 10 |	M |	Reference No |
| `Trans Time` |	String |	20 |	M |	Transaction time |
| `Amount` |	String |	10 |	M |	Transaction amount |
| `AppCode` |	String |	8 |	M |	 Approval code of the transaction|
| `Signature`	 | String |	3	 | O |	Signature data |
| `ReferNo` |	String |	10 |	O |	Reference  No |
| `TraceNo` |	String |	6 |	O	 |6 digits  traceno|
| `BatchNo` |	String |	6	 |M	 | 6 digits batch no |
| `Merchant Name`	| String |	20 |	M |	Merchant name |
|`Merchant Id` |	String |	8	 |M	  |15 digits Merchant ID |
| `Card No`	 |String |	16 |	M |	Card  No |
| `Terminal Id` |	String	 |15 |	M |	8 digits Terminal ID|
|`Sale Total Amt` |	String |	10 |	O |	Total sale amount |
| `Sale Total Num` |	String	| 10 |	O	 | Total sale number |
| `Sale Void Total Amt` |	String |	10	| O	 |Total void sale amount |
| `Sale Void Total Num` |	String |	10 |	O |	Total void  sale number |
| `Refund Total Amt` |	String |	10	 | O |	Total refund amount |
| `Refund Total Num`	 | String |	10 |	O |	Total refund number |
 |`Refund  Void Total Amt` |	String	 | 10	| O |	Total void refund amount|
| `Refund Void Total Num`	 |String	 | 10	 | O |	 Total void refund number|
| `SettleMsg` |	String |	2 |	O |	Settlement message |
| `CardholderName` |	String |	20 |	O |	Cardholder name |
 |`TipAmount` |	String |	10 |	O |	Transaction tip amount|
| `App` |	String	| 5	 | O |	EMV application label name |
 |`Aid` |	String	| 16 |	O |	16 digits EMV application ID |
| `TC` |	String |	16	 | O |	16 digits EMV  transaction cryptogram|
| `TVR` |	String |	10 |	O	 | 10  digits EMV terminal  verification result|
 |`TSI` |	String |	4	| O	 | 4 digits EMV transaction status information|
 |`ATC` |	String	| 2	 |O	 |2 digits EMV Application transaction counter| 
 |`Local Curr Code` |	String	| 3	 |O	 |Local currency code. For Dcc txn|
 |`Cardholder Code` |	String	| 3	 |O	 |Cardholder currency code. For Dcc  txn|
 |`Fx Rate` |	String	| 6	 |O	 |Rate.For Dcc txn |
 |`Foreign  Amt` |	String	|10	|O|	Cardholder currency Amount.For Dcc txn|
 |`Tenure` |	String	|3 |	O | 	For instalment txn |
 |`Product Code` |	String	|3	|O|	For instalment txn |
 |`Interest Amt` |	String |	10 |	O	|For instalment txn.For instalment String monthly Amt|
 |`DeviceId` |	String |	10	|O	|For  OPI|
 |`RequestId` |	String	|10	| O |	For OPI|
 |`DeviceSN` |	String	|10|	O|	Serial Number|
| `FlagNac` |	Boolean	|2	|O|	For OPI|
 |`IsMicros` |	Boolean |	2	|O|	Micros solution is enable|
 |`Token`	 | String	|10 |	O |	For OPI,MT token|
 |`SequenceNum` |	String	| 10|	O	|For OPI|
 |`DccFlag` |	Boolean |	2	|O |	If it is Dcc transaction, it is 'True'|
|`PinVerify` |	Boolean |	2 |	O	|Pin entered, it is 'TRUE'|
| `ExpDate` |	String	|4 |	O	|Expire Date |
 |`Currency` |	String	| 3	 |O |	Currency code |
 |`Signed` |	Boolean	|5	|O	|If have signature,it is 'TRUE'|
 |`SignData` |	String	|5|	O|	The data in receipt|



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







