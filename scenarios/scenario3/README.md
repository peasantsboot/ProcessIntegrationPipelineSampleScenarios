# Scenario 3

Scenario 3 uses the Maintain Order at Runtime feature. A message is sent to one receiver and split whereas the split messages should be kept in order.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 3 - IF Split with Order at Runtime --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

If you run the request, in the message monitor you should see two messages sent to the mocked receiver with receiver **Receiver_31**,
one for the item (interface **PurchaseOrderItem**) and one for a trigger file (interface **PurchaseOrderTrigger**). Latter should always be processed after the first message.

<br>![](/images/09_01_Scenario3_MPL.png)

Go back to [Main page](../../README.md)
