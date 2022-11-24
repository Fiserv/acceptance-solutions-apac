# Document Matrix

This API is used to fetch the Document Matrix details using certain criteria sent in request message.

## How it works
1. Merchant needs to use this API if the merchant documents are submitted to Fiserv for partner credit underwriting process.
2. API has to be used to fetch the document matrix and use subsequent upload document API.
3. API response will contain the possible set of documents which the Partner can provide as part of Funding proof, Partner POI,
   Partner POA, Other categories, etc. 


## Endpoint

GET `https://www.uat.fdmerchantservices.com/boardinggateway/Externalboarding/secure/document`

## Payload Example

### Request Payload

```json
{
    "channelCode": "",
    "packageLevel": "",
    "userId": "",
    "boardingType": "NEWMID",
    "institutionCode": "100",
    "appChannel": "A12",
    "appType": "Tab",
    "institutionId": "47000000",
    "typeOfBusiness": "LLPARTNERSIP",
    "mccCode": "5542",
    "merchantGrade": "FH",
    "merchantType": "LG",
    "acceptanceType": "POSMOB",
    "international": "No",
    "iciciMerchant": "No",
    "dcc": "No",
    "fundingCurrency": "NET_INR"
}

```
  
***Token should be sent as Authorization.***

### Minimum Requirements

The table below contains the mandatory fields required for a successful request. The full request schemas are available in our [API Explorer](../api/?type=get&path=/Externalboarding/secure/document).

### Request
| Variable | Type | Length |  Mandatory / Optional / Conditional (M / O / C)  | Description / Values |
| -------- | ------- | -- | ------------ | ------------------ |
|`boardingType`|Alphanumeric|20|M|Type of Merchant: New MID / Add MID / Add TID|
|`institutionCode`|Alphanumeric|3|M|The unique value assigned to each channel.|
|`appChannel`|Alphanumeric|20|M|Application Channel|
|`appType`|Alphanumeric|8|M|Fixed Value API.|
|`institutionId`|Numeric|10|M|Institution number assigned to the institution.|
|`typeOfBusiness`|Alphanumeric|50|M|Type of business (eg.Sole Proprietor, Individual etc.)|
|`mccCode`|Numeric|20|M|Unique value assigned for each industry.|
|`merchantGrade`|Alphanumeric|40|M|The grade of the merchant decided as per the turnover.|
|`merchantType`|Alphanumeric|20|M|Type of merchant (eg.Large merchant,SME|
|`acceptanceType`|Alphanumeric|10|M|Static Value: ECOM / POSMOB |
|`international`|Alphanumeric|3|M|Applicable if the merchant accepts international transactions.|
|`iciciMerchant`|Alphanumeric|20|O|Applicable if the merchant is ICICI current bank account holder.|
|`dcc`|Alphanumeric|3|O|Applicable if the merchant has foreign rate conversion (Y/N).|
|`fundingCurrency`|Alphanumeric|8|M|The currency is settled to the merchant NET_INR, NET_USD, NET_AUD etc.|
|`newFundingAc`|Alphanumeric|20|O|Merchant's settlement account|


### Successful Response Payload

```json

{
  "status": {
    "statusCode": 200,
    "message": "Success"
  },
  "data": {
    "documentUpload": {
      "postFill": [
        {
          "categoryName": "LOCATION PHOTOS",
          "categoryInd": "E",
          "levels": [
            {
              "level": "1",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "2",
                  "documentName": "Capture the Merchant Store Photos",
                  "documentType": "D",
                  "fillType": "postfill",
                  "documentShortName": "Capture the Merchant Store Photos"
                }
              ]
            }
          ]
        },
        {
          "categoryName": "MITC",
          "categoryInd": "E",
          "levels": [
            {
              "level": "1",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "1",
                  "documentName": "MITC Document Page 1",
                  "documentType": "D",
                  "fillType": "postfill",
                  "documentShortName": "MITC Document Page 1"
                }
              ]
            },
            {
              "level": "2",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "118",
                  "documentName": "MITC Document Page 2",
                  "documentType": "D",
                  "fillType": "postfill",
                  "documentShortName": "MITC Document Page 2"
                }
              ]
            }
          ]
        },
        {
          "categoryName": "SOC",
          "categoryInd": "E",
          "levels": [
            {
              "level": "1",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "3",
                  "documentName": "socDocument",
                  "documentType": "D",
                  "fillType": "postfill",
                  "documentShortName": "socDocument"
                }
              ]
            }
          ]
        }
      ],
      "prefill": [
        {
          "categoryName": "Funding Proof",
          "categoryInd": "E",
          "levels": [
            {
              "level": "1",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "13",
                  "documentName": "cheque",
                  "documentType": "D",
                  "fillType": "prefill",
                  "documentShortName": "I-view, Cancelled Cheque"
                }
              ]
            },
            {
              "level": "2",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "7",
                  "documentName": "nachDocument",
                  "documentType": "D",
                  "fillType": "prefill",
                  "documentShortName": "NACH"
                }
              ]
            }
          ]
        },
        {
          "categoryName": "Other",
          "categoryInd": "E",
          "levels": [
            {
              "level": "1",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "18",
                  "documentName": "Non-HPCL Invoice or Agreement",
                  "documentType": "D",
                  "fillType": "prefill",
                  "documentShortName": "Non-HPCL Invoice or Agreement"
                }
              ]
            },
            {
              "level": "2",
              "isMandatory": "M",
              "documents": [
                {
                  "documentId": "14",
                  "documentName": "GSTN Declaration",
                  "documentType": "D",
                  "fillType": "prefill",
                  "documentShortName": "GSTN Declaration"
                },
                {
                  "documentId": "111",
                  "documentName": "GSTN Number",
                  "documentType": "D",
                  "fillType": "prefill",
                  "documentShortName": "GSTN Number"
                }
              ]
            }
          ]
        }
      ]
    },
    "document": [
      {
        "documentId": "89",
        "documentName": "Drugs Selling Lic issued by Food&Drug",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "89"
          }
        ],
        "documentShortName": "Drugs Selling Lic issued by Food&Drug"
      },
      {
        "documentId": "46",
        "documentName": "Lease Rent agreement Individual",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "46"
          }
        ],
        "documentShortName": "Lease Rent agreement Individual"
      },
      {
        "documentId": "48",
        "documentName": "PL",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "48"
          }
        ],
        "documentShortName": "PL"
      },
      {
        "documentId": "49",
        "documentName": "Declaration for accepting Donation",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "49"
          }
        ],
        "documentShortName": "Declaration for accepting Donation"
      },
      {
        "documentId": "112",
        "documentName": "GSTN Number for Sole Proprietors",
        "validations": [
          {
            "validationCode": "26",
            "validationType": "DATAPULL",
            "validationName": "Enter GSTN Number",
            "required": "Y",
            "documentId": "112",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/fetch"
            }
          }
        ],
        "preFields": [
          {
            "documentId": "112",
            "fieldName": "number",
            "fieldDisplayName": "Enter GSTN Number",
            "preField": "Y"
          },
          {
            "documentId": "112",
            "fieldName": "docType",
            "fieldDisplayName": "Type",
            "defaultValue": "gstSearch",
            "preField": "Y"
          }
        ],
        "postFields": [
          {
            "documentId": "112",
            "fieldName": "tradeName",
            "fieldDisplayName": "Trade Name",
            "signzyField": "displayLegalname",
            "preField": "N"
          },
          {
            "documentId": "112",
            "fieldName": "legalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "solePropLegalName",
            "preField": "N"
          },
          {
            "documentId": "112",
            "fieldName": "disputeLegalAddress",
            "fieldDisplayName": "Registered Address",
            "signzyField": "address",
            "preField": "N"
          },
          {
            "documentId": "112",
            "fieldName": "gstn",
            "fieldDisplayName": "GSTIN Number",
            "signzyField": "number",
            "preField": "N"
          },
          {
            "documentId": "112",
            "fieldName": "dateTrading",
            "fieldDisplayName": "Date of Commencement",
            "signzyField": "dateOfIssue",
            "preField": "N"
          },
          {
            "documentId": "112",
            "fieldName": "disputePinCode",
            "fieldDisplayName": "Pin Code",
            "signzyField": "pincode",
            "preField": "N"
          },
          {
            "documentId": "112",
            "fieldName": "merchantDetails.businessName",
            "fieldDisplayName": "Entity Name",
            "signzyField": "solePropEntityName",
            "preField": "N"
          }
        ],
        "documentShortName": "GSTN Number for Sole Proprietors"
      },
      {
        "documentId": "90",
        "documentName": "License by Indian Medical Coun",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "90"
          }
        ],
        "documentShortName": "License by Indian Medical Coun"
      },
      {
        "documentId": "118",
        "documentName": "MITC Document Page 2",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "118"
          }
        ],
        "documentShortName": "MITC Document Page 2"
      },
      {
        "documentId": "91",
        "documentName": "Resolution  to avail services",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "91"
          }
        ],
        "documentShortName": "Resolution  to avail services"
      },
      {
        "documentId": "92",
        "documentName": "Lease Rent agreement for Individual",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "92"
          }
        ],
        "documentShortName": "Lease Rent agreement for Individual"
      },
      {
        "documentId": "93",
        "documentName": "Agreement Copy for Socities&Associations",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "93"
          }
        ],
        "documentShortName": "Agreement Copy for Socities&Associations"
      },
      {
        "documentId": "51",
        "documentName": "Charity commisenor Certificate",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "51"
          }
        ],
        "documentShortName": "Charity commisenor Certificate"
      },
      {
        "documentId": "52",
        "documentName": "Trust Deed",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "52"
          }
        ],
        "documentShortName": "Trust Deed"
      },
      {
        "documentId": "96",
        "documentName": "LLP Agreement Deed",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "96"
          }
        ],
        "documentShortName": "LLP Agreement Deed"
      },
      {
        "documentId": "11",
        "documentName": "individualPan",
        "validations": [
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "11",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          },
          {
            "validationCode": "12",
            "validationType": "OCR",
            "validationName": "OCR via Signzy",
            "required": "Y",
            "documentId": "11"
          }
        ],
        "preFields": [],
        "postFields": [
          {
            "documentId": "11",
            "fieldName": "name",
            "fieldDisplayName": "Name",
            "signzyField": "autoregResponse.name",
            "preField": "N"
          },
          {
            "documentId": "11",
            "fieldName": "principalInfo.dateOfBirth",
            "fieldDisplayName": "DOB",
            "signzyField": "autoregResponse.dob",
            "preField": "N"
          },
          {
            "documentId": "11",
            "fieldName": "principalInfo.panCardNumber",
            "fieldDisplayName": "Individual PAN",
            "signzyField": "autoregResponse.number",
            "preField": "N"
          }
        ],
        "documentShortName": "Individual Pancard"
      },
      {
        "documentId": "12",
        "documentName": "businessPan",
        "validations": [
          {
            "validationCode": "12",
            "validationType": "OCR",
            "validationName": "OCR via Signzy",
            "required": "Y",
            "documentId": "12"
          },
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "12",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          }
        ],
        "preFields": [],
        "postFields": [
          {
            "documentId": "12",
            "fieldName": "legalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "autoregResponse.name",
            "preField": "N"
          },
          {
            "documentId": "12",
            "fieldName": "dateOfIssue",
            "fieldDisplayName": "Date of Commencement",
            "signzyField": "autoregResponse.dateOfIssue",
            "preField": "N"
          },
          {
            "documentId": "12",
            "fieldName": "businessPancard",
            "fieldDisplayName": "Corporate Pancard",
            "signzyField": "autoregResponse.number",
            "preField": "N"
          }
        ],
        "documentShortName": "Corporate Pancard"
      },
      {
        "documentId": "13",
        "documentName": "cheque",
        "validations": [
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "13",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          },
          {
            "validationCode": "12",
            "validationType": "OCR",
            "validationName": "OCR via Signzy",
            "required": "Y",
            "documentId": "13"
          }
        ],
        "preFields": [],
        "postFields": [
          {
            "documentId": "13",
            "fieldName": "ifsc",
            "fieldDisplayName": "IFSC",
            "signzyField": "autoregResponse.ifsc",
            "preField": "N"
          },
          {
            "documentId": "13",
            "fieldName": "bankAccountNumber",
            "fieldDisplayName": "Bank Account Number",
            "signzyField": "autoregResponse.number",
            "preField": "N"
          },
          {
            "documentId": "13",
            "fieldName": "bankName",
            "fieldDisplayName": "Bank Name",
            "signzyField": "autoregResponse.bankName",
            "preField": "N"
          }
        ],
        "documentShortName": "Iview,Cancelled Cheque/Bank Statement"
      },
      {
        "documentId": "59",
        "documentName": "Tax receipts for property tax paid",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "59"
          }
        ],
        "documentShortName": "Tax receipts for property tax paid"
      },
      {
        "documentId": "19",
        "documentName": "VAT Registration Certificate",
        "validations": [
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "19",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          },
          {
            "validationCode": "5",
            "validationType": "DATAPULL",
            "validationName": "Enter VAT Number",
            "required": "Y",
            "documentId": "19",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/fetch"
            }
          }
        ],
        "preFields": [
          {
            "documentId": "19",
            "fieldName": "docType",
            "fieldDisplayName": "Type",
            "defaultValue": "tin",
            "preField": "Y"
          },
          {
            "documentId": "19",
            "fieldName": "number",
            "fieldDisplayName": "Enter VAT Number",
            "preField": "Y"
          }
        ],
        "postFields": [
          {
            "documentId": "19",
            "fieldName": "displayLegalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "displayLegalname",
            "preField": "N"
          },
          {
            "documentId": "19",
            "fieldName": "disputePinCode",
            "fieldDisplayName": "Pin Code",
            "signzyField": "pincode",
            "preField": "N"
          },
          {
            "documentId": "19",
            "fieldName": "legalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "name",
            "preField": "N"
          },
          {
            "documentId": "19",
            "fieldName": "dateTrading",
            "fieldDisplayName": "Date of Commencement",
            "signzyField": "dateOfIssue",
            "preField": "N"
          },
          {
            "documentId": "19",
            "fieldName": "businessRegNumber",
            "fieldDisplayName": "VAT Number",
            "signzyField": "number",
            "preField": "N"
          },
          {
            "documentId": "19",
            "fieldName": "disputeLegalAddress",
            "fieldDisplayName": "Registered Address",
            "signzyField": "address",
            "preField": "N"
          }
        ],
        "documentShortName": "VAT Registration Certificate"
      },
      {
        "documentId": "2",
        "documentName": "Capture the Merchant Store Photos",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "2"
          }
        ],
        "documentShortName": "Capture the Merchant Store Photos"
      },
      {
        "documentId": "3",
        "documentName": "socDocument",
        "validations": [],
        "documentShortName": "socDocument"
      },
      {
        "documentId": "5",
        "documentName": "cheque",
        "validations": [
          {
            "validationCode": "10",
            "validationType": "DATAPULL",
            "validationName": "Enter Bank Account Number",
            "required": "Y",
            "documentId": "5",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/bank"
            }
          },
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "5",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          },
          {
            "validationCode": "19",
            "validationType": "PENNYDROP",
            "validationName": "Penny Drop",
            "required": "Y",
            "documentId": "5",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/bank"
            }
          },
          {
            "validationCode": "12",
            "validationType": "OCR",
            "validationName": "OCR via Signzy",
            "required": "Y",
            "documentId": "5"
          }
        ],
        "preFields": [
          {
            "documentId": "5",
            "fieldName": "beneficiaryAccount",
            "fieldDisplayName": "Bank Account Number",
            "signzyField": "autoregResponse.number",
            "preField": "Y"
          },
          {
            "documentId": "5",
            "fieldName": "beneficiaryIFSC",
            "fieldDisplayName": "IFSC Code",
            "signzyField": "autoregResponse.ifsc",
            "preField": "Y"
          },
          {
            "documentId": "5",
            "fieldName": "bankName",
            "fieldDisplayName": "Bank Name",
            "signzyField": "autoregResponse.bankName",
            "preField": "Y"
          }
        ],
        "postFields": [
          {
            "documentId": "5",
            "fieldName": "bankName",
            "fieldDisplayName": "Bank Name",
            "signzyField": "autoregResponse.bankName",
            "preField": "N"
          },
          {
            "documentId": "5",
            "fieldName": "bankAccountNumber",
            "fieldDisplayName": "Bank A/C",
            "signzyField": "essentials.beneficiaryAccount",
            "preField": "N"
          },
          {
            "documentId": "5",
            "fieldName": "nameOnBankAccount",
            "fieldDisplayName": "Customer Name",
            "signzyField": "result.bankTransfer.beneName",
            "preField": "N"
          },
          {
            "documentId": "5",
            "fieldName": "ifsc",
            "fieldDisplayName": "IFSC",
            "signzyField": "essentials.beneficiaryIFSC",
            "preField": "N"
          }
        ],
        "documentShortName": "Cancelled Cheque/Bank Statement"
      },
      {
        "documentId": "8",
        "documentName": "Ecom Technical Template",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "8"
          }
        ],
        "documentShortName": "Ecom Technical Template"
      },
      {
        "documentId": "9",
        "documentName": "E-com Addendum",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "9"
          }
        ],
        "documentShortName": "E-com Addendum"
      },
      {
        "documentId": "20",
        "documentName": "GSTN Registration Certificate",
        "validations": [
          {
            "validationCode": "26",
            "validationType": "DATAPULL",
            "validationName": "Enter GSTN Number",
            "required": "Y",
            "documentId": "20",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/fetch"
            }
          },
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "20"
          }
        ],
        "preFields": [
          {
            "documentId": "20",
            "fieldName": "docType",
            "fieldDisplayName": "Type",
            "defaultValue": "gstSearch",
            "preField": "Y"
          },
          {
            "documentId": "20",
            "fieldName": "number",
            "fieldDisplayName": "Enter GSTN Number",
            "preField": "Y"
          }
        ],
        "postFields": [
          {
            "documentId": "20",
            "fieldName": "displayLegalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "displayLegalname",
            "preField": "N"
          },
          {
            "documentId": "20",
            "fieldName": "legalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "name",
            "preField": "N"
          },
          {
            "documentId": "20",
            "fieldName": "disputeLegalAddress",
            "fieldDisplayName": "Registered Address",
            "signzyField": "address",
            "preField": "N"
          },
          {
            "documentId": "20",
            "fieldName": "gstn",
            "fieldDisplayName": "GSTIN Number",
            "signzyField": "number",
            "preField": "N"
          }
        ],
        "documentShortName": "GSTN Registration Certificate"
      },
      {
        "documentId": "21",
        "documentName": "Udhyog Aadhar",
        "validations": [
          {
            "validationCode": "7",
            "validationType": "DATAPULL",
            "validationName": "Enter Udhyog Aadhar",
            "required": "Y",
            "documentId": "21",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/fetch"
            }
          },
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "21",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          }
        ],
        "preFields": [
          {
            "documentId": "21",
            "fieldName": "docType",
            "fieldDisplayName": "Type",
            "defaultValue": "udhyogAadhaarUan",
            "preField": "Y"
          },
          {
            "documentId": "21",
            "fieldName": "number",
            "fieldDisplayName": "Enter Udhyog Aadhar",
            "preField": "Y"
          }
        ],
        "postFields": [
          {
            "documentId": "21",
            "fieldName": "displayLegalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "displayLegalname",
            "preField": "N"
          },
          {
            "documentId": "21",
            "fieldName": "dateOfIssue",
            "fieldDisplayName": "Date of Commencement",
            "signzyField": "dateOfIssue",
            "preField": "N"
          },
          {
            "documentId": "21",
            "fieldName": "legalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "name",
            "preField": "N"
          },
          {
            "documentId": "21",
            "fieldName": "dateOfIssue",
            "fieldDisplayName": "Date of Commencement",
            "signzyField": "autoregResponse.dateOfIssue",
            "preField": "N"
          },
          {
            "documentId": "21",
            "fieldName": "number",
            "fieldDisplayName": "UAN",
            "signzyField": "number",
            "preField": "N"
          }
        ],
        "documentShortName": "Udhyog Aadhar"
      },
      {
        "documentId": "65",
        "documentName": "Partnership Deed",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "65"
          }
        ],
        "documentShortName": "Partnership Deed"
      },
      {
        "documentId": "22",
        "documentName": "ShopEstablishmentActCertificate",
        "validations": [
          {
            "validationCode": "8",
            "validationType": "DATAPULL",
            "validationName": "Enter Shop and Est License Number & State",
            "required": "Y",
            "documentId": "22",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/fetch"
            }
          }
        ],
        "preFields": [
          {
            "documentId": "22",
            "fieldName": "docType",
            "fieldDisplayName": "Type",
            "defaultValue": "snec",
            "preField": "Y"
          },
          {
            "documentId": "22",
            "fieldName": "number",
            "fieldDisplayName": "Shop License Number",
            "preField": "Y"
          },
          {
            "documentId": "22",
            "fieldName": "state",
            "fieldDisplayName": "Shop License State",
            "preField": "Y"
          }
        ],
        "postFields": [
          {
            "documentId": "22",
            "fieldName": "displayLegalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "displayLegalname",
            "preField": "N"
          },
          {
            "documentId": "22",
            "fieldName": "legalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "name",
            "preField": "N"
          },
          {
            "documentId": "22",
            "fieldName": "dateOfIssue",
            "fieldDisplayName": "Date of Commencement",
            "signzyField": "dateOfIssue",
            "preField": "N"
          },
          {
            "documentId": "22",
            "fieldName": "disputeLegalAddress",
            "fieldDisplayName": "Registered Address",
            "signzyField": "address",
            "preField": "N"
          },
          {
            "documentId": "22",
            "fieldName": "businessRegNumber",
            "fieldDisplayName": "License Number",
            "signzyField": "number",
            "preField": "N"
          },
          {
            "documentId": "22",
            "fieldName": "disputePinCode",
            "fieldDisplayName": "disputePinCode",
            "signzyField": "splitAddress.pincode",
            "preField": "N"
          }
        ],
        "documentShortName": "Shop & Establishment Act Certificate / Gomastha"
      },
      {
        "documentId": "66",
        "documentName": "Registered Partnership Deed",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "66"
          }
        ],
        "documentShortName": "Registered Partnership Deed"
      },
      {
        "documentId": "23",
        "documentName": "drivingLicence",
        "validations": [
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "23",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          },
          {
            "validationCode": "12",
            "validationType": "OCR",
            "validationName": "OCR via Signzy",
            "required": "Y",
            "documentId": "23"
          }
        ],
        "preFields": [],
        "postFields": [
          {
            "documentId": "23",
            "fieldName": "principalInfo.pinCode",
            "fieldDisplayName": "Pin Code",
            "signzyField": "autoregResponse.pincode",
            "preField": "N"
          },
          {
            "documentId": "23",
            "fieldName": "principalInfo.state",
            "fieldDisplayName": "State",
            "signzyField": "autoregResponse.state",
            "preField": "N"
          },
          {
            "documentId": "23",
            "fieldName": "principalInfo.city",
            "fieldDisplayName": "City",
            "signzyField": "autoregResponse.city",
            "preField": "N"
          },
          {
            "documentId": "23",
            "fieldName": "name",
            "fieldDisplayName": "Name",
            "signzyField": "autoregResponse.name",
            "preField": "N"
          },
          {
            "documentId": "23",
            "fieldName": "principalInfo.address",
            "fieldDisplayName": "Address",
            "signzyField": "autoregResponse.address",
            "preField": "N"
          },
          {
            "documentId": "23",
            "fieldName": "number",
            "fieldDisplayName": "License Number",
            "signzyField": "autoregResponse.number",
            "preField": "N"
          }
        ],
        "documentShortName": "Driving License"
      },
      {
        "documentId": "67",
        "documentName": "Property Ownership deed",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "67"
          }
        ],
        "documentShortName": "Property Ownership deed"
      },
      {
        "documentId": "24",
        "documentName": "passport",
        "validations": [
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "24",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          },
          {
            "validationCode": "12",
            "validationType": "OCR",
            "validationName": "OCR via Signzy",
            "required": "Y",
            "documentId": "24"
          }
        ],
        "preFields": [],
        "postFields": [
          {
            "documentId": "24",
            "fieldName": "name",
            "fieldDisplayName": "Name",
            "signzyField": "autoregResponse.name",
            "preField": "N"
          },
          {
            "documentId": "24",
            "fieldName": "principalInfo.state",
            "fieldDisplayName": "State",
            "signzyField": "autoregResponse.state",
            "preField": "N"
          },
          {
            "documentId": "24",
            "fieldName": "principalInfo.city",
            "fieldDisplayName": "City",
            "signzyField": "autoregResponse.city",
            "preField": "N"
          },
          {
            "documentId": "24",
            "fieldName": "principalInfo.address",
            "fieldDisplayName": "Address",
            "signzyField": "autoregResponse.address",
            "preField": "N"
          },
          {
            "documentId": "24",
            "fieldName": "principalInfo.pinCode",
            "fieldDisplayName": "Pin Code",
            "signzyField": "autoregResponse.pincode",
            "preField": "N"
          },
          {
            "documentId": "24",
            "fieldName": "number",
            "fieldDisplayName": "Passport Number",
            "signzyField": "autoregResponse.number",
            "preField": "N"
          }
        ],
        "documentShortName": "Passport"
      },
      {
        "documentId": "25",
        "documentName": "aadhaar",
        "validations": [
          {
            "validationCode": "12",
            "validationType": "OCR",
            "validationName": "OCR via Signzy",
            "required": "Y",
            "documentId": "25"
          },
          {
            "validationCode": "18",
            "validationType": "DATAEDIT",
            "validationName": "Data Editable",
            "required": "Y",
            "documentId": "25",
            "api": {
              "url": "/boarding/document/{appURN}/textmatch"
            }
          }
        ],
        "preFields": [],
        "postFields": [
          {
            "documentId": "25",
            "fieldName": "principalInfo.state",
            "fieldDisplayName": "State",
            "signzyField": "autoregResponse.state",
            "preField": "N"
          },
          {
            "documentId": "25",
            "fieldName": "principalInfo.city",
            "fieldDisplayName": "City",
            "signzyField": "autoregResponse.city",
            "preField": "N"
          },
          {
            "documentId": "25",
            "fieldName": "name",
            "fieldDisplayName": "Name",
            "signzyField": "autoregResponse.name",
            "preField": "N"
          },
          {
            "documentId": "25",
            "fieldName": "number",
            "fieldDisplayName": "Aadhaar Number",
            "signzyField": "autoregResponse.number",
            "preField": "N"
          },
          {
            "documentId": "25",
            "fieldName": "principalInfo.address",
            "fieldDisplayName": "Address",
            "signzyField": "autoregResponse.address",
            "preField": "N"
          },
          {
            "documentId": "25",
            "fieldName": "principalInfo.pinCode",
            "fieldDisplayName": "Pin Code",
            "signzyField": "autoregResponse.pincode",
            "preField": "N"
          },
          {
            "documentId": "25",
            "fieldName": "principalInfo.dateOfBirth",
            "fieldDisplayName": "DOB",
            "signzyField": "autoregResponse.dob",
            "preField": "N"
          }
        ],
        "documentShortName": "Aadhar Card"
      },
      {
        "documentId": "69",
        "documentName": "Importer-Exporter with PAN Card",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "69"
          }
        ],
        "documentShortName": "Importer-Exporter with PAN Card"
      },
      {
        "documentId": "27",
        "documentName": "Articles of Association AOA",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "27"
          }
        ],
        "preFields": [],
        "postFields": [
          {
            "documentId": "27",
            "fieldName": "bankAccountNumber",
            "fieldDisplayName": "Bank A/C",
            "signzyField": "essentials.beneficiaryAccount",
            "preField": "N"
          },
          {
            "documentId": "27",
            "fieldName": "ifsc",
            "fieldDisplayName": "IFSC",
            "signzyField": "essentials.beneficiaryIFSC",
            "preField": "N"
          },
          {
            "documentId": "27",
            "fieldName": "nameOnBankAccount",
            "fieldDisplayName": "Customer Name",
            "signzyField": "result.bankTransfer.beneName",
            "preField": "N"
          }
        ],
        "documentShortName": "Articles of Association AOA"
      },
      {
        "documentId": "28",
        "documentName": "Memorandum of association MOA",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "28"
          }
        ],
        "documentShortName": "Memorandum of association MOA"
      },
      {
        "documentId": "71",
        "documentName": "Last available Income Tax",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "71"
          }
        ],
        "documentShortName": "Last available Income Tax"
      },
      {
        "documentId": "72",
        "documentName": "Income Tax Return - Proprietor",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "72"
          }
        ],
        "documentShortName": "Income Tax Return - Proprietor"
      },
      {
        "documentId": "73",
        "documentName": "Tax Return - Partnership",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "73"
          }
        ],
        "documentShortName": "Tax Return - Partnership"
      },
      {
        "documentId": "30",
        "documentName": "Certificate of Incorporation",
        "validations": [
          {
            "validationCode": "6",
            "validationType": "DATAPULL",
            "validationName": "Enter CIN (ROC) Number",
            "required": "Y",
            "documentId": "30",
            "api": {
              "url": "/boarding/signzy/identity/{appURN}/fetch"
            }
          }
        ],
        "preFields": [
          {
            "documentId": "30",
            "fieldName": "docType",
            "fieldDisplayName": "Type",
            "defaultValue": "simpleSearchCin",
            "preField": "Y"
          },
          {
            "documentId": "30",
            "fieldName": "number",
            "fieldDisplayName": "Enter CIN",
            "preField": "Y"
          }
        ],
        "postFields": [
          {
            "documentId": "30",
            "fieldName": "displayLegalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "displayLegalname",
            "preField": "N"
          },
          {
            "documentId": "30",
            "fieldName": "number",
            "fieldDisplayName": "CIN",
            "signzyField": "number",
            "preField": "N"
          },
          {
            "documentId": "30",
            "fieldName": "legalName",
            "fieldDisplayName": "Legal Name",
            "signzyField": "name",
            "preField": "N"
          },
          {
            "documentId": "101",
            "fieldName": "disputeLegalAddress",
            "fieldDisplayName": "Registered Address",
            "validationName": "PDF",
            "required": "Y"
          }
        ],
        "documentShortName": "Power of Attorney to members"
      },
      {
        "documentId": "106",
        "documentName": "Tax ack land premises allotment",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "106"
          }
        ],
        "documentShortName": "Tax ack land premises allotment"
      },
      {
        "documentId": "108",
        "documentName": "Govt registration of AOP BOI",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "108"
          }
        ],
        "documentShortName": "Govt registration of AOP BOI"
      },
      {
        "documentId": "82",
        "documentName": "Certificate-cum-ack by District Ind",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "82"
          }
        ],
        "documentShortName": "Certificate-cum-ack by District Ind"
      },
      {
        "documentId": "40",
        "documentName": "SalesTaxServiceTaxPTRegCerti",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "40"
          }
        ],
        "documentShortName": "SalesTaxServiceTaxPTRegCerti"
      },
      {
        "documentId": "86",
        "documentName": "Reg Certi under Statute Act of GOI",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "86"
          }
        ],
        "documentShortName": "Reg Certi under Statute Act of GOI"
      },
      {
        "documentId": "87",
        "documentName": "Application Form for VAT Registration",
        "validations": [
          {
            "validationCode": "27",
            "validationType": "PDF",
            "validationName": "PDF",
            "required": "Y",
            "documentId": "87"
          }
        ],
        "documentShortName": "Application Form for VAT Registration"
      }
    ]
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
|`200`| Success |
|`400`| Terminal had not been set up correctly. |  
|`401`| Unauthorized |
|`900`|  Invalid App URN |  
|`901`| App URN is not matching. |
|`902`| App URN is a mandatory value. |
|`903`| Application had already submitted. |  
|`904`| JSON Processing Error |
|`905`| JSON Parse Error |  
|`906`| JSON Mapping Error |
|`907`| Comment field empty. |
|`908`| App URN does not match. |
