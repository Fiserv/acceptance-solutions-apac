# Local Integration Checklist1

### Welcome to Fiserv Local integration solution

The local integration acts as an interface / communication layer between the Fiserv terminal application ('Parent application') and the third-party application ('Consumer application').<BR/> 

Before you begin, both the consumer application and the parent app must be installed in same device. The Fiserv Interface library (.aar library) will be integrated into Consumer app. A transaction flow will consist of the following steps:<BR/>

 - The Consumer application's transaction flow will call Fiserv Interface library to perform a transaction.
 - The interface library after performing sanity checks, will initiate the corresponding Parent application's transaction flow.
 - The Parent application completes the transaction and communicates back the result to the Fiserv Interface library.
 - The Fiserv Interface in turn communicates back the result to the Consumer application.

Handy tips for you to kick start your local based integration:

1) <B>Set up your test account here</B>

 Additionally, these are a few pre-requisites for local integration solution using Fiserv's Android based terminals.

 - The Interface library (MSInterfaceSdk.aar)
 - Android Studio 3.x
 - Kitkat or higher versions of Android - API Level 19+

2) For <B>hospitality-based</B> merchants, if you do require cloud-based integration to Oracle Opera Payment Interface (OPI) to 
   support Oracle Property Management System (PMS).

    - Please reach out to our support team for an assessment with a through run through of OPI checklist
    - Engage your appointed Oracle OPI solutions provider for a technical discussion with our integration support team

3) Assess with your in-house network architecture team and align on the connectivity requirements

    - For detailed technical compatibility requirements, do reach out to our integration support team

4) Check if your appointed point of sale (POS) provider had been certified with Fiserv here.




 











