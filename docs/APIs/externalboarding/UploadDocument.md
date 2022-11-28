# Document Upload

This API is used for uploading of documents by merchants.

## How it works
1. Merchant needs to use this API as a part of Create URN API with application URN generated in the request API, to tag the documents to 
   a particular Application URN.
2. This API would follow the Get Document matrix API and has to be submitted before Application Submit API.
3. The API response will give unique document IDs for each document which has to be provided in subsequent application APIs. 

## Endpoint

POST `https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/document/{appUrn}`

## Payload Example

### Request Payload

```json

https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/document/10000745

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/document/{appUrn}).

### Request
| Variable | Type | Length |  Mandatory / Optional / Conditional  (M / O / C)  | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
|`appURN`|Alphanumeric|30|M|App URN is returned as part of Create URN API.|
|`docType`|Alphanumeric|30|| Name of document being uploaded. |
|`fileType`|Alphanumeric|10|M| Type of the file uploaded. |
|`principalNo`|Alphanumeric|2|M|If there are two Principal Owners for which the documents are uploaded. - the first set value
should be set as 1 - the second set value should be set as 2. If there are multiple sets of UBO for which documents are to be uploaded, each set will have its respective number listed in sequential manner.|
|`imageFront`|File|-|M|Front copy of the document. If the document only consists of a single part, the same file has to be uploaded as part of file 1. |
|`imageBack`|File|-|O|Back copy of the document. If the document only consists of a single part, file 2 remains blank.|
|`categoryName`|Alphanumeric|30|M| Category of document that is being uploaded. This can be referred to, from tag categoryName in the Get Document Matrix API..|
|`level`|Alphanumeric|2|M|Level of document that is being uploaded. This can be referred from tag level in the Get Document Matrix API.|


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
| Error Code |  Description / Values |
| --------  | ------------------ |
|`100`| Invalid request |
|`101`| Missing mandatory fields |  
|`103`| Data not found, please contact application support team. |
|`200`| Success |  
|`301`| Document type required |
|`302`| IO exception |
|`303`| Atleast one document required. |  
|`304`| Invalid document type |
|`400`| Terminal had not been set up correctly. |  
|`415`| Invalid media type |
|`500`| Internal error, please contact Application Support Team. |
|`700`| No record found for the given App URN and Sales ID. |
|`701`| Unable to create App URN. |  
|`708`| App URN had already been submitted. |
|`900`| Invalid App URN |  
|`901`| App URN mismatch |
|`902`| App URN is a mandatory value. |
|`903`| Application had already submitted. |  
|`904`| JSON Processing Error |
|`905`| JSON Parse Error |  
|`906`| JSON Mapping Error |
|`907`| Comment field empty. |
|`908`| App URN does mismatch |
