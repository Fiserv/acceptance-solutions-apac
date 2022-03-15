# Document Upload

This API is used to document upload. Merchants needs to add session 
token received during login api call in the header of this API,


## Endpoint

GET `/Externalboarding/secure/document/{appUrn}`

## Payload Example

### Request Payload

```json


```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The below table contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/document/{appUrn}).

### Request
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `appURN` |	*Alphanumeric* |	30 | M |	App URN retured as part of Create URN API |	 
| `docType` |	*Alphanumeric* |	30  |	  |	Document Name of document being uploaded. |  	
| `fileType` |	*Alphanumeric*  |	10	M |	The type of the file that is uploaded	 |
| `principalNo` |	*Alphanumeric* |	2 |	M	| |	
| `Image Front` |	*file*	|	M |	Front copy of the document. If document has single part, same has to be uploaded as part of file1. |
| `Image Back` |	*file*	|	O |	Back copy of the document. If document has single part, file2 remains blank	|
| `categoryName` |	*Alphanumeric* |	30	M	Category of document being uploaded. This can be refered from tag categoryName in Get Document Matrix API	|
| `level` |	*Alphanumeric* |	2 |	M |	Level of document being uploaded. This can be refered from tag level in Get Document Matrix API	|
| `Entity` |	*Alphanumeric* |		M		
| `Mandatory` |	*Alphanumeric* |	10	M

### Successful Response Payload

```json

{
  "status": {
    "statusCode": 200,
    "message": "Success"
  },
  "data": {
    "merchantDocument": {
      "appURN": "8000110311",
      "docId": "88173d0b16f14c7c9c920d0e16cb90e6",
      "docType": "cheque",
      "fileType": ".jpeg",
      "principalNo": 0,
      "locationNo": 0,
      "categoryName": "Funding Proof",
      "level": "1",
      "mandatory": "Y",
      "entity": "Merchant"
    },
    "autoregResponse": {
      "number": "658205602030",
      "bankName": "ICICI BANK",
      "ifsc": "GAUT0MOBILE"
    }
  }
}
```

### Error Response Payload

```json
{
	"status": {
		"statusCode": 401,
		"message": "Unauthorized"
	},
	"data": null
}
```

### Response
| Variable | Type | Length |  Mandatory/Optional/Conditional  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `merchantId` | *string* | 20 | M | Merchant ID |




Below table provides the list of application's error code and its description.

| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`401` |Token not found|  
|`200` |Success|
|`300` |Request Failure|
|`500` |Internal Server Error|
|`404` |Not Found|
|`502` |Request Timed Out|
