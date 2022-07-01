# USB / Static Wi-fi 

USB / Static Wi-fi is an integration between system to APOS device. E.g., Biller can integrate with payment app and complete the payment transaction.

Financial payment transactions supported by USB / Static Wi-fi to biller: Sale, PreAuth Sale, PreAuth Completion, Transaction Status Check, EMI Sale, Void, Settlement, Bharat QR code generation.

## How it works
- System Requirements to setup USB / Static Wi-fi
    - OS: Windows 8 and above
    - Cable: Micro USB Data Cable for RS232 Serial communication.
    - Wi-Fi: Same Wi-Fi connectivity for Socket communication for Both PAX and Integrating APPs
    - JDK Version: JDK 1.8.0 version or above (64 bit or 32 bit)
    - Other Libs: (Available in Windows as javax.mail.jar)
    - Use any serial lib for java that should support window platform
    - Get a list of available port name and select comm port no
    - Open VSP (Virtual Serial Port ) 
    -  PAX Use the following detail for serial communication 
        - BaudRate – 9600 
        - Partity – NONE 
        - StopBits – 1
        - DataBits – 8 
        - Use The JAVA NIO Channels or Classic Input/Output Streams to read and write data 
        - System Requirements to setup USB / Static Wi-fi 
        - Download and install the desired MCommerce app (Full Download)
        - Full Download A920 integration kit in your system
        - Perform Standard Initialization steps. (Key Injection, Initialization, TMK Download Login)
        - Go to ECR Preference settings menu enable ECR option and select the ECR type as USB
        - Connect ECR and the terminal by RS232
        - Connect the desired cable (USB) to PC
        - Trigger transactions from PC application to check the line status

        |  Param1    | Descriptions |  Comment |
        | ---------- |---------------------- | ------------------ |
        | `dataType` | Indicate the request data type.| active | 

        - Terminal will reply a ACK message

### Payload Examples - Request

### Sale Request
```
{
    "workflow": "CardTransaction",
    "transaction_type": "sale",
    "base24Request": {
        "functionCode": "01",
        "customerNum": "20000",
        "suppressPrintChargeSlips": "n",
        "userDefinedFields": "40000",
        "totalTxnAmount": "300",
        "mrn": "RS1113"
    }
}
```
### PreAuth Sale Request
```json
{
    "workflow": "CardTransaction",
    "transaction_type": "preAuth",
    "base24Request": {
        "functionCode": "02",
        "customerNum": "20000",
        "suppressPrintChargeSlips": "n",
        "userDefinedFields": "40000",
        "totalTxnAmount": "20000",
        "mrn": "34343434"
    }
}
```
### Void Request
```json
{
    "workflow": "CardTransaction",
    "transaction_type": "void",
    "base24Request": {
        "functionCode": "05",
        "customerNum": "20000",
        "suppressPrintChargeSlips": "n",
        "userDefinedFields": "40000",
        "terminalInvoiceNo": "000038",
        "totalTxnAmount": "",
        "mrn": "34343434"
    }
}
```
### PreAuth Completion Request
```json
{
    "workflow": "CardTransaction",
    "transaction_type": "Pre-auth comp",
    "base24Request": {
        "functionCode": "03",
        "customerNum": "20000",
        "cardLastFourDigit": "0010",
        "suppressPrintChargeSlips": "n",
        "userDefinedFields": "40000",
        "authCode": "000038",
        "terminalInvoiceNo": "000038",
        "totalTxnAmount": "20000",
        "mrn": "34343434"
    }
}
```
### EMI Request
```json
{
    "workflow": "CardTransaction",
    "transaction_type": "EMI",
    "base24Request": {
        "functionCode": "08",
        "tenure": "03",
        "customerNum": "20000",
        "suppressPrintChargeSlips": "n",
        "userDefinedFields": "40000",
        "totalTxnAmount": "20000",
        "mrn": "34343434"
    }
}
```


### Transaction Status check Request

```json
{
    "workflow": "CardTransaction",
    "transaction_type": "transaction enquiry",
    "base24Request": {
        "functionCode": "11",
        "terminalInvoiceNo": "000088",
        "mrn": "1231412"
    }
}
```
### Settlement Request

```json
{
    "workflow": "CardTransaction",
    "transaction_type": "Settelment",
    "base24Request": {
        "functionCode": "12",
        "suppressPrintChargeSlips": "n"
    }
}
```
### Request
The table below identifies the required properties in the request message

| Variable | Type | Length | Mandatory / Optional / Conditional (M / O / C) | Description / Values |
| -------- | -------- | -------------- | -----------------------| ------------------------- |
| `functionCode` | String | 2 | M | 01 - Sale (Sale, DCC) |
|  | 	|  | 02 - Preauth Sale |
|  | 	|  | 03 - Preauth Completion |
|  | 	|  | 05 - Void |
|  | 	|  | 08 - EMI Sale |
|  | 	|  | 05 - Void |
|  | 	|  | 12 - Settlement Transaction |
|  | 	|  | 11 - Transaction status check |
| `Total Txn Amount ( Auth + ConvFee+ GTS)` | String | 10 |	M |	This transaction involves amount "100.00" |
| `Tip Amt` | String | 10 | O | This transaction involves "10.00" | 
| `Detail` | String | 2 | O | To define the respond message in detail format. Y means detail message, N or skip this format means simple format "Y" |
| `ECR Ref` | String | 10 | O |	ECR reference no. up to 16 digits |
| `Merchant Reference Number(MRN)` | String	| 20 | M | Unique merchant number for reconciliation|
| `Terminal Invoice No` | String | 20 |	O (Mandatory for void & PreAuth Completion transaction)	| Use the terminal Invoice No to indicate the invoice of terminal |
| `Customer Number` | String | 20 | O |	To identify this transaction is initiated by respective customer |
| `User Defined Fields` | String | 8 | O | UDF fields |
| `Pwd` | String | 20 | O | Void password |
| `RRN` | String | 3 | O | 12 digits RRN |
| `Auth Code` |	String | 8 | O (Mandatory for Pre Auth Completion transaction) | Approval code of authorization |
| `Print charge slip` |	String | 2 | O | Y or N (Default - Y ) |
| `Transaction_type` | String | 10 | O (Mandatory for Transaction check status transaction ) | Type of transaction |
| `Tenure` | String | 3 | O (Mandatory for EMI transaction)	| The instalment plan of this transaction |
| `Checksum` | String | 50 | O | Checksum for **data** field. Use SHA256 method to calculate **data** field |

### Response in Payload

### Sale Response
```json
{
    "base24Response": {
        "AID": "A0000000031010",
        "AMID": "470000095241203",
        "ATID": "33533344",
        "TSI": "F800",
        "TVR": "0280248040",
        "acquirerName": "IMS-V/M",
        "appName": "VISA CARD CREDITO DEVISA",
        "appVersionNo": "1.03.02_20220114",
        "authCode": "167167",
        "batchNo": "1",
        "cardType": "VISA CARD",
        "currencySelection": "INR",
        "customerName": "VISA ACQUIRER TEST/CARD 21",
        "customerNum": "20000",
        "dateTime": "20220119114831",
        "dccFlag": "0",
        "emiFlag": "0",
        "expDate": "2212",
        "fdMID": "470000095241203",
        "fdTID": "33533344",
        "functionCode": "01",
        "isNAC": false,
        "isTransactionSuccess": false,
        "issuerCode": "1",
        "maskedCardNo": "4761 73** **** 0010",
        "merchantInvoiceNo": "7777777",
        "mrn": "7777777",
        "pinVerified": "1",
        "posEntryMode": "INSERT",
        "responseCode": "Transaction Success",
        "rrn": "000000000001",
        "singFree": "0",
        "source": "TILL",
        "suppressPrintChargeSlips": "n",
        "terminalInvoiceNo": "1",
        "totalTxnAmount": "40000",
        "transactionCertificate": "B06F22A0139A23FA",
        "transactionCurrency": "INR",
        "transactionMode": "Card",
        "userDefinedFields": "40000"
    },
    "status": "Transaction Success"
}

```
### PreAuth Sale Response

```json
{
    "base24Response": {
        "AID": "A0000000031010",
        "AMID": "470000095241203",
        "ATID": "33533344",
        "TSI": "F800",
        "TVR": "0280248040",
        "acquirerName": "IMS-V/M",
        "appName": "CREDITO DE VISA",
        "appVersionNo": "1.03.02_20211219",
        "authCode": "098577",
        "batchNo": "1",
        "cardType": "VISA CARD",
        "currencySelection": "INR",
        "customerName": "VISA ACQUIRER TEST/CARD 21",
        "customerNum": "40000000000",
        "dateTime": "20220103200410",
        "dccFlag": "0",
        "emiFlag": "0",
        "expDate": "2212",
        "fdMID": "470000095241203",
        "fdTID": "33533344",
        "functionCode": "02",
        "isNAC": false,
        "isTransactionSuccess": false,
        "issuerCode": "1",
        "maskedCardNo": "4761 73** **** 0010",
        "merchantInvoiceNo": "88888888",
        "mrn": "88888888",
        "pinVerified": "1",
        "posEntryMode": "INSERT",
        "responseCode": "Transaction Success",
        "rrn": "000000000003",
        "singFree": "0",
        "source": "TILL",
        "suppressPrintChargeSlips": "n",
        "terminalInvoiceNo": "3",
        "totalTxnAmount": "300000000",
        "transactionCertificate": "5EDF86CC440E2A4A",
        "transactionCurrency": "INR",
        "transactionMode": "Card",
        "userDefinedFields": "600000000000"
    },
    "status": "Transaction Success"
}
```
### Void Response
```json
{
    "base24Response": {
        "AMID": "470000095241203",
        "ATID": "33533344",
        "acquirerName": "IMS-V/M",
        "appName": "VISA CARD",
        "appVersionNo": "1.03.02_20220114",
        "authCode": "167167",
        "batchNo": "1",
        "cardType": "VISA CARD",
        "currencySelection": "INR",
        "customerNum": "80000",
        "dateTime": "20220119114831",
        "dccFlag": "0",
        "emiFlag": "0",
        "expDate": "2212",
        "fdMID": "47000009524120",
        "fdTID": "33533344",
        "functionCode": "05",
        "isNAC": false,
        "isTransactionSuccess": false,
        "issuerCode": "1",
        "maskedCardNo": "4761 73** **** 0010",
        "merchantInvoiceNo": "888888",
        "mrn": "888888",
        "pinVerified": "0",
        "posEntryMode": "INSERT",
        "responseCode": "Transaction Success",
        "rrn": "000000000002",
        "singFree": "1",
        "source": "TILL",
        "suppressPrintChargeSlips": "n",
        "terminalInvoiceNo": "2",
        "totalTxnAmount": "40000",
        "transactionCurrency": "INR",
        "transactionMode": "Card",
        "userDefinedFields": "50000"
    },
    "status": "Transaction Success"
}

```
### PreAuth Completion Response
```json
{
    "base24Response": {
        "AMID": "470000095241203",
        "ATID": "33533344",
        "acquirerName": "IMS-V/M",
        "appName": "MASTERCARD",
        "appVersionNo": "1.03.02_20220114",
        "authCode": "006142",
        "batchNo": "3",
        "cardType": "MASTERCARD",
        "currencySelection": "INR",
        "customerNum": "20000",
        "dateTime": "20220120153224",
        "dccFlag": "0",
        "emiFlag": "0",
        "expDate": "2512",
        "fdMID": "470000095241203",
        "fdTID": "33533344",
        "functionCode": "03",
        "isNAC": false,
        "isTransactionSuccess": false,
        "issuerCode": "2",
        "maskedCardNo": "5413 33** **** 0508",
        "merchantInvoiceNo": "343423234",
        "mrn": "343423234",
        "pinVerified": "0",
        "posEntryMode": "INSERT",
        "responseCode": "Transaction Success",
        "rrn": "000000000041",
        "singFree": "1",
        "source": "TILL",
        "suppressPrintChargeSlips": "n",
        "terminalInvoiceNo": "26",
        "totalTxnAmount": "20000",
        "transactionCurrency": "INR",
        "transactionMode": "Card",
        "userDefinedFields": "40000"
    },
    "status": "Transaction Success"
}

```

### EMI Response
```json
{
    "base24Response": {
        "AID": "A0000000041010",
        "AMID": "470000095241203",
        "ATID": "33533344",
        "EMIPerMonthINR": "000000006811",
        "EMIProcFeeINR": "000000000800",
        "EMITenure": "03",
        "TSI": "E800",
        "TVR": "0000048000",
        "acquirerName": "IMS-V/M",
        "annualROIReducing": "00000",
        "appName": "MASTERCARD",
        "appVersionNo": "1.03.02_20220114",
        "authCode": "006177",
        "batchNo": "5",
        "cardType": "MASTERCARD",
        "currencySelection": "INR",
        "customerName": "MTIP50 MCD 16A",
        "customerNum": "20000",
        "dateTime": "20220120181646",
        "dccFlag": "0",
        "emiFlag": "1",
        "expDate": "2512",
        "fdMID": "470000095241203",
        "fdTID": "33533344",
        "functionCode": "08",
        "interestRate": "13.00",
        "isNAC": false,
        "isTransactionSuccess": false,
        "issuerCode": "2",
        "maskedCardNo": "5413 33** ****0508",
        "merchDisAmtINR": "0",
        "merchantInvoiceNo": "34343434",
        "mrn": "34343434",
        "pinVerified": "1",
        "posEntryMode": "INSERT",
        "prodCode": "",
        "productAmtINR": "20000",
        "responseCode": "Transaction Success",
        "rrn": "000000000066",
        "singFree": "0",
        "source": "TILL",
        "suppressPrintChargeSlips": "n",
        "terminalInvoiceNo": "33",
        "totalTxnAmount": "20000",
        "transactionCertificate": "8ABC6EACE6926401",
        "transactionCurrency": "INR",
        "transactionMode": "Card",
        "userDefinedFields": "40000"
    },
    "status": "Transaction Success"
}

```
### Settlement Response
```json
{
    "base24Response": {
        "acquirerName": "IMS-V/M",
        "batchNo": "2",
        "dateTime": "220118171958",
        "fdMID": "470000032001091",
        "fdTID": "33533344",
        "functionCode": "12",
        "isNAC": false,
        "isTransactionSuccess": false,
        "responseCode": "Transaction Success",
        "source": " RUPAY 1 â‚¹ 200.00 0 â‚¹ 0.00 VISA CARD 3 â‚¹ 650.00 0 â‚¹ 0.00 MASTERCARD 3 â‚¹ 804.00 0 â‚¹ 0.00",
        "suppressPrintChargeSlips": "n",
        "transactionMode": "Card"
    },
    "status": "Transaction Success"
}

```
### Transaction Status check Request
```json
{
    "base24Response": {
        "AID": "A0000000031010",
        "AMID": "470000095241203",
        "ATID": "33533344",
        "TSI": "0000",
        "TVR": "0000000000",
        "acquirerName": "IMS-V/M",
        "appName": "VISA CARD",
        "appVersionNo": "1.03.02_20220323",
        "authCode": "129513",
        "batchNo": "6",
        "cardType": "VISA CARD",
        "currencySelection": "INR",
        "customerNum": "20000",
        "dateTime": "20220422112454",
        "dccFlag": "0",
        "emiFlag": "0",
        "expDate": "2212",
        "fdMID": "470000095241203",
        "fdTID": "33533344",
        "functionCode": "11",
        "isNAC": false,
        "isTransactionSuccess": false,
        "issuerCode": "1",
        "maskedCardNo": "4012 00** ****9400",
        "merchantInvoiceNo": "Guru220403",
        "mrn": "Guru220403",
        "pinVerified": "0",
        "posEntryMode": "CLSS",
        "responseCode": "Transaction Success",
        "rrn": "000000000145",
        "singFree": "0",
        "source": "TILL",
        "terminalInvoiceNo": "88",
        "totalTxnAmount": "90000",
        "transactionCertificate": "31EAB6DE086CDF55",
        "transactionCurrency": "INR",
        "transactionMode": "Card",
        "userDefinedFields": "40000"
    },
    "status": "Transaction Success"
}

```
### Response
The table below identifies the required properties in the response message

| Variable | Type |     Length     | Mandatory / Optional / Conditional (M / O / C)  |     Description / Values      |
| -------- | -------- | -------------- | -----------------------| ------------------------- |
| `functionCode` | String | 2 | M | 01 - Sale (Sale, DCC) |
|  | 	| | | 02 - Preauth Sale |
|  | 	| | | 03 - Preauth Completion |
|  | 	| | | 05 - Void |
|  | 	| | | 08 - EMI Sale |
|  | 	| | | 12 - Settlement Transaction |
|  | 	| | | 11 - Transaction status check |
| `Source` | String | 10 | O | TILL,  Mobile,  ATVM,  etc.|
| `TIP amount` | String | 10 | O | Length 10 including decimal |
| `Total Transaction amount ( Bill Amount + Convenience Fee + GST )` | String |	10 | M | Length 10 including decimal |
| `Fuel  Discount  Cashback` | String |	10 | O | Length 10 including decimal |
| `Convenience Fee` | String | 10 | O |	Length 10 including decimal |
| `CGST` | String | 10 | O | Length 10 including decimal |
| `SGST` | String | 10 | O | Length 10 including decimal |
| `Bill amount` | String | 10 |	O | Length 10 including decimal |
|`EMI specific data`|	String|	20|	O|	Interest rate,  Processing fee, Tenure,  etc.|
|`Merchant  Reference  Number(MRN)`|	String|	20	|M	| Same as request |
|`Terminal  Invoice  number`|	String|	8|	M |	Terminal  Invoice Number|
|`Currency selection`|	String	|3|	O|	Currency code/currency which been selected|
|`Transaction ID`	|String|	10	|M|	Same as request |
|`Customer name`|	String|	25|	O|	Customer name extracted from Card|
|`User defined fields`|	String|	30|	O| Same as request |
|`Masked  Card  Number`|	String|	21|	M|	First Six digit & last four digit. In between number should be masked|
|`Application Version  Number`|	String | 10| M |This is terminal application version number|
|`Date & Time`|	Timestamp| 20| M |	Host Date & Time|
|`ATID`| String	|8|	M|	Acquirer TID|
|`AMID`| String| 15	|M | Acquirer MID|
|`Acquirer  Name`| String | 20| M | Acquirer Name|
|`Response Code` | String |	12|	M |	Host Response code, it has response message|
|`Batch Number`| String| 6 | M | Terminal Batch Number |
|`Card Type`| String| 10| M |	Type of card |
|`RRN`|	String | 12	| M| RRN received from host |
|`SE`|	String | 10	| O |Value would be populated incase of Amex txns|
|`EMV specific Data`|	String	|256|	O	|EMV data like TC , Application identifier,  Application Name, TSI, etc.|
|`DCC Indicator` |String |1| O |"EMI  flag  yes or no,  YES :1 , NO : 0 To be sent in OTC EMI Sale, EMI Void"|
|`EMI flag`| String| 1 | O | "EMI  flag  yes or no,  YES :1 , NO : 0 To be sent in OTC EMI Sale, EMI Void"|
|`Pos Entry Mode`| String |	3| O |Magstipe,Chip, Contactless, Manual entry, etc.|
|`Pin Verified`| String|3| O |**Yes** when PIN was entered & **No** when pin was not prompt|
|`Auth Code`| String | 8 | M | Received from Issuer/host |
|`Biller Id`| String | 10 | O | Same as request |
|`Specific Indicator` |	String | 3 | O | To be used for BBPS |
|`Merchant unique number` | String | 20 | O | Same as request |
| `Terminal Invoice number`| String | 20 | O | Same as request |
| `Suppress Print Charge Slip` | String | 2	| O	|**Yes** or **No**  -To suppress chargeslip prints for financial transactions|
|`EMI`	| String |20| O | EMI details – emi flag is 1/0 EMI reference number generated is 8 bytes Tenure, discount amount, product amount, EMI per month|
|`Consumer Number`|	String|	20	|O|	CRN / Consumer number 20 bytes|
|`Card Last four digit`| String | 4 | O | Used for pre-auth completion & cancellation transaction |
|`Email ID`| String | 50 | O | Email ID on which Email needs to be received 50 bytes optional |
|`Card Txn mode`| String | 3 |	O|	Txn Mode |
|`Purchase amount` | String | 10 | O | Purchase amount |
|`Cash back amount`| String| 10| O | Transaction cash back amount|
|`NAC Status` |	String	| 3	| O | Identify the network status True -> private network False -> public network|
|`Card Exp Date`| String | 4 |O| Transaction card expire date |
|`DCC Yes/NO flag`| String | 10 | O | DCC Conversion flag  Yes or No & the response converted amount, exchange rate and margin fee|





The table below provides the list of error codes and description for this application.
| ErrorCode |  Description/Values |
| --------  | ------------------ |
| -1 |	The equipment is busy |
| -2 |	Please reactivate GP Merchant |
| -3 |	Unknown path |
| -4 |	Amount error |
| -5 |	Unknown trading channels |
| -6 |	Exchange currency inconsistency |
| -7 |	Inconsistent Business Number and Terminal Number |
| 0	| Successful trade |
| 1	 | Transaction failure |
| 2	 | Order number duplication |
| 3	| Please reactivate GP Merchant |
| 4	| Unopened FPS transaction |
| 5	| Exchange currencies not supported |
| 6	| Error in transaction amount |
| 7	| Unsupported transaction types |
| 8	| Error inquiring order |












