# Scenario 6A

Scenario 6A is similar like scenario 6 except that we run the scenario on the integrated messaging runtime which is supported as of integration package version 1.0.9.
The integrated messaging runtime combines inbound conversion as well as receiver and interface determination in one single pipeline step leading to an improvement in terms of runtime performance. 
- The scenario-specific integration flows of scenario 6 can be reused.
- The scenario simulates an IDoc inbound scenario. You can either run a single IDoc or a bulk IDoc. For bulk, the mocked IDoc sender simply duplicates the very same request message and creates an IDoc bulk message.
- The generic IDoc inbound processing flow forwards the messages to the asynchronous integrated messaging runtime pipeline.
- The scenario supports different tenant stages like DEV, QA, PRD.

<br>![](/images/Scenario_6A.png)

**Note**: Scenario 6A reuses the same integration package like scenario 6. So, ensure that you have deployed the scenario 6 integration flows whereas for the Partner Directory dedicated objects for scenario 6A have to be setup.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 6A - P2P with Integrated Messaging Runtime --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- If you run the single IDoc request, you should see one single IDoc ID passed back in the response. A message of message type **FLIGHTBOOKING/CREATEFROMDAT.FLIGHTBOOKING/CREATEFROMDAT01** should be sent from sender **BS_A6A_P** to receiver **BS_ERP6A_P**.
- If you run the bulk IDoc request, you should see two IDoc IDs passed back in the response. The bulk message is split and two messages of message type **FLIGHTBOOKING/CREATEFROMDAT.FLIGHTBOOKING/CREATEFROMDAT01** should be sent to **BS_ERP6A_P**.

**Note**: We assume that you run the scenario on your production landscape. Actually, during runtime the logical system **A6PCLNT602** is mapped to an alias **BS_A6A** which is used across all tenant stages to identify the integration scenario stored in the Partner Directory.
Using the very same alias, the business name of the sending system **BS_A6A_P** is also fetched and used for monitoring purposes. Afer having determined the receiver alias **BS_ERP6A**, it is then mapped to the actual receiver **BS_ERP6A_P**.

In any case, in the monitoring you should see a log of the generic integration flow **Pipeline Generic Step02 - Integrated Messaging Runtime Async**

<br>![](/images/19_01_Scenario6A_MPL.png)

**Note**: The generic IDoc inbound processing flow discards duplicate messages based on a combination of the sender component and the IDoc number.
In this case, the generic IDoc inbound processing flow stops message processing and ends with the custom status **DuplicateDiscarded**.
It might happen that the mocked IDoc sender creates duplicates if you rerun the scenario at a later point of time.
To avoid this, you can maintain a new sender component name in the Pre-request Script tab of your Postman collection folder of scenario 6.
In this case, you can first clean up the Partner Directory with the old name and then re-run the Update Partner Directory requests with the new name.

Go back to [Main page](../../README.md)
