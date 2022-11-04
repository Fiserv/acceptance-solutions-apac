# Local Based Integration Checklist

<img src="https://raw.githubusercontent.com/Fiserv/acceptance-solutions-apac/develop/assets/images/pos3.jpg " width="1185">

### Local Based Integration Use Cases 

Our local integration APIs facilitates to connect with your in-house central or any standalone systems to automate the entire billing to payments transactions.<BR/>

From inventory tracking, reservations, billing and reconciliation applications that your business is using, our local-based API opens many possibilities for your business to cater to your business’ payment eco-system.<BR/> <br>
<br>



<B> Use case considerations on how our local based integration can support your ecosystem: </B>

 - Your current point of sale (POS) system(s) have been implemented on local-based connectivity
 - Technically your business direction for your payment and reporting ecosystem is planned to be on local-based integrations
 - *If you are a hospitality-based business using Oracle Opera Payment Interface (OPI) to support Oracle Property Management System (PMS) solutions
   - Enjoy the benefits of enabling tokenized payment transactions to be integrated to Oracle Payment Interface (OPI)
 - Optimize your financial management with digitalized receipts that can be viewed and downloaded on Fiserv Business Point (merchant portal)

<B>Once you have assessed the use cases, discover our APIs [here](./?path=docs/LocalPOI.md&branch=develop) for a further deep dive.</B>

<BR/>


<img src="https://raw.githubusercontent.com/Fiserv/acceptance-solutions-apac/develop/assets/images/pos5.jpg " width="1185">


### Welcome to Fiserv Local Based integration solution

The local integration acts as an interface / communication layer between the Fiserv terminal application ('Parent application') and the third-party application ('Consumer application').<BR/> 

Before you begin, both the consumer application and the parent app must be installed in same device. The Fiserv Interface library (.aar library) will be integrated into Consumer app. A transaction flow will consist of the following steps:<BR/>

 - The Consumer application's transaction flow will call Fiserv Interface library to perform a transaction.
 - The interface library after performing sanity checks, will initiate the corresponding Parent application's transaction flow.
 - The Parent application completes the transaction and communicates back the result to the Fiserv Interface library.
 - The Fiserv Interface in turn communicates back the result to the Consumer application.

  Handy tips for you to kick start your local based integration:

1. <B>Set up your test account [here](./?path=docs/introduction/contact-us.md&branch=develop)</B>

2. Additionally, these are a few <b>pre-requisites</b> for local integration solution using Fiserv's Android based terminals.

    - The Interface library (MSInterfaceSdk.aar) 
    - Android Studio 3.x
    - Kitkat or higher versions of Android - API Level 19+

2. For <B>hospitality-based</B> merchants, if you do require cloud-based integration to Oracle Opera Payment Interface (OPI) to support Oracle Property Management System (PMS).

   - Please reach out to our support team for an assessment with a through run through of OPI checklist
   - Engage your appointed Oracle OPI solutions provider for a technical discussion with our integration support team

3. Assess with your <b>in-house network architecture team </b> and align on the connectivity requirements

   - For detailed technical compatibility requirements, do reach out to our integration support team

4. Check if your appointed point of sale (POS) provider had been certified with Fiserv [here](./?path=docs/LocalPOI.md&branch=develop).


<img src="https://raw.githubusercontent.com/Fiserv/acceptance-solutions-apac/develop/assets/images/pos6.jpg " width="1185">

# Step 3: Define
## Who, What and When?

<B>Scope out what your business requires</B>

1. Define and finalize your requirements for integration to your point of sale (POS)
   - Who are the users, and what are their integration requirements to be utilised with point of sale (POS) systems?
   - What are you trying to achieve from a customer experience, operational and reporting perspective?
   - When is your intended target launch date?
2. Decide on the integration approach
3. Do reach out to your account manager to apply for test terminal(s), with information that will help us assist you better:-
   - No. of test terminals required
   - Define which payment modes are required
   - Plan out when do you target to conduct testing and 
   - When is your targeted go-live date in production

<BR/>

<img src="https://raw.githubusercontent.com/Fiserv/acceptance-solutions-apac/develop/assets/images/pos7.jpg " width="1185">

# Step 4: Integrate
## Break the big plan into small steps

<B>Integrate and communicate</B>

1. Identify key points of contact from your various stakeholders.
2. Plan with your technology department / external vendor on the timelines.
3. Review Fiserv API documents [here](./?path=docs/LocalPOI.md&branch=develop).Explore the sample request and response APIs provided in the sandbox.
4. <b>Kick start your integration development with our APIs.</b>

For any clarifications or support required on technical integration, do reach out to our integration support teams [here](./?path=docs/introduction/contact-us.md&branch=develop).

<div style="background-color:grey;"><b>Handy Tips</b>: You may wish to consider discussing early with your team on which test scenarios would be required. The test scenarios are typically based on your daily operational needs. (Eg.which are your customers’ most used payment modes.)</div>


<img src="https://raw.githubusercontent.com/Fiserv/acceptance-solutions-apac/develop/assets/images/pos8.jpg " width="1185">


# Step 5: Test
## Plan, Test and Review

<B>A well planned testing provides assurance for a smooth go-live.</B>

1. Analyse the testing scope and requirements
2. Draft out the test plan, timelines and test cases with your technology team, external vendors (if applicable), and internal users
3. Align with Fiserv on your testing plans
   - Check on any firewalls / IPs that needs to be set-up
   - Ensure the relevant test keys and / test certificates have been installed, pointing to the sandbox environment
4. Execute the testing process
    - For any clarifications or support on testing challenges during integration, do reach out to our integration support teams [here](./?path=docs/introduction/contact-us.md&branch=develop).
5. Test cycle closure upon successful completion

<BR/>

<img src="https://raw.githubusercontent.com/Fiserv/acceptance-solutions-apac/develop/assets/images/pos9.jpg " width="1185">

# Step 6: Activate
## Deploy & Go-Live

<B>Live verification and monitoring</B>

1. Please engage your account manager to ensure your production credentials have been set-up
2. Apply for production terminals, with these information ready:
   - No. of terminals required
   - Define which payment modes are required
   - Information fields on charge slips / eReceipts
   - For deployment:
     - Points of contact for coordinating on-site
     - Date, time and location(s) for deployment
   - Conduct live verification
3. Monitor the performance of the Fiserv payment terminals to your point of sale (POS) systems

For any queries post deployment, do contact our support teams [here](./?path=docs/introduction/contact-us.md&branch=develop).
