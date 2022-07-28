# USB / Static Wi-fi

USB / Static Wi-fi is an integration between system to APOS device. E.g., Biller can integrate with payment app and complete the payment transaction.

Financial payment transactions supported by USB / Static Wi-fi to biller: Sale, PreAuth Sale, PreAuth Completion, Transaction Status Check, EMI Sale, Void, Settlement, Bharat QR code generation.

## How it works
-	System Requirements to setup USB / Static Wi-fi
    -	OS: Windows 8 and above
    -	Cable: Micro USB Data Cable for RS232 Serial communication.
    -	Wi-Fi: Same Wi-Fi connectivity for Socket communication for Both PAX and Integrating APPs
    -	JDK Version: JDK 1.8.0 version or above (64 bit or 32 bit)
    -	Other Libs: (Available in Windows as javax.mail.jar)
    -	Use any serial lib for java that should support window platform
    -	Get a list of available port name and select comm port no
    -	Open VSP (Virtual Serial Port ) 
    -	PAX Use the following detail for serial communication 
        -	BaudRate – 9600 
        -	Partity – NONE 
        -	StopBits – 1 
        -	DataBits – 8
    -	Use The JAVA NIO Channels or Classic Input/Output Streams to read and write data 
-	Bluetooth Setup 
    -	POS terminal and PC Client should be connected. Then we send some information from PC to POS terminal by ECR-Bluetooth
    -	User should choose a paired Bluetooth device as our ECR’s target device after
        we select the Type-Bluetooth as our ECR communication type. If the device, we want to choose was not paired, we must pair it at first, then choose the device as our target device
    -	System Requirements to setup USB / Static Wi-fi 
    -	Download and install the desired MCommerce app (Full Download)
    -	Full Download A920 integration kit in your system
    -	Perform Standard Initialization steps. (Key Injection, Initialization, TMK Download & Login)
    -	Go to ECR Preference settings menu enable ECR option and select the ECR type as USB
    -	Connect ECR and the terminal by RS232
-	Connect the desired cable (USB) to PC
- Trigger transactions from PC application to check the line status

|  Param1    | Descriptions |  Comment |
| ---------- | ---------------------------------- | ------------------ |
| `dataType` | Indicate the request data type.| active | 


- Terminal will reply a ACK message

### Payload Examples - Request

### Sale Request
```json
{
    "checksum": "0e6bacee3c2580ce9b3c28e8193cab04dbc02489b88922e0b36813e2e7cc232a",
    "data": {
        "amt": "10",
        "detail": "Y",
        "ecrRef": "aru-test-0123456"
    },
    "dataType": "sale"
}
```

### PreAuth Sale Request
```json
{
    "checksum": "0e6bacee3c2580ce9b3c28e8193cab04dbc02489b88922e0b36813e2e7cc232a",
    "data": {
        "amt": "10",
        "detail": "Y",
        "ecrRef": "aru-test-0123456"
    },
    "dataType": "preAuth"
}
```

### Void Request
```json

{
    "checksum": "11b42d973ab77d51bd56ddc5f9c2cbda0771ad437672cd0973c6ebea77a598b9",
    "data": {
        "invoiceNo": "71",
        "detail": "Y"
    },
    "dataType": "void"
}

```

### PreAuth Completion Request
```json
{
    "checksum": "0e6bacee3c2580ce9b3c28e8193cab04dbc02489b88922e0b36813e2e7cc232a",
    "data": {
        "amt": "10",
        "appCode": "143756",
        "invoiceNo": "12",
        "detail": "Y",
        "ecrRef": "aru-test-0123456"
    },
    "dataType": "preAuthCom"
}

```

### EMI Request
```json
{
    "checksum": "0e6bacee3c2580ce9b3c28e8193cab04dbc02489b88922e0b36813e2e7cc232a",
    "data": {
        "amt": "10",
        "tenure": "03",
        "detail": "Y",
        "ecrRef": "aru-test-0123456"
    },
    "dataType": "EMI"
}
```

### Refund Request
```json
{
    "checksum": "96918665b6e2f61013b9972ecc0cecfcf81bc2f9c67a27423f87d4e56725b007",
    "data": {
        "amt": "10",
        "detail": "Y",
        "rrn": "091000000063"
    },
    "dataType": "refund"
}
```

### Settlement Request
```json
{
    "checksum": "57a95ba3414991f4babd813acac7f1ee4f10946f72ac5f124aa69a2f4aefbae4",
    "data": {
        "acqName": "All"
    },
    "dataType": "settle"
}
```

### Method of calculating the checksum Request
```
SHA256({"amt":"35900","detail":"Y","ecrRef":"1234567890123456"})

```


### Request
The table below identifies the required properties in the request message

| Variable | Type |     Length     | Mandatory / Optional / Conditional (M / O / C)  |     Description / Values      |
| -------- | -------- | -------------- | -----------------------| ------------------------- |
|`dataType`|String|2|M|01 - Sale (Sale, DCC) 
| | | | | 02 - Preauth Sale |
| | | | | 03 - Preauth Completion |
| | | | | 04 - Refund |
| | | | | 05 - Void | 
| | | | | 08 - EMI Sale |
| | | | | 12 - Settlement Transaction|
|`amt`|String|10|M|Transaction amount in decimals - "100.00"|
|`detail`|String|2|O|To define the response message in detail format. 
| | | | | 'Y' means detail message, 'N' means skip this format|
|`ecrRef`|String|2|O|ECR reference no. up to 16 digits|
|`merchantReferenceNumber`|String|10|O|Unique merchant number for reconcilation - Value to be populated in statement in FT Number|
|`terminalInvoiceNumber`|String|20|M|Use the terminal Invoice No to indicate the invoice of terminal|
|`acqName`|String|20|O|To identify this transaction is initiated by respective Acquirer (Mandatory for void & PreAuth Completion transaction)|
|`userDefinedFields`|String|20|O|UDF fields|
|`pwd `|String|8|O|Void password|
|`rrn`|String|20|O|12 digits RRN|
|`authCode`|String|3|O|Approval code of authorization|
|`printChargeslip`|String|8|O |Y or N ( Default - Y )  (Mandatory for Pre Auth Completion transaction)|
|`emi`|String|20|O|EMI details – emi flag is 1/0 
| | | | | EMI reference number generated is 8 bytes |
| | | | |Tenure, discount amount, product amount, EMI per month|
|`checksum`|String|10|O (Mandatory for Transaction check status transaction)|Checksum for "data" field.Use SHA256 method to calculate “data” field|



### Response in Payload
### Sale Response  
```json
{
    "checksum": "d3152810ce39a7c6c74c4320017cc65c9c482857fe29bbd03512cf8fb7d1867b",
    "data": {
        "adjAmt": "000000000010",
        "aid": "A0000000041010",
        "amt": "10",
        "appCode": "R34200",
        "atc": "02B7",
        "batchNo": "2",
        "cardHolderName": "ARUMUGAM M",
        "cardType": "MASTER",
        "entryMode": "C",
        "expData": "2412",
        "merchantID": "000001080044542",
        "noSign": "Y",
        "pan": "5149 16** ****7742",
        "referenceNo": "091000000061",
        "status": "A",
        "stt": "Y",
        "tc": "02607F617B604749",
        "terminalId": "72611214",
        "tsi": "E800",
        "tvr": "0000008000",
        "txnDate": "20210910",
        "txnId": "71",
        "txnTime": "1347"
    },
    "dataType": "sale"
}
```

### Void Response
```json
{
    "checksum": "a21854b4aa4d134e460579939958d270b79d47204d79a8ea7cf970c736e44b71",
    "data": {
        "adjAmt": "000000000010",
        "amt": "10",
        "appCode": "R34200",
        "cardHolderName": "ARUMUGAM M",
        "expData": "2412",
        "pan": "5149 16** ****7742",
        "status": "A",
        "txnDate": "20210910",
        "txnId": "72",
        "txnTime": "1347"
    },
    "dataType": "void"
}
```

### Refund Response
```json
{
    "checksum": "89672c091ceeb3da18e851d77f02d132a8f52f7efbd02e62bc8662b6faf5293c",
    "data": {
        "adjAmt": "000000000010",
        "aid": "A0000000041010",
        "amt": "10",
        "appCode": "R37218",
        "atc": "02B9",
        "batchNo": "2",
        "cardHolderName": "ARUMUGAM M",
        "cardType": "MASTER",
        "entryMode": "C",
        "expData": "2412",
        "merchantID": "000001080044542",
        "noSign": "Y",
        "pan": "5149 16** ****742",
        "referenceNo": "091000000064",
        "status": "A",
        "stt": "N",
        "tc": "FE6D09B983F6BA33",
        "terminalId": "72611214",
        "tsi": "E800",
        "tvr": "0000008000",
        "txnDate": "20210910",
        "txnId": "74",
        "txnTime": "1418"
    },
    "dataType": "refund"
}
```

### Settlement Response
```json
{
    "checksum": "4f3af609a7a4e4764c0b01dc7dac35d41a274e8522a162ea6ed34907011c27c8",
    "data": [
        {
            "acqName": "FDMSV/M",
            "batchNo": "2",
            "batchUpload": "Y",
            "rspCode": "00",
            "rspText": "Success",
            "txnDate": "20210910",
            "txnTime": "142610"
        }
    ],
    "dataType": "settle",
    "status": "A"
}
```

### Checksum Response
```
checksum":"89672c091ceeb3da18e851d77f02d132a8f52f7efbd02e62bc8662b6faf5293c"

```

### Response
The table below identifies the required properties in the response message
*Response (Base24Constant.java)*	

| Variable |	Type |	Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | ------- | ------- |------- | ------------------ | 
|`dataType`|String|2|M|01 - Sale (Sale, DCC) |
| | | | | 02 - Preauth Sale |
| | | | | 03 - Preauth Completion | 
| | | | | 04 - Refund |
| | | | | 05 - Void  |
| | | | | 08 - EMI Sale | 
| | | | | 12 - Settlement Transaction|
|`amt`|String|10|M|Transaction amount in decimals - "100.00"|
|`aid`|String|10|O|Acquirer ID|
|`adjAmt`|String|10|O|Adjustment Amount|
|`authCode`|String|8|M|Auth Code|
|`atc`|String|12|O|Application Counter Value|
|`batchNumber`|String|6|M|Terminal Batch Number|
|`cardholderName`|String|25|O|Name of the cardholder|
|`cardType`|String|10|M|Type of card|
|`posEntryMode`|String|3|O|Magstripe,Chip, Contactless, Manual entry, etc.|
|`cardExpDate`|String|4|O|Transaction card expiry date|
|`merchantID`|String|16|M|Merchant ID|
|`signature`|String|2|O|Y' or 'N'|
|`panNumber`|String|16|O|This will identify as Card number|
|`referenceNumber`|String|20|M|This will identify as Reference Number|
|`status`|String|2|O|Status - "A"|
|`tc`|String|10|O|Transaction Number|
|`terminalID`|String|8|M|Terminal ID|
|`tvr`|String|10|O|Terminal Reference|
|`txndate`|Timestamp|10|M|Transaction date|
|`txntime`|Timestamp|10|M|Transaction time|
|`txnid`|String|10|M|Transaction Id|
|`checksum`|String|50|O|Checksum for "data" field.Use SHA256 method to calculate “data” field|
|`acquirerName`|String|20|M|Acquirer Name|
|`emi`|String|20|O|EMI details – emi flag is 1/0 
| | | | |EMI reference number generated is 8 bytes
| | | | |Tenure, discount amount, product amount, EMI per month|
|`batchUpload`|String|2|O|Y' or 'N'|
|`responseCode`|String|2|M|Host Response code, it has response message|
|`responseText`|String|20|M|Text of response message|


The table below provides the list of error codes and description for this application.
| ErrorCode |  Description/Values | Comments |
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
|`22`|Suspected malfunction|Issuer Decline. Merchant should advise cardholder to use different card for transaction|"
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