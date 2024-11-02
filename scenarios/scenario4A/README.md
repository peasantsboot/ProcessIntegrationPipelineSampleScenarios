# Scenario 4A

Scenario 4A is similar to scenario 4, however in the current case we use a custom extension to determine the list of receivers instead of running an XSLT
from the Partner Directory. Furthermore, since each receiver has one interface only, we can bypass the interface determination. So, the receivers and their interfaces
are determined in a scenario-specific integration flow **PIPSamplesScenario4_Step04_CustomReceiverDetermination**.
- We do not need to upload an XSLT to determine the receivers. Instead, we provide the information about the end point of the integration flow running a mapping to determine receivers adn interfaces.
- We can reuse the integration flows from scenario 4.

We assume that you have gone through the prerequisites and the scenario setup.

## Partner Directory entries

Recently, we have shipped a Partner Directory user interface in SAP Integration Suite that allows you to maintain the Partner Directory entries. After you have 

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 4 -  Custom Extension for Receiver Determination --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request should be routed from sender **Sender_4A** to receiver **Receiver_41**.
- The second request should be routed from sender **Sender_4A** to receiver **Receiver_43**.
- The third request should be routed from sender **Sender_4A** to the receivers **Receiver_42** and **Receiver_43**.
- For the last request no xpath condition could be met and hence the message should be routed to the default receiver **Receiver_41**. In this case, the custom status of the **Pipeline Generic Step04 - Receiver Determination** flow should be **ReceiverNotFoundDefault**.

In any cases, you should see a message processing log for the integration flow **PIPSamplesScenario4_Step04_CustomReceiverDetermination** were the message mapping to determine the receivers and interfaces is carried out.
Furthermore, you should not see any log for the pipeline step 5 since this step is actually bypassed.

<br>![](/images/17_01_Scenario4A_MPL.png)

Go back to [Main page](../../README.md)
