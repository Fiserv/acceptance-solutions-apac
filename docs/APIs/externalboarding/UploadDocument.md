# Document Upload

This API is used to upload documents for merchants.

## How it works
1. Merchant needs to use this API as a part of Create URN API with application URN generated in the request API to tag the documents to 
   a particular Application URN.
2. API would follow the Get Document matrix API and has to be submitted before Application Submit API.
3. API response will give unique document ids for each document which has to be provided in subsequent application APIs. 

## Endpoint

POST `https://www.uat.fdmerchantservices.com/Externalboarding/secure/document/{appUrn}`

## Payload Example

### Request Payload

```json

https://www.uat.fdmerchantservices.com/Externalboarding/secure/document/10000745

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/document/{appUrn}).

### Request
| Variable | Type | Length |  Mandatory / Optional / Conditional  (M / O / C)  | Description/Values |
| -------- | :-------: | :--: | :------------: | ------------------ |
| `appURN` |	*Alphanumeric* |	30 | M |	App URN retured as part of Create URN API |	 
| `docType` |	*Alphanumeric* |	30  |	  |	Document Name of document being uploaded. |  	
| `fileType` |	*Alphanumeric*  |	10	| M |	The type of the file that is uploaded	 |
| `principalNo` |	*Alphanumeric* |	2 |	M	| |	
| `Image Front` |	*file* |	|	M |	Front copy of the document. If document has single part, same has to be uploaded as part of file1. |
| `Image Back` |	*file* |	|	O |	Back copy of the document. If document has single part, file2 remains blank	|
| `categoryName` |	*Alphanumeric* |	30|	M |	Category of document being uploaded. This can be refered from tag categoryName in Get Document Matrix API	|
| `level` |	*Alphanumeric* |	2 |	M |	Level of document being uploaded. This can be refered from tag level in Get Document Matrix API	|
| `Entity` |	*Alphanumeric* |	|	M		| |
| `Mandatory` |	*Alphanumeric* |	10 |	M ||

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

The table below provides the list of application's error code and its description.
| ErrorCode |  Description/Values |
| --------  | ------------------ |
|`100`| Invalid Request |
|`101`| Missing Mandatory Fields |  
|`103`| Data Not Found.Please contact Application Support Team |
|`200`|  Success |  
|`301`| Document Type Required |
|`302`| IOException |
|`303`| Atleast One Document Required |  
|`304`| Invalid Document Type |
|`400`| Terminal not in Proper Status |  
|`415`| Invalid media type |
|`500`| Internal Error. Please contact Application Support Team |
|`700`| No record found for given AppURN and Sales Id |
|`701`| Unable to create APPURN |  
|`708`| AppURN already submitted |
|`900`|  Invalid AppURN |  
|`901`| AppURN Not Match |
|`902`| AppURN is Mandatory |
|`903`| Application already Submitted |  
|`904`| Json Processing Error |
|`905`|  Json Parse Error |  
|`906`| Json Mapping Error |
|`907`| Comments are empty |
|`908`| App URN not matching |
