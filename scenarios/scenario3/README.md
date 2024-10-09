# Scenario 3

Scenario 3 uses the Maintain Order at Runtime feature. A message is sent to one receiver and split whereas the split messages should be kept in order.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 3 - IF Split with Order at Runtime --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**. Run the request.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged. Let's use a new feature that we have recently shipped with SAP Integration Suite, the Message Status Overview. In the monitoring page, select the **Message Status Overview** tile.

<br>![](/images/09_01_Scenario3_MessageStatusOverview.png)

In the Message Status Overview, you can get an overview based on different artifact types and parameters. Select **Overview By Sender** from the drop down menu. You should see 8 new compelted messages for the sender 3. Select the respective entry.

<br>![](/images/09_02_Scenario3_SelectSender3.png)

In the message monitor you should see two messages sent to the mocked receiver with receiver **Receiver_31**,
one for the item (interface **PurchaseOrderItem**) and one for a trigger file (interface **PurchaseOrderTrigger**). Latter should always be processed after the first message.

<br>![](/images/09_03_Scenario3_MPL.png)

Furthermore, you can filter on the custom header properties, in our example we filter on the purchase order.

<br>![](/images/09_04_Scenario3_CustomHeaders.png)

Go back to [Main page](../../README.md)
