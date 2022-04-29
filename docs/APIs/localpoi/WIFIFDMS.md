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
-	Terminal Setup 
    -	Download and install the desired MCommerce app (Full Download)
    -	Full Download A920 integration kit in your system
    -	Perform Standard Initialization steps. (Key Injection, Initialization, TMK Download & Login)
    -	Go to ECR Preference settings menu enable ECR option and select the ECR type as USB
    -	Connect ECR and the terminal by RS232
-	Connect the desired cable (USB) to PC
-	Trigger transactions from PC application to check the line status
    | Param1 |  Param2 | Descriptions | Comment |
    | --------  | ------ | ------ | ------ |
    | dataType | | Indicate the request data type. | `active` |
-	Terminal will reply a ACK message

### Payload Examples

### Request Payload

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
The below table identifies the required properties in the request message
| Variable | Mandatory/Optional/Conditional | Description/Values |
| --------  | ------------------ |	--------  |
|`Data Type`|	M	Sale , Preauth Sale|Preauth Completion,  Void, EMI Sale, Settlement Transaction, Refund|
|`Amt`|	M |	This transaction involves amount "100.00"|
|`Detail`|	O	| To define the respond message in detail format. Y means detail message, N or skip this format means simple format "Y"(optional) |
|`ECR Ref`|	O	| ECR reference no. up to 16 digits. (optional) |
|`Merchant Reference Number (MRN)`|	O	| Unique merchant number for reconciliation. This merchant reference Number|
|`Terminal Invoice No`|	O (Mandatory for void & PreAuth Completion transaction) |	Use the terminal Invoice No to indicate the invoice of terminal|
|`Acq Name`|	O (Mandatory for Settlement transaction)	|To identify this transaction is initiated by respective Acquirer|
|`User Defined Fields`|	O	|UDF fields|
|`Pwd`| 	O	| Void password (Optional)|
|`RRN`|	O(Mandatory for Refund transaction) |	12 digits RRN (optional)|
|`Auth Code`|	O (Mandatory for PreAuth Completion transaction) |	Approval code of authorization|
|`Print charge slip`|	O	|Y or N ( Default - Y ) |
|`Tenure`|	O (Mandatory for EMI transaction) |	The instalment plan of this transaction|
|`checksum`|	M	Checksum for "data" field data. Use SHA256 |calculate **data** field data. Calculation should be done to include in transaction request message|

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
The below table identifies the required properties in the response message
*Response (Base24Constant.java)*	
| Variable |	Description / Values |
| --------  | ------------------ |
|`Data Type`|	Sale , Preauth Sale,Preauth Completion,  Void, EMI Sale, Settlement Transaction, Refund|
|`Amount`|	Length 10 including decimal|
|`AID`|	Acquirer ID|
|`Adj Amt`|	Amount|
|`Auth code	`|Auth Code|
|`ATC`|	Application Counter Value|
|`Batch Number`|Terminal Batch Number|
|`Cardholder Name`|	Name of the cardholder|
|`Card Type`|	This will card type|
|`Pos Entry Mode`|	Magstipe,Chip, Contactless, Manual entry, etc|
|`Card Exp Date`|	Transaction card expire date|
|`Merchant ID`|	Merchant ID|
|`No signature`|	Y' or 'N'|
|`Pan Number`|	This will identify as Card number|
|`Reference Number	`|This will identify as Reference Number|
|`Status`|Status - "A"|
|`Tc`|Transaction Number|
|`Terminal ID`|	Terminal ID|
|`TVR`|Terminal Reference|
|`Txn date`|	Transaction date|
|`Txn time`|	Transaction time|
|`Txn id`|	Transaction Id|
|`checksum`|Checksum for "data" field data. Use SHA256 |
|`calculate`| “data” field data. Calculation should be done to include in transaction response message|
|`Acquirer Name`|Acquirer Name|
|`EMI specific data`|Interest rate, Processing fee, Tenure, etc|
|`Batch Upload`|Y' or 'N'|
|`Response Code`|	Host Response code, it has response message|
|`Response Text`|Text of response message| 


The table below provides the list of error codes and description for this application.
| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`-1` |	The equipment is busy |
|`-2` |	Please reactivate GP Merchant |
|`-3` |	Unknown path |
|`-4` |	Amount error |
|`-5` |	Unknown trading channels |
|`-6` |	Exchange currency inconsistency |
|`-7` |	Inconsistent Business Number and Terminal Number |
|`0` |	Successful trade |
|`1` |	Transaction failure |
|`2` |	Order number duplication |
|`3` |	Please reactivate GP Merchant |
|`4` |	Unopened FPS transaction |
|`5` |	Exchange currencies not supported |
|`6` |	Error in transaction amount |
|`7` |	Unsupported transaction types |
|`8` |	Error inquiring order |





