# Scenario 6

Scenario 6 simulates an IDoc inbound scenario. You can either run a single IDoc or a bulk IDoc. For bulk, the mocked IDoc sender simply duplicates the very same request message and creates an IDoc bulk message.

<br>![](/images/Scenario_6.png)

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 6 - Point-to-Point with IDoc inbound --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- If you run the single IDoc request, you should see one single IDoc ID passed back in the response. A message of message type **FLIGHTBOOKING_CREATEFROMDAT.FLIGHTBOOKING_CREATEFROMDAT01** should be sent to **Receiver_61**.
- If you run the bulk IDoc request, you should see two IDoc IDs passed back in the response. The bulk message is split and two messages of message type **FLIGHTBOOKING_CREATEFROMDAT.FLIGHTBOOKING_CREATEFROMDAT01** should be sent to **Receiver_61**.

In any case, the IDoc numbers are displayed in the header Application Message ID.
Furthermore, for the generic IDoc inbound processing flow **Pipeline Generic Step01 - Inbound Processing for Idoc**, all IDoc numbers are added as custom header.

<br>![](/images/12_01_Scenario6_MPL.png)

**Note**: The generic IDoc inbound processing flow discards duplicate messages based on a combination of the sender component and the IDoc number.
In this case, the generic IDoc inbound processing flow stops message processing and ends with the custom status **DuplicateDiscarded**.
It might happen that the mocked IDoc sender creates duplicates if you rerun the scenario at a later point of time.
To avoid this, you can maintain a new sender component name in the Pre-request Script tab of your Postman collection folder of scenario 6.
In this case, you can first clean up the Partner Directory with the old name and then re-run the Update Partner Directory requests with the new name.

Go back to [Main page](../../README.md)
