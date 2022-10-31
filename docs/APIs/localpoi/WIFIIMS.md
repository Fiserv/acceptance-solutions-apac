# USB / Static Wi-fi 

USB / Static Wi-fi is an integration between system to APOS(Android Point of Sale) device. E.g., Biller / retailer can integrate with payment application and complete the payment transaction.

Financial payment transactions supported by USB / Static Wi-fi to biller / retailer: Sale, Pre-Authorization Sale, Pre-Authorization Completion, Transaction Status Check, Installment/EMI Sale, Void, Settlement, Bharat QR code generation.

## How it works

System Requirements to setup USB / Static Wi-fi

 <ul> 
  <li> OS: Windows 8 and above
	 Cable: Micro USB Data Cable for RS232 Serial communication. </li>
  <li> Wi-Fi: Same Wi-Fi connectivity  for Socket communication for Both PAX and Integrating APPs </li>
 <li> JDK Version: JDK 1.8.0 version or above (64 bit or 32 bit) </li>
 <li> Other Libs: (Available in Windows as javax.mail.jar) </li>
 <li> Use any serial lib for java that should support window platform </li>
 <li> Get a list of available port name and select comm port no </li>
 <li> Open VSP (Virtual Serial Port ) </li>
 <li> PAX Use the following detail for serial communication </li>
<li> BaudRate – 9600 </li>
            <li> Partity – NONE </li>
            <li> StopBits – 1 </li>
            <li> DataBits – 8 </li>
            <li> Use The JAVA NIO Channels or Classic Input/Output  Streams to read and write data </li>
            <li> System Requirements to setup USB / Static Wi-fi </li>
            <li> Download and install the desired MCommerce app (Full Download) </li>
            <li> Full Download A920 integration kit in your system </li>
            <li> Perform Standard Initialization steps. (Key Injection, Initialization, TMK Download Login) </li>
            <li> Go to ECR Preference settings menu enable ECR option and select the ECR type as USB </li>
            <li> Connect ECR and the terminal by RS232 </li>
            <li> Connect the desired cable (USB) to PC </li>
            <li> Trigger transactions from PC application to check the line status
            </li>
          </ul>


   For digital transactions, the supported functionalities are listed below.

   <table border="0">
  <tr>
    <th>Value Added Services</th>
    <th>India</th>
    <th>Australia</th>
  </tr>
  <tr>
    <td>BBPS (Bharat Bill Pay)</td>
     <td align="center">&#10004;</td>
  <td></td>
  </tr>
   <tr>
    <td>UPI QR</td>
     <td align="center">&#10004;</td>
  <td></td>
  </tr>
   <tr>
    <td>Bharat QR</td>
     <td align="center">&#10004;</td>
   <td></td>
  </tr>
   <tr>
    <td>FASTag</td>
     <td align="center">&#10004;</td>
   <td></td>
  </tr>
     <tr>
    <td>MobiKwik</td>
     <td align="center">&#10004;</td>
  <td></td>
  </tr>


For card transactions, the supported functionalities are listed below.

<table border="0">
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
    <td>DCC(Dynamic Currency Conversion)</td>
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
  

|  Param1    | Descriptions  |  Comment |
| ---------- |---------------------- | ------------------ |
| `dataType` | Indicate the request data type.| active |  a ACK message

### Payload Examples - Request

dTransale",

        - Terminal will reply
    "base24Request": {
        "functionCode
### Sale Request
```
{
    "workflow": "Car": s"
        "customerNum": "20000",
        "suppressPrintCha"01",Slips": "n",
        "userDefinedFieldrge: "40000",
        "totalTxnAmouction",
    "transaction_type": "sant": "300",
        "mrn": "RS1113"
    }
}
```
### Pre-Authorization Request
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
### Pre-Authorization Completion Request
```json
{
    "base24Request": {
        "functionCode": "03",
        "customerNum": "20000",
        "workflow": "CardTransaction",
        "transaction_type": "Pre-auth comp",
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
### Installment / EMI Request
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


### Transaction Status Enquiry

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

| Variable | Type | Length | Mandatory / Optional /Conditional (M / O / C) | Description / Values |
| -------- | -------- | -------------- | -----------------------| ------------------------- |
|`functionCode`|String|2|M|01 = Sale ( Sale, DCC ). |
| | | | | 02 = Pre-Authorization. |
| | | | | 03 = Pre-Authorization Completion.|
| | | | | 04 = Refund |
| | | | | 05 = Void |
| | | | | 06 = TIP |
| | | | | 07 = Cash @ POS. |
| | | | | 08 = Installment/ EMI Sale. |
| | | | | 11 = Settlement Transaction. |
| | | | | 12 = Transaction status. |
| | | | | 13 = UPI QR  Generation. |
| | | | | 14 = UPI QR Last Transaction Status. | 
| | | | | 15 = Bharat QR  Generation.|
| | | | | 16 = Bharat  QR Last Transaction Status. | 
| | | | | 17 = Google Pay Wallet. |
| | | | | 18 = Tone Tag wallet. |
| | | | | 19 = Non-Carded Transactions. |
|`authCode`|String|8|M|Used for Pre-authorization completion & cancellation transaction.|
|`totalTxnAmount`|String|10|M|Total Amount including (Auth + ConvFee+ GST) in decimals-"100.00".|
|`tipAmount`|String|10|O|Transaction which involves tip amount in decimals-"10.00".|
|`detail`|String|2|O|To define the response message in detail format. |
| | | | |'Y' means detail message, 'N' means skip this format.|
|`ecrRef`|String|16|O|ECR reference number generated in transaction.|
|`merchantReferenceNumber`|String|20|M|Unique merchant number for reconcilation - Value to be populated in statement in FT Number.|
|`terminalInvoiceNumber`|String|20|O |Use the terminal Invoice No to indicate the invoice of terminal (Mandatory for void & PreAuth Completion transaction).|
| `CGST` | *string* | 10 | C | Central GST Including decimal (E.g. 10.00 for $10 CGST).If CGST is included in the total amount. |
| `IGST` | *string* | 10 | C | Integrated GST Including decimal (E.g. 10.00 for $10 IGST).If IGST is included in the total amount. |
| `SGST` | *string* | 10 | C | State GST Including decimal (E.g. 100.00 for $10 SGST).If SGST is included in the total amount. |
|`customerNumber`|String|20|O|To identify this transaction is initiated by respective customer.|
|`userDefinedFields`|String|8|O|UDF fields.|
|`pwd `|String|20|O|Void password.|
|`rrn`|String|12|M|The same value received in the original transaction response needs to be submitted across.|
|`authCode`|String|8|O|Used for Pre-authorization completion & cancellation transaction.|
|`dccFlag`|String|1|O|DCC Conversion flag - Yes or No.Response contains converted amount, exchange rate and margin fee.|
|`printChargeslip`|String|2|O|To enable charge slip printing - Y or N ( Default mode = Y ).|
|`emailID`|String|50|O|Email ID of the email that needs to be received. This is an optional 50 bytes variable.|
|`transactionType`|String|10|O |Type of transaction.|
|`emi`|String|3|O | EMI details – emi flag is 1/0 
| | | | | EMI reference number generated is 8 bytes |
| | | |  |Tenure, discount amount, product amount, EMI per month (Mandatory for EMI transaction).|
|`emiFlag`|String|1|O|To be sent in for Over the Counter (OTC)<br> transactions such as:<br> - Installment / EMI Sale <br>- Installment / EMI Void <br>Flag is defined as: 0 = Non-EMI (Non-installment / Non-EMI)<br> 1 = EMI (Installment / EMI).|
|`cardLastFourDigit`|String|4|O|Last 4 digits of Card Number. To be included for Pre-Authorization completion and cancellation transaction.|
|`consumerNumber`|String|20|M|Consumer number ( CRN )The value that is populated in statement of the session ID.|
|`checksum`|String|50|O|Checksum for "data" field. Use SHA256 method to calculate “data” field.|


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
### Pre-Authorization Sale Response

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
        "terminalInvoiceNo": "2",
        "totalTxnAmount": "40000",
        "transactionCurrency": "INR",
        "transactionMode": "Card",
        "userDefinedFields": "50000", 
        "rrn": "000000000002",
        "singFree": "1",
        "source": "TILL",
        "suppressPrintChargeSlips": "n"
    },
    "status": "Transaction Success"
}

```
### Pre-Authorization Completion Response
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

| Variable | Type |  Length  | Mandatory / Optional / Conditional (M / O / C)  |  Description / Values  |
| -------- | -------- | -------------- | -----------------------| ------------------------- |
|`functionCode`|String|2|M|01 = Sale ( Sale, DCC ).|
| | | | | 02 = Pre-Authorization. |
| | | | | 03 = Pre-Authorization Completion. |
| | | | | 04 = Refund |
| | | | | 05 = Void |
| | | | | 06 = TIP |
| | | | | 07 = Cash @ POS. |
| | | | | 08 = Installment/ EMI Sale. |
| | | | | 11 = Settlement Transaction. |
| | | | | 12 = Transaction status. |
| | | | | 13 = UPI QR  Generation. |
| | | | | 14 =  UPI QR Last Transaction Status. | 
| | | | | 15 = Bharat QR  Generation.|
| | | | | 16 =  Bharat  QR Last Transaction Status. | 
| | | | | 17 = Google  Wallet. |
| | | | | 18 = Tone Tag wallet. |
| | | | | 19 = Non-carded Transaction. |
|`source`|String|10|O|APOS(Android Point of Sale), Mobile, ECR (Electronic Cash Register), ATVM (Automatic Vending Machine).|
|`tipAmount`|String|10|M|Tip Amount entered during the transaction. |
|`totalTxnAmount`|String|10|O|Total Amount including (Auth + ConvFee+ GST) in decimals - "100.00".|
|`convenienceFee `|String|10|O|Convenience  Fee including decimal.|
| `CGST` | *string* | 10 | C | Central GST Including decimal (E.g. 10.00 for $10 CGST).If CGST is included in the total amount. |
| `IGST` | *string* | 10 | C | Integrated GST Including decimal (E.g. 10.00 for $10 IGST).If IGST is included in the total amount. |
| `SGST` | *string* | 10 | C | State GST Including decimal (E.g. 100.00 for $10 SGST).If SGST is included in the total amount. |
|`billAmount`|String|10|O|Bill amount including decimal.|
|`merchantReferenceNumber`|String|20|M|Same as request.|
|`terminalInvoiceNumber`|String|8|M|Terminal Invoice Number.|
|`currencySelection`|String|3|O|Currency code / currency that had been selected.|
|`transactioID`|String|10|M|Same as request.|
|`customerName`|String|25|O|Customer name extracted from Card.|
|`userDefinedFields`|String|30|O|Same as request.|
|`maskedCardNumber`|String|21|M|First 6 digits and last 4 digits. The numbers in between should be masked.|
|`applicationVersionNumber`|String|10|M|Version number of terminal application used.|
|`date & Time`|Timestamp|20|M|Host Date & Time.|
|`aTID`|String|8|M|Acquirer TID.|
|`aMID`|String|15|M|Acquirer MID.|
|`acquirerName`|String|20|M|Acquirer Name.|
|`responseCode`|String|12|M|Host Response code, it has response message.|
|`batchNumber`|String|6|M|Terminal Batch Number.|
|`cardType`|String|10|M|Type of card.|
|`rrn`|String|12|M|RRN received from host.|
|`se`|String|10|O|Value would be populated incase of Amex txns.|
|`emv`|String|256|O|EMV data like TC , Application identifier, Application Name, TSI, etc.|
|`emiFlag`|String|1|O|To be sent in for Over the Counter (OTC) transactions such as: - Installment / EMI Sale - Installment / EMI Void Flag is defined as: 0 = Non-EMI (Non-installment / Non-EMI) 1 = EMI (Installment / EMI.|
|`posEntryMode`|String|3|O|Magstripe,Chip, Contactless, Manual entry, etc.|
|`pinVerified`|String|3|O|"Yes" when PIN was entered & "No" when pin was not prompt.|
|`authCode`|String|8|M|Used for Pre-authorization completion & cancellation transaction.|
|`billerID`|String|10|O|Same as request.|
|`specificIndicator `|String|3|O|To be used for BBPS. |
|`merchantUniqueNumber`|String|20|O|Same as request. |
|`suppressPrintChargeslip `|String|2|O|“Yes” or “No”  -To suppress chargeslip prints for financial transactions.|
|`emi`|String|20|O|EMI details – emi flag is 1/0  EMI reference number generated is 8 bytes Tenure, discount amount, product amount, EMI per month.|
|`consumerNumber`|String|20|M|Consumer number ( CRN )The value that is populated in statement of the session ID.|
|`cardLastFourDigit`|String|4|O|Last 4 digits of Card Number. To be included for Pre-Authorization completion and cancellation transaction.|
|`emailID`|String|50|O|Email ID of the email that needs to be received. This is an optional 50 bytes variable.|
|`cardTxnMode`|Strin|O| Transaction cashback amount.|
|`nacStatus `|String|3|O|Identifies the network status <br> - True = private network <br> - False = public network.|g|3|O|Transaction Mode.|
|`purchaseAmount `|String|10|O|Purchase amount .|
|`cashBackAmount`|String|10|O|Transaction cashback amount.|
|`cardExpiryDate`|String|4|O|Expiry date of the card used for transaction.|
|`dccFlag`|String|1|O|DCC Conversion flag - Yes or No.Response contains converted amount, exchange rate and margin fee.|



The table below provides the list of error codes and description for this application.
| ErrorCode |  Description / Values | Comments |
| --------  | ------------------ | -------------|
|`00`|Balance is approved|Merchant should go ahead with reciept generation.|
|`01`|Place Call|Contact Customer Support / Business Manager.|
|`02`|Over Floor Limit|Contact Customer Support / Business Manager.|
|`03`|Merchant Not on File|Contact Customer Support / Business Manager.|
|`12`|Invalid Transaction|Issuer Decline. Merchant should advise cardholder to use different card for transaction.|
|`14`|Invalid Account|Issuer Decline. Merchant should advise cardholder to use different card for transaction.|
|`19`|Retry Transaction|Contact Customer Support / Business Manager.|
|`25`|CAF Not Found|Contact Customer Support / Business Manager.|
|`30`|Invalid msg format|Contact Customer Support / Business Manager.|
|`31`|Card Not Supported| Contact Customer Support / Business Manager.|
|`41`|Lost or Stolen Card|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`43`|CAF Status 3, stolen card|Issuer declined the transaction. Merchant should advise cardholder to use a different card for the transaction.|
|`51`|Pin Tries Exceeded|Issuer declined the transaction. The number of tries using PIN had exceeded. Merchant should advise cardholder to use a different card for the transaction.|
|`54`|Expired Card|Issuer declined the transaction. Merchant should advise cardholder to use a different valid card for the transaction.|
|`55`|Incrrect Pin|Issuer declined the transaction. Merchant should advise cardholder to retry with the correct PIN.|
|`58`|Transaction not allowed|Issuer declined the transaction. Merchant should advise cardholder to use a different card for transaction.|
|`91`|Authorization Request timed out|Contact Customer Support / Business Manager.|
