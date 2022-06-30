# Local Integration Checklist

### Welcome to Fiserv Local integration solution

The local integration acts as an interface / communication layer between the Fiserv terminal application ('Parent application') and the third-party application ('Consumer application').<BR/> 

Before you begin, both the consumer application and the parent app must be installed in same device. The Fiserv Interface library (.aar library) will be integrated into Consumer app. A transaction flow will consist of the following steps:<BR/>

 - The Consumer application's transaction flow will call Fiserv Interface library to perform a transaction.
 - The interface library after performing sanity checks, will initiate the corresponding Parent application's transaction flow.
 - The Parent application completes the transaction and communicates back the result to the Fiserv Interface library.
 - The Fiserv Interface in turn communicates back the result to the Consumer application.

Handy tips for you to kick start your local based integration:





