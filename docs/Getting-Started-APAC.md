# Getting Started with APAC Merchant Solutions 

APAC Merchant Solutions a one-stop-solution for SMB and enterprise clients, as well as ISO’s to get easy and instant access to API’s required to integrate with our terminal and eCommerce solutions.

From payments to onboarding, eCommerce or Point-of-Sale integrations, enjoy the benefits of hassle free integration through seamless sample code sharing, quick access sandbox environment, test credential management. 

APAC Merchant Solution extends a multitude of payment options to support your payment needs, including debit cards, credit cards and digital payments like Apple Pay, and Google Pay, as well as local payment methods.

Our services include; tokenization, 3-D Secure, creating and managing recurring payments, instalments, setting up standing instructions, EMV and contactless payments, secure hosted Payment Pages, Payment URLs, and more.

Browse our catalogue and integrate with our APIs to enrich your clients' digital experiences.

# Cloud POI

- [Login](./?path=/docs/APIs/CloudPOI/Login.md)

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
