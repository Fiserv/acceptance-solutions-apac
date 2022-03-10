# Welcome to Merchant Solutions Web Services

The Merchant Solutions APIs are built on the foundation of REST. The APIs accept standard JSON requests and return JSON encoded responses while leveraging industry standard [HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) for a seamless integration. Interaction through our APIs provides the developer community the ability to retrieve/update the customer demographic information, account's financial information,and, the payment instrument details in a simple and intuitive manner. It also provides APIs to retrieve transactions, statements details, loyalty points, offers, and, multiple EMIs conversion details.  

Our APIs are broadly grouped into following sub-catagories.  Please click to specific category of interest to get more details

# Cloud POI
- [Login](./?path=/docs/APIs/UAM/UAM.md)

- [Payment API](./?path=docs/APIs/PaymentAPI/ProcessAmount.md)

# Commerce Connect
- Coming soon

#  Boarding
- Comming soon

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
