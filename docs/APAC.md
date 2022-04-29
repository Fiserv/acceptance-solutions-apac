# Welcome to Merchant Solutions Web Services

The Merchant Solutions APIs are built on the foundation of REST. The APIs accept standard JSON requests and return JSON encoded responses while leveraging industry standard [HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) for a seamless integration. Interaction through our APIs provides the developer community the ability to retrieve/update the customer demographic information, account's financial information,and, the payment instrument details in a simple and intuitive manner. It also provides APIs to retrieve transactions, statements details, loyalty points, offers, and, multiple EMIs conversion details.  

Our APIs are broadly grouped into following sub-catagories. Please click to specific category of interest to get more details

# Cloud POI

- [Login](./?path=/docs/APIs/UAM/UAM.md)

- [Sale Card](./?path=docs/APIs/PaymentAPI/SaleCard.md)

- [PreAuth Sale](./?path=docs/APIs/PaymentAPI/PreAuthSale.md)

- [PreAuth Completion](./?path=docs/APIs/PaymentAPI/PreAuthCompletion.md)

- [Refund](./?path=docs/APIs/PaymentAPI/Refund.md)

- [Void](./?path=docs/APIs/PaymentAPI/Void.md)

- [EMI Sale](./?path=docs/APIs/PaymentAPI/EMISale.md)

- [Transaction status Check](./?path=docs/APIs/PaymentAPI/TransactionStatusCheck.md)

- [Sale with Local Payment Method](./?path=docs/APIs/PaymentAPI/SaleLocalPaymentMethod.md)

- [Settlement Transaction](./?path=docs/APIs/PaymentAPI/SettlementTransaction.md)

#  Boarding

- [Login](./?path=/docs/APIs/externalboarding/Login.md)

- [Create URN](./?path=/docs/APIs/externalboarding/CreateURN.md)

- [Get Package List](./?path=/docs/APIs/externalboarding/GetPackageList.md)

- [Get Package ID](./?path=/docs/APIs/externalboarding/GetPackageId.md)

- [Get Document Matrix](./?path=/docs/APIs/externalboarding/GetDocumentMatrix.md)

- [Upload Document](./?path=/docs/APIs/externalboarding/UploadDocument.md)

- [MID - Inquiry](./?path=/docs/APIs/externalboarding/MidInquiry.md)

- [SUBMIT - New Merchant](./?path=/docs/APIs/externalboarding/NewMerchant.md)

- [SUBMIT - Additional Outlet](./?path=/docs/APIs/externalboarding/AdditionalOutlet.md)

- [SUBMIT - Additional Device](./?path=/docs/APIs/externalboarding/AdditionalDevice.md)

- [SUBMIT - Single MID PayFac](./?path=/docs/APIs/externalboarding/SingleMIDPayFac.md)

- [SUBMIT - Multi MID PayFac](./?path=/docs/APIs/externalboarding/MultiMIDPayFac.md)

- [Application Status Inquiry](./?path=/docs/APIs/externalboarding/ApplicationStatusInquiry.md)

---

## Access Merchant Solution APIs

Follow the below steps to get an access to the Developer Studio and use merchant solution APIs.

### 1. Sign up for  Developer Studio

Request for APIs credentials through your Account relationship manager.

### 2. Getting your API key

The Account relationship manager will share the credentials via the preferred secure channel.

### 3. Constructing the API call

Once the credentials are provided, make a call to the signon API. In the response, a a unique one-time token will be provided in the response. 

Use the token for any subsequent API calls.  The token must be passed in the request header name "Authorization".  

---
